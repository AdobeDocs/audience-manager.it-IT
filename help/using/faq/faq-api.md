---
description: Domande e problemi comuni sulle API.
seo-description: Domande e problemi comuni sulle API.
seo-title: Domande frequenti sulle API
solution: Audience Manager
title: Domande frequenti sulle API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 100%

---


# Domande frequenti sulle API {#api-faq}

Domande e problemi comuni sulle API.

<!-- 

faq_api.xml

 -->

La documentazione [REST API](../api/rest-api-main/rest-api-main.md) contiene informazioni dettagliate su metodi ed esempi di codice specifici.

<br> 

**Perché [!UICONTROL DIL] effettua chiamate evento con i metodi [!UICONTROL GET] e [!UICONTROL POST]?**

[!UICONTROL DIL] trasmette i dati ad [!DNL Audience Manager] con un metodo `GET` o `POST` basato sulla lunghezza della stringa di interrogazione della chiamata evento. Per impostazione predefinita, questo comportamento è integrato nei metodi `GET` e `POST`. Non è specifico per [!DNL Audience Manager].

* [!UICONTROL DIL] effettua chiamate evento con `GET` quando un URL contiene 2048 caratteri o meno. Una chiamata evento `GET` include i dati nell’URL come parametri della stringa di interrogazione, che vengono trasmessi come coppie chiave-valore.

* [!UICONTROL DIL] effettua chiamate evento con `POST` quando un URL contiene più di 2048 caratteri. Una chiamata evento `POST` include i dati nel corpo della richiesta. [!UICONTROL DIL] inserisce i dati in coppie chiave-valore e trasmette le informazioni come dati del modulo anziché nella stringa di interrogazione URL.

Anche se ogni metodo trasmette i dati in modo diverso, questo non influisce sulla funzionalità. Ad esempio, con entrambi i metodi, [!DNL Audience Manager] invia comunque i dati alle destinazioni, le sincronizzazioni ID funzionano normalmente e puoi creare caratteristiche dai segnali di dati.

<br> 

**Cosa mi permettono di fare le [!UICONTROL REST API]?**

Le [!UICONTROL REST API]ti consentono di lavorare in modo programmatico con la maggior parte delle funzioni e funzionalità di [!DNL Audience Manager] disponibili nell’interfaccia utente.

<br> 

**Come posso ottenere un [!UICONTROL REST API] ID cliente e un segreto della ?**

Per ottenere le credenziali di accesso all’[!DNL API], contatta il rappresentante delle soluzioni dei partner. Le nostre API utilizzano gli standard [OAuth 2.0](https://oauth.net/2/) per l’autenticazione, l’autorizzazione e il rinnovo dei token. Per ulteriori informazioni, consulta [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth).
