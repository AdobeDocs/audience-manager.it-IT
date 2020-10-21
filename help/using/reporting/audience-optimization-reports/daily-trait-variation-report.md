---
description: Questo rapporto restituisce un elenco di caratteristiche che sono state realizzate almeno 10.000 volte nei 30 giorni precedenti le date selezionate e hanno una deviazione standard maggiore o uguale a 1,7 in entrambe le direzioni nello stesso intervallo di tempo. Il rapporto consente di valutare il modo in cui il numero di impression di utenti univoci in una caratteristica varia nel tempo.
seo-description: Questo rapporto restituisce un elenco di caratteristiche che sono state realizzate almeno 10.000 volte nei 30 giorni precedenti le date selezionate e hanno una deviazione standard maggiore o uguale a 1,7 in entrambe le direzioni nello stesso intervallo di tempo. Il rapporto consente di valutare il modo in cui il numero di impression di utenti univoci in una caratteristica varia nel tempo.
seo-title: Rapporto sulla variazione giornaliera delle caratteristiche
solution: Audience Manager
title: Rapporto sulla variazione giornaliera delle caratteristiche
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---


# Rapporto sulla variazione giornaliera delle caratteristiche {#daily-trait-variation-report}

Questo rapporto restituisce un elenco di caratteristiche che sono state realizzate almeno 10.000 volte nei 30 giorni precedenti le date selezionate e hanno una deviazione standard maggiore o uguale a 1,7 in entrambe le direzioni nello stesso intervallo di tempo. Il rapporto consente di valutare il modo in cui il numero di impression di utenti univoci in una caratteristica varia nel tempo.

>[!NOTE]
>
>Il report Daily Trait Variation (Variazione caratteristica giornaliera) nel Audience Manager  aderisce ai principi RBAC. Potete visualizzare solo le caratteristiche provenienti da origini dati a cui avete accesso in base al gruppo [di utenti](/help/using/features/administration/administration-overview.md) RBAC a cui appartenete.

La deviazione standard misura la quantità di variazione o dispersione dalla media (o dal valore medio/previsto). Una deviazione standard bassa indica che i punti dati tendono ad essere molto vicini alla media. Una deviazione standard elevata indica che i punti dati sono distribuiti su un ampio intervallo di valori.

![](assets/daily_trait_variation.png)

Utilizza l’ [!UICONTROL Date] elenco per selezionare una o più date per il rapporto. Nella parte inferiore dell’elenco viene visualizzato un grafico a barre con colori che rappresenta visivamente l’intervallo di deviazione standard per tutte le caratteristiche di tutte le date selezionate. La linea verticale nera indica la media.

La colonna centrale contiene un elenco di caratteristiche, identificate da [!UICONTROL Trait ID] e [!UICONTROL Trait Name]. Fate clic su una caratteristica per accedere a una finestra di dialogo a comparsa che consente di selezionare una delle seguenti opzioni:

* **Mantieni solo:** Rimuove tutte le altre caratteristiche dal rapporto e visualizza i dati solo per questa caratteristica.
* **Escludi:** Rimuove questa caratteristica dal rapporto e visualizza i dati per tutte le altre caratteristiche. Potete escludere più caratteristiche.
* **Visualizza dati:** Consente di visualizzare i dati per la riga. È inoltre possibile scaricare tutte le righe come file di testo.

Nella [!UICONTROL Standard Deviation] colonna sono visualizzati grafici a barre con colori che mostrano la deviazione standard per ogni caratteristica nell’intervallo selezionato. Le barre rosse indicano caratteristiche con una deviazione standard negativa (i punti dati tendono ad essere al di sotto della media). Le barre verdi indicano caratteristiche con una deviazione standard positiva (i punti dati tendono ad essere al di sopra della media). Passate il puntatore del mouse su una barra per visualizzare una finestra di dialogo a comparsa con ulteriori informazioni e opzioni per mantenere o escludere tale caratteristica e visualizzare ulteriori informazioni.

Nella parte inferiore del rapporto sono visualizzate delle icone che consentono di esportare i dati in vari formati, ripristinare eventuali modifiche apportate al rapporto (ad esempio escludendo le caratteristiche), attivare o disattivare gli aggiornamenti automatici e aggiornare i dati del rapporto. Consultate [Icone e strumenti del rapporto spiegati](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Casi d&#39;uso {#use-cases}

**Esempio n. 1**: questo rapporto può essere molto utile in situazioni in cui hai caratteristiche con un alto livello di stagionalità. Ad esempio, supponiamo che il vostro negozio online stia testando promozioni stagionali di vari tipi e prezzi. Sono state definite le seguenti caratteristiche in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Supponiamo che eseguiate il [!UICONTROL Daily Trait Variation] rapporto il 20 dicembre e che notiate una deviazione positiva significativa sulle caratteristiche sopra menzionate negli ultimi 30 giorni. Questo può suggerire che i visitatori stiano cercando i prodotti indicati nella promozione stagionale. Per sfruttare questa tendenza, potete quindi investire di più nel targeting di creativi per quella specifica categoria di prodotti per i visitatori che sono interessati a loro.

**Esempio n. 2**: questo rapporto può essere utile per identificare le anomalie di targeting relative a problemi di tag o configurazioni errate delle caratteristiche. Immaginate di aver definito la seguente caratteristica in base alle categorie del vostro negozio online:

* `productPage == "smartphones"`

A causa di una riconfigurazione dello store, la pagina degli smartphone viene suddivisa in più pagine, in base ai nomi dei marchi. Tuttavia, si dimentica di aggiornare le caratteristiche definite in [!DNL Audience Manager].

Un mese dopo, esegui il [!UICONTROL Daily Trait Variation] rapporto e noti un&#39;ampia deviazione negativa sulla `productPage == "smartphones"` caratteristica, anche se il numero del visitatore è aumentato, in base all&#39;analisi del sito. In base a queste informazioni, ti rendi conto che non hai aggiornato le caratteristiche [!DNL Audience Manager] per le nuove pagine di prodotto, quindi sai che devi creare le caratteristiche seguenti:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Una volta effettuata questa operazione, il pubblico sarà in grado di soddisfare le caratteristiche appena create.
