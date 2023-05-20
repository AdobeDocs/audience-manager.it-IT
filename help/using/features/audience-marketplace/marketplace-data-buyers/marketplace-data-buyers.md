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
source-wordcount: '727'
ht-degree: 2%

---

# [!UICONTROL Audience Marketplace] per gli acquirenti di dati {#audience-marketplace-for-data-buyers}

Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti da [!DNL Audience Manager].

>[!NOTE]
>[Autorizzazioni basate sul ruolo](../../../reporting/reports-dashboard.md) controllare l’accesso a [!UICONTROL Audience Marketplace] funzioni.
>
>* Gli amministratori possono creare feed di dati, gestire gli abbonati e abbonarsi ai feed di dati.
>* Gli utenti possono cercare e visualizzare solo i feed.


## Il [!UICONTROL Marketplace]: Informazioni su {#about-marketplace}

Il [!UICONTROL Marketplace] è un [!DNL Audience Manager] funzionalità per gli acquirenti di dati che elenca i feed di dati a cui puoi iscriverti. Esso elenca una tariffa forfettaria, [!DNL CPM]e feed di dati privati. Questi feed vengono forniti da fornitori di terze parti che utilizzano [!DNL Audience Manager] per vendere dati.

In [!UICONTROL Marketplace], gli strumenti di reporting consentono di tenere traccia dell’utilizzo dei feed e della sovrapposizione tra i [!UICONTROL traits] e quelli in un feed di dati sottoscritto. Infine, con [!UICONTROL Audience Marketplace], [!DNL Adobe] si occupa delle fatture e dei pagamenti delle commissioni (anche se è necessario segnalare autonomamente l&#39;utilizzo quando si sottoscrive un [!DNL CPM] feed). Queste funzioni consentono di trovare origini dati efficaci senza sprecare tempo alla ricerca di un provider di dati.

>[!TIP]
>
>Utilizza il **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** per trovare feed di dati di alta qualità a cui abbonarti. Quindi, torna alla sezione [!DNL Audience Manager] interfaccia utente o utilizzare il [Audience Marketplace API buyer](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) per iscriversi ai feed trovati.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

Il [!UICONTROL Marketplace] L&#39;elenco contiene informazioni che è possibile ordinare e cercare per trovare il feed di dati appropriato. Elementi in [!UICONTROL Marketplace] l&#39;elenco dell&#39;acquirente include:

* **[!UICONTROL Search]**: trova i feed di dati per nome o descrizione testuale.
* **[!UICONTROL Similar Traits]**: mostra il numero di simili [!UICONTROL traits] da un feed di dati. Questa colonna viene visualizzata dopo l&#39;immissione di [!UICONTROL trait] o [!UICONTROL segment] per filtrare in base a nella **[!UICONTROL Similarity To]** sezione.
* **[!UICONTROL Name]**: nome del feed di dati.
* **[!UICONTROL Description]**: informazioni sul contenuto di un feed di dati.
* **[!UICONTROL Provider]**: nome del provider di dati.
* **[!UICONTROL Traits]**: numero di [!UICONTROL traits] in un feed di dati.
* **[!UICONTROL 30 Day Provider Unique Users]**: numero di utenti univoci visualizzati negli ultimi 30 giorni.
* **[!UICONTROL 30 Day Overlapped Uniques]**: il numero di utenti nel tuo account che si sovrappongono agli utenti nell’account del provider.
* **[!UICONTROL Feed Overlap]**: valore degli univoci sovrapposti a 30 giorni, visualizzato in percentuali, calcolato come: univoci sovrapposti a 30 giorni dall’acquirente dei dati / univoci univoci di 30 giorni dall’acquirente dei dati) x 100.
* **[!UICONTROL Private Feeds]**: vedi [Feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: numero di abbonamenti disponibili a un provider di dati.

 

Per trovare facilmente i feed di dati migliori per le tue esigenze, utilizza i seguenti filtri disponibili sul lato sinistro della sezione [!UICONTROL Marketplace] pagina:

* **[!UICONTROL Similarity To]**: filtra i feed dati in base alla loro somiglianza con una [!UICONTROL trait] o [!UICONTROL segment] a tua scelta. Quando si immette [!UICONTROL trait] o al segmento con cui confrontare, puoi utilizzare [!UICONTROL trait] o [!UICONTROL segment] ID o i rispettivi nomi.
* **[!UICONTROL Similarity Cutoff]**: trascina il cursore per filtrare i feed di dati in base alla somiglianza tra [!UICONTROL traits] sono per il tuo selezionato [!UICONTROL trait] o [!UICONTROL segment]. Per ulteriori informazioni su [!UICONTROL trait] punteggi di somiglianza, vedi [Punteggio di somiglianza delle caratteristiche](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: filtra i feed di dati in base allo stato della tua iscrizione.
* **[!UICONTROL Plan Use Case]**: filtra i feed di dati in base ai casi di utilizzo supportati: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]**, e **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: filtra i feed di dati in base al loro tipo di prezzo.

## Ricerca di elementi simili [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] consente di trovare [!UICONTROL traits] da vari feed di dati, in base alla somiglianza con il [!UICONTROL traits] o segmenti. Ecco come eseguire questa operazione:

1. Vai a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilizza il **[!UICONTROL Similarity To]** selettore per scegliere tra un filtro basato su una [!UICONTROL trait] o [!UICONTROL segment]. Puoi filtrare in base a [!UICONTROL trait]/[!UICONTROL segment] ID o nome. La casella di ricerca mostra automaticamente i suggerimenti pertinenti in base all’input.
3. Dopo aver identificato la caratteristica o il segmento in base al quale desideri filtrare, fai clic su di esso nell’elenco dei suggerimenti.
4. Per limitare i risultati, utilizzare **[!UICONTROL Similarity Cutoff]** cursore per spostarsi da un dispositivo meno simile [!UICONTROL traits], a quelli più simili.

Una volta completato il filtro, nella pagina dei risultati verrà visualizzata una nuova colonna: **[!UICONTROL Similar Traits]**. Questa colonna mostra il numero di simili [!UICONTROL traits] a quello filtrato da, da ogni feed di dati che soddisfa i criteri di filtro.

Per visualizzare l’elenco completo delle caratteristiche simili, fai clic sul numero in **[!UICONTROL Similar Traits]** colonna.

>[!NOTE]
>
> L’Audience Marketplace mostra i primi 500 simili [!UICONTROL trait] risultati da nei feed di dati.

Guarda il video seguente per una panoramica completa su come trovare simili [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Feed di dati privati {#private-data-feeds}

In [!UICONTROL Marketplace] , a volte il nome del provider e [!UICONTROL trait] i dati sono contrassegnati come privati. Questo indica che [feed di dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md). Un feed di dati privato consente ai venditori di limitare l’accesso dell’acquirente ai propri dati. I venditori possono rendere privati i feed quando offrono offerte speciali, sconti o quando la privacy e il controllo degli accessi sono importanti per loro. In qualità di acquirente, devi inviare una richiesta di abbonamento al venditore se desideri accedere a un feed privato. Consulta [Iscriviti a un feed di dati privato](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) per i dettagli.

>[!MORELIKETHIS]
>
>* [Informazioni sulla pagina Dettagli piano in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Sconti per gli acquirenti di dati](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

