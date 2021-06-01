---
description: Realizzazioni di caratteristiche di backfill per acquisire tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione di caratteristiche.
seo-description: Realizzazioni di caratteristiche di backfill per acquisire tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione di caratteristiche.
seo-title: Realizzazioni di caratteristiche di backfill
title: Realizzazioni di caratteristiche di backfill
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: 'Data Explorer '
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# Realizzazioni di caratteristiche di backfill {#backfill-trait-realizations}

Realizzazioni di caratteristiche di backfill per acquisire tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione di caratteristiche.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] è una funzionalità premium che migliora l’esperienza di Audience Manager sbloccando ulteriori casi di utilizzo. Il backfill richiede una potenza di elaborazione aggiuntiva ed è disponibile per tutti i clienti di Audience Manager a un costo incrementale. Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe.

Quando crei caratteristiche da segnali non utilizzati, puoi scegliere di retrocompilare le realizzazioni delle caratteristiche per un periodo di tempo specifico. [!DNL Audience Manager] acquisisce i dati storici sui tipi di pubblico idonei per la nuova caratteristica e li memorizza sul profilo corrispondente. Puoi vedere **[!UICONTROL Backfill Options]** nella sezione [!UICONTROL Trait Expression] del **[Generatore di caratteristiche](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Puoi retrocompilare le realizzazioni di caratteristiche per caratteristiche basate su regole e onboarded.

Ecco come retrocompilare le realizzazioni delle caratteristiche:

1. Vai a [!UICONTROL Audience Data > Signals > Search] e esegui una ricerca di segnali o utilizza il [dashboard di segnali](../../features/data-explorer/data-explorer-signals-dashboard.md) per identificare i segnali da utilizzare nella nuova caratteristica.
1. Crea una nuova caratteristica in base ai segnali desiderati.
1. Utilizza il **[!UICONTROL Backfill Options]** nella sezione **[!UICONTROL Trait Expression]** per selezionare l’intervallo di tempo per il quale vuoi retrocompilare le realizzazioni delle caratteristiche. Gli intervalli predefiniti di backfill includono 1, 7, 14 e 30 giorni. Puoi anche scegliere un intervallo di date personalizzato fino a 30 giorni.

   ![caratteristica-backfill](assets/signals-trait-backfill.png)

1. (Facoltativo) Fai clic su **[!UICONTROL Estimate Realizations]** nella sezione **[!UICONTROL Estimated Trait Realizations]** per visualizzare i valori stimati [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] per la caratteristica di cui è stato eseguito il backfill negli ultimi 7 giorni.

   ![stime-caratteristiche-realizzazioni](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Il recupero e la stima delle caratteristiche non sono disponibili per le caratteristiche con espressioni che utilizzano i seguenti operatori:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Crea la caratteristica.

Una volta completata la creazione della caratteristica, potrai vedere le sue realizzazioni con backfill incluse nelle statistiche di realizzazione.

Guarda il video seguente per un video che illustra come retrocompilare le caratteristiche.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latenza di recupero delle caratteristiche {#trait-backfilling-latency}

Le caratteristiche create di recente iniziano a catturare i tipi di pubblico due o tre ore dopo la creazione. Tuttavia, a causa del grande volume di dati che [!DNL Audience Manager] esegue su base giornaliera, la popolazione precompilata non si riflette immediatamente nei grafici [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population].

L’Audience Manager aggiorna il [!UICONTROL Trait Graph] con la popolazione precompilata entro 48 ore dalla creazione della caratteristica.

## Limite di recupero delle caratteristiche {#trait-backfilling-limit}

[!UICONTROL Data Explorer] consente di eseguire il backfill fino a 50 caratteristiche al mese, con il contatore di backfill ripristinato il 1 giorno di ogni mese.

>[!NOTE]
>
>La quota di recupero delle caratteristiche non viene riportata dai mesi precedenti. Ad esempio, se riempi di nuovo 30 caratteristiche questo mese, la quota di recupero delle caratteristiche per il mese successivo viene reimpostata su 50, non su 70.

## Impatto sul reporting {#reporting-impact}

Le realizzazioni con caratteristiche retroriempite si riflettono nelle metriche [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population], in quanto [!DNL Audience Manager] trasforma i segnali storici in realizzazioni di caratteristiche.

Tuttavia, i valori [!UICONTROL Trait Graph], [!UICONTROL General Reports] e [!UICONTROL Trend Reports] non vengono aggiornati retroattivamente con le metriche storiche precedentemente compilate prima della data di creazione delle caratteristiche.
