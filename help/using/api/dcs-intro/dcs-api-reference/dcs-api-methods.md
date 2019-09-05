---
description: Invia dati all'API DCS utilizzando i metodi GET o POST.
seo-description: Invia dati all'API DCS utilizzando i metodi GET o POST.
seo-title: Metodi API DCS
solution: Audience Manager
title: Metodi API DCS
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# Metodi API DCS {#dcs-api-methods}

Inviare dati all [!UICONTROL DCS][!DNL API] 'uso `GET` o `POST` ai metodi.

È possibile inviare dati all' [!UICONTROL DCS] uso di uno o `GET``POST` più metodi. Date un'occhiata alle chiamate di esempio di seguito utilizzando [l'effetto curl](https://curl.haxx.se/). In tutte e tre le chiamate campione, stiamo aggiungendo i segnali `c_likes = famous popstar` e `c_loves = famous actress` il profilo `12345678901234567890123456789012345678`dispositivo.


## Inviare dati tramite GET {#send-data-via-get}

La dimensione massima consentita per `GET` le chiamate è 8 K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Inviare dati tramite POST {#send-data-via-post}

Prendete nota dei requisiti per l'invio di dati utilizzando il `POST` metodo:

* La dimensione massima consentita è 32 K.
* Impostate il tipo di contenuto su `application/x-www-form-urlencoded`.

### Chiamata di esempio

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
