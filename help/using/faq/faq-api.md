---
description: Domande e problemi comuni sulle API.
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: Domande frequenti sulle API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
TQID: https://experienceleague.adobe.com/IKztfem2G3SCH36c-2Qe5cJWVhPWRLQXjU5TEgF9Cgs
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 100%

---

# Domande frequenti sulle API{#api-faq}

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
