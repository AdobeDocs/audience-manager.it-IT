---
description: Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati in base alle impression e ai tassi di conversione. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Il confronto di questi diversi tipi di segmenti all’interno dei rapporti e tra i rapporti ti consente di ottimizzare le campagne esistenti e di trovare i segmenti trascurati che potresti voler inviare a una destinazione per il targeting.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Rapporto sulle prestazioni dei segmenti
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# Rapporto sulle prestazioni dei segmenti{#segment-performance-report}

Il report [!UICONTROL Segment Performance] confronta i segmenti mappati e non mappati in base alle impression e ai tassi di conversione. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Il confronto di questi diversi tipi di segmenti all’interno dei rapporti e tra i rapporti ti consente di ottimizzare le campagne esistenti e di trovare i segmenti trascurati che potresti voler inviare a una destinazione per il targeting.

## Come leggere i risultati dei segmenti mappati {#read-mapped-segment-results}

Il report [!UICONTROL Segment Performance] mappato visualizza tutti i segmenti creati e inviati a una destinazione per il targeting. La posizione dei segmenti mappati in un report può indicare molto su quali segmenti stanno funzionando correttamente e dove potrebbe essere necessario apportare alcune modifiche.

Per leggere il rapporto, è utile dividere i risultati in 4 sezioni con linee immaginarie (in rosso) e le categorie visualizzate nel rapporto di esempio seguente.

![](assets/mapped-segment-performance.png)

Le etichette nell’esempio e nella tabella seguente possono aiutarti a comprendere le prestazioni dei segmenti e come rispondere a questi risultati.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posizione </th> 
   <th colname="col2" class="entry"> Posizionamento Indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Buoni tassi di conversione. </p> <p>Puoi ottenere più conversioni aumentando le impression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Bassi tassi di conversione. </p> <p>Potrebbe essere utile evitare di eseguire il targeting di questi segmenti. I segmenti in questa sezione sono particolarmente adatti al confronto con quelli dei risultati dei segmenti non mappati. Alcuni dei segmenti non mappati potrebbero offrire prestazioni migliori rispetto ai segmenti di cui già esegui il targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a destra</b> </p> </td> 
   <td colname="col2"> <p>Prestazioni elevate. Lascia stare questi segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a destra</b> </p> </td> 
   <td colname="col2"> <p>Bassi tassi di conversione e impression elevate. </p> <p>Le prestazioni dei segmenti in questa sezione non sono soddisfacenti. Puoi spostare il budget da questi segmenti e in segmenti nel quadrante in alto a sinistra del rapporto. Questo aiuterà a ridurre le impression e a migliorare i tassi di conversione per i segmenti in questa sezione in basso a destra. Inoltre, confronta questi segmenti mappati con i segmenti non mappati. Alcuni dei segmenti non mappati potrebbero offrire prestazioni migliori rispetto ai segmenti di cui già esegui il targeting. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come leggere i risultati dei segmenti non mappati {#read-unmapped-segment-results}

Osservare i segmenti non mappati in un report [!UICONTROL Segment Performance] è un ottimo modo per trovare nuovi segmenti che non hai considerato per il targeting. Infatti, alcuni di questi segmenti potrebbero avere prestazioni superiori a quelle dei segmenti mappati. Questo perché un segmento non mappato deve soddisfare una serie di criteri di qualificazione da includere nel rapporto. Per essere incluso in questo rapporto, un segmento non mappato deve:

* Avere conversioni superiori alla media di tutti i segmenti mappati.
* Rientra nei primi 100 segmenti non mappati per tasso di conversione.

Per leggere questo rapporto, è utile dividere i risultati in 4 sezioni con linee immaginarie (in rosso) e categorie visualizzate nel rapporto di esempio seguente.

![](assets/unmapped-segment-performance.png)

In questo rapporto, desideri concentrarti solo sui segmenti non mappati, nella sezione in alto a sinistra. Questi segmenti non mappati mostrano tassi di conversione elevati per un basso livello di impression rispetto ai segmenti nelle altre tre sezioni.

>[!NOTE]
>
>I periodi di look-back di 7 giorni e 30 giorni sono disponibili solo per le date di domenica **[!UICONTROL Date Through]**.
