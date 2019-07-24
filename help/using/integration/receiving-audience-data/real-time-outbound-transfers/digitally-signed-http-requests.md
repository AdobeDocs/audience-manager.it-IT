---
description: Audience Manager richiede che le richieste server-to-server HTTP siano firmate digitalmente per validità. Questo documento descrive come firmare le richieste HTTP con le chiavi private.
seo-description: Audience Manager richiede che le richieste server-to-server HTTP siano firmate digitalmente per validità. Questo documento descrive come firmare le richieste HTTP con le chiavi private.
seo-title: Richieste HTTP firmate digitalmente
solution: Audience Manager
title: Richieste HTTP firmate digitalmente
uuid: 1183 a 70 f -0 c 96-42 cf-a 4 f 5-37 a 83 ffa 1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# Digitally Signed `HTTP` Requests {#digitally-signed-http-requests}

Audience Manager requires the `HTTP` server-to-server requests to be digitally signed for validity. This document describes how you can sign `HTTP` requests with private keys.

## Panoramica {#overview}

<!-- digitally_signed_http_requests.xml -->

Using a private key provided by you and shared with [!DNL Audience Manager], we can digitally sign the `HTTP` requests that are sent between [IRIS](../../../reference/system-components/components-data-action.md#iris) and your HTTP server. Questo garantisce che:

* **Autenticità**: solo il mittente che dispone della chiave privata ([!UICONTROL IRIS]) può inviare `HTTP(S)` messaggi validi al partner.
* **Integrità messaggio**: con questo approccio, anche su `HTTP`, sei protetto da un uomo nel centro centrale dove i messaggi diventano distorti.

[!UICONTROL IRIS] dispone del supporto incorporato per ruotare le chiavi con zero tempo, come mostrato nella [sezione Rotazione della](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) sezione privata di seguito.

## Information you need to provide {#info-to-provide}

For an `HTTP` real-time server-to-server destination, contact your [!DNL Audience Manager] consultant and specify:

* Chiave utilizzata per firmare la richiesta.
* The name of the `HTTP` header that will hold the generated signature (X-Signature in the example header below).
* Facoltativo: il tipo di hash utilizzato per la firma (md 5, sha 1, sha 256).

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## How it works {#how-it-works}

1. [!UICONTROL IRIS] crea il `HTTP` messaggio da inviare al partner.
1. [!UICONTROL IRIS] crea una firma in base al `HTTP` messaggio e alla chiave privata comunicata dal partner.
1. [!UICONTROL IRIS] invia la `HTTP(S)` richiesta al partner. Questo messaggio contiene la firma e il messaggio effettivo, come illustrato nell'esempio precedente.
1. The partner server receives the `HTTP(S)` request. It reads the message body and the signature received from [!UICONTROL IRIS].
1. In base al corpo del messaggio ricevuto e alla chiave privata, il server partner ricalcola la firma. See the [How to calculate the signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from [!UICONTROL IRIS] (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. Solo il mittente che ha la chiave privata può inviare una firma valida (autenticità). Inoltre, un uomo al centro non può modificare il messaggio e generare una nuova firma valida, poiché non dispone della chiave privata (integrità del messaggio).

![](assets/iris-digitally-sign-http-request.png)

## How to calculate the signature {#calculate-signature}

[!DNL HMAC] (Codice di autenticazione del messaggio hash) è il metodo utilizzato per [!UICONTROL IRIS] la firma dei messaggi. Le implementazioni e le librerie sono disponibili fondamentalmente in ogni linguaggio di programmazione. [!DNL HMAC] non ha attacchi di estensione noti. See an example in [!DNL Java] below:

```
// Message to be signed.
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

The RFC for the [!DNL HMAC] hash implementation is [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). A test site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (note that you have to [convert](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64).

## Rotating the private key {#rotate-private-key}

Per motivi di sicurezza, si consiglia di ruotare periodicamente la chiave privata. Spetta a voi decidere la chiave privata e il periodo di rotazione. In order to achieve the key rotation with zero downtime, [!UICONTROL IRIS] supports adding multiple signature headers. Un'intestazione conterrà la firma generata con la chiave precedente, un'altra intestazione conterrà la firma generata utilizzando la nuova chiave privata. Vedi sotto i passaggi descritti di seguito:

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] inizierà a inviare due intestazioni di firma (una utilizzando la chiave precedente, l'altra mediante la nuova chiave).
1. Dopo aver ricevuto entrambe le intestazioni, è possibile scegliere di eliminare la chiave precedente e solo verificare la nuova firma.
1. The old key is removed from [!DNL Audience Manager] and [!UICONTROL IRIS] only sends the new signature header. Le chiavi sono state ruotate.

## Data used for signing {#data-signing}

For `GET` type destinations, the message used for signing will be the *REQUEST_PATH + QUERY STRING* (e.g. */from-aam-s2s?sids=1,2,3*). IRIS does not take into account the hostname or `HTTP` headers - these can be modified / misconfigured along the path or reported incorrectly.

For `POST` type destinations, the message used for signing is the *REQUEST BODY*. Anche le intestazioni o altri parametri di richiesta vengono ignorati.
