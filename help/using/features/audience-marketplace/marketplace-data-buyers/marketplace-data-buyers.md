---
description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti dall’interno di Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace per gli acquirenti di dati
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 1%

---

# [!UICONTROL Audience Marketplace] per gli acquirenti di dati {#audience-marketplace-for-data-buyers}

Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti da [!DNL Audience Manager].

>[!NOTE]
>[Le autorizzazioni basate sul ruolo](../../../reporting/reports-dashboard.md) controllano l&#39;accesso alle funzionalità di [!UICONTROL Audience Marketplace].
>
>* Gli amministratori possono creare feed di dati, gestire gli abbonati e abbonarsi ai feed di dati.
>* Gli utenti possono cercare e visualizzare solo i feed.

## [!UICONTROL Marketplace]: Informazioni su {#about-marketplace}

[!UICONTROL Marketplace] è una funzionalità di [!DNL Audience Manager] per gli acquirenti di dati che elenca i feed di dati a cui è possibile iscriversi. Elenca feed di dati privati, [!DNL CPM] e a velocità fissa. Questi feed vengono forniti da fornitori di terze parti che utilizzano [!DNL Audience Manager] per vendere dati.

In [!UICONTROL Marketplace], gli strumenti di reporting consentono di tenere traccia dell&#39;utilizzo dei feed e della sovrapposizione tra [!UICONTROL traits] e quelli in un feed di dati sottoscritto. Infine, con [!UICONTROL Audience Marketplace], [!DNL Adobe] si occupa delle fatture e dei pagamenti delle tariffe (anche se è necessario segnalare autonomamente l&#39;utilizzo quando si sottoscrive un feed [!DNL CPM]). Queste funzioni consentono di trovare origini dati efficaci senza sprecare tempo alla ricerca di un provider di dati.

>[!TIP]
>
>Utilizza **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** per trovare feed di dati di alta qualità a cui puoi iscriverti. Quindi, torna all&#39;interfaccia utente [!DNL Audience Manager] o utilizza l&#39;[Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) per iscriverti ai feed trovati.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

L&#39;elenco [!UICONTROL Marketplace] contiene informazioni che è possibile ordinare e cercare per trovare il feed di dati appropriato. Gli elementi nell&#39;elenco dell&#39;acquirente di [!UICONTROL Marketplace] includono:

* **[!UICONTROL Search]**: trova feed dati per nome o descrizione testuale.
* **[!UICONTROL Similar Traits]**: mostra il numero di [!UICONTROL traits] simili da un feed di dati. Questa colonna viene visualizzata dopo l&#39;immissione di [!UICONTROL trait] o [!UICONTROL segment] in base al quale filtrare nella sezione **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: nome del feed dati.
* **[!UICONTROL Description]**: informazioni sul contenuto di un feed di dati.
* **[!UICONTROL Provider]**: nome del provider di dati.
* **[!UICONTROL Traits]**: numero di [!UICONTROL traits] in un feed di dati.
* **[!UICONTROL 30 Day Provider Unique Users]**: numero di utenti univoci visualizzati negli ultimi 30 giorni.
* **[!UICONTROL 30 Day Overlapped Uniques]**: numero di utenti nel tuo account che si sovrappongono agli utenti nell&#39;account del provider.
* **[!UICONTROL Feed Overlap]**: valore di univoci sovrapposti a 30 giorni, visualizzato in percentuali, calcolato come: univoci sovrapposti a 30 giorni dall&#39;acquirente dati / univoci univoci a 30 giorni dall&#39;acquirente dati) x 100.
* **[!UICONTROL Private Feeds]**: Vedere [Feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: numero di sottoscrizioni disponibili con un provider di dati.

 

Per trovare facilmente i feed di dati più adatti alle tue esigenze, utilizza i seguenti filtri disponibili sul lato sinistro della pagina [!UICONTROL Marketplace]:

* **[!UICONTROL Similarity To]**: Filtra i feed dati in base alla somiglianza con [!UICONTROL trait] o [!UICONTROL segment] scelta. Quando inserisci [!UICONTROL trait] o il segmento con cui confrontare, puoi utilizzare l&#39;ID [!UICONTROL trait] o [!UICONTROL segment], o i rispettivi nomi.
* **[!UICONTROL Similarity Cutoff]**: trascina il cursore per filtrare i feed di dati in base alla somiglianza di [!UICONTROL traits] con [!UICONTROL trait] o [!UICONTROL segment] selezionati. Per ulteriori informazioni sui [!UICONTROL trait] punteggi di somiglianza, consulta [Punteggio di somiglianza caratteristiche](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: filtra i feed di dati in base allo stato dell&#39;abbonamento.
* **[!UICONTROL Plan Use Case]**: filtra i feed di dati in base ai casi d&#39;uso supportati: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** e **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: filtra i feed di dati in base al tipo di prezzo.

## Ricerca di [!UICONTROL Traits] simili {#finding-similar-traits}

[!UICONTROL Audience Marketplace] consente di trovare [!UICONTROL traits] da vari feed di dati, in base alla somiglianza con i [!UICONTROL traits] o segmenti esistenti. Ecco come eseguire questa operazione:

1. Vai a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilizza il selettore **[!UICONTROL Similarity To]** per scegliere tra un filtro basato su [!UICONTROL trait] o [!UICONTROL segment]. È possibile filtrare in base all&#39;ID o al nome [!UICONTROL trait]/[!UICONTROL segment]. La casella di ricerca mostra automaticamente i suggerimenti pertinenti in base all’input.
3. Dopo aver identificato la caratteristica o il segmento in base al quale desideri filtrare, fai clic su di esso nell’elenco dei suggerimenti.
4. Per limitare i risultati, utilizzare il dispositivo di scorrimento **[!UICONTROL Similarity Cutoff]** per passare da [!UICONTROL traits] meno simili a risultati più simili.

Una volta completato il filtro, verrà visualizzata una nuova colonna nella pagina dei risultati: **[!UICONTROL Similar Traits]**. Questa colonna mostra il numero di [!UICONTROL traits] simili a quello filtrato da, da ogni feed di dati che soddisfa i criteri di filtro.

Per visualizzare l&#39;elenco completo delle caratteristiche simili, fare clic sul numero nella colonna **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> In Audience Marketplace vengono visualizzati i primi 500 risultati [!UICONTROL trait] simili provenienti da nei feed di dati.

Guarda il video seguente per una panoramica completa su come trovare [!UICONTROL traits] simili.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Feed di dati privati {#private-data-feeds}

Nell&#39;elenco [!UICONTROL Marketplace], a volte il nome del provider e i dati [!UICONTROL trait] sono contrassegnati come privati. Indica un [feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md). Un feed di dati privato consente ai venditori di limitare l’accesso dell’acquirente ai propri dati. I venditori possono rendere privati i feed quando offrono offerte speciali, sconti o quando la privacy e il controllo degli accessi sono importanti per loro. In qualità di acquirente, devi inviare una richiesta di abbonamento al venditore se desideri accedere a un feed privato. Per ulteriori informazioni, consulta [Iscriviti a un feed di dati privato](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

>[!MORELIKETHIS]
>
>* [Informazioni sulla pagina Dettagli piano in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Sconti per gli acquirenti di dati](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
