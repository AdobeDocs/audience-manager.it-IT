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


# Audience Marketplace per gli acquirenti di dati {#audience-marketplace-for-data-buyers}

Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti direttamente [!DNL Audience Manager]dall&#39;interno.

>[!NOTE]
>[Le autorizzazioni basate su ruolo](../../../reporting/reports-dashboard.md) consentono di accedere [!UICONTROL Audience Marketplace] alle funzioni.
>
>* Gli amministratori possono creare feed di dati, gestire gli abbonati e abbonarsi a feed di dati.
>* Gli utenti possono cercare e visualizzare solo i feed.


## Marketplace: Informazioni {#about-marketplace}

<!-- c_marketplace_about.xml -->

È [!UICONTROL Marketplace][!DNL Audience Manager] una funzione per gli acquirenti di dati che elenca i feed di dati a cui puoi abbonarti. Elenca i feed di dati, [!DNL CPM]o quelli privati. Questi feed vengono forniti dai fornitori di terze parti che usano [!DNL Audience Manager] per vendere dati. In [!UICONTROL Marketplace], gli strumenti di reporting consentono di monitorare l&#39;utilizzo dei feed e la sovrapposizione tra le caratteristiche e quelle in un feed di dati sottoscritto. Infine, si verifica l [!UICONTROL Audience Marketplace]&#39;attenzione [!DNL Adobe] delle fatture e dei pagamenti delle tariffe (anche se è necessario utilizzare l&#39;uso autonomo per la sottoscrizione a [!DNL CPM] un feed). Queste funzioni consentono di trovare origini dati efficaci senza perdere tempo cercando un fornitore di dati.

>[!TIP]
> 
>Utilizza **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** per trovare feed di dati di qualità elevata a cui puoi abbonarti. Quindi, torna nell&#39;interfaccia utente di Audience Manager oppure usa l [&#39;API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) Audience Marketplace per effettuare l&#39;iscrizione ai feed trovati.

![](assets/buyer_marketplace.png)

[!UICONTROL Marketplace] L&#39;elenco contiene informazioni che puoi ordinare e cercare per trovare il feed di dati più adatto alle tue esigenze. Gli elementi nell&#39;elenco [!UICONTROL Marketplace] dell&#39;acquirente includono:

* **[!UICONTROL Search]:** Trova feed di dati per nome o descrizione testo.
* **[!UICONTROL Name]:** Nome del feed di dati.
* **[!UICONTROL Description]:** Informazioni sul contenuto di un feed di dati.
* **[!UICONTROL Provider]:** Nome del provider di dati.
* **[!UICONTROL Traits]:** Numero di caratteristiche in un feed di dati.
* **[!UICONTROL 30 Day Provider Unique Users]:** Numero di utenti unici visti negli ultimi 30 giorni.
* **[!UICONTROL 30 Day Overlapped Uniques]:** Numero di utenti nel vostro account che si sovrappongono agli utenti nell&#39;account del fornitore.
* **[!UICONTROL Feed Overlap]:** Il valore unificato per 30 giorni, visualizzato in percentuali, calcolato come: L&#39;acquirente dati 30 giorno è sovrapposto a uniques/dati dell&#39;acquirente 30 giorni) x 100.
* **[!UICONTROL Private Feeds]:** Consultate [Feed dati privati](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]:** Numero di iscrizioni con un provider di dati.

## Feed dati privati {#private-data-feeds}

Nell&#39; [!UICONTROL Marketplace] elenco, a volte il nome del fornitore e i dati delle caratteristiche sono contrassegnati come privati. Indica un [feed di dati privato](../../../features/audience-marketplace/marketplace-private-feeds.md). Un feed di dati privato consente ai venditori di limitare l&#39;accesso degli acquirenti ai loro dati. I venditori possono rendere i feed privati quando offrono offerte speciali, sconti o quando la privacy e il controllo degli accessi sono importanti. In qualità di acquirente, devi inviare una richiesta di iscrizione al venditore se desideri accedere a un feed privato. Per informazioni dettagliate, consulta [Iscrizione a un feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) dati privato.

>[!MORE_ LIKE_ THIS]
>
>* [Informazioni sulla pagina Dettagli piano in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Sconti per gli acquirenti di dati](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

