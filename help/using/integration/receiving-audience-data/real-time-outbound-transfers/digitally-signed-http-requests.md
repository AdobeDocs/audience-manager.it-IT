---
description: Audience Manager richiede la firma digitale per la validità delle richieste HTTP(S) da server a server. Questo documento descrive come firmare le richieste HTTP con chiavi private.
seo-description: Audience Manager richiede la firma digitale per la validità delle richieste HTTP(S) da server a server. Questo documento descrive come firmare le richieste HTTP(S) con chiavi private.
seo-title: Richieste HTTP con firma digitale
solution: Audience Manager
title: Richieste HTTP con firma digitale
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
translation-type: tm+mt
source-git-commit: e7bb837a9a4a4e41ca5c73a192f68a4caa30335d

---


# Richieste con firma digitale `HTTP(S)`{#digitally-signed-http-requests}

Audience Manager richiede la firma digitale per la validità delle richieste da `HTTP(S)` server a server. Questo documento descrive come firmare `HTTP(S)` le richieste con chiavi private.

## Panoramica {#overview}

<!-- digitally_signed_http_requests.xml -->

Utilizzando una chiave privata fornita dall'utente e condivisa con [!DNL Audience Manager], possiamo firmare digitalmente le `HTTP(S)` richieste inviate tra [IRIS](../../../reference/system-components/components-data-action.md#iris) e il server HTTP(S). Ciò assicura:

* **Autenticità**: solo il mittente con la chiave privata ([!UICONTROL IRIS]) può inviare `HTTP(S)` messaggi validi al partner.
* **Integrità** del messaggio: con questo approccio, anche su `HTTP`, si è protetti da un uomo in attacco medio dove i messaggi vengono distorti.

[!UICONTROL IRIS] è dotato di supporto integrato per ruotare i tasti senza tempi di inattività, come illustrato nella sezione [Ruotare la chiave](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) privata riportata di seguito.

## Informazioni da fornire {#info-to-provide}

Per una destinazione server-to-server in tempo `HTTP(S)` reale, contattate il vostro [!DNL Audience Manager] consulente e specificate:

* Chiave utilizzata per firmare la richiesta.
* Nome dell' `HTTP(S)` intestazione che contiene la firma generata (firma X nell'intestazione di esempio seguente).
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

## How it works {#how-it-works}

1. [!UICONTROL IRIS] crea il `HTTP(S)` messaggio da inviare al partner.
1. [!UICONTROL IRIS] crea una firma basata sul `HTTP(S)` messaggio e sulla chiave privata comunicata dal partner.
1. [!UICONTROL IRIS] invia la `HTTP(S)` richiesta al partner. Questo messaggio contiene la firma e il messaggio effettivo, come mostrato nell'esempio precedente.
1. Il server partner riceve la `HTTP(S)` richiesta. Legge il corpo del messaggio e la firma ricevuta da [!UICONTROL IRIS].
1. In base al corpo del messaggio ricevuto e alla chiave privata, il server partner ricalcola la firma. Per ulteriori informazioni, vedere [Come calcolare la sezione relativa alla firma](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) , vedere di seguito.
1. Confrontare la firma creata sul server partner (destinatario) con quella ricevuta da [!UICONTROL IRIS] (mittente).
1. Se le firme corrispondono, **autenticità** e integrità **del** messaggio sono stati convalidati. Solo il mittente che possiede la chiave privata può inviare una firma valida (autenticità). Inoltre, un uomo al centro non può modificare il messaggio e generare una nuova firma valida, poiché non dispone della chiave privata (integrità del messaggio).

![](assets/iris-digitally-sign-http-request.png)

## Modalità di calcolo della firma {#calculate-signature}

[!DNL HMAC] (Codice di autenticazione dei messaggi basato su hash) è il metodo utilizzato per [!UICONTROL IRIS] la firma dei messaggi. Implementazioni e librerie sono disponibili in ogni linguaggio di programmazione. [!DNL HMAC] non ha attacchi di estensione noti. Di seguito è riportato un esempio [!DNL Java] :

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

La RFC per l'implementazione [!DNL HMAC] hash è [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un sito di prova: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) ( [convertire](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) la codifica esadecimale in base64).

## Rotazione della chiave privata {#rotate-private-key}

Per motivi di sicurezza, si consiglia di ruotare periodicamente la chiave privata. Sta a voi decidere la chiave privata e il periodo di rotazione. Per ottenere la rotazione chiave senza tempi di inattività, [!UICONTROL IRIS] è possibile aggiungere più intestazioni firma. Un'intestazione contiene la firma generata con la chiave precedente, un'altra contiene la firma generata con la nuova chiave privata. Consulta i passaggi descritti di seguito:

1. Il partner comunica la nuova chiave privata a [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] inizierà a inviare due intestazioni di firma (una utilizzando la chiave precedente, l'altra utilizzando la nuova chiave).
1. Dopo aver iniziato a ricevere entrambe le intestazioni, è possibile scegliere di ignorare la chiave precedente e di guardare solo la nuova firma.
1. La vecchia chiave viene rimossa [!DNL Audience Manager] e invia [!UICONTROL IRIS] solo la nuova intestazione della firma. I tasti sono stati ruotati.

## Dati utilizzati per la firma {#data-signing}

Per `GET` le destinazioni dei tipi, il messaggio utilizzato per la firma sarà *REQUEST_PATH + QUERY STRING* (ad esempio */from-aam-s2s?sids=1,2,3*). IRIS non prende in considerazione il nome host o `HTTP(S)` le intestazioni, che possono essere modificati/non configurati lungo il percorso o riportati in modo errato.

Per `POST` i tipi di destinazioni, il messaggio utilizzato per la firma è il *REQUEST BODY*. Anche in questo caso, le intestazioni o altri parametri di richiesta vengono ignorati.
