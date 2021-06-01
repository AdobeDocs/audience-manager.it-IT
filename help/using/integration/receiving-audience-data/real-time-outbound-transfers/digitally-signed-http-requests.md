---
description: Ad Audience Manager, per la validità, le richieste da server a server HTTP(S) devono essere firmate digitalmente. Questo documento descrive come firmare le richieste HTTP con chiavi private.
seo-description: Ad Audience Manager, per la validità, le richieste da server a server HTTP(S) devono essere firmate digitalmente. Questo documento descrive come firmare le richieste HTTP(S) con chiavi private.
seo-title: Richieste HTTP(S) con firma digitale
solution: Audience Manager
title: Richieste HTTP(S) con firma digitale
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Trasferimenti di dati in uscita
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# Richieste `HTTP(S)` con firma digitale {#digitally-signed-http-requests}

Ad Audience Manager, la validità delle richieste da server a server deve essere firmata digitalmente. `HTTP(S)` Questo documento descrive come firmare le richieste `HTTP(S)` con chiavi private.

## Panoramica {#overview}

<!-- digitally_signed_http_requests.xml -->

Utilizzando una chiave privata fornita dall&#39;utente e condivisa con [!DNL Audience Manager], possiamo firmare digitalmente le richieste `HTTP(S)` inviate tra [IRIS](../../../reference/system-components/components-data-action.md#iris) e il server HTTP(S). Ciò assicura:

* **Autenticità**: solo il mittente con la chiave privata ([!UICONTROL IRIS]) può inviare  `HTTP(S)` messaggi validi al partner.
* **Integrità** del messaggio: con questo approccio, anche  `HTTP`, si è protetti da un uomo in attacco medio dove i messaggi vengono distorti.

[!UICONTROL IRIS] dispone di un supporto integrato per ruotare i tasti con zero tempi di inattività, come illustrato nella sezione  [Ruota la ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) chiave privata riportata di seguito.

## Informazioni da fornire {#info-to-provide}

Per una destinazione da server a server in tempo reale `HTTP(S)`, contatta il tuo consulente [!DNL Audience Manager] e specifica:

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
1. [!UICONTROL IRIS] invia la  `HTTP(S)` richiesta al partner. Questo messaggio contiene la firma e il messaggio effettivo, come illustrato nell’esempio precedente.
1. Il server partner riceve la richiesta `HTTP(S)` . Legge il corpo del messaggio e la firma ricevuta da [!UICONTROL IRIS].
1. In base al corpo del messaggio ricevuto e alla chiave privata, il server partner ricalcola la firma. Per ulteriori informazioni, consulta la sezione [Come calcolare la firma](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) .
1. Confrontare la firma creata sul server partner (destinatario) con quella ricevuta da [!UICONTROL IRIS] (mittente).
1. Se le firme corrispondono, sono stati convalidati i valori **autenticità** e **integrità del messaggio**. Solo il mittente che dispone della chiave privata può inviare una firma valida (autenticità). Inoltre, un utente al centro non può modificare il messaggio e generare una nuova firma valida, in quanto non dispone della chiave privata (integrità del messaggio).

![](assets/iris-digitally-sign-http-request.png)

## Come calcolare la firma {#calculate-signature}

[!DNL HMAC] (Codice di autenticazione dei messaggi basato su hash) è il metodo utilizzato da  [!UICONTROL IRIS] per la firma dei messaggi. Le implementazioni e le librerie sono disponibili praticamente in ogni linguaggio di programmazione. [!DNL HMAC] non ha attacchi di estensione noti. Vedi un esempio in [!DNL Java] qui sotto:

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

La RFC per l’ [!DNL HMAC] implementazione hash è [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un sito di prova: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (nota che è necessario [convertire](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) la codifica esadecimale in base64).

## Rotazione della chiave privata {#rotate-private-key}

Per ruotare la chiave privata, i partner devono comunicare la nuova chiave privata al proprio [!DNL Adobe Audience Manager] consulente. La chiave precedente viene rimossa da [!DNL Audience Manager] e [!UICONTROL IRIS] invia solo la nuova intestazione di firma. I tasti sono stati ruotati.

## Dati utilizzati per la firma {#data-signing}

Per le destinazioni di tipo `GET`, il messaggio utilizzato per la firma sarà *REQUEST_PATH + QUERY STRING* (ad esempio */from-aam-s2s?sids=1,2,3*). IRIS non prende in considerazione il nome host o le intestazioni `HTTP(S)` - queste possono essere modificate/configurate in modo errato lungo il percorso o riportate in modo errato.

Per le destinazioni di tipo `POST`, il messaggio utilizzato per la firma è *REQUEST BODY*. Anche in questo caso, le intestazioni o altri parametri di richiesta vengono ignorati.
