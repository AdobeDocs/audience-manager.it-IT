---
description: Questo rapporto restituisce un elenco di caratteristiche che sono state realizzate almeno 10.000 volte nei 30 giorni precedenti le date selezionate e con una deviazione standard maggiore o uguale a 1,7 in entrambe le direzioni nello stesso intervallo di tempo. Il rapporto consente di valutare la variazione nel tempo del numero di impression da parte di utenti univoci in una caratteristica.
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Rapporto sulla variazione giornaliera delle caratteristiche
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# Rapporto sulla variazione giornaliera delle caratteristiche {#daily-trait-variation-report}

Questo rapporto restituisce un elenco di caratteristiche che sono state realizzate almeno 10.000 volte nei 30 giorni precedenti le date selezionate e con una deviazione standard maggiore o uguale a 1,7 in entrambe le direzioni nello stesso intervallo di tempo. Il rapporto consente di valutare la variazione nel tempo del numero di impression da parte di utenti univoci in una caratteristica.

>[!NOTE]
>
>Il rapporto Variazione caratteristiche giornaliero in Audience Manager è conforme ai principi RBAC. Puoi visualizzare solo le caratteristiche dalle origini dati a cui hai accesso in base al [gruppo di utenti RBAC](/help/using/features/administration/administration-overview.md) a cui appartieni.

La deviazione standard misura l&#39;entità della variazione o della dispersione rispetto alla media (o al valore medio/atteso). Una deviazione standard bassa indica che i punti dati tendono a essere molto vicini alla media. Una deviazione standard elevata indica che i punti dati sono distribuiti su un ampio intervallo di valori.

![](assets/daily_trait_variation.png)

Utilizzare l&#39;elenco [!UICONTROL Date] per selezionare una o più date per il report. Nella parte inferiore dell&#39;elenco viene visualizzato un grafico a barre con colori che fornisce un indicatore visivo dell&#39;intervallo di deviazione standard per tutte le caratteristiche in tutte le date selezionate. La linea verticale nera indica la media.

La colonna centrale contiene un elenco di caratteristiche identificate da [!UICONTROL Trait ID] e [!UICONTROL Trait Name]. Fate clic su una caratteristica per accedere a una finestra di dialogo a comparsa che consente di selezionare una delle seguenti opzioni:

* **Mantieni solo:** rimuove tutte le altre caratteristiche dal report e visualizza i dati solo per questa caratteristica.
* **Escludi:** rimuove questa caratteristica dal report e visualizza i dati per tutte le altre caratteristiche. Puoi escludere più caratteristiche.
* **Visualizza dati:** consente di visualizzare i dati per tale riga. È inoltre possibile scaricare tutte le righe come file di testo.

Nella colonna [!UICONTROL Standard Deviation] sono visualizzati grafici a barre con colori che visualizzano la deviazione standard per ogni caratteristica nell&#39;intervallo selezionato. Le barre rosse indicano caratteristiche con una deviazione standard negativa (i punti di dati tendono a essere al di sotto della media). Le barre verdi indicano caratteristiche con una deviazione standard positiva (i punti di dati tendono a essere al di sopra della media). Passa il mouse su una barra per visualizzare una finestra di dialogo a comparsa con ulteriori informazioni e opzioni per mantenere o escludere tale caratteristica e visualizzare ulteriori informazioni.

Nella parte inferiore del rapporto vengono visualizzate le icone che consentono di esportare i dati in vari formati, ripristinare eventuali modifiche apportate al rapporto (ad esempio escludendo le caratteristiche), abilitare o disabilitare gli aggiornamenti automatici e aggiornare i dati del rapporto. Vedi [Icone e strumenti del report](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casi d&#39;uso {#use-cases}

**Esempio #1**: questo rapporto può essere molto utile in situazioni in cui si hanno caratteristiche con un elevato livello di stagionalità. Ad esempio, supponiamo che il tuo negozio online stia testando promozioni stagionali di vari tipi e prezzi. In [!DNL Audience Manager] sono definite le seguenti caratteristiche:

* `productPage == "December Promotion"`
* `price > "500"`

Si supponga di eseguire il report [!UICONTROL Daily Trait Variation] il 20 dicembre e di notare una deviazione positiva solida sulle caratteristiche sopra indicate negli ultimi 30 giorni. Questo può suggerire che i visitatori sono alla ricerca dei prodotti menzionati nella tua promozione stagionale. Per sfruttare questa tendenza, puoi quindi investire più impegno nel targeting dei creativi per quella specifica categoria di prodotto sui visitatori che sono interessati a loro.

**Esempio #2**: questo rapporto può aiutarti a identificare le anomalie di targeting relative ai problemi di assegnazione tag o a configurazioni errate delle caratteristiche. Immagina di aver definito la seguente caratteristica in base alle categorie del tuo negozio online:

* `productPage == "smartphones"`

A causa di una riconfigurazione del tuo negozio, stai suddividendo la pagina degli smartphone in più pagine, in base ai nomi dei marchi. Tuttavia, si dimentica di aggiornare le caratteristiche definite in [!DNL Audience Manager].

Un mese dopo, esegui il rapporto [!UICONTROL Daily Trait Variation] e noti una deviazione negativa elevata sulla caratteristica `productPage == "smartphones"`, anche se il numero di visitatori è aumentato, in base all&#39;analisi del sito. In base a queste informazioni, ti rendi conto che non hai aggiornato le caratteristiche in [!DNL Audience Manager] per le nuove pagine di prodotti, quindi sai che devi creare le caratteristiche seguenti:

* productPage == samsung
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Dopo aver eseguito questa operazione, vedrai il pubblico che si qualifica per le caratteristiche appena create.
