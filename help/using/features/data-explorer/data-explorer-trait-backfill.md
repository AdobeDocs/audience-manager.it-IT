---
description: Realizza le caratteristiche delle caratteristiche per acquisire audience storiche ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.
seo-description: Realizza le caratteristiche delle caratteristiche per acquisire audience storiche ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.
seo-title: Realizzazioni caratteristica backfill
title: Realizzazioni caratteristica backfill
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Backfill Trait Realizations {#backfill-trait-realizations}

Realizza le caratteristiche delle caratteristiche per acquisire audience storiche ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.

[!UICONTROL Data Explorer Trait Backfill] è una funzionalità premium che migliora l'esperienza Audience Manager sbloccando altri casi d'uso. Il backfill richiede ulteriori capacità di elaborazione ed è disponibile per tutti i clienti di Audience Manager a un costo incrementale. Per ulteriori informazioni, contattate il rappresentante vendite Adobe.

Quando create tratti da segnali inutilizzati, potete scegliere di retrocompilare le caratteristiche delle caratteristiche in un determinato periodo di tempo. [!DNL Audience Manager] acquisisce i dati storici sui tipi di pubblico idonei per la nuova caratteristica e li memorizza sul profilo corrispondente. You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Potete riempire le realizzazioni delle caratteristiche per le caratteristiche basate su regole e caricate.

Ecco come riempire le realizzazioni delle caratteristiche:

1. Go to [!UICONTROL Audience Data > Signals > Search] amd run a Signals Search or use the [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) to identify the signals to use in the new trait.
1. Create una nuova caratteristica basata sui segnali desiderati.
1. Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. Intervalli di backfill predefiniti includono 1, 7, 14 e 30 giorni. Puoi anche scegliere un intervallo di date personalizzato fino a 30 giorni.
   ![](assets/signals-trait-backfill.png)
1. (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >Le caratteristiche e la stima delle caratteristiche non sono disponibili per le caratteristiche con espressioni che utilizzano i seguenti operatori:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Create la caratteristica.

Una volta terminata la creazione della caratteristica, le relative rappresentazioni rientrate saranno incluse nelle statistiche di stabilità.

## Trait Backfilling Latency {#trait-backfilling-latency}

Le caratteristiche appena create iniziano a acquisire l'audience da due a tre ore dopo la creazione. However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] consente di ripristinare fino a 50 caratteristiche al mese, con il contatore di backfill che viene reimpostato il giorno di ogni mese.

>[!NOTE]
>
>La quota di backfill trait non viene aggiornata dai mesi precedenti. Ad esempio, se riutilizzate 30 caratteristiche questo mese, la quota di backfill per il mese successivo viene reimpostata su 50, non su 70.

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date.