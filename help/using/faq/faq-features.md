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


# Domande frequenti sulle funzioni e sulle funzioni del prodotto{#product-features-and-functions-faq}

Domande e problemi comuni su prodotti e funzioni.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Cos&#39;è il mio ID organizzazione e come lo trovo?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. Consiste in una stringa alfanumerica composta da 24 caratteri seguita [!UICONTROL @AdobeOrg]da.

Ad esempio, un *`Organization ID`* esempio di questo esempio: `1FD6776A524453CC0A490D44@AdobeOrg`.

Viene *`Organization ID`* usato dall&#39;API [DIL](../dil/dil-overview.md) di Audience Manager, dal [servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/)e da altre [!DNL Experience Cloud] soluzioni. Gli utenti con autorizzazioni Amministratore possono trovare il *`Organization ID`*[!DNL Adobe Admin Console]contenuto. Consultate [Amministrazione - Domande frequenti sulla gestione utenti](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**Posso creare in massa caratteristiche o destinazioni?**

Sì. Consultate [Strumenti di gestione di massa](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools] Gli strumenti *non sono* supportati da [!DNL Audience Manager]. Sono fornite per comodità e solo per cortesia. Per modifiche in massa, consigliamo di lavorare con [le API](../api/api.md) Audience Manager.

<br> 

**[!DNL Audience Manager]È possibile ridurre la necessità di tag di terze parti o pixel e migliorare i tempi di caricamento delle pagine?**

Se [!DNL Audience Manager] è integrato con il partner dati di terze parti, puoi sostituire i relativi pixel e tag con una chiamata ID server-to-server a [!DNL Audience Manager]. In questo caso [!DNL Audience Manager] , attiverai una singola chiamata ID la prima volta che un utente viene visualizzato e sincronizza tali informazioni con il tuo partner di terze parti. Ciò elimina la necessità di effettuare più chiamate pixel da ogni pagina. La riduzione delle chiamate pixel può migliorare i tempi di caricamento delle pagine.

<br> 

**Ho effettuato la sottoscrizione a un feed di dati. Dove sono memorizzati i dati?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Vai a **[!UICONTROL Audience Data > Traits]** ed espandi [!UICONTROL 3rd-Party Data] la cartella per visualizzare le caratteristiche o creare segmenti e modelli con questi dati.

<br> 

**Che cosa è[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager ( [!UICONTROL Tag Insertion Manager] TIM) da creare e gestire [!UICONTROL data collection code (DIL)]. Questa funzione è obsoleta ed è stata sostituita per la prima volta [!UICONTROL Dynamic Tag Manager (DTM)][!DNL Adobe Launch]da e successivamente. Per ulteriori informazioni, vedi [Adobe Launch](https://docs.adobelaunch.com/) e [Gestione tag dinamica](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Quali sono le differenze tra modelli algoritmici e raccomandazioni? Quando devo usarli?**

**Modelli algoritmici**

I modelli algoritmici non solo trovano le caratteristiche più influenti, ma anche gli utenti di valutazione basati su tali caratteristiche e assegnano ogni utente a un punteggio individuale. Potete quindi creare caratteristiche algoritmiche per eseguire il targeting dei vostri utenti. Con controlli di precisione e REACH nel Generatore caratteristiche, potete specificare quali utenti hanno le caratteristiche influenti da destinare.

I modelli algoritmici consentono di selezionare gli utenti con livelli di accuratezza diversi e di eseguire il test in Audience Lab, il cui gruppo di utenti viene convertito meglio. Guarda il caso d&#39;uso dettagliato in [Confronta modelli in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Nei modelli algoritmici, il modello viene eseguito ogni 8 giorni e aggiorna gli utenti idonei per le caratteristiche algoritmiche.

**Consigli sulle caratteristiche**

Recommendations offre un modo rapido per ottenere informazioni su altre caratteristiche simili a quelle utilizzate in un segmento.

Quando:

* Durante la creazione di un segmento hai bisogno di informazioni rapide;
* State utilizzando i segmenti per campagne brevi o per rimuovere rapidamente i destinatari che effettuano conversioni;
* Stai cercando di massimizzare la portata.

<br> 

**C&#39;è differenza tra i segmenti Adobe Analytics e Audience Manager?**

Sì, leggi [i segmenti in Analytics e Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) per una descrizione dettagliata delle differenze.
