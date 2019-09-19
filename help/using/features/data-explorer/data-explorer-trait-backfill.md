---
description: Realizzazioni delle caratteristiche di backfill per catturare i tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.
seo-description: Realizzazioni delle caratteristiche di backfill per catturare i tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.
seo-title: Realizzazioni caratteristica backfill
title: Realizzazioni caratteristica backfill
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Realizzazioni caratteristica backfill {#backfill-trait-realizations}

Realizzazioni delle caratteristiche di backfill per catturare i tipi di pubblico storici ed evitare la perdita di dati rilevanti prima di una data di creazione delle caratteristiche.

[!UICONTROL Data Explorer Trait Backfill] è una funzionalità premium che migliora l'esperienza di Audience Manager sbloccando altri casi di utilizzo. Il backfill richiede ulteriore potenza di elaborazione ed è disponibile per tutti i clienti di Audience Manager a un costo incrementale. Per ulteriori informazioni, contattate il vostro rappresentante commerciale Adobe.

Quando create caratteristiche da segnali non utilizzati, potete scegliere di recuperare le realizzazioni delle caratteristiche in un periodo di tempo specifico. [!DNL Audience Manager] acquisisce i dati storici sulle audience idonee per la nuova caratteristica e le memorizza sul profilo corrispondente. Potete visualizzarlo **[!UICONTROL Backfill Options]** nella [!UICONTROL Trait Expression] sezione del **[Generatore](../../features/traits/about-trait-builder.md)** di caratteristiche.

>[!NOTE]
>
>Potete eseguire il backfill delle realizzazioni delle caratteristiche per caratteristiche basate su regola e registrate.

Di seguito viene illustrato come eseguire il backfill delle realizzazioni delle caratteristiche:

1. Vai a [!UICONTROL Audience Data > Signals > Search] e esegui una ricerca dei segnali o usa il dashboard [dei](../../features/data-explorer/data-explorer-signals-dashboard.md) segnali per identificare i segnali da utilizzare nella nuova caratteristica.
1. Create una nuova caratteristica basata sui segnali desiderati.
1. Utilizzate **[!UICONTROL Backfill Options]** nella **[!UICONTROL Trait Expression]** sezione per selezionare l'intervallo di tempo per il quale desiderate eseguire il backfill delle realizzazioni delle caratteristiche. Gli intervalli predefiniti di recupero includono 1, 7, 14 e 30 giorni. Potete anche scegliere un intervallo di date personalizzato fino a 30 giorni.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Facoltativo) Fai clic **[!UICONTROL Estimate Realizations]** nella **[!UICONTROL Estimated Trait Realizations]** sezione per visualizzare i valori [!UICONTROL Unique Trait Realizations] e i valori stimati per la caratteristica con [!UICONTROL Total Trait Population] il backfill negli ultimi 7 giorni.

   ![stime-caratteristiche-realizzazioni](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Il recupero e la stima delle caratteristiche non sono disponibili per le caratteristiche con espressioni che utilizzano i seguenti operatori:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Crea la caratteristica.

Una volta completata la creazione della caratteristica, vedrete le relative realizzazioni con backfill incluse nelle statistiche di realizzazione.

## Latenza di recupero caratteristiche {#trait-backfilling-latency}

Le caratteristiche create di recente iniziano a catturare i tipi di pubblico due o tre ore dopo la creazione. Tuttavia, a causa dell'elevato volume di dati che [!DNL Audience Manager] esegue su base giornaliera, la popolazione con backfill non si riflette immediatamente nei [!UICONTROL Unique Trait Realizations] grafici e [!UICONTROL Total Trait Population] nei grafici.

Audience Manager aggiorna i contenuti [!UICONTROL Trait Graph] con la popolazione con backfill entro 48 ore dalla creazione delle caratteristiche.

## Limite di recupero caratteristiche {#trait-backfilling-limit}

[!UICONTROL Data Explorer] consente di eseguire il backfill fino a 50 caratteristiche al mese, con il contatore di backfill ripristinato il 1 giorno di ogni mese.

>[!NOTE]
>
>Il contingente di recupero delle caratteristiche non è riportato dai mesi precedenti. Ad esempio, se riempi 30 caratteristiche questo mese, la quota di recupero delle caratteristiche per il mese successivo viene reimpostata su 50, non su 70.

## Impatto sulla segnalazione {#reporting-impact}

Le realizzazioni con tratto con backfill si riflettono nelle [!UICONTROL Unique Trait Realizations] metriche e nelle [!UICONTROL Total Trait Population] metriche, in quanto [!DNL Audience Manager] trasforma i segnali storici in realizzazioni con caratteristiche.

Tuttavia, [!UICONTROL Trait Graph], [!UICONTROL General Reports]e [!UICONTROL Trend Reports] non vengono aggiornati retroattivamente con le metriche storiche sottoposte a backfill prima della data di creazione delle caratteristiche.