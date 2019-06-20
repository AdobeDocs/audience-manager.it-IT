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


# Richieste firmate `HTTP` digitalmente {#digitally-signed-http-requests}

Audience Manager richiede che le `HTTP` richieste server-to-server siano firmate digitalmente per validità. Questo documento descrive come effettuare `HTTP` le richieste con le chiavi private.

## Panoramica {#overview}

<!-- digitally_signed_http_requests.xml -->

Utilizzando una chiave privata fornita da voi e condivisa con [!DNL Audience Manager], possiamo firmare digitalmente le `HTTP` richieste inviate tra [IRIS](../../../reference/system-components/components-data-action.md#iris) e il server HTTP. Questo garantisce che:

* **Autenticità**: solo il mittente che dispone della chiave privata ([!UICONTROL IRIS]) può inviare `HTTP(S)` messaggi validi al partner.
* **Integrità messaggio**: con questo approccio, anche su `HTTP`, sei protetto da un uomo nel centro centrale dove i messaggi diventano distorti.

[!UICONTROL IRIS] dispone del supporto incorporato per ruotare le chiavi con zero tempo, come mostrato nella [sezione Rotazione della](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) sezione privata di seguito.

## Informazioni necessarie per fornire {#info-to-provide}

Per una `HTTP` destinazione server-to-server in tempo reale, contattate il [!DNL Audience Manager] consulente e specificate:

* Chiave utilizzata per firmare la richiesta.
* Nome dell&#39; `HTTP` intestazione che contiene la firma generata (X-Signature nell&#39;intestazione di esempio sotto).
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

## Come funziona {#how-it-works}

1. [!UICONTROL IRIS] crea il `HTTP` messaggio da inviare al partner.
1. [!UICONTROL IRIS] crea una firma in base al `HTTP` messaggio e alla chiave privata comunicata dal partner.
1. [!UICONTROL IRIS] invia la `HTTP(S)` richiesta al partner. Questo messaggio contiene la firma e il messaggio effettivo, come illustrato nell&#39;esempio precedente.
1. Il server partner riceve la `HTTP(S)` richiesta. Legge il corpo del messaggio e la firma ricevuta [!UICONTROL IRIS].
1. In base al corpo del messaggio ricevuto e alla chiave privata, il server partner ricalcola la firma. Vedere [la sezione Come calcolare](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) la sezione firma appena riportata di seguito.
1. Confrontare la firma creata sul server partner (ricevitore) con quella ricevuta da [!UICONTROL IRIS] (mittente).
1. Se le firme corrispondono, l&#39; **integrità** e l **&#39;integrità** del messaggio sono state convalidate. Solo il mittente che ha la chiave privata può inviare una firma valida (autenticità). Inoltre, un uomo al centro non può modificare il messaggio e generare una nuova firma valida, poiché non dispone della chiave privata (integrità del messaggio).

![](assets/iris-digitally-sign-http-request.png)

## Come calcolare la firma {#calculate-signature}

[!DNL HMAC] (Codice di autenticazione del messaggio hash) è il metodo utilizzato per [!UICONTROL IRIS] la firma dei messaggi. Le implementazioni e le librerie sono disponibili fondamentalmente in ogni linguaggio di programmazione. [!DNL HMAC] non ha attacchi di estensione noti. Consultate un esempio di [!DNL Java] seguito:

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

L&#39;RFC per l&#39;implementazione [!DNL HMAC] hash è [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un sito di prova: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (tenete presente che [dovete convertire](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) la codifica esadecimale nella base 64).

## Rotazione della chiave privata {#rotate-private-key}

Per motivi di sicurezza, si consiglia di ruotare periodicamente la chiave privata. Spetta a voi decidere la chiave privata e il periodo di rotazione. Per ottenere la rotazione chiave con zero tempo, [!UICONTROL IRIS] è consigliabile aggiungere più intestazioni di firma. Un&#39;intestazione conterrà la firma generata con la chiave precedente, un&#39;altra intestazione conterrà la firma generata utilizzando la nuova chiave privata. Vedi sotto i passaggi descritti di seguito:

1. Partner comunica la nuova chiave privata a [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] inizierà a inviare due intestazioni di firma (una utilizzando la chiave precedente, l&#39;altra mediante la nuova chiave).
1. Dopo aver ricevuto entrambe le intestazioni, è possibile scegliere di eliminare la chiave precedente e solo verificare la nuova firma.
1. La vecchia chiave viene rimossa e [!DNL Audience Manager] invia [!UICONTROL IRIS] solo la nuova intestazione della firma. Le chiavi sono state ruotate.

## Dati utilizzati per la firma {#data-signing}

Per `GET` le destinazioni di tipo, il messaggio utilizzato per la firma sarà *REQUEST_ PATH + QUERY STRING* (ad es. */from-aam-s2s? sids = 1,2,3*). IRIS non prende in considerazione il nome host o le `HTTP` intestazioni, che possono essere modificate/configurate in modo errato lungo il percorso o segnalate in modo errato.

Per `POST` le destinazioni di tipo, il messaggio utilizzato per la firma è il corpo *richiesta*. Anche le intestazioni o altri parametri di richiesta vengono ignorati.
