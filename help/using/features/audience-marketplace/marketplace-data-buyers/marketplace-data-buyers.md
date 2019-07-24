---
description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti direttamente da Audience Manager
seo-description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti direttamente da Audience Manager
seo-title: Audience Marketplace per gli acquirenti di dati
solution: Audience Manager
title: Audience Marketplace per gli acquirenti di dati
topic: API DIL
uuid: f 505 b 5 f 4-4231-4 e 84-993 a-cd 64128 b 540 f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace for Data Buyers {#audience-marketplace-for-data-buyers}

Overview and workflow for data buyers who want to purchase third-party data from within [!DNL Audience Manager].

>[!NOTE]
>[Le autorizzazioni basate su ruolo](../../../reporting/reports-dashboard.md) consentono di accedere [!UICONTROL Audience Marketplace] alle funzioni.
>
>* Gli amministratori possono creare feed di dati, gestire gli abbonati e abbonarsi a feed di dati.
>* Gli utenti possono cercare e visualizzare solo i feed.


## The Marketplace: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

The [!UICONTROL Marketplace] is an [!DNL Audience Manager] feature for data buyers that lists data feeds you can subscribe to. It lists flat rate, [!DNL CPM], or private data feeds. These feeds are provided by third-party vendors that use [!DNL Audience Manager] to sell data. In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your traits and those in a subscribed data feed. Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). Queste funzioni consentono di trovare origini dati efficaci senza perdere tempo cercando un fornitore di dati.

>[!TIP]
> 
>Use the **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** to find high quality data feeds that you can subscribe to. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

[!UICONTROL Marketplace] L'elenco contiene informazioni che puoi ordinare e cercare per trovare il feed di dati più adatto alle tue esigenze. Items in the [!UICONTROL Marketplace] buyer's list include:

* **[!UICONTROL Search]:** Trova feed di dati per nome o descrizione testo.
* **[!UICONTROL Name]:** Nome del feed di dati.
* **[!UICONTROL Description]:** Informazioni sul contenuto di un feed di dati.
* **[!UICONTROL Provider]:** Nome del provider di dati.
* **[!UICONTROL Traits]:** Numero di caratteristiche in un feed di dati.
* **[!UICONTROL 30 Day Provider Unique Users]:** Numero di utenti unici visti negli ultimi 30 giorni.
* **[!UICONTROL 30 Day Overlapped Uniques]:** Numero di utenti nel vostro account che si sovrappongono agli utenti nell'account del fornitore.
* **[!UICONTROL Feed Overlap]:** Il valore unificato per 30 giorni, visualizzato in percentuali, calcolato come: L'acquirente dati 30 giorno è sovrapposto a uniques/dati dell'acquirente 30 giorni) x 100.
* **[!UICONTROL Private Feeds]:** Consultate [Feed dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]:** Numero di iscrizioni con un provider di dati.

## Feed dati privati {#private-data-feeds}

In the [!UICONTROL Marketplace] list, sometimes the provider's name and trait data are marked as private. This indicates a [private data feed](../../../features/audience-marketplace/marketplace-private-feeds.md). Un feed di dati privato consente ai venditori di limitare l'accesso degli acquirenti ai loro dati. I venditori possono rendere i feed privati quando offrono offerte speciali, sconti o quando la privacy e il controllo degli accessi sono importanti. In qualità di acquirente, devi inviare una richiesta di iscrizione al venditore se desideri accedere a un feed privato. See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_ LIKE_ THIS]
>
>* [Informazioni sulla pagina Dettagli piano in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Sconti per gli acquirenti di dati](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

