---
description: Inviare dati all’API DCS utilizzando i metodi GET o POST.
seo-description: Inviare dati all’API DCS utilizzando i metodi GET o POST.
seo-title: Metodi dell’API DCS
solution: Audience Manager
title: Metodi dell’API DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 6%

---

# [!DNL DCS] [!DNL API] Metodi {#dcs-api-methods}

Invia i dati a [!DNL DCS] [!DNL API] utilizzando i metodi `GET` o `POST`.

Puoi inviare dati a [!DNL DCS] utilizzando uno dei metodi `GET` o `POST`. Osserva le chiamate di esempio riportate di seguito, utilizzando [curl](https://curl.haxx.se/). In tutte e tre le chiamate di esempio, stiamo aggiungendo i segnali `c_likes = famous popstar` e `c_loves = famous actress` al profilo del dispositivo `12345678901234567890123456789012345678`.

## Invia dati tramite [!DNL GET] {#send-data-via-get}

La dimensione massima consentita per le chiamate `GET` è 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Invia dati tramite [!DNL POST] {#send-data-via-post}

Osserva i requisiti per l’invio di dati utilizzando il metodo `POST` :

* La dimensione massima consentita è 32K.
* Imposta il tipo di contenuto su `application/x-www-form-urlencoded`.

### Chiamata di esempio

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
