---
description: Visualizzare le informazioni sulla cronologia dei processi batch in uscita per una destinazione e un periodo di tempo specificati.
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: Cronologia dei file in uscita
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
TQID: https://experienceleague.adobe.com/bAoUgntw3hZBsEuyPQV6yX2ftNRFV9HIv9QbierOgmA
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 152
ht-degree: 1%

---

# Cronologia dei file in uscita {#outbound-file-history}

Visualizzare le informazioni sulla cronologia dei processi batch in uscita per una destinazione e un periodo di tempo specificati.

<!-- 

t_reports_outbound_history.xml

 -->

1. Fare clic su **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Risultato passaggio](assets/outbound_history.png)

1. Nella casella **[!UICONTROL Search for a Destination]**, iniziare a digitare e selezionare la destinazione desiderata.
1. Nella casella **[!UICONTROL Select a Date Range]**, specifica le date di inizio e fine per il report, quindi fai clic su **[!UICONTROL Apply Date Filter]**.

   ![Risultato passaggio](assets/outbound_history_stats.png)

   La tabella seguente contiene informazioni corrispondenti alle colonne del rapporto:

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linee </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome file di sincronizzazione dati </td> 
   <td colname="col2"> <p>Elenco di tutti i file in uscita generati da <span class="keyword"> Adobe</span> per questa destinazione ed elaborati insieme. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Completato </td> 
   <td colname="col2"> <p>Numero di record inviati correttamente da <span class="keyword"> Audience Manager</span> alla destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non riuscito </td> 
   <td colname="col2"> <p>Numero di record che non è stato possibile inviare alla destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record ricevuti </td> 
   <td colname="col2"> <p>Numero totale di record <span class="keyword"> Adobe</span> generati nei file e che hanno tentato di inviare alla destinazione. Nella maggior parte dei casi, dovrebbe corrispondere al numero totale di file riusciti e di file non riusciti. </p> </td> 
  </tr> 
 </tbody> 
</table>
