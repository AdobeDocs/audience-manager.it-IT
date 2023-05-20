---
description: Il rapporto Tendenza segmento restituisce i dati sulle impression e sui tassi di click-through di segmenti mappati e non mappati nel tempo. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confronta le tendenze e il volume per le metriche selezionate per ottenere un’immagine migliore del comportamento dei tipi di pubblico nel tempo.
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: Rapporto sulle tendenze dei segmenti
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 2%

---

# Rapporto sulle tendenze dei segmenti{#segment-trend-report}

Il rapporto Tendenza segmento restituisce i dati sulle impression e sui tassi di click-through di segmenti mappati e non mappati nel tempo.

Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting.

Confronta le tendenze e il volume per le metriche selezionate per ottenere un’immagine migliore del comportamento dei tipi di pubblico nel tempo.

## Caso d&#39;uso {#use-cases}

Utilizza il [!UICONTROL Segment Trend] report per convalidare le prestazioni di un segmento nel tempo e individuare le tendenze in base a prestazioni affidabili o scalabili.

Con questo rapporto, puoi capire quale delle tue proprietà web mostra un aumento difettoso o difettoso e risolvere eventuali problemi. Questo rapporto è il passaggio successivo dopo aver identificato il pubblico di interesse per [!UICONTROL Segment Performance] per garantire che le prestazioni forti o scarse che hai visto nel [!UICONTROL Segment Performance] è coerente nel tempo.

## Utilizzo del rapporto Tendenza segmento {#using-the-report}

Passa da **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** per selezionare i segmenti mappati o meno su una destinazione. Seleziona **[!UICONTROL All]** per includere tutti i segmenti nel rapporto.

Regolare l&#39;intervallo di look-back con **[!UICONTROL Date Through]** cursore.

Fai clic su uno dei segmenti sotto **[!UICONTROL Date Through]** cursore per visualizzare l’opzione di mantenere solo quel segmento nel rapporto o escluderlo.

Utilizza il **[!UICONTROL Line Item]** per selezionare le proprietà nel portfolio per le quali si desidera restituire le informazioni.

In **[!UICONTROL Segment Data Source]** , selezionare le origini dati contenenti i segmenti che si desidera visualizzare nel rapporto.

Utilizza il **[!UICONTROL Segment]** per selezionare i segmenti da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Line Item] ID, come descritto nel passaggio 3 di [Importare file di dati di Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo, assicurerai che il rapporto descriva nei dettagli la proprietà web come [!UICONTROL Line Item] invece del [!UICONTROL Line Item] ID

## Interpretazione dei risultati {#interpreting-results}

Il [!UICONTROL Segment Trend] report restituisce i dati in un grafico a linee solo per un intervallo di 14 giorni. In questo esempio, il rapporto mostra le tendenze di impression e click-through per un set di segmenti mappati e non mappati.

Passa il cursore sopra una riga per ottenere ulteriori informazioni su quella particolare tendenza del segmento. Per ulteriori informazioni, consulta la descrizione nella tabella seguente il rapporto di esempio.

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
   <td colname="col2"> <p>ID univoco di questo segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Voce</span> </p> </td> 
   <td colname="col2"> <p>La proprietà web per la quale stai visualizzando questo rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Clic</span> </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica hanno fatto clic su elementi nella proprietà Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressioni</span> </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica sono stati esposti al tuo inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Percentuale di click-through. Questa metrica inoltra la percentuale di impression seguita da clic. Dividi i clic per impression per ottenere questa metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Univoci segmento</span> </p> </td> 
   <td colname="col2"> <p>Il numero di membri del segmento negli ultimi 30 giorni. </p> </td> 
  </tr> 
 </tbody> 
</table>
