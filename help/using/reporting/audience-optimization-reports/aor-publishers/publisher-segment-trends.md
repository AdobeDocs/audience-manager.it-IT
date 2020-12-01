---
description: Il rapporto Trend segmento restituisce i dati sulle impression e i tassi di click-through dei segmenti mappati e non mappati nel tempo. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confronta tendenze e volume per le metriche selezionate per ottenere un'immagine migliore del comportamento dell'audience nel tempo.
seo-description: Il rapporto Trend segmento restituisce i dati sulle impression e i tassi di click-through dei segmenti mappati e non mappati nel tempo. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confronta tendenze e volume per le metriche selezionate per ottenere un'immagine migliore del comportamento dell'audience nel tempo.
seo-title: Rapporto sulle tendenze dei segmenti
solution: Audience Manager
title: Rapporto sulle tendenze dei segmenti
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 2%

---


# Rapporto sulle tendenze dei segmenti{#segment-trend-report}

Il rapporto Trend segmento restituisce i dati sulle impression e i tassi di click-through dei segmenti mappati e non mappati nel tempo.

Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting.

Confronta tendenze e volume per le metriche selezionate per ottenere un&#39;immagine migliore del comportamento dell&#39;audience nel tempo.

## Caso d&#39;uso {#use-cases}

Utilizzate il report [!UICONTROL Segment Trend] per convalidare le prestazioni di un segmento nel tempo e per individuare le tendenze in base a prestazioni o scala elevate.

Con questo rapporto, puoi capire quale delle tue proprietà web mostra un calo o un aumento difettoso e risolvere eventuali problemi, a seconda delle necessità. Questo rapporto è il passo successivo dopo che hai identificato il pubblico di interesse nel report [!UICONTROL Segment Performance], per assicurarti che le prestazioni forti o negative visualizzate nella scheda [!UICONTROL Segment Performance] siano coerenti nel tempo.

## Utilizzo del report Trend segmento {#using-the-report}

Passa da **[!UICONTROL Mapped]** a **[!UICONTROL Unmapped]** per selezionare o meno i segmenti mappati a una destinazione. Selezionare **[!UICONTROL All]** per includere tutti i segmenti nel rapporto.

Regolare la finestra di look-back con il cursore **[!UICONTROL Date Through]**.

Fai clic su uno dei segmenti sotto il cursore **[!UICONTROL Date Through]** per visualizzare l&#39;opzione per mantenere solo quel segmento nel rapporto o escluderlo.

Utilizzate la casella a discesa **[!UICONTROL Line Item]** per selezionare le proprietà del portafoglio per le quali desiderate restituire informazioni.

Nella casella a discesa **[!UICONTROL Segment Data Source]**, seleziona le origini dati contenenti i segmenti che desideri vedere nel rapporto.

Utilizzate la casella a discesa **[!UICONTROL Segment]** per selezionare i segmenti da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per gli ID [!UICONTROL Line Item], come descritto nel passaggio 3 di [Importa file di dati Google Ad Manager (ex DFP) in  Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). A questo scopo, assicuratevi che il rapporto descriva la proprietà Web come [!UICONTROL Line Item] invece dell&#39; [!UICONTROL Line Item] ID.

## Interpretazione dei risultati {#interpreting-results}

Il report [!UICONTROL Segment Trend] restituisce i dati in un grafico a linee solo per un intervallo di 14 giorni. In questo esempio, il rapporto mostra tendenze di impression e click-through per un insieme di segmenti mappati e non mappati.

Passa il cursore sopra una riga per ottenere ulteriori informazioni su quella particolare tendenza del segmento. Vedere le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

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
   <td colname="col2"> <p>ID univoco del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Voce</span> </p> </td> 
   <td colname="col2"> <p>Proprietà Web per la quale viene visualizzato il rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Clic</span> </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica hanno fatto clic sugli elementi nella proprietà Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressioni</span> </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica sono stati esposti al tuo inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Frequenza di click-through. Questa metrica invia la percentuale di impression seguita da clic. Dividi i clic per impression per ottenere questa metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmento di analisi</span> </p> </td> 
   <td colname="col2"> <p>Numero di membri del segmento, negli ultimi 30 giorni. </p> </td> 
  </tr> 
 </tbody> 
</table>
