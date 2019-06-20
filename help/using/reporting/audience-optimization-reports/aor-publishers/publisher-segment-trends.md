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


# Report tendenza segmento{#segment-trend-report}

Il rapporto Tendenza segmento restituisce i dati su impression e percentuali di clic di segmenti mappati e non mappati nel tempo.

Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting.

Confronta le tendenze e il volume delle metriche selezionate per ottenere un&#39;immagine migliore del comportamento dei tuoi tipi di pubblico nel tempo.

## Caso d&#39;uso {#use-cases}

Usa [!UICONTROL Segment Trend] il rapporto per convalidare le prestazioni di un segmento nel tempo e per individuare le tendenze in base a prestazioni o scala robuste.

Con questo rapporto potete capire quali delle vostre proprietà Web mostrano un incremento o un incremento anomalo, e la risoluzione di problemi come necessario. Questo rapporto rappresenta il passaggio successivo dopo l&#39;identificazione dell&#39;audience interesse nel [!UICONTROL Segment Performance] report, per garantire che le prestazioni rigorose o di scarso livello visualizzato nella [!UICONTROL Segment Performance] scheda siano coerenti nel tempo.

## Utilizzo del report Tendenza segmento {#using-the-report}

Alterna **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** seleziona i segmenti mappati a una destinazione o meno. Seleziona **[!UICONTROL All]** per includere tutti i segmenti nel rapporto.

Regolare la finestra di look-back con il **[!UICONTROL Date Through]** cursore.

Fai clic su uno dei segmenti sotto il **[!UICONTROL Date Through]** cursore per visualizzare l&#39;opzione per mantenere solo tale segmento nel rapporto o escluderlo.

Utilizza il **[!UICONTROL Line Item]** menu a discesa per selezionare le proprietà nel tuo portfolio per le quali vuoi restituire le informazioni.

Nel menu **[!UICONTROL Segment Data Source]** a discesa, seleziona le origini dati contenenti i segmenti che desideri vedere nel rapporto.

Utilizza il **[!UICONTROL Segment]** menu a discesa per selezionare i segmenti da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando abilitate [!UICONTROL Audience Optimization for Publishers], dovete includere metadati descrittivi per [!UICONTROL Line Item] gli ID, come descritto nel Passaggio 3 di [Importa file di dati DFP in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In tal modo, assicuratevi che il rapporto contenga la proprietà Web come [!UICONTROL Line Item] invece dell&#39; [!UICONTROL Line Item] ID.

## Interpretazione dei risultati {#interpreting-results}

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
