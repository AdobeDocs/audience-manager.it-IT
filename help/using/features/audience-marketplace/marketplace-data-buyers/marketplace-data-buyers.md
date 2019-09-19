---
description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti da Audience Manager
seo-description: Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti da Audience Manager
seo-title: Audience Marketplace per gli acquirenti di dati
solution: Audience Manager
title: Audience Marketplace per gli acquirenti di dati
topic: API DIL
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace per gli acquirenti di dati {#audience-marketplace-for-data-buyers}

Panoramica e flusso di lavoro per gli acquirenti di dati che desiderano acquistare dati di terze parti dall'interno [!DNL Audience Manager].

>[!NOTE]
>[Le autorizzazioni](../../../reporting/reports-dashboard.md) basate sul ruolo controllano l'accesso alle [!UICONTROL Audience Marketplace] funzioni.
>
>* Gli amministratori possono creare feed di dati, gestire gli abbonati e abbonarsi ai feed di dati.
>* Gli utenti possono cercare e visualizzare solo i feed.


## Marketplace: Informazioni {#about-marketplace}

<!-- c_marketplace_about.xml -->

Questa [!UICONTROL Marketplace] è una [!DNL Audience Manager] funzione per gli acquirenti di dati in cui sono elencati i feed di dati a cui puoi iscriverti. Elenca i feed di dati flat rate [!DNL CPM], o privati. Questi feed vengono forniti da fornitori di terze parti che utilizzano [!DNL Audience Manager] per vendere i dati. Gli strumenti di [!UICONTROL Marketplace]reporting consentono di tenere traccia dell’utilizzo dei feed e della sovrapposizione tra le caratteristiche e quelle di un feed di dati con sottoscrizione. Infine, con [!UICONTROL Audience Marketplace], [!DNL Adobe] si prende cura delle fatture e dei pagamenti delle tariffe (anche se è necessario eseguire autoreport sull'utilizzo quando si sottoscrive un [!DNL CPM] feed). Queste funzioni consentono di trovare origini dati efficaci senza perdere tempo a cercare un provider di dati.

>[!TIP]
> 
>Utilizza **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** per trovare feed di dati di alta qualità a cui puoi abbonarti. Quindi, tornate nell’interfaccia utente di Audience Manager o utilizzate l’API [](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) Audience Marketplace per iscrivervi ai feed che avete trovato.

![](assets/buyer_marketplace.png)

L' [!UICONTROL Marketplace] elenco contiene informazioni che è possibile ordinare e cercare per individuare il feed di dati più adatto alle proprie esigenze. Gli elementi nell'elenco dell' [!UICONTROL Marketplace] acquirente includono:

* **[!UICONTROL Search]** : Trova feed di dati per nome o descrizione del testo.
* **[!UICONTROL Name]** : Nome del feed di dati.
* **[!UICONTROL Description]** : Informazioni sul contenuto di un feed di dati.
* **[!UICONTROL Provider]** : Nome del provider di dati.
* **[!UICONTROL Traits]** : Numero di caratteristiche in un feed di dati.
* **[!UICONTROL 30 Day Provider Unique Users]** : Numero di utenti univoci visti negli ultimi 30 giorni.
* **[!UICONTROL 30 Day Overlapped Uniques]** : Il numero di utenti nell'account che si sovrappongono con gli utenti nell'account del fornitore.
* **[!UICONTROL Feed Overlap]** : Il valore di univocità sovrapposto di 30 giorni, visualizzato in percentuale, calcolato come segue: Acquirente dati 30 giorni sovrapposti unques / acquirente dati 30 giorni (uniche) x 100.
* **[!UICONTROL Private Feeds]** : Consultate Feed [di dati](../../../features/audience-marketplace/marketplace-private-feeds.md)privati.
* **[!UICONTROL Currently Subscribed Plan Count]** : Numero di sottoscrizioni possedute con un provider di dati.

## Feed dati privati {#private-data-feeds}

Nell' [!UICONTROL Marketplace] elenco, a volte i dati relativi a nome e caratteristiche del provider sono contrassegnati come privati. Indica un feed [di dati](../../../features/audience-marketplace/marketplace-private-feeds.md)privato. Un feed di dati privato consente ai venditori di limitare l'accesso dell'acquirente ai propri dati. I venditori possono rendere privati i propri feed quando offrono offerte speciali, sconti o quando per loro è importante avere il controllo sulla privacy e sull'accesso. In qualità di acquirente, è necessario inviare una richiesta di iscrizione al venditore se si desidera accedere a un feed privato. Per informazioni, consulta [Iscrizione a feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) dati privati.

>[!MORE_LIKE_this]
>
>* [Informazioni sulla pagina Dettagli piano in Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Sconti per gli acquirenti di dati](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

