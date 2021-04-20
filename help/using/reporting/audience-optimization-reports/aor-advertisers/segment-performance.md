---
description: Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati in base a impression e tassi di conversione. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confrontando questi diversi tipi di segmenti all’interno dei rapporti e tra di essi è possibile ottimizzare le campagne esistenti e trovare segmenti trascurati che è possibile inviare a una destinazione per il targeting.
seo-description: Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati in base a impression e tassi di conversione. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confrontando questi diversi tipi di segmenti all’interno dei rapporti e tra di essi è possibile ottimizzare le campagne esistenti e trovare segmenti trascurati che è possibile inviare a una destinazione per il targeting.
seo-title: Rapporto sulle prestazioni dei segmenti
solution: Audience Manager
title: Rapporto sulle prestazioni dei segmenti
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# Rapporto sulle prestazioni dei segmenti{#segment-performance-report}

Il rapporto [!UICONTROL Segment Performance] confronta i segmenti mappati e non mappati per impression e tassi di conversione. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confrontando questi diversi tipi di segmenti all’interno dei rapporti e tra di essi è possibile ottimizzare le campagne esistenti e trovare segmenti trascurati che è possibile inviare a una destinazione per il targeting.

## Come leggere i risultati del segmento mappato {#read-mapped-segment-results}

Il rapporto [!UICONTROL Segment Performance] mappato visualizza tutti i segmenti creati e inviati a una destinazione per il targeting. La posizione dei segmenti mappati in un rapporto può fornire informazioni dettagliate sulle prestazioni dei segmenti e su dove potrebbe essere necessario apportare alcune modifiche.

Per leggere il rapporto, aiuta a dividere i risultati in 4 sezioni con linee immaginarie (in rosso) e le categorie mostrate nel rapporto di esempio sottostante.

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
   <td colname="col2"> <p>Bassi tassi di conversione. </p> <p>Puoi evitare di eseguire il targeting di questi segmenti. I segmenti in questa sezione sono candidati ideali per il confronto con quelli nei risultati dei segmenti non mappati. Alcuni dei segmenti non mappati potrebbero avere prestazioni migliori dei segmenti per i quali stai già eseguendo il targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a destra</b> </p> </td> 
   <td colname="col2"> <p>Prestazioni elevate. Lascia stare questi segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a destra</b> </p> </td> 
   <td colname="col2"> <p>Bassi tassi di conversione e impression elevate. </p> <p>I segmenti in questa sezione non funzionano bene. È possibile spostare il budget da questi segmenti e in segmenti nel quadrante in alto a sinistra del rapporto. In questo modo sarà possibile ridurre le impression e migliorare i tassi di conversione per i segmenti in questa sezione in basso a destra. Inoltre, confronta questi segmenti mappati con i segmenti non mappati. Alcuni dei segmenti non mappati potrebbero avere prestazioni migliori dei segmenti per i quali stai già eseguendo il targeting. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come leggere i risultati dei segmenti non mappati {#read-unmapped-segment-results}

Osservare i segmenti non mappati in un rapporto [!UICONTROL Segment Performance] è un ottimo modo per trovare nuovi segmenti che non hai considerato per il targeting. Infatti, alcuni di questi segmenti possono superare i segmenti mappati. Questo perché un segmento non mappato deve soddisfare un set di criteri di qualificazione da includere in questo rapporto. Per essere incluso in questo rapporto, un segmento non mappato deve:

* Avere conversioni maggiori della media di tutti i segmenti mappati.
* I primi 100 segmenti non mappati in base al tasso di conversione.

Per leggere questo rapporto, aiuta a dividere i risultati in 4 sezioni con linee immaginarie (in rosso) e categorie mostrate nel rapporto di esempio sottostante.

![](assets/unmapped-segment-performance.png)

In questo rapporto desideri concentrarti solo sui segmenti non mappati nella sezione in alto a sinistra. Questi segmenti non mappati presentano tassi di conversione elevati per un basso livello di impression rispetto ai segmenti delle altre tre sezioni.

>[!NOTE]
>
>I periodi di look-back di 7 giorni e 30 giorni sono disponibili solo per le date di domenica **[!UICONTROL Date Through]**.
