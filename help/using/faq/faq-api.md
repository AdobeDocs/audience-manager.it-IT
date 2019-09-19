---
description: Domande e problemi comuni relativi alle API.
seo-description: Domande e problemi comuni relativi alle API.
seo-title: Domande frequenti sulle API
solution: Audience Manager
title: Domande frequenti sulle API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domande frequenti sulle API{#api-faq}

Domande e problemi comuni relativi alle API.

<!-- 

faq_api.xml

 -->

La documentazione API [](../api/rest-api-main/rest-api-main.md) REST contiene informazioni dettagliate su metodi e esempi di codice specifici.

<br> 

**Perché[!UICONTROL DIL]effettuare chiamate di eventi con[!UICONTROL GET]e[!UICONTROL POST]metodi?**

[!UICONTROL DIL] trasmette i dati a [!DNL Audience Manager] con un metodo `GET` `POST` o basato sulla lunghezza della stringa di query della chiamata dell’evento. Questo comportamento è integrato in `GET` e `POST` metodi per impostazione predefinita. Non è specifico a [!DNL Audience Manager].

* [!UICONTROL DIL] effettua chiamate di evento con `GET` un URL contenente almeno 2048 caratteri. Una chiamata `GET` evento include i dati nell'URL come parametri di stringa di query, che vengono passati come coppie chiave-valore.

* [!UICONTROL DIL] effettua chiamate di evento con `POST` un URL contenente più di 2048 caratteri. Una chiamata `POST` evento include i dati nel corpo della richiesta. [!UICONTROL DIL] inserisce i dati in coppie chiave-valore e trasmette le informazioni come dati del modulo anziché nella stringa query URL.

Anche se ogni metodo trasmette i dati in modo diverso, questo non influisce sulla funzionalità. Ad esempio, con entrambi i metodi, invia [!DNL Audience Manager] comunque i dati alle destinazioni, le sincronizzazioni ID funzionano normalmente e puoi creare caratteristiche dai segnali dati.

<br> 

**Cosa mi[!UICONTROL REST API]permette di fare?**

Questo [!UICONTROL REST API]consente di lavorare in modo programmatico con la maggior parte delle [!DNL Audience Manager] funzioni e funzionalità disponibili nell'interfaccia utente.

<br> 

**Come posso ottenere un ID[!UICONTROL REST API]cliente e un segreto?**

Per ottenere le credenziali di [!DNL API] accesso, contattate il rappresentante delle soluzioni partner. Le nostre API utilizzano gli standard [OAuth 2.0](https://oauth.net/2/) per l'autenticazione, l'autorizzazione e il rinnovo dei token. Per ulteriori informazioni, consulta Autenticazione [](../api/rest-api-main/aam-api-getting-started.md#oauth) OAuth.
