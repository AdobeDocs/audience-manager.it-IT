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


# Domande frequenti sulle API{#api-faq}

Domande e problemi comuni dell&#39;API.

<!-- 

faq_api.xml

 -->

La [documentazione REST API](../api/rest-api-main/rest-api-main.md) contiene dettagli su metodi e esempi di codice specifici.

<br> 

**Perché[!UICONTROL DIL]effettuare chiamate evento con[!UICONTROL GET]metodi e[!UICONTROL POST]metodi?**

[!UICONTROL DIL] trasmette dati a [!DNL Audience Manager] un metodo `GET` o `POST` a un metodo in base alla lunghezza della stringa query della chiamata dell&#39;evento. Per impostazione predefinita, questo comportamento è integrato e `GET``POST` metodi. Non è specifico [!DNL Audience Manager].

* [!UICONTROL DIL] effettua chiamate evento con `GET` un URL contenente un massimo di 2048 caratteri. Una `GET` chiamata evento include dati nell&#39;URL come parametri stringa query, che vengono passati come coppie chiave-valore.

* [!UICONTROL DIL] effettua chiamate evento con `POST` un URL contenente più di 2048 caratteri. Una `POST` chiamata evento include dati nel corpo della richiesta. [!UICONTROL DIL] inserisce i dati in coppie chiave-valore e trasmette le informazioni come dati del modulo anziché nella stringa di query URL.

Anche se ogni metodo trasmette dati in modo diverso, questo non influisce sulle funzionalità. Ad esempio, con uno dei due metodi, invia [!DNL Audience Manager] comunque dati alle destinazioni, le sincronizzazioni ID funzionano normalmente ed è possibile creare caratteristiche dai segnali dati.

<br> 

**Cosa mi consente[!UICONTROL REST API]di fare?**

Gli [!UICONTROL REST API]s consentono di lavorare a livello di programmazione con la maggior parte [!DNL Audience Manager] delle funzionalità e funzioni disponibili nell&#39;interfaccia utente.

<br> 

**Come si ottiene un[!UICONTROL REST API]ID client e un segreto?**

Contatta il rappresentante Soluzioni Partner per ottenere [!DNL API] le credenziali di accesso. Le nostre API usano [gli standard oauth 2.0](https://oauth.net/2/) per l&#39;autenticazione token, l&#39;autorizzazione e il rinnovo. Consulta [Autenticazione oauth](../api/rest-api-main/aam-api-getting-started.md#oauth) per ulteriori informazioni.
