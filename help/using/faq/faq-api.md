---
description: Domande e problemi comuni dell'API.
seo-description: Domande e problemi comuni dell'API.
seo-title: Domande frequenti sulle API
solution: Audience Manager
title: Domande frequenti sulle API
uuid: 8222 ebf 0-b 50 e -4 f 48-8021-dbfca 2828 b 7 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

Domande e problemi comuni dell'API.

<!-- 

faq_api.xml

 -->

The [REST API](../api/rest-api-main/rest-api-main.md) documentation contains details about specific methods and code samples.

<br> 

**Perché[!UICONTROL DIL]effettuare chiamate evento con[!UICONTROL GET]metodi e[!UICONTROL POST]metodi?**

[!UICONTROL DIL] trasmette dati a [!DNL Audience Manager] un metodo `GET` o `POST` a un metodo in base alla lunghezza della stringa query della chiamata dell'evento. This behavior is built in to `GET` and `POST` methods by default. It is not specific to [!DNL Audience Manager].

* [!UICONTROL DIL] effettua chiamate evento con `GET` un URL contenente un massimo di 2048 caratteri. A `GET` event call includes data in the URL as query string parameters, which are passed in as key-value pairs.

* [!UICONTROL DIL] effettua chiamate evento con `POST` un URL contenente più di 2048 caratteri. A `POST` event call includes data in the body of the request. [!UICONTROL DIL] inserisce i dati in coppie chiave-valore e trasmette le informazioni come dati del modulo anziché nella stringa di query URL.

Anche se ogni metodo trasmette dati in modo diverso, questo non influisce sulle funzionalità. For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.

<br> 

**Cosa mi consente[!UICONTROL REST API]di fare?**

The [!UICONTROL REST API]s let you work programmatically with most [!DNL Audience Manager] features and functions that are available in the user interface.

<br> 

**Come si ottiene un[!UICONTROL REST API]ID client e un segreto?**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
