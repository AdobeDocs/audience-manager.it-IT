---
description: Invia dati all'API DCS utilizzando i metodi GET o POST.
seo-description: Invia dati all'API DCS utilizzando i metodi GET o POST.
seo-title: Metodi API DCS
solution: Audience Manager
title: Metodi API DCS
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Metodi API DCS {#dcs-api-methods}

Inviare dati all [!UICONTROL DCS][!DNL API] &#39;uso `GET` o `POST` ai metodi.

È possibile inviare dati all&#39; [!UICONTROL DCS] uso di uno o `GET``POST` più metodi. Date un&#39;occhiata alle chiamate di esempio di seguito utilizzando [l&#39;effetto curl](https://curl.haxx.se/). In tutte e tre le chiamate campione, stiamo aggiungendo i segnali `c_likes = famous popstar` e `c_loves = famous actress` il profilo `12345678901234567890123456789012345678`dispositivo.

>[!NOTE]
>
>Nel codice ed esempi, *il corsivo* rappresenta un segnaposto variabile. Sostituire un valore reale per il segnaposto quando si inviano dati a [!UICONTROL DCS] questo metodo.

## Inviare dati tramite GET {#send-data-via-get}

La dimensione massima consentita per `GET` le chiamate è 8 K.

<pre><code>curl -i "<i>yourcompany.demdex.net/event</i>?
d_ uuid =<i>12345678901234567890123456789012345678</i>&amp; d_ rtbd = json &amp;<i>c_ likes = famose % 20 popstar</i>&amp;<i>c_ loves = famosa % 20 acl</i>"</code>
</pre>

## Inviare dati tramite POST {#send-data-via-post}

Prendete nota dei requisiti per l&#39;invio di dati utilizzando il `POST` metodo:

* La dimensione massima consentita è 32 K.
* Impostate il tipo di contenuto su `application/x-www-form-urlencoded`.

### Chiamata di esempio

<pre><code>curl -x POST\ 
 https://yourcompany.demdex.net/event<i></i>\ 
 -h'content-type: application/x-www-form-urlencoded '\ 
 -d'<i>c_ likes = famoso % 20 popstar</i>&amp;<i>c_ loves = famoso % 20 actress</i>&amp;<i>d_ uuid = 12345678901234567890123456789012345678</i>'</code>
</pre>

<pre><code>curl -x POST\ 
 https://yourcompany.demdex.net/event<i></i>\ 
 -h'content-type: application/x-www-form-urlencoded '\ 
 -d'<i>c_ likes = famoso % 20 popstar</i>&amp; <i>c_ loves = famoso % 20 actress</i>&amp;<i>d_ uuid = 12345678901234567890123456789012345678</i>'</code>
</pre>
