---
description: Domande e problemi comuni su prodotti e funzioni.
keywords: cookie di Audience Manager
seo-description: Domande e problemi comuni su prodotti e funzioni.
seo-title: Domande frequenti sulle funzioni e sulle funzioni del prodotto
solution: Audience Manager
title: Domande frequenti sulle funzioni e sulle funzioni del prodotto
uuid: da 5 f 5089-24 a 8-4455-88 a 6-eb 62 d 83939 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Product Features and Functions FAQ{#product-features-and-functions-faq}

Domande e problemi comuni su prodotti e funzioni.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Cos'è il mio ID organizzazione e come lo trovo?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

For example, an *`Organization ID`* looks like this: `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**Posso creare in massa caratteristiche o destinazioni?**

Sì. See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools] Gli strumenti *non sono* supportati da [!DNL Audience Manager]. Sono fornite per comodità e solo per cortesia. For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

<br> 

**[!DNL Audience Manager]È possibile ridurre la necessità di tag di terze parti o pixel e migliorare i tempi di caricamento delle pagine?**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. Ciò elimina la necessità di effettuare più chiamate pixel da ogni pagina. La riduzione delle chiamate pixel può migliorare i tempi di caricamento delle pagine.

<br> 

**Ho effettuato la sottoscrizione a un feed di dati. Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**Che cosa è[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Quali sono le differenze tra modelli algoritmici e raccomandazioni? When should I use each of them?**

**Modelli algoritmici**

I modelli algoritmici non solo trovano le caratteristiche più influenti, ma anche gli utenti di valutazione basati su tali caratteristiche e assegnano ogni utente a un punteggio individuale. Potete quindi creare caratteristiche algoritmiche per eseguire il targeting dei vostri utenti. Con controlli di precisione e REACH nel Generatore caratteristiche, potete specificare quali utenti hanno le caratteristiche influenti da destinare.

I modelli algoritmici consentono di selezionare gli utenti con livelli di accuratezza diversi e di eseguire il test in Audience Lab, il cui gruppo di utenti viene convertito meglio. See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Nei modelli algoritmici, il modello viene eseguito ogni 8 giorni e aggiorna gli utenti idonei per le caratteristiche algoritmiche.

**Consigli sulle caratteristiche**

Recommendations offre un modo rapido per ottenere informazioni su altre caratteristiche simili a quelle utilizzate in un segmento.

Quando:

* Durante la creazione di un segmento hai bisogno di informazioni rapide;
* State utilizzando i segmenti per campagne brevi o per rimuovere rapidamente i destinatari che effettuano conversioni;
* Stai cercando di massimizzare la portata.

<br> 

**C'è differenza tra i segmenti Adobe Analytics e Audience Manager?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.
