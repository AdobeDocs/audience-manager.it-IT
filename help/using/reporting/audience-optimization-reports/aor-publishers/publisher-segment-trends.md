---
description: Il rapporto Tendenza segmento restituisce i dati su impression e percentuali di clic di segmenti mappati e non mappati nel tempo. Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting. Confronta le tendenze e il volume delle metriche selezionate per ottenere un'immagine migliore del comportamento dei tuoi tipi di pubblico nel tempo.
seo-description: Il rapporto Tendenza segmento restituisce i dati su impression e percentuali di clic di segmenti mappati e non mappati nel tempo. Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting. Confronta le tendenze e il volume delle metriche selezionate per ottenere un'immagine migliore del comportamento dei tuoi tipi di pubblico nel tempo.
seo-title: Report tendenza segmento
solution: Audience Manager
title: Report tendenza segmento
uuid: f 84 e 8 d 0 a -74 e 5-430 c-b 61 c-efb 696 faee 93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Trend Report{#segment-trend-report}

Il rapporto Tendenza segmento restituisce i dati su impression e percentuali di clic di segmenti mappati e non mappati nel tempo.

Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting.

Confronta le tendenze e il volume delle metriche selezionate per ottenere un'immagine migliore del comportamento dei tuoi tipi di pubblico nel tempo.

## Caso d'uso {#use-cases}

Use the [!UICONTROL Segment Trend] report to validate a segment's performance over time and to pinpoint trends based on strong performance or scale.

Con questo rapporto potete capire quali delle vostre proprietà Web mostrano un incremento o un incremento anomalo, e la risoluzione di problemi come necessario. This report is the next step after you identify your audience of interest in the [!UICONTROL Segment Performance] report, to ensure that the strong or poor performance you saw in the [!UICONTROL Segment Performance] tab is consistent over time.

## Using the Segment Trend Report {#using-the-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Adjust the look-back window with the **[!UICONTROL Date Through]** slider.

Click any of the segments under the **[!UICONTROL Date Through]** slider to bring up the option to keep only that segment in the report or exclude it.

Use the **[!UICONTROL Line Item]** drop-down box to select the properties in your portfolio for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item] IDs, as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item] ID.

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment Trend] Il rapporto restituisce i dati in un grafico a linee solo per un intervallo di 14 giorni. In questo esempio, il report mostra le tendenze di impression e click-through per un insieme di segmenti mappati e non mappati.

Passa il cursore su una linea per ottenere ulteriori informazioni su quella tendenza particolare del segmento. Vedere descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmento</span> </p> </td> 
   <td colname="col2"> <p>Il nome alfanumerico assegnato a questo segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID segmento</span> </p> </td> 
   <td colname="col2"> <p>L'ID univoco di questo segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Elemento linea</span> </p> </td> 
   <td colname="col2"> <p>La proprietà Web per la quale stai visualizzando il rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Clic</span> </p> </td> 
   <td colname="col2"> <p>Numero di volte in cui i membri di questa caratteristica hanno fatto clic sugli elementi nella proprietà Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressioni</span> </p> </td> 
   <td colname="col2"> <p>Numero di volte in cui i membri di questa caratteristica sono stati esposti alle scorte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Tasso di click-through. Questa metrica rimuove la percentuale di impression seguito dai clic. Divide i clic per impression per ottenere questa metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unione segmenti</span> </p> </td> 
   <td colname="col2"> <p>Numero di membri del segmento negli ultimi 30 giorni. </p> </td> 
  </tr> 
 </tbody> 
</table>
