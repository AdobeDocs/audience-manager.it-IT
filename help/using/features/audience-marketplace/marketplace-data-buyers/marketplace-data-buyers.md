---
description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti dall'interno  Audience Manager
seo-description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti dall'interno  Audience Manager
seo-title: Audience Marketplace per gli acquirenti di dati
solution: Audience Manager
title: Audience Marketplace per gli acquirenti di dati
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 3%

---


# [!UICONTROL Audience Marketplace] per gli acquirenti di dati  {#audience-marketplace-for-data-buyers}

Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti da [!DNL Audience Manager].

>[!NOTE]
>[Autorizzazioni basate su ruolo](../../../reporting/reports-dashboard.md) controllano l&#39;accesso alle funzionalità [!UICONTROL Audience Marketplace].
>
>* Gli amministratori possono creare feed di dati, gestire gli abbonati e abbonarsi ai feed di dati.
>* Gli utenti possono cercare e visualizzare solo i feed.


## Il [!UICONTROL Marketplace]: Informazioni su {#about-marketplace}

La [!UICONTROL Marketplace] è una funzione [!DNL Audience Manager] per gli acquirenti di dati in cui sono elencati i feed di dati a cui puoi iscriverti. Elenca i feed di dati flat rate, [!DNL CPM] e privati. Questi feed vengono forniti da fornitori di terze parti che utilizzano [!DNL Audience Manager] per vendere i dati.

In [!UICONTROL Marketplace], gli strumenti di reporting consentono di monitorare l&#39;utilizzo dei feed e la sovrapposizione tra [!UICONTROL traits] e quelli in un feed di dati con sottoscrizione. Infine, con [!UICONTROL Audience Marketplace], [!DNL Adobe] si occupa delle fatture e dei pagamenti per le tariffe (anche se è necessario segnalare autonomamente l&#39;utilizzo al momento della sottoscrizione a un feed [!DNL CPM]). Queste funzioni consentono di trovare origini dati efficaci senza perdere tempo a cercare un provider di dati.

>[!TIP]
>
>Utilizzate il programma **[Audience Finder del Adobe](https://www.adobe-audience-finder.com/)** per trovare feed di dati di alta qualità a cui potete iscrivervi. Quindi, tornate all&#39;interfaccia utente [!DNL Audience Manager] o utilizzate l&#39; [ Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) per iscrivervi ai feed che avete trovato.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

L&#39;elenco [!UICONTROL Marketplace] contiene informazioni che è possibile ordinare e cercare per individuare il feed di dati più adatto alle proprie esigenze. Gli elementi nell&#39;elenco [!UICONTROL Marketplace] dell&#39;acquirente includono:

* **[!UICONTROL Search]**: Trova feed di dati per nome o descrizione del testo.
* **[!UICONTROL Similar Traits]**: Mostra il numero di elementi simili  [!UICONTROL traits] da un feed di dati. Questa colonna viene visualizzata dopo che è stato immesso un [!UICONTROL trait] o [!UICONTROL segment] da filtrare nella sezione **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Nome del feed di dati.
* **[!UICONTROL Description]**: Informazioni sul contenuto di un feed di dati.
* **[!UICONTROL Provider]**: Nome del provider di dati.
* **[!UICONTROL Traits]**: Il numero di  [!UICONTROL traits] contenuti in un feed di dati.
* **[!UICONTROL 30 Day Provider Unique Users]**: Numero di utenti univoci visti negli ultimi 30 giorni.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Il numero di utenti nell&#39;account che si sovrappongono con gli utenti nell&#39;account del fornitore.
* **[!UICONTROL Feed Overlap]**: Il valore di univocità sovrapposto di 30 giorni, visualizzato in percentuale, calcolato come segue: Acquirente dati 30 giorni sovrapposti unques / acquirente dati 30 giorni (uniche) x 100.
* **[!UICONTROL Private Feeds]**: Consultate Feed [ di dati ](../../../features/audience-marketplace/marketplace-private-feeds.md)privati.
* **[!UICONTROL Currently Subscribed Plan Count]**: Numero di sottoscrizioni possedute con un provider di dati.

 

Per trovare facilmente i feed di dati migliori per le vostre esigenze, utilizzate i seguenti filtri disponibili sul lato sinistro della pagina [!UICONTROL Marketplace]:

* **[!UICONTROL Similarity To]**: Filtrare i feed di dati in base alla loro somiglianza con una  [!UICONTROL trait] o  [!UICONTROL segment] dell&#39;utente scelto. Quando immetti il [!UICONTROL trait] o il segmento a cui confrontarti, puoi utilizzare l&#39;ID [!UICONTROL trait] o [!UICONTROL segment] o i rispettivi nomi.
* **[!UICONTROL Similarity Cutoff]**: Trascinate il cursore per filtrare i feed di dati in base alla loro somiglianza  [!UICONTROL traits] con quelli selezionati  [!UICONTROL trait] o  [!UICONTROL segment]. Per ulteriori informazioni sui [!UICONTROL trait] punteggi per similarità, vedere [Punteggio per similarità caratteristica](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrate i feed di dati in base al vostro stato di iscrizione.
* **[!UICONTROL Plan Use Case]**: Filtrare i feed di dati in base ai casi di utilizzo supportati:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** e  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrare i feed di dati in base al tipo di prezzo.

## Ricerca di elementi simili [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] ti offre la possibilità di trovare  [!UICONTROL traits] da vari feed di dati, in base alla loro similarità con i tuoi segmenti  [!UICONTROL traits] o quelli esistenti. Come procedere:

1. Vai a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilizzate il selettore **[!UICONTROL Similarity To]** per scegliere tra un filtro basato su [!UICONTROL trait] o [!UICONTROL segment]. Potete filtrare in base all&#39;ID o al nome [!UICONTROL trait]/[!UICONTROL segment]. Nella casella di ricerca vengono visualizzati automaticamente i suggerimenti pertinenti in base all’input immesso.
3. Dopo aver identificato la caratteristica o il segmento per il quale si desidera filtrare, fate clic su di esso nell&#39;elenco dei suggerimenti.
4. Per restringere i risultati, utilizzare il cursore **[!UICONTROL Similarity Cutoff]** per passare da meno simile [!UICONTROL traits] a più simili.

Una volta completato il filtro, nella pagina dei risultati verrà visualizzata una nuova colonna: **[!UICONTROL Similar Traits]**. Questa colonna mostra il numero di [!UICONTROL traits] simili a quello filtrato da, da ogni feed di dati che soddisfa i criteri di filtro.

Per visualizzare l&#39;elenco completo delle caratteristiche simili, fare clic sul numero nella colonna **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
>  Audience Marketplace visualizza i primi 500 risultati [!UICONTROL trait] simili provenienti dai vari feed di dati.

Guardate il video seguente per una panoramica completa su come trovare simili [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Feed di dati privati {#private-data-feeds}

Nell&#39;elenco [!UICONTROL Marketplace], talvolta il nome del provider e i dati [!UICONTROL trait] sono contrassegnati come privati. Indica un [feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md). Un feed di dati privato consente ai venditori di limitare l&#39;accesso dell&#39;acquirente ai propri dati. I venditori possono rendere privati i propri feed quando offrono offerte speciali, sconti o quando per loro è importante avere il controllo sulla privacy e sull&#39;accesso. In qualità di acquirente, è necessario inviare una richiesta di iscrizione al venditore se si desidera accedere a un feed privato. Per ulteriori informazioni, vedere [Iscrizione a un feed di dati privato](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

>[!MORELIKETHIS]
>
>* [Informazioni sulla pagina Dettagli piano in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Sconti per gli acquirenti di dati](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

