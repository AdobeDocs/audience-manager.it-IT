---
description: Il rapporto Performance Performance (Prestazioni segmento) confronta i segmenti mappati e non mappati tramite impression e tassi di conversione. Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting. Il confronto tra questi tipi di segmenti diversi all'interno e tra i rapporti consente di ottimizzare le campagne esistenti e individuare segmenti trascurati che potresti desiderare inviare a una destinazione per il targeting.
seo-description: Il rapporto Performance Performance (Prestazioni segmento) confronta i segmenti mappati e non mappati tramite impression e tassi di conversione. Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting. Il confronto tra questi tipi di segmenti diversi all'interno e tra i rapporti consente di ottimizzare le campagne esistenti e individuare segmenti trascurati che potresti desiderare inviare a una destinazione per il targeting.
seo-title: Report sulle prestazioni dei segmenti
solution: Audience Manager
title: Report sulle prestazioni dei segmenti
uuid: 5156 a 4 c 7-831 d -4 a 95-a 1 be-eb 516 f 0 d 91 b 7
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Segment Performance Report{#segment-performance-report}

[!UICONTROL Segment Performance] Il rapporto confronta i segmenti mappati e non mappati tramite impression e tassi di conversione. Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting. Il confronto tra questi tipi di segmenti diversi all'interno e tra i rapporti consente di ottimizzare le campagne esistenti e individuare segmenti trascurati che potresti desiderare inviare a una destinazione per il targeting.

## How to Read Your Mapped Segment Results {#read-mapped-segment-results}

The mapped [!UICONTROL Segment Performance] report displays all the segments you created and sent to a destination for targeting.The position of your mapped segments in a report can tell you a lot about which segments are performing well and where you might need to make some adjustments.

Per leggere il rapporto, è utile suddividere i risultati in 4 sezioni con righe immaginarie (in rosso) e le categorie mostrate nel rapporto di esempio sottostante.

![](assets/mapped-segment-performance.png)

Le etichette nell'esempio e nella tabella seguente possono aiutarti a comprendere le prestazioni dei segmenti e come rispondere a tali risultati.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posizione </th> 
   <th colname="col2" class="entry"> Posizionamento indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Tassi di conversione validi. </p> <p>Potreste essere in grado di ottenere più conversioni aumentando le impression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Tassi di conversione ridotti. </p> <p>Potresti voler evitare di targeting di questi segmenti. I segmenti in questa sezione rendono i candidati straordinari per il confronto con quelli nei risultati non mappati. Alcuni dei segmenti non mappati possono essere migliori rispetto ai segmenti già impostati come destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a destra</b> </p> </td> 
   <td colname="col2"> <p>Prestazioni elevate. Lascia questi segmenti da soli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a destra</b> </p> </td> 
   <td colname="col2"> <p>Tassi di conversione bassi e impression elevate. </p> <p>I segmenti in questa sezione non funzionano correttamente. Potrebbe essere utile spostare il budget lontano da questi segmenti e nei segmenti nel quadrante sinistro superiore del report. Ciò consentirà di ridurre le impression e di migliorare i tassi di conversione per i segmenti in questa sezione in basso a destra. Confronta anche questi segmenti mappati con i segmenti non mappati. Alcuni dei segmenti non mappati possono essere migliori rispetto ai segmenti già impostati come destinazione. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Unmapped Segment Results {#read-unmapped-segment-results}

Looking at unmapped segments in a [!UICONTROL Segment Performance] report is a great way to find new segments you haven't considered for targeting. In effetti, alcuni di questi segmenti possono prevalere sui segmenti mappati. poiché un segmento non mappato deve soddisfare un insieme di criteri di qualifica da includere in questo report. Per essere inclusi in questo rapporto, un segmento non mappato deve:

* Hanno conversioni superiori alla media di tutti i segmenti mappati.
* Dai primi 100 segmenti non mappati per tasso di conversione.

Per leggere questo rapporto, è utile suddividere i risultati in 4 sezioni con righe immaginarie (in rosso) e categorie mostrate nel rapporto di esempio sottostante.

![](assets/unmapped-segment-performance.png)

In questo rapporto, vuoi solo concentrarti su quei segmenti non mappati nella sezione in alto a sinistra. Questi segmenti non mappati presentano tassi di conversione elevati per un livello basso di impression quando confrontato ai segmenti nelle altre tre sezioni.

>[!NOTE]
>
>7-day and 30-day look-back periods are only available for Sunday **[!UICONTROL Date Through]** dates.
