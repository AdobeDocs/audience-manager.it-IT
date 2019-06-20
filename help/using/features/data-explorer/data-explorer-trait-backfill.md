---
description: Realizza le caratteristiche delle caratteristiche per acquisire audience storiche ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.
seo-description: Realizza le caratteristiche delle caratteristiche per acquisire audience storiche ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.
seo-title: Realizzazioni caratteristica backfill
title: Realizzazioni caratteristica backfill
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Realizzazioni caratteristica backfill {#backfill-trait-realizations}

Realizza le caratteristiche delle caratteristiche per acquisire audience storiche ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.

[!UICONTROL Data Explorer Trait Backfill] è una funzionalità premium che migliora l&#39;esperienza Audience Manager sbloccando altri casi d&#39;uso. Il backfill richiede ulteriori capacità di elaborazione ed è disponibile per tutti i clienti di Audience Manager a un costo incrementale. Per ulteriori informazioni, contattate il rappresentante vendite Adobe.

Quando create tratti da segnali inutilizzati, potete scegliere di retrocompilare le caratteristiche delle caratteristiche in un determinato periodo di tempo. [!DNL Audience Manager] acquisisce i dati storici sui tipi di pubblico idonei per la nuova caratteristica e li memorizza sul profilo corrispondente. Potete visualizzare la **[!UICONTROL Backfill Options]**[!UICONTROL Trait Expression] sezione del Generatore **[di caratteristiche](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Potete riempire le realizzazioni delle caratteristiche per le caratteristiche basate su regole e caricate.

Ecco come riempire le realizzazioni delle caratteristiche:

1. Passate da [!UICONTROL Audience Data > Signals > Search] amd a un&#39;opzione di ricerca o utilizzate il [dashboard Segnali](../../features/data-explorer/data-explorer-signals-dashboard.md) per identificare i segnali da utilizzare nel nuovo tratto.
1. Create una nuova caratteristica basata sui segnali desiderati.
1. Utilizzate la **[!UICONTROL Backfill Options]** sezione nella **[!UICONTROL Trait Expression]** sezione per selezionare l&#39;intervallo di tempo per il quale desiderate riempire le caratteristiche delle caratteristiche. Intervalli di backfill predefiniti includono 1, 7, 14 e 30 giorni. Puoi anche scegliere un intervallo di date personalizzato fino a 30 giorni.
   ![](assets/signals-trait-backfill.png)
1. (Facoltativo) Fai clic **[!UICONTROL Estimate Realizations]** nella **[!UICONTROL Estimated Trait Realizations]** sezione per visualizzare i valori stimati [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] i valori per il tratto con riempimento negli ultimi 7 giorni.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >Le caratteristiche e la stima delle caratteristiche non sono disponibili per le caratteristiche con espressioni che utilizzano i seguenti operatori:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Create la caratteristica.

Una volta terminata la creazione della caratteristica, le relative rappresentazioni rientrate saranno incluse nelle statistiche di stabilità.

## Latenza backfill {#trait-backfilling-latency}

Le caratteristiche appena create iniziano a acquisire l&#39;audience da due a tre ore dopo la creazione. Tuttavia, a causa dell&#39;elevato volume di dati [!DNL Audience Manager] che avvengono su base giornaliera, la popolazione smartinata non si riflette immediatamente nei grafici [!UICONTROL Unique Trait Realizations] e nei [!UICONTROL Total Trait Population] grafici.

Audience Manager aggiorna la [!UICONTROL Trait Graph] popolazione con sottotitoli entro 48 ore dalla creazione delle caratteristiche.

## Limite backfill caratteristica {#trait-backfilling-limit}

[!UICONTROL Data Explorer] consente di ripristinare fino a 50 caratteristiche al mese, con il contatore di backfill che viene reimpostato il giorno di ogni mese.

>[!NOTE]
>
>La quota di backfill trait non viene aggiornata dai mesi precedenti. Ad esempio, se riutilizzate 30 caratteristiche questo mese, la quota di backfill per il mese successivo viene reimpostata su 50, non su 70.

## Impatto sui rapporti {#reporting-impact}

Le caratteristiche di caratteristica backched si riflettono nelle [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population] metriche, in quanto [!DNL Audience Manager] converte i segnali storici nelle realizzazioni delle caratteristiche.

Tuttavia, l &#39; [!UICONTROL Trait Graph], [!UICONTROL General Reports]e non [!UICONTROL Trend Reports] vengono aggiornati retroattivamente con le metriche storiche completate prima della data di creazione delle caratteristiche.