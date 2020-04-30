---
description: Domande e problemi comuni relativi a prodotti e funzioni.
keywords: audience manager cookies
seo-description: Domande e problemi comuni relativi a prodotti e funzioni.
seo-title: Domande frequenti su funzioni e funzionalità del prodotto
solution: Audience Manager
title: Domande frequenti su funzioni e funzionalità del prodotto
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Domande frequenti su funzioni e funzionalità del prodotto{#product-features-and-functions-faq}

Domande e problemi comuni relativi a prodotti e funzioni.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Qual è il mio ID organizzazione e come lo trovo?**

L’ID *`Organization ID`* è univoco e identifica l’organizzazione [!DNL Audience Manager] e l’ [!DNL Adobe Experience Cloud]. È composta da una stringa alfanumerica con distinzione tra maiuscole e minuscole di 24 caratteri seguita da [!UICONTROL @AdobeOrg].

Esempio: *`Organization ID`* `1FD6776A524453CC0A490D44@AdobeOrg`.

L’ *`Organization ID`* API viene utilizzata dall’API [DIL](../dil/dil-overview.md) di Audience Manager, dal servizio [identità](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform e da altre [!DNL Experience Cloud] soluzioni. Gli utenti con autorizzazioni di amministratore possono trovare *`Organization ID`* il collegamento nel [!DNL Adobe Admin Console]. Consultate le Domande frequenti [Amministrazione - Gestione utente](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

<br> 

**Posso creare caratteristiche o destinazioni in massa?**

Sì. Consultate Strumenti [di gestione di](../reference/bulk-management-tools/bulk-management-intro.md)massa.

>[!NOTE]
>
>Gli [!UICONTROL Bulk Management Tools] strumenti non *sono* supportati da [!DNL Audience Manager]. Sono fornite solo per comodità e per cortesia. Per modifiche di massa, consigliamo di utilizzare le API [](../api/api.md) Audience Manager.

<br> 

**È possibile[!DNL Audience Manager]ridurre la necessità di tag o pixel di terze parti e migliorare i tempi di caricamento delle pagine?**

Se [!DNL Audience Manager] è integrato con il partner dati di terze parti, puoi sostituire i pixel e i tag con una chiamata ID server-to-server a [!DNL Audience Manager]. In questo caso, [!DNL Audience Manager] attiverebbe una singola chiamata ID la prima volta che vediamo un utente e sincronizziamo tali informazioni con il tuo partner di terze parti. Questo elimina la necessità di effettuare chiamate con più pixel da ogni pagina. La riduzione delle chiamate in pixel può migliorare i tempi di caricamento delle pagine.

<br> 

**Mi sono iscritto a un feed di dati. Dove vengono memorizzati i dati?**

Il feed di dati e tutte le caratteristiche contenute nel feed vengono visualizzati come sottocartelle e caratteristiche in [!DNL Audience Manager]. Vai a **[!UICONTROL Audience Data > Traits]** ed espandi la [!UICONTROL 3rd-Party Data] cartella per visualizzare le caratteristiche o creare segmenti e modelli con questi dati.

<br> 

**Che cosa è[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager utilizzato [!UICONTROL Tag Insertion Manager] (TIM) per creare e gestire [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

<br> 

**Quali sono le differenze tra i modelli algoritmici e le raccomandazioni sulle caratteristiche? Quando dovrei usare ognuna di esse?**

**Modelli algoritmici**

I modelli algoritmici non solo trovano le caratteristiche più influenti, ma anche assegnano agli utenti un punteggio in base a tali caratteristiche e assegnano a ciascun utente un punteggio individuale. Quindi create caratteristiche algoritmiche per eseguire il targeting degli utenti. Con i controlli di precisione e portata nel Generatore di caratteristiche, puoi specificare quali utenti tra tutti coloro che hanno le caratteristiche influenti a cui vuoi rivolgerti.

Modelli algoritmici consente di selezionare gli utenti a diversi livelli di precisione e di verificare in Audience Lab quale gruppo di utenti converte meglio. Consulta i casi d’uso dettagliati in [Confronta modelli in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In Modelli algoritmici, il modello viene eseguito ogni 8 giorni e aggiorna gli utenti qualificati per le caratteristiche algoritmiche.

**Consigli sulle caratteristiche**

Trait Recommendations è un modo rapido per ottenere informazioni su altre caratteristiche simili a quelle utilizzate in un segmento.

Dovresti utilizzare le raccomandazioni sulle caratteristiche quando:

* Durante la creazione di un segmento è necessario disporre di informazioni rapide;
* Si utilizzano i segmenti per campagne brevi o quando si desidera eliminare rapidamente il pubblico che effettua la conversione;
* Stai cercando di massimizzare la portata.

<br> 

**C&#39;è qualche differenza tra i segmenti di Adobe Analytics e Audience Manager?**

Sì, leggi [Comprensione dei segmenti in Analytics e Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) per una descrizione dettagliata delle differenze.
