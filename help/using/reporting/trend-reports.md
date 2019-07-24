---
description: Un rapporto Tendenza restituisce dati sulle tendenze sui segmenti e sui segmenti.
seo-description: Un rapporto Tendenza restituisce dati sulle tendenze sui segmenti e sui segmenti.
seo-title: Report sulle tendenze
solution: Audience Manager
title: Report sulle tendenze
uuid: bedbe 7 d 4-7 cbb -4403-9104-312 f 9230 aea 1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trend Reports{#trend-reports}

Un rapporto Tendenza restituisce dati sulle tendenze sui segmenti e sui segmenti.

## Panoramica {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo utenti ai [!UICONTROL Trend] rapporti. Gli utenti possono vedere solo le caratteristiche e i segmenti nei rapporti che possono visualizzare. [!UICONTROL RBAC] consente di controllare quali dei team interni di dati di reporting sono in grado di visualizzare.

Ad esempio, un'agenzia che gestisce diversi account pubblicitari può configurare le autorizzazioni del gruppo di utenti in modo che un team che gestisce l'account dell'inserzionista A non possa vedere i dati di reporting dell'inserzionista B.

Run a [!UICONTROL Trend] report when you need to:

* Rivedete i dati delle tendenze per caratteristiche e segmenti.
* Tieni traccia delle tendenze di 1, 7, 14, 30, 60 e 90 giorni.
* Confronta le tendenze e le tendenze del segmento nel tempo.
* Identificare caratteristiche e segmenti di prestazioni potenti o scadenti.
* Esportare dati (formato. csv) per un'ulteriore analisi e condivisione.

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports.png)

1. Configura le seguenti opzioni:

   **Tipo di rapporto:** Seleziona il tipo di rapporto desiderato (Caratteristica o Segmento).

   **Intervallo di date:** Specifica l'intervallo di date per il rapporto (data di inizio e data di fine).

   **Intervallo di visualizzazione:** Specificare l'intervallo di visualizzazione (intervalli 1, 7, 14, 30, 60 e 90 giorni).

2. Cerca una caratteristica o un segmento per nome o ID.
3. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.
4. Genera il rapporto da visualizzare nei dati in formato grafico o esporta il rapporto in formato CSV.

## Run a Trend Report {#run-trend-report}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: **[!UICONTROL Trait]** or **[!UICONTROL Segment]**.
1. Fate clic sulle caselle di data per visualizzare un calendario, quindi selezionate le date di inizio e fine del rapporto.
1. Specificate l'intervallo di visualizzazione: per 1, 7, 14, 30, 60 o 90 giorni.
1. Cerca una caratteristica o un segmento per nome o ID.
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time.
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   Queste opzioni ignorano tutte le cartelle e i grafici solo per caratteristiche o segmenti selezionati singolarmente.

   Oppure

   Click **[!UICONTROL Export to CSV]** to export the trait or segment data and all folders in CSV format for further analysis and sharing. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sono calcolate [!UICONTROL Rule-based Traits] solo per.

1. (Facoltativo) Passa il cursore su singole caratteristiche o segmenti per visualizzare il numero di visite e la data di ogni dato.

   Potete fare clic sulle intestazioni di colonna nella tabella per ordinare i risultati in ordine crescente o decrescente.

For [!UICONTROL Trended Trait] reports, zeroes indicate that [!DNL Audience Manager] did not collect data for that day. Le voci vuote indicano che la caratteristica non esiste. L'esempio seguente mostra esempi di entrambi i tipi di voci:

![](assets/trended_data.png)
