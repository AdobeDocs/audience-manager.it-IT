---
description: Il rapporto Trend segmento restituisce i dati sulle impression e sui tassi di click-through di segmenti mappati e non mappati nel tempo. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confronta tendenze e volume delle metriche selezionate per ottenere un'immagine migliore del comportamento del pubblico nel tempo.
seo-description: Il rapporto Trend segmento restituisce i dati sulle impression e sui tassi di click-through di segmenti mappati e non mappati nel tempo. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confronta tendenze e volume delle metriche selezionate per ottenere un'immagine migliore del comportamento del pubblico nel tempo.
seo-title: Rapporto sulle tendenze dei segmenti
solution: Audience Manager
title: Rapporto sulle tendenze dei segmenti
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# Rapporto sulle tendenze dei segmenti{#segment-trend-report}

Il rapporto Trend segmento restituisce i dati sulle impression e sui tassi di click-through di segmenti mappati e non mappati nel tempo.

Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting.

Confronta tendenze e volume delle metriche selezionate per ottenere un&#39;immagine migliore del comportamento del pubblico nel tempo.

## Caso d&#39;uso {#use-cases}

Utilizza il rapporto [!UICONTROL Segment Trend] per convalidare le prestazioni di un segmento nel tempo e per individuare le tendenze in base a prestazioni o scala elevate.

Con questo rapporto, puoi capire quale delle proprietà web mostra un calo o un aumento difettoso e risolvere i problemi, se necessario. Questo rapporto è il passaggio successivo dopo aver identificato il pubblico di interesse nel rapporto [!UICONTROL Segment Performance] per garantire che le prestazioni forti o scarse visualizzate nella scheda [!UICONTROL Segment Performance] siano coerenti nel tempo.

## Utilizzo del rapporto sulle tendenze del segmento {#using-the-report}

Passa da **[!UICONTROL Mapped]** a **[!UICONTROL Unmapped]** per selezionare i segmenti mappati a una destinazione o meno. Seleziona **[!UICONTROL All]** per includere tutti i segmenti nel rapporto.

Regolare la finestra di look-back con il cursore **[!UICONTROL Date Through]**.

Fai clic su uno dei segmenti sotto il cursore **[!UICONTROL Date Through]** per visualizzare l’opzione per mantenere solo quel segmento nel rapporto o escluderlo.

Utilizza la casella a discesa **[!UICONTROL Line Item]** per selezionare le proprietà del tuo portfolio per cui vuoi restituire informazioni.

Nella casella a discesa **[!UICONTROL Segment Data Source]** , seleziona le origini dati contenenti i segmenti che desideri visualizzare nel rapporto.

Utilizza la casella a discesa **[!UICONTROL Segment]** per selezionare i segmenti da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando abiliti [!UICONTROL Audience Optimization for Publishers], devi includere metadati descrittivi per [!UICONTROL Line Item] ID, come descritto nel passaggio 3 di [Importa file di dati Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo, assicurati che il report descriva la proprietà Web come [!UICONTROL Line Item] invece dell&#39; [!UICONTROL Line Item] ID.

## Interpretazione dei risultati {#interpreting-results}

Il rapporto [!UICONTROL Segment Trend] restituisce i dati sotto forma di grafico a linee solo per un intervallo di 14 giorni. In questo esempio, il rapporto mostra le tendenze di impression e click-through per un set di segmenti mappati e non mappati.

Passa il puntatore del mouse su una riga per ottenere ulteriori informazioni su tale particolare tendenza del segmento. Vedi le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto di esempio.

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
   <td colname="col2"> <p>Nome alfanumerico assegnato al segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID segmento</span> </p> </td> 
   <td colname="col2"> <p>ID univoco del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Voce</span> </p> </td> 
   <td colname="col2"> <p>La proprietà Web per la quale viene visualizzato questo rapporto. </p> </td> 
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
   <td colname="col2"> <p>Frequenza di click-through. Questa metrica inoltra la percentuale di impression seguita dai clic. Per ottenere questa metrica, suddividi i clic per impression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Uniche segmenti</span> </p> </td> 
   <td colname="col2"> <p>Il numero di membri del segmento, negli ultimi 30 giorni. </p> </td> 
  </tr> 
 </tbody> 
</table>
