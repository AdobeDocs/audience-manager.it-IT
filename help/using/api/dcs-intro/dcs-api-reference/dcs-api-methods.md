---
description: Invia dati all’API DCS utilizzando i metodi GET o POST.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: Metodi API DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# Metodi [!DNL DCS] [!DNL API] {#dcs-api-methods}

Invia dati a [!DNL DCS] [!DNL API] utilizzando i metodi `GET` o `POST`.

È possibile inviare dati a [!DNL DCS] utilizzando uno dei metodi `GET` o `POST`. Osserva le chiamate di esempio di seguito, utilizzando [curl](https://curl.haxx.se/). In tutte e tre le chiamate di esempio, i segnali `c_likes = famous popstar` e `c_loves = famous actress` vengono aggiunti al profilo dispositivo `12345678901234567890123456789012345678`.

## Invia dati tramite [!DNL GET] {#send-data-via-get}

La dimensione massima consentita per `GET` chiamate è 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Invia dati tramite [!DNL POST] {#send-data-via-post}

Tenere presenti i requisiti per l&#39;invio di dati utilizzando il metodo `POST`:

* La dimensione massima consentita è 32 K.
* Imposta il tipo di contenuto su `application/x-www-form-urlencoded`.

### Chiamata di esempio

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
