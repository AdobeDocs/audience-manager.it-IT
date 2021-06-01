---
description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti dall’interno di Audience Manager
seo-description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti dall’interno di Audience Manager
seo-title: Audience Marketplace per gli acquirenti di dati
solution: Audience Manager
title: Audience Marketplace per gli acquirenti di dati
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] per gli acquirenti di dati  {#audience-marketplace-for-data-buyers}

Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti da [!DNL Audience Manager].

>[!NOTE]
>[Le autorizzazioni basate sul ruolo](../../../reporting/reports-dashboard.md) controllano l&#39;accesso alle funzioni [!UICONTROL Audience Marketplace].
>
>* Gli amministratori possono creare feed di dati, gestire gli abbonati e abbonarsi ai feed di dati.
>* Gli utenti possono cercare e visualizzare solo i feed.


## Il [!UICONTROL Marketplace]: Informazioni su {#about-marketplace}

La [!UICONTROL Marketplace] è una funzione [!DNL Audience Manager] per gli acquirenti di dati che elenca i feed di dati a cui puoi abbonarti. Elenca feed di dati privati, a tariffa fissa [!DNL CPM]. Questi feed sono forniti da fornitori di terze parti che utilizzano [!DNL Audience Manager] per vendere dati.

In [!UICONTROL Marketplace], gli strumenti di reporting consentono di monitorare l’utilizzo dei feed e la sovrapposizione tra il [!UICONTROL traits] e quelli in un feed di dati con sottoscrizione. Infine, con [!UICONTROL Audience Marketplace], [!DNL Adobe] si occupa delle fatture e dei pagamenti per le tariffe (anche se è necessario segnalare l’utilizzo al momento dell’abbonamento a un feed [!DNL CPM]). Queste funzioni consentono di trovare fonti di dati efficaci senza perdere tempo alla ricerca di un provider di dati.

>[!TIP]
>
>Utilizza il **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** per trovare feed di dati di alta qualità a cui puoi abbonarti. Quindi, torna all&#39;interfaccia utente [!DNL Audience Manager] o utilizza l&#39; [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) per abbonarti ai feed che hai trovato.

![buyer-marketplace-panoramica](assets/buyer-marketplace-overview.png)

L&#39;elenco [!UICONTROL Marketplace] contiene informazioni che puoi ordinare e cercare per trovare il feed di dati più adatto alle tue esigenze. Gli elementi nell&#39;elenco dell&#39;acquirente [!UICONTROL Marketplace] includono:

* **[!UICONTROL Search]**: Trova feed di dati per nome o descrizione del testo.
* **[!UICONTROL Similar Traits]**: Mostra il numero di elementi simili  [!UICONTROL traits] da un feed di dati. Questa colonna viene visualizzata dopo aver inserito un [!UICONTROL trait] o [!UICONTROL segment] per filtrare per nella sezione **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Nome del feed di dati.
* **[!UICONTROL Description]**: Informazioni sul contenuto di un feed di dati.
* **[!UICONTROL Provider]**: Nome del provider di dati.
* **[!UICONTROL Traits]**: Il numero di  [!UICONTROL traits] in un feed di dati.
* **[!UICONTROL 30 Day Provider Unique Users]**: Il numero di utenti univoci visti negli ultimi 30 giorni.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Il numero di utenti nel tuo account che si sovrappongono agli utenti nell’account del provider.
* **[!UICONTROL Feed Overlap]**: Il valore univoco sovrapposto a 30 giorni, visualizzato in percentuali, calcolato come segue: Acquirente dati 30 giorni sovrapposti univoci / Acquirente dati 30 giorni univoci) x 100.
* **[!UICONTROL Private Feeds]**: Consulta Feed di dati  [privati](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Il numero di sottoscrizioni disponibili con un provider di dati.

 

Per trovare facilmente i migliori feed di dati per le tue esigenze, utilizza i seguenti filtri disponibili sul lato sinistro della pagina [!UICONTROL Marketplace]:

* **[!UICONTROL Similarity To]**: Filtrare i feed di dati in base alla loro somiglianza con una  [!UICONTROL trait] o  [!UICONTROL segment] dell’utente scelto. Quando immetti il [!UICONTROL trait] o il segmento a cui confrontare, puoi utilizzare l&#39;ID [!UICONTROL trait] o [!UICONTROL segment] o i rispettivi nomi.
* **[!UICONTROL Similarity Cutoff]**: Trascina il cursore per filtrare i feed di dati in base alla loro somiglianza  [!UICONTROL traits] con quelli selezionati  [!UICONTROL trait] o  [!UICONTROL segment]. Per ulteriori informazioni sui punteggi di similarità [!UICONTROL trait], consulta [Punteggio di similarità delle caratteristiche](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtra i feed di dati in base allo stato dell’abbonamento.
* **[!UICONTROL Plan Use Case]**: Filtrare i feed di dati in base ai relativi casi di utilizzo supportati:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** e  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrare i feed di dati in base al tipo di prezzo.

## Ricerca di valori simili [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] offre la possibilità di trovare  [!UICONTROL traits] da vari feed di dati, in base alla loro somiglianza con i segmenti esistenti  [!UICONTROL traits] o esistenti. Ecco come eseguire questa operazione:

1. Vai a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilizza il selettore **[!UICONTROL Similarity To]** per scegliere tra un filtro basato su [!UICONTROL trait] o [!UICONTROL segment]. Puoi filtrare in base all’ [!UICONTROL trait]/[!UICONTROL segment] ID o al nome. La casella di ricerca mostra automaticamente i suggerimenti pertinenti in base all’input.
3. Dopo aver identificato la caratteristica o il segmento per cui desideri filtrare, fai clic su di esso nell’elenco dei suggerimenti.
4. Per limitare i risultati, utilizza il cursore **[!UICONTROL Similarity Cutoff]** per passare da meno simile [!UICONTROL traits] a più simili.

Una volta completato il filtro, visualizzerai una nuova colonna nella pagina dei risultati: **[!UICONTROL Similar Traits]**. Questa colonna mostra il numero di [!UICONTROL traits] simili a quello filtrato da, da ogni feed di dati che soddisfa i criteri di filtro.

Per visualizzare l’elenco completo delle caratteristiche simili, fai clic sul numero nella colonna **[!UICONTROL Similar Traits]** .

>[!NOTE]
>
> In Audience Marketplace vengono visualizzati i primi 500 risultati [!UICONTROL trait] simili provenienti dai vari feed di dati.

Guarda il video seguente per una panoramica completa su come trovare simili [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Feed di dati privati {#private-data-feeds}

Nell&#39;elenco [!UICONTROL Marketplace], a volte il nome del provider e i dati [!UICONTROL trait] sono contrassegnati come privati. Indica un [feed dati privato](../../../features/audience-marketplace/marketplace-private-feeds.md). Un feed di dati privato consente ai venditori di limitare l’accesso dell’acquirente ai propri dati. I venditori possono rendere i feed privati quando offrono offerte speciali, sconti o quando la privacy e il controllo degli accessi sono importanti per loro. In qualità di acquirente, devi inviare una richiesta di abbonamento al venditore se desideri accedere a un feed privato. Per ulteriori informazioni, consulta [Abbonati a un feed di dati privato](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) .

>[!MORELIKETHIS]
>
>* [Informazioni sulla pagina Dettagli piano in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
* [Sconti per gli acquirenti di dati](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

