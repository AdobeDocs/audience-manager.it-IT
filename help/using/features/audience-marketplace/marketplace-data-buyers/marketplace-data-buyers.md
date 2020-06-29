---
description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti da  Audience Manager
seo-description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti da  Audience Manager
seo-title: ' Audience Marketplace per gli acquirenti di dati'
solution: Audience Manager
title: ' Audience Marketplace per gli acquirenti di dati'
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 1%

---


# [!UICONTROL Audience Marketplace] per gli acquirenti di dati {#audience-marketplace-for-data-buyers}

Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti dall&#39;interno [!DNL Audience Manager].

>[!NOTE]
>[Le autorizzazioni](../../../reporting/reports-dashboard.md) basate sul ruolo controllano l&#39;accesso alle [!UICONTROL Audience Marketplace] funzioni.
>
>* Gli amministratori possono creare feed di dati, gestire gli abbonati e abbonarsi ai feed di dati.
>* Gli utenti possono cercare e visualizzare solo i feed.


## Il [!UICONTROL Marketplace]seguente indirizzo: Informazioni {#about-marketplace}

Questa [!UICONTROL Marketplace] è una [!DNL Audience Manager] funzione per gli acquirenti di dati in cui sono elencati i feed di dati a cui puoi iscriverti. Elenca i feed di dati flat rate [!DNL CPM]e privati. Questi feed vengono forniti da fornitori di terze parti che utilizzano [!DNL Audience Manager] per vendere i dati.

Gli strumenti di [!UICONTROL Marketplace]reporting consentono di tenere traccia dell’utilizzo dei feed e della sovrapposizione tra i feed di dati [!UICONTROL traits] e quelli sottoscritti. Infine, con [!UICONTROL Audience Marketplace], [!DNL Adobe] si prende cura delle fatture e dei pagamenti delle tariffe (anche se è necessario eseguire autoreport sull&#39;utilizzo quando si sottoscrive un [!DNL CPM] feed). Queste funzioni consentono di trovare origini dati efficaci senza perdere tempo a cercare un provider di dati.

>[!TIP]
>
>Utilizza **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**per trovare feed di dati di alta qualità a cui puoi iscriverti. Quindi, tornate nell&#39;interfaccia[!DNL Audience Manager]utente o utilizzate la[API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)Audience Marketplace Buyer per iscrivervi ai feed trovati.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

L&#39; [!UICONTROL Marketplace] elenco contiene informazioni che è possibile ordinare e cercare per individuare il feed di dati più adatto alle proprie esigenze. Gli elementi nell&#39;elenco dell&#39; [!UICONTROL Marketplace] acquirente includono:

* **[!UICONTROL Search]**: Trova feed di dati per nome o descrizione del testo.
* **[!UICONTROL Similar Traits]**: Mostra il numero di elementi simili [!UICONTROL traits] da un feed di dati. Questa colonna viene visualizzata dopo l’immissione di un [!UICONTROL trait] filtro o [!UICONTROL segment] per nella **[!UICONTROL Similarity To]** sezione.
* **[!UICONTROL Name]**: Nome del feed di dati.
* **[!UICONTROL Description]**: Informazioni sul contenuto di un feed di dati.
* **[!UICONTROL Provider]**: Nome del provider di dati.
* **[!UICONTROL Traits]**: Il numero di [!UICONTROL traits] contenuti in un feed di dati.
* **[!UICONTROL 30 Day Provider Unique Users]**: Numero di utenti univoci visti negli ultimi 30 giorni.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Il numero di utenti nell&#39;account che si sovrappongono con gli utenti nell&#39;account del fornitore.
* **[!UICONTROL Feed Overlap]**: Il valore di univocità sovrapposto di 30 giorni, visualizzato in percentuale, calcolato come segue: Acquirente dati 30 giorni sovrapposti unques / acquirente dati 30 giorni (uniche) x 100.
* **[!UICONTROL Private Feeds]**: Consultate Feed [di dati](../../../features/audience-marketplace/marketplace-private-feeds.md)privati.
* **[!UICONTROL Currently Subscribed Plan Count]**: Numero di sottoscrizioni possedute con un provider di dati.

 

Per trovare facilmente i feed di dati migliori per le vostre esigenze, utilizzate i seguenti filtri disponibili sul lato sinistro della [!UICONTROL Marketplace] pagina:

* **[!UICONTROL Similarity To]**: Filtrare i feed di dati in base alla loro somiglianza con uno [!UICONTROL trait] o [!UICONTROL segment] dell&#39;utente scelto. Quando immetti il segmento o [!UICONTROL trait] il segmento con cui confrontarti, puoi utilizzare l’ [!UICONTROL trait] ID o [!UICONTROL segment] l’ID o i rispettivi nomi.
* **[!UICONTROL Similarity Cutoff]**: Trascinate il cursore per filtrare i feed di dati in base alla loro similarità [!UICONTROL traits] con quelli selezionati [!UICONTROL trait] o [!UICONTROL segment]. Per ulteriori informazioni sui punteggi per [!UICONTROL trait] similarità, consulta Valutazione per [affinità caratteristica](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrate i feed di dati in base al vostro stato di iscrizione.
* **[!UICONTROL Plan Use Case]**: Filtrare i feed di dati in base ai casi di utilizzo supportati: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** e **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrare i feed di dati in base al tipo di prezzo.

## Ricerca di valori simili [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] consente di trovare [!UICONTROL traits] da vari feed di dati, in base alla loro similarità con i segmenti [!UICONTROL traits] o gli elementi esistenti. Come procedere:

1. Vai a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Usate il **[!UICONTROL Similarity To]** selettore per scegliere tra un filtro basato su un [!UICONTROL trait] filtro o [!UICONTROL segment]. Puoi filtrare in base a [!UICONTROL trait]/[!UICONTROL segment] ID o nome. Nella casella di ricerca vengono visualizzati automaticamente i suggerimenti pertinenti in base all’input immesso.
3. Dopo aver identificato la caratteristica o il segmento per il quale si desidera filtrare, fate clic su di esso nell&#39;elenco dei suggerimenti.
4. Per restringere i risultati, usate il **[!UICONTROL Similarity Cutoff]** cursore per passare da meno simili [!UICONTROL traits]a più simili.

Una volta completato il filtro, nella pagina dei risultati verrà visualizzata una nuova colonna: **[!UICONTROL Similar Traits]**. Questa colonna mostra il numero di elementi simili [!UICONTROL traits] a quelli filtrati da ciascun feed di dati che soddisfa i criteri di filtro.

Per visualizzare l&#39;elenco completo delle caratteristiche simili, fare clic sul numero nella **[!UICONTROL Similar Traits]** colonna.

>[!NOTE]
>
>  Audience Marketplace visualizza i primi 500 risultati simili [!UICONTROL trait] dai vari feed di dati.

Guardate il video sottostante per una panoramica completa su come trovare simili [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Feed dati privati {#private-data-feeds}

Nell&#39; [!UICONTROL Marketplace] elenco, a volte il nome e [!UICONTROL trait] i dati del provider sono contrassegnati come privati. Indica un feed [di dati](../../../features/audience-marketplace/marketplace-private-feeds.md)privato. Un feed di dati privato consente ai venditori di limitare l&#39;accesso dell&#39;acquirente ai propri dati. I venditori possono rendere privati i propri feed quando offrono offerte speciali, sconti o quando per loro è importante avere il controllo sulla privacy e sull&#39;accesso. In qualità di acquirente, è necessario inviare una richiesta di iscrizione al venditore se si desidera accedere a un feed privato. Per informazioni, consulta [Iscrizione a feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) dati privati.

>[!MORELIKETHIS]
>
>* [Informazioni sulla pagina Dettagli piano in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Sconti per gli acquirenti di dati](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

