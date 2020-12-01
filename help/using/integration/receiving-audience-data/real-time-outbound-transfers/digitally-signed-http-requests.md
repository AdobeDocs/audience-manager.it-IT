---
description: ' Audience Manager richiede la firma digitale per la validità delle richieste HTTP(S) da server a server. Questo documento descrive come firmare le richieste HTTP con chiavi private.'
seo-description: ' Audience Manager richiede la firma digitale per la validità delle richieste HTTP(S) da server a server. Questo documento descrive come firmare le richieste HTTP(S) con chiavi private.'
seo-title: Richieste HTTP con firma digitale
solution: Audience Manager
title: Richieste HTTP con firma digitale
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: 4877aa5391193ee2187609fdc9cb3740c91feb96
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# Richieste con firma digitale `HTTP(S)` {#digitally-signed-http-requests}

 Audience Manager richiede la firma digitale delle richieste `HTTP(S)` server per la validità. Questo documento descrive come firmare le richieste `HTTP(S)` con chiavi private.

## Panoramica {#overview}

<!-- digitally_signed_http_requests.xml -->

Utilizzando una chiave privata fornita dall&#39;utente e condivisa con [!DNL Audience Manager], è possibile firmare digitalmente le `HTTP(S)` richieste inviate tra [IRIS](../../../reference/system-components/components-data-action.md#iris) e il server HTTP(S). Ciò assicura:

* **Autenticità**: solo il mittente con la chiave privata ([!UICONTROL IRIS]) può inviare  `HTTP(S)` messaggi validi al partner.
* **Integrità** del messaggio: con questo approccio, anche su  `HTTP`, si è protetti da un uomo in attacco medio dove i messaggi vengono distorti.

[!UICONTROL IRIS] è dotato di supporto integrato per ruotare i tasti senza tempi di inattività, come mostrato nella sezione  [Ruotare la ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) chiave privata sottostante.

## Informazioni da fornire {#info-to-provide}

Per una destinazione da server a server in tempo reale `HTTP(S)`, contattare il consulente [!DNL Audience Manager] e specificare:

* Chiave utilizzata per firmare la richiesta.
* Nome dell&#39;intestazione `HTTP(S)` che conterrà la firma generata (firma X nell&#39;intestazione di esempio seguente).
* Facoltativo: il tipo di hash utilizzato per la firma (md5, sha1, sha256).

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

1. [!UICONTROL IRIS] crea il  `HTTP(S)` messaggio da inviare al partner.
1. [!UICONTROL IRIS] crea una firma basata sul  `HTTP(S)` messaggio e sulla chiave privata comunicata dal partner.
1. [!UICONTROL IRIS] invia la  `HTTP(S)` richiesta al partner. Questo messaggio contiene la firma e il messaggio effettivo, come mostrato nell&#39;esempio precedente.
1. Il server partner riceve la richiesta `HTTP(S)`. Legge il corpo del messaggio e la firma ricevuta da [!UICONTROL IRIS].
1. In base al corpo del messaggio ricevuto e alla chiave privata, il server partner ricalcola la firma. Vedere la sezione [Come calcolare la firma](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) appena sotto su come ottenere questo risultato.
1. Confrontare la firma creata sul server partner (destinatario) con quella ricevuta da [!UICONTROL IRIS] (mittente).
1. Se le firme corrispondono, l&#39;**autenticità** e **integrità del messaggio** sono state convalidate. Solo il mittente che possiede la chiave privata può inviare una firma valida (autenticità). Inoltre, un uomo al centro non può modificare il messaggio e generare una nuova firma valida, in quanto non dispone della chiave privata (integrità del messaggio).

![](assets/iris-digitally-sign-http-request.png)

## Come calcolare la firma {#calculate-signature}

[!DNL HMAC] (Codice di autenticazione dei messaggi basato su hash) è il metodo utilizzato  [!UICONTROL IRIS] per la firma dei messaggi. Implementazioni e librerie sono disponibili in ogni linguaggio di programmazione. [!DNL HMAC] non ha attacchi di estensione noti. Vedere un esempio in [!DNL Java] di seguito:

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

La RFC per l&#39;implementazione hash [!DNL HMAC] è [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un sito di prova: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (è necessario [convertire](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) la codifica esadecimale in base64).

## Rotazione della chiave privata {#rotate-private-key}

Per ruotare la chiave privata, i partner devono comunicare la nuova chiave privata al proprio [!DNL Adobe Audience Manager] consulente. La vecchia chiave viene rimossa da [!DNL Audience Manager] e [!UICONTROL IRIS] invia solo la nuova intestazione della firma. I tasti sono stati ruotati.

## Dati utilizzati per la firma {#data-signing}

Per le destinazioni di tipo `GET`, il messaggio utilizzato per la firma sarà *REQUEST_PATH + QUERY STRING* (ad esempio */from-aam-s2s?sids=1,2,3*). IRIS non prende in considerazione il nome host o le intestazioni `HTTP(S)`, che possono essere modificate/non configurate lungo il percorso o riportate in modo errato.

Per le destinazioni di tipo `POST`, il messaggio utilizzato per la firma è il *BODY RICHIESTA*. Anche in questo caso, le intestazioni o altri parametri di richiesta vengono ignorati.
