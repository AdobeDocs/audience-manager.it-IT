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


# Report sulle caratteristiche giornaliere {#daily-trait-variation-report}

Questo rapporto restituisce un elenco di caratteristiche realizzate almeno 10,000 volte nei 30 giorni precedenti alle date selezionate e una deviazione standard maggiore o uguale a 1.7 in entrambe le direzioni rispetto alla stessa intervallo temporale. Il rapporto consente di valutare il modo in cui il numero di impression degli utenti unici di una caratteristica fluttua nel tempo.

>[!NOTE]
>
>Il rapporto sulla variazione giornaliera delle caratteristiche in Audience Manager rispetta i principi RBAC. Potete visualizzare solo le caratteristiche delle origini dati a cui avete accesso in base al [gruppo](/help/using/features/administration/administration-overview.md) RBAC a cui appartenete.

Deviazione standard misura la quantità di variazione o dispersione dalla media (o valore medio/previsto). Una deviazione standard bassa indica che i punti dati tendono a essere molto vicini al significato. Una deviazione standard elevata indica che i punti dati si estendono su un&#39;ampia gamma di valori.

![](assets/daily_trait_variation.png)

Utilizzate [!UICONTROL Date] l&#39;elenco per selezionare una o più date per il rapporto. Nella parte inferiore dell&#39;elenco viene visualizzato un grafico a barre con codifica colori che fornisce un rappresentante visivo dell&#39;intervallo di deviazione standard per tutte le date selezionate. La linea verticale nera indica il significato.

La colonna centrale contiene un elenco di caratteristiche, identificate da [!UICONTROL Trait ID] e [!UICONTROL Trait Name]. Fate clic su una caratteristica per accedere a una finestra di dialogo a comparsa che consente di selezionare le opzioni seguenti:

* **Mantieni solo:** Rimuove tutte le altre caratteristiche dal rapporto e visualizza i dati solo per questa caratteristica.
* **Escludi:** Rimuove questa caratteristica dal rapporto e visualizza i dati per tutte le altre caratteristiche. Potete escludere più caratteristiche.
* **Visualizza dati:** Consente di visualizzare i dati per la riga. È inoltre possibile scaricare tutte le righe come file di testo.

La [!UICONTROL Standard Deviation] colonna visualizza grafici a barre codificati con colori che mostrano la deviazione standard per ogni caratteristica sull&#39;intervallo selezionato. Le barre rosse indicano caratteristiche con deviazione standard negativa (i punti dati tendono ad essere sotto la media). Le barre verdi indicano caratteristiche con deviazione standard positiva (i punti dati tendono ad essere superiori alla significata). Passate il puntatore del mouse su una barra per visualizzare una finestra di dialogo a comparsa con ulteriori informazioni e opzioni per mantenere o escludere tale caratteristica e visualizzare ulteriori informazioni.

Nella parte inferiore del rapporto sono visualizzate le icone che consentono di esportare i dati in vari formati, ripristinare le modifiche eventualmente apportate al rapporto (ad esempio escludendo le caratteristiche), abilitare o disabilitare gli aggiornamenti automatici e aggiornare i dati del rapporto. Consultate [Icone e strumenti di rapporto descritti](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casi d&#39;uso {#use-cases}

**Esempio # 1**: Questo rapporto può essere molto utile nelle situazioni in cui si hanno caratteristiche con un livello di stagionalità elevato. Ad esempio, supponiamo che l&#39;archivio online stia testando promozioni stagionali di diversi tipi e prezzi. Sono [!DNL Audience Manager]disponibili le caratteristiche seguenti:

* `productPage == "December Promotion"`
* `price > "500"`

Supponiamo di eseguire il [!UICONTROL Daily Trait Variation] rapporto il 20 dicembre e di osservare una deviazione positiva positiva sulle caratteristiche riportate sopra negli ultimi 30 giorni. Ciò suggerisce ai visitatori di cercare i prodotti indicati nella promozione stagionale. Per capitalizzare questa tendenza, potete investire più sforzi nel targeting delle credenziali per quella specifica categoria di prodotti sui visitatori interessati.

**Esempio # 2**: Questo rapporto può facilitare l&#39;identificazione delle anomalie di targeting correlate a problemi di tag o a configurazioni sbagliate. Immagina di aver definito le caratteristiche seguenti in base alle categorie del negozio online:

* `productPage == "smartphones"`

A causa di una riconfigurazione dello store, la pagina smartphone viene suddivisa in più pagine, in base ai nomi dei marchi. Tuttavia, si dimentica di aggiornare le caratteristiche definite in [!DNL Audience Manager].

Un mese dopo, esegui [!UICONTROL Daily Trait Variation] il rapporto e osserva una notevole deviazione negativa sulla `productPage == "smartphones"` caratteristica, anche se il numero del visitatore è aumentato in base all&#39;analisi del sito. In base a queste informazioni, non hai aggiornato le caratteristiche per [!DNL Audience Manager] le nuove pagine di prodotti, per cui sai che devi creare le caratteristiche seguenti:

* Productpage = = &quot;samsung&quot;
* Productpage = = &quot;apple&quot;
* Productpage = = &quot;huawei&quot;

In tal modo, visualizzerai il pubblico idoneo per le caratteristiche appena create.
