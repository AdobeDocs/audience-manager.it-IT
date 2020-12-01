---
description: Realizzazioni delle caratteristiche di backfill per catturare i tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.
seo-description: Realizzazioni delle caratteristiche di backfill per catturare i tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.
seo-title: Realizzazioni di caratteristiche di backfill
title: Realizzazioni di caratteristiche di backfill
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# Realizzazioni di caratteristiche di backfill {#backfill-trait-realizations}

Realizzazioni delle caratteristiche di backfill per catturare i tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] è una funzionalità premium che migliora l&#39;esperienza del Audience Manager  sbloccando ulteriori casi di utilizzo. Il backfill richiede ulteriore potenza di elaborazione ed è disponibile per tutti i clienti  Audience Manager a un costo incrementale. Per ulteriori informazioni, contattate il rappresentante commerciale  Adobe.

Quando create caratteristiche da segnali non utilizzati, potete scegliere di recuperare le realizzazioni delle caratteristiche in un periodo di tempo specifico. [!DNL Audience Manager] acquisisce i dati storici sulle audience idonee per la nuova caratteristica e le memorizza sul profilo corrispondente. È possibile vedere la **[!UICONTROL Backfill Options]** nella sezione [!UICONTROL Trait Expression] del **[Generatore di caratteristiche](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Potete eseguire il backfill delle realizzazioni delle caratteristiche per caratteristiche basate su regola e registrate.

Di seguito viene illustrato come eseguire il backfill delle realizzazioni delle caratteristiche:

1. Accedete a [!UICONTROL Audience Data > Signals > Search] e eseguite una ricerca dei segnali oppure utilizzate il [Dashboard dei segnali](../../features/data-explorer/data-explorer-signals-dashboard.md) per identificare i segnali da utilizzare nella nuova caratteristica.
1. Create una nuova caratteristica basata sui segnali desiderati.
1. Utilizzate **[!UICONTROL Backfill Options]** nella sezione **[!UICONTROL Trait Expression]** per selezionare l&#39;intervallo di tempo per il quale desiderate eseguire il backfill delle realizzazioni delle caratteristiche. Gli intervalli predefiniti di recupero includono 1, 7, 14 e 30 giorni. Potete anche scegliere un intervallo di date personalizzato fino a 30 giorni.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Facoltativo) Fare clic su **[!UICONTROL Estimate Realizations]** nella sezione **[!UICONTROL Estimated Trait Realizations]** per visualizzare i valori stimati [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] per la caratteristica di cui è stato eseguito il backfill negli ultimi 7 giorni.

   ![stime-caratteristiche-realizzazioni](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Il recupero e la stima delle caratteristiche non sono disponibili per le caratteristiche con espressioni che utilizzano i seguenti operatori:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Crea la caratteristica.

Una volta completata la creazione della caratteristica, vedrete le relative realizzazioni con backfill incluse nelle statistiche di realizzazione.

Guardate il video seguente per un video che illustra come tornare a capo delle caratteristiche.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latenza di recupero caratteristica {#trait-backfilling-latency}

Le caratteristiche create di recente iniziano a catturare i tipi di pubblico due o tre ore dopo la creazione. Tuttavia, a causa del grande volume di dati che [!DNL Audience Manager] esegue giornalmente, la popolazione ripiena non si riflette immediatamente nei grafici [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population].

 Audience Manager aggiorna la [!UICONTROL Trait Graph] con la popolazione ripiena entro 48 ore dalla creazione delle caratteristiche.

## Limite di recupero delle caratteristiche {#trait-backfilling-limit}

[!UICONTROL Data Explorer] consente di eseguire il backfill fino a 50 caratteristiche al mese, con il contatore di backfill ripristinato il 1 giorno di ogni mese.

>[!NOTE]
>
>Il contingente di recupero delle caratteristiche non è riportato dai mesi precedenti. Ad esempio, se riempi 30 caratteristiche questo mese, la quota di recupero delle caratteristiche per il mese successivo viene reimpostata su 50, non su 70.

## Impatto sui report {#reporting-impact}

Le realizzazioni con caratteristiche precompilate si riflettono nelle metriche [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population], in quanto [!DNL Audience Manager] trasforma i segnali storici in realizzazioni con caratteristiche.

Tuttavia, le [!UICONTROL Trait Graph], [!UICONTROL General Reports] e [!UICONTROL Trend Reports] non vengono aggiornate retroattivamente con le metriche storiche sottoposte a backfill prima della data di creazione delle caratteristiche.