---
description: Audience Manager richiede che le richieste HTTP(S) server-to-server siano firmate digitalmente per la validità. Questo documento descrive come firmare le richieste HTTP con le chiavi private.
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: Richieste HTTP(S) con firma digitale
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---

# `HTTP(S)` richieste con firma digitale {#digitally-signed-http-requests}

Audience Manager richiede che le richieste server-to-server `HTTP(S)` siano firmate digitalmente per la validità. In questo documento viene descritto come firmare `HTTP(S)` richieste con chiavi private.

## Panoramica {#overview}

<!-- digitally_signed_http_requests.xml -->

Utilizzando una chiave privata fornita dall&#39;utente e condivisa con [!DNL Audience Manager], è possibile firmare digitalmente le richieste `HTTP(S)` inviate tra [IRIS](../../../reference/system-components/components-data-action.md#iris) e il server HTTP(S). In questo modo:

* **Autenticità**: solo il mittente che dispone della chiave privata ([!UICONTROL IRIS]) può inviare messaggi `HTTP(S)` validi al partner.
* **Integrità del messaggio**: con questo approccio, anche su `HTTP`, sei protetto da un uomo in mezzo all&#39;attacco in cui i messaggi vengono distorti.

[!UICONTROL IRIS] dispone del supporto integrato per la rotazione delle chiavi senza tempi di inattività, come illustrato nella sezione [Rotazione della chiave privata](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) di seguito.

## Informazioni da fornire {#info-to-provide}

Per una destinazione server-to-server in tempo reale `HTTP(S)`, contatta il tuo consulente [!DNL Audience Manager] e specifica:

* Chiave utilizzata per firmare la richiesta.
* Nome dell&#39;intestazione `HTTP(S)` che conterrà la firma generata (X-Signature nell&#39;intestazione di esempio seguente).
* Facoltativo: tipo di hash utilizzato per la firma (md5, sha1, sha256).

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

## Come funziona {#how-it-works}

1. [!UICONTROL IRIS] crea il messaggio `HTTP(S)` da inviare al partner.
1. [!UICONTROL IRIS] crea una firma basata sul messaggio `HTTP(S)` e sulla chiave privata comunicata dal partner.
1. [!UICONTROL IRIS] invia la richiesta `HTTP(S)` al partner. Questo messaggio contiene la firma e il messaggio effettivo, come illustrato nell’esempio precedente.
1. Il server partner riceve la richiesta `HTTP(S)`. Legge il corpo del messaggio e la firma ricevuta da [!UICONTROL IRIS].
1. In base al corpo del messaggio ricevuto e alla chiave privata, il server partner ricalcola la firma. Per informazioni su come ottenere questo risultato, vedere la sezione [Come calcolare la firma](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature).
1. Confrontare la firma creata sul server partner (ricevitore) con quella ricevuta da [!UICONTROL IRIS] (mittente).
1. Se le firme corrispondono, sono state convalidate l&#39;**autenticità** e l&#39;**integrità del messaggio**. Solo il mittente che dispone della chiave privata può inviare una firma valida (autenticità). Inoltre, un utente al centro non può modificare il messaggio e generare una nuova firma valida, in quanto non dispone della chiave privata (integrità del messaggio).

![](assets/iris-digitally-sign-http-request.png)

## Come calcolare la firma {#calculate-signature}

[!DNL HMAC] (codice di autenticazione dei messaggi basato su hash) è il metodo utilizzato da [!UICONTROL IRIS] per la firma dei messaggi. Le implementazioni e le librerie sono disponibili praticamente in ogni linguaggio di programmazione. [!DNL HMAC] non ha attacchi di estensione noti. Vedi un esempio in [!DNL Java] di seguito:

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
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

La RFC per l&#39;implementazione hash [!DNL HMAC] è [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un sito di test: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (si noti che è necessario [convertire](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) la codifica esadecimale in base64).

## Rotazione della chiave privata {#rotate-private-key}

Per ruotare la chiave privata, i partner devono comunicare la nuova chiave privata al proprio consulente [!DNL Adobe Audience Manager]. La chiave precedente è stata rimossa da [!DNL Audience Manager] e [!UICONTROL IRIS] invia solo la nuova intestazione della firma. Le chiavi sono state ruotate.

## Dati utilizzati per la firma {#data-signing}

Per le destinazioni di tipo `GET`, il messaggio utilizzato per la firma sarà *REQUEST_PATH + QUERY STRING* (ad esempio */from-aam-s2s?sids=1,2,3*). IRIS non prende in considerazione il nome host o le intestazioni `HTTP(S)`, che possono essere modificate/configurate in modo errato lungo il percorso o segnalate in modo errato.

Per le destinazioni di tipo `POST`, il messaggio utilizzato per la firma è il *CORPO DELLA RICHIESTA*. Anche in questo caso, le intestazioni o altri parametri di richiesta vengono ignorati.
