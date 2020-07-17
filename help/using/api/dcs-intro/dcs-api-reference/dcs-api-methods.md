---
description: Inviare i dati all'API DCS utilizzando i metodi GET o POST.
seo-description: Inviare i dati all'API DCS utilizzando i metodi GET o POST.
seo-title: Metodi dell’API DCS
solution: Audience Manager
title: Metodi dell’API DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---


# [!DNL DCS] [!DNL API] Metodi {#dcs-api-methods}

Invia i dati al [!DNL DCS][!DNL API] utilizzando `GET` o `POST` metodi.

È possibile inviare dati al [!DNL DCS] sito utilizzando uno dei `GET` metodi o `POST` . Date un&#39;occhiata alle chiamate di esempio riportate di seguito, utilizzando [curl](https://curl.haxx.se/). In tutte e tre le chiamate campione, stiamo aggiungendo i segnali `c_likes = famous popstar` e `c_loves = famous actress` al profilo del dispositivo `12345678901234567890123456789012345678`.

## Invia dati tramite [!DNL GET] {#send-data-via-get}

La dimensione massima consentita per `GET` le chiamate è 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Invia dati tramite [!DNL POST] {#send-data-via-post}

Tenere presenti i requisiti per l&#39;invio di dati utilizzando il `POST` metodo:

* La dimensione massima consentita è 32 K.
* Impostate il tipo di contenuto su `application/x-www-form-urlencoded`.

### Chiamata di esempio

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
