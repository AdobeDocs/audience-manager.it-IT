---
description: Questo rapporto restituisce un elenco di caratteristiche che sono state realizzate almeno 10.000 volte nei 30 giorni precedenti la data o le date selezionate e hanno una deviazione standard maggiore o uguale a 1,7 in entrambe le direzioni nello stesso intervallo di tempo. Il rapporto ti aiuta a valutare il modo in cui il numero di impression provenienti da utenti univoci in una caratteristica varia nel tempo.
seo-description: Questo rapporto restituisce un elenco di caratteristiche che sono state realizzate almeno 10.000 volte nei 30 giorni precedenti la data o le date selezionate e hanno una deviazione standard maggiore o uguale a 1,7 in entrambe le direzioni nello stesso intervallo di tempo. Il rapporto ti aiuta a valutare il modo in cui il numero di impression provenienti da utenti univoci in una caratteristica varia nel tempo.
seo-title: Rapporto sulla variazione giornaliera delle caratteristiche
solution: Audience Manager
title: Rapporto sulla variazione giornaliera delle caratteristiche
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---

# Rapporto sulla variazione giornaliera delle caratteristiche {#daily-trait-variation-report}

Questo rapporto restituisce un elenco di caratteristiche che sono state realizzate almeno 10.000 volte nei 30 giorni precedenti la data o le date selezionate e hanno una deviazione standard maggiore o uguale a 1,7 in entrambe le direzioni nello stesso intervallo di tempo. Il rapporto ti aiuta a valutare il modo in cui il numero di impression provenienti da utenti univoci in una caratteristica varia nel tempo.

>[!NOTE]
>
>Il rapporto Variazione caratteristiche giornaliera in Audience Manager è conforme ai principi RBAC. Puoi visualizzare solo le caratteristiche delle origini dati a cui hai accesso in base al [Gruppo di utenti RBAC](/help/using/features/administration/administration-overview.md) a cui appartieni.

La deviazione standard misura la quantità di variazione o dispersione dalla media (o valore medio/previsto). Una deviazione standard bassa indica che i punti dati tendono a essere molto vicini alla media. Una deviazione standard elevata indica che i punti dati sono distribuiti su un ampio intervallo di valori.

![](assets/daily_trait_variation.png)

Utilizza l’elenco [!UICONTROL Date] per selezionare una o più date per il rapporto. Nella parte inferiore dell’elenco viene visualizzato un grafico a barre con codice a colori che rappresenta visivamente l’intervallo di deviazione standard per tutte le caratteristiche in tutte le date selezionate. La linea verticale nera indica la media.

La colonna centrale contiene un elenco di caratteristiche, identificate da [!UICONTROL Trait ID] e [!UICONTROL Trait Name]. Fai clic su una caratteristica per accedere a una finestra di dialogo a comparsa che consente di selezionare una delle seguenti opzioni:

* **Mantieni solo:** rimuove dal rapporto tutte le altre caratteristiche e visualizza i dati solo per questa caratteristica.
* **Escludi:** rimuove questa caratteristica dal rapporto e visualizza i dati per tutte le altre caratteristiche. È possibile escludere più caratteristiche.
* **Visualizza dati:** ti consente di visualizzare i dati per quella riga. È inoltre possibile scaricare tutte le righe come file di testo.

La colonna [!UICONTROL Standard Deviation] visualizza grafici a barre con codice a colori che mostrano la deviazione standard per ogni caratteristica nell’intervallo selezionato. Le barre rosse indicano le caratteristiche con una deviazione standard negativa (i punti dati tendono a essere inferiori alla media). Le barre verdi indicano le caratteristiche con una deviazione standard positiva (i punti dati tendono ad essere al di sopra della media). Passa il cursore sopra una barra per visualizzare una finestra di dialogo a comparsa con ulteriori informazioni e opzioni per mantenere o escludere tale caratteristica e visualizzare ulteriori informazioni.

Le icone vengono visualizzate nella parte inferiore del rapporto che consentono di esportare i dati in vari formati, annullare eventuali modifiche apportate al rapporto (ad esempio l’esclusione delle caratteristiche), abilitare o disabilitare gli aggiornamenti automatici e aggiornare i dati del rapporto. Consultare [Spiegazione di icone e strumenti dei rapporti](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casi d&#39;uso {#use-cases}

**Esempio n.1**: questo rapporto può essere molto utile in situazioni in cui hai caratteristiche con un alto livello di stagionalità. Ad esempio, supponiamo che il tuo negozio online stia testando promozioni stagionali di vari tipi e prezzi. Hai le seguenti caratteristiche definite in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Supponiamo di eseguire il rapporto [!UICONTROL Daily Trait Variation] del 20 dicembre e di notare una deviazione positiva significativa sulle caratteristiche di cui sopra negli ultimi 30 giorni. Questo può suggerire ai visitatori di cercare i prodotti menzionati nella promozione stagionale. Per sfruttare questa tendenza, puoi quindi investire di più nel targeting di creativi per quella specifica categoria di prodotti per i visitatori che sono interessati a loro.

**Esempio n.2**: questo rapporto può essere utile per identificare le anomalie di targeting relative a problemi di assegnazione tag o configurazioni errate delle caratteristiche. Immagina di aver definito la seguente caratteristica in base alle categorie del tuo negozio online:

* `productPage == "smartphones"`

A causa di una riconfigurazione del tuo negozio, stai suddividendo la pagina smartphone in più pagine, in base ai nomi dei marchi. Tuttavia, dimentichi di aggiornare le caratteristiche definite in [!DNL Audience Manager].

Un mese dopo, esegui il rapporto [!UICONTROL Daily Trait Variation] e noti una deviazione negativa significativa sulla caratteristica `productPage == "smartphones"`, anche se il numero di visitatori è aumentato, in base all’analisi del sito. In base a queste informazioni, ti rendi conto di non aver aggiornato le caratteristiche in [!DNL Audience Manager] per le nuove pagine di prodotto, quindi sai che devi creare le seguenti caratteristiche:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Una volta fatto questo, vedrai il tuo pubblico qualificarsi per le caratteristiche appena create.
