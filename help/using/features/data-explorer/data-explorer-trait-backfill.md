---
description: Recupera le realizzazioni delle caratteristiche per acquisire pubblici storici ed evitare la perdita di dati rilevanti prima della data di creazione di una caratteristica.
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: Realizzazioni di caratteristiche di backfill
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 1%

---

# Realizzazioni di caratteristiche di backfill {#backfill-trait-realizations}

Recupera le realizzazioni delle caratteristiche per acquisire pubblici storici ed evitare la perdita di dati rilevanti prima della data di creazione di una caratteristica.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] è una funzionalità premium che migliora l’esperienza di Audience Manager sbloccando casi d’uso aggiuntivi. Il backfill richiede una potenza di elaborazione aggiuntiva ed è disponibile per tutti i clienti Audienci Manager a un costo incrementale. Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe.

Quando crei caratteristiche da segnali non utilizzati, puoi scegliere di eseguire la retrocompilazione delle realizzazioni delle caratteristiche in un periodo di tempo specifico. [!DNL Audience Manager] acquisisce i dati storici sui tipi di pubblico idonei per la nuova caratteristica e li memorizza nel profilo corrispondente. È possibile visualizzare **[!UICONTROL Backfill Options]** nel [!UICONTROL Trait Expression] sezione del **[Generatore di caratteristiche](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Puoi retrocompilare le realizzazioni delle caratteristiche per le caratteristiche basate su regole e onboarded.

Ecco come retrocompilare le realizzazioni delle caratteristiche:

1. Vai a [!UICONTROL Audience Data > Signals > Search] è stato modificato l’esecuzione di una ricerca di segnali o l’utilizzo di [Dashboard dei segnali](../../features/data-explorer/data-explorer-signals-dashboard.md) per identificare i segnali da utilizzare nella nuova caratteristica.
1. Crea una nuova caratteristica in base ai segnali desiderati.
1. Utilizza il **[!UICONTROL Backfill Options]** nel **[!UICONTROL Trait Expression]** per selezionare l&#39;intervallo di tempo per il quale si desidera eseguire la retrocompilazione delle realizzazioni delle caratteristiche. Gli intervalli di backfill predefiniti includono 1, 7, 14 e 30 giorni. Puoi anche scegliere un intervallo di date personalizzato fino a 30 giorni.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Facoltativo) Fai clic su **[!UICONTROL Estimate Realizations]** nel **[!UICONTROL Estimated Trait Realizations]** sezione per visualizzare la stima [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] valori per la caratteristica backfill negli ultimi 7 giorni.

   ![stima-caratteristiche-realizzazioni](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Il backfill e la stima delle caratteristiche non sono disponibili per le caratteristiche con espressioni che utilizzano i seguenti operatori:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Crea la caratteristica.

Una volta completata la creazione della caratteristica, le realizzazioni retrocompilate verranno incluse nelle statistiche di realizzazione.

Guarda il video seguente per un video che illustra come retrocompilare le caratteristiche.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latenza di backfill delle caratteristiche {#trait-backfilling-latency}

Le nuove caratteristiche create iniziano a catturare il pubblico da due a tre ore dopo la creazione. Tuttavia, a causa del grande volume di dati che [!DNL Audience Manager] prestazioni su base giornaliera, la popolazione recuperata non viene riflessa immediatamente nel [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] grafici.

L’Audience Manager aggiorna il [!UICONTROL Trait Graph] con la popolazione backfill entro 48 ore dalla creazione delle caratteristiche.

## Limite di retrocompilazione delle caratteristiche {#trait-backfilling-limit}

[!UICONTROL Data Explorer] consente di eseguire il backfill di un massimo di 50 caratteristiche al mese, con il contatore di backfill reimpostato il 1 giorno di ogni mese.

>[!NOTE]
>
>La quota di retrocompilazione delle caratteristiche non è riportata dai mesi precedenti. Ad esempio, se questo mese esegui la retrocompilazione di 30 caratteristiche, la quota di retrocompilazione delle caratteristiche per il mese successivo viene reimpostata su 50 e non su 70.

## Impatto sul reporting {#reporting-impact}

Le realizzazioni delle caratteristiche in backfill si riflettono nel [!UICONTROL Unique Trait Realizations] e [!UICONTROL Total Trait Population] metriche, come [!DNL Audience Manager] trasforma i segnali storici in realizzazioni di caratteristiche.

Tuttavia, il [!UICONTROL Trait Graph], [!UICONTROL General Reports], e [!UICONTROL Trend Reports] non vengono aggiornati retroattivamente con metriche storiche restituite prima della data di creazione delle caratteristiche.
