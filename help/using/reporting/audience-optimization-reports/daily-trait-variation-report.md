---
description: Questo rapporto restituisce un elenco di caratteristiche realizzate almeno 10,000 volte nei 30 giorni precedenti alle date selezionate e una deviazione standard maggiore o uguale a 1.7 in entrambe le direzioni rispetto alla stessa intervallo temporale. Il rapporto consente di valutare il modo in cui il numero di impression degli utenti unici di una caratteristica fluttua nel tempo.
seo-description: Questo rapporto restituisce un elenco di caratteristiche realizzate almeno 10,000 volte nei 30 giorni precedenti alle date selezionate e una deviazione standard maggiore o uguale a 1.7 in entrambe le direzioni rispetto alla stessa intervallo temporale. Il rapporto consente di valutare il modo in cui il numero di impression degli utenti unici di una caratteristica fluttua nel tempo.
seo-title: Report sulle caratteristiche giornaliere
solution: Audience Manager
title: Report sulle caratteristiche giornaliere
uuid: 4 e 82 bb 17-d 447-4 ed 1-a 4 fc-e 15 b 0 f 1 b 47 f 0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Daily Trait Variation Report {#daily-trait-variation-report}

Questo rapporto restituisce un elenco di caratteristiche realizzate almeno 10,000 volte nei 30 giorni precedenti alle date selezionate e una deviazione standard maggiore o uguale a 1.7 in entrambe le direzioni rispetto alla stessa intervallo temporale. Il rapporto consente di valutare il modo in cui il numero di impression degli utenti unici di una caratteristica fluttua nel tempo.

>[!NOTE]
>
>Il rapporto sulla variazione giornaliera delle caratteristiche in Audience Manager rispetta i principi RBAC. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

Deviazione standard misura la quantità di variazione o dispersione dalla media (o valore medio/previsto). Una deviazione standard bassa indica che i punti dati tendono a essere molto vicini al significato. Una deviazione standard elevata indica che i punti dati si estendono su un'ampia gamma di valori.

![](assets/daily_trait_variation.png)

Use the [!UICONTROL Date] list to select one or more dates for your report. Nella parte inferiore dell'elenco viene visualizzato un grafico a barre con codifica colori che fornisce un rappresentante visivo dell'intervallo di deviazione standard per tutte le date selezionate. La linea verticale nera indica il significato.

The middle column contains a list of traits, identified by [!UICONTROL Trait ID] and [!UICONTROL Trait Name]. Fate clic su una caratteristica per accedere a una finestra di dialogo a comparsa che consente di selezionare le opzioni seguenti:

* **Mantieni solo:** Rimuove tutte le altre caratteristiche dal rapporto e visualizza i dati solo per questa caratteristica.
* **Escludi:** Rimuove questa caratteristica dal rapporto e visualizza i dati per tutte le altre caratteristiche. Potete escludere più caratteristiche.
* **Visualizza dati:** Consente di visualizzare i dati per la riga. È inoltre possibile scaricare tutte le righe come file di testo.

The [!UICONTROL Standard Deviation] column displays color-coded bar charts that display the standard deviation for each trait over the selected interval. Le barre rosse indicano caratteristiche con deviazione standard negativa (i punti dati tendono ad essere sotto la media). Le barre verdi indicano caratteristiche con deviazione standard positiva (i punti dati tendono ad essere superiori alla significata). Passate il puntatore del mouse su una barra per visualizzare una finestra di dialogo a comparsa con ulteriori informazioni e opzioni per mantenere o escludere tale caratteristica e visualizzare ulteriori informazioni.

Nella parte inferiore del rapporto sono visualizzate le icone che consentono di esportare i dati in vari formati, ripristinare le modifiche eventualmente apportate al rapporto (ad esempio escludendo le caratteristiche), abilitare o disabilitare gli aggiornamenti automatici e aggiornare i dati del rapporto. See [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casi d'uso {#use-cases}

**Esempio # 1**: Questo rapporto può essere molto utile nelle situazioni in cui si hanno caratteristiche con un livello di stagionalità elevato. Ad esempio, supponiamo che l'archivio online stia testando promozioni stagionali di diversi tipi e prezzi. You have the following traits defined in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Say you run the [!UICONTROL Daily Trait Variation] report on the 20th of December and you notice a solid positive deviation on the above mentioned traits in the past 30 days. Ciò suggerisce ai visitatori di cercare i prodotti indicati nella promozione stagionale. Per capitalizzare questa tendenza, potete investire più sforzi nel targeting delle credenziali per quella specifica categoria di prodotti sui visitatori interessati.

**Esempio # 2**: Questo rapporto può facilitare l'identificazione delle anomalie di targeting correlate a problemi di tag o a configurazioni sbagliate. Immagina di aver definito le caratteristiche seguenti in base alle categorie del negozio online:

* `productPage == "smartphones"`

A causa di una riconfigurazione dello store, la pagina smartphone viene suddivisa in più pagine, in base ai nomi dei marchi. However, you forget to update the traits defined in [!DNL Audience Manager].

One month later, you run the [!UICONTROL Daily Trait Variation] report and notice a large negative deviation on the `productPage == "smartphones"` trait, although your visitor number has increased, according to your site analytics. Based on this information, you realize that you haven't updated the traits in [!DNL Audience Manager] for your new product pages, so you know that you need to create the following traits:

* Productpage = = "samsung"
* Productpage = = "apple"
* Productpage = = "huawei"

In tal modo, visualizzerai il pubblico idoneo per le caratteristiche appena create.
