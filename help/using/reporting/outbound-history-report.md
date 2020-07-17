---
description: Visualizzare le informazioni sulla cronologia dei processi batch in uscita per una destinazione e un periodo di tempo specificati.
seo-description: Visualizzare le informazioni sulla cronologia dei processi batch in uscita per una destinazione e un periodo di tempo specificati.
seo-title: Cronologia dei file in uscita
solution: Audience Manager
title: Cronologia dei file in uscita
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 7%

---


# Cronologia dei file in uscita {#outbound-file-history}

Visualizzare le informazioni sulla cronologia dei processi batch in uscita per una destinazione e un periodo di tempo specificati.

<!-- 

t_reports_outbound_history.xml

 -->

1. Clic **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Risultato del passaggio](assets/outbound_history.png)

1. Nella **[!UICONTROL Search for a Destination]** casella, iniziate a digitare e selezionate la destinazione desiderata.
1. Nella **[!UICONTROL Select a Date Range]** casella, specifica le date di inizio e di fine del rapporto, quindi fai clic su **[!UICONTROL Apply Date Filter]**.

   ![Risultato del passaggio](assets/outbound_history_stats.png)

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
   <td colname="col1"> Nome file sincronizzazione dati </td> 
   <td colname="col2"> <p>Elenco di tutti i file in uscita generati da <span class="keyword"> Adobe</span> per questa destinazione elaborati insieme. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Riuscito </td> 
   <td colname="col2"> <p>Numero di record che sono stati inviati correttamente da <span class="keyword"> Audience Manager</span> alla destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non riuscito </td> 
   <td colname="col2"> <p>Numero di record che non è stato possibile inviare alla destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record ricevuti </td> 
   <td colname="col2"> <p>Numero totale di record <span class="keyword"> generati da Adobe</span> nei file e tentati di inviarli alla destinazione. Nella maggior parte dei casi, questo deve essere il numero totale di file riusciti e non riusciti. </p> </td> 
  </tr> 
 </tbody> 
</table>
