---
description: Invia dati all’API DCS utilizzando i metodi GET o POST.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: Metodi dell’API DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 4%

---

# [!DNL DCS] [!DNL API] Metodi {#dcs-api-methods}

Invia dati a [!DNL DCS] [!DNL API] utilizzo `GET` o `POST` metodi.

Puoi inviare dati a [!DNL DCS] utilizzando uno dei `GET` o `POST` metodi. Osserva le chiamate di esempio riportate di seguito, utilizzando [ricciolo](https://curl.haxx.se/). In tutte e tre le chiamate di esempio, stiamo aggiungendo i segnali `c_likes = famous popstar` e `c_loves = famous actress` al profilo dispositivo `12345678901234567890123456789012345678`.

## Inviare dati tramite [!DNL GET] {#send-data-via-get}

Tieni presente che la dimensione massima consentita per `GET` chiamate è 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Inviare dati tramite [!DNL POST] {#send-data-via-post}

Osserva i requisiti per l’invio dei dati utilizzando `POST` metodo:

* La dimensione massima consentita è 32 K.
* Imposta il tipo di contenuto su `application/x-www-form-urlencoded`.

### Chiamata di esempio

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
