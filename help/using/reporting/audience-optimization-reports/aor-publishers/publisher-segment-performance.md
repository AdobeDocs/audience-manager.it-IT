---
description: Il rapporto sulle prestazioni dei segmenti confronta i segmenti mappati e non mappati in base alle impression e ai valori univoci dei segmenti in tempo reale. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Il confronto di questi diversi tipi di segmenti all’interno dei rapporti e tra i rapporti ti consente di ottimizzare le campagne esistenti e di trovare i segmenti trascurati che potresti voler inviare a una destinazione per il targeting.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Rapporto sulle prestazioni dei segmenti per publisher
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# Rapporto sulle prestazioni dei segmenti{#segment-performance-report}

Il rapporto sulle prestazioni dei segmenti confronta i segmenti mappati e non mappati in base alle impression e ai valori univoci dei segmenti in tempo reale.

Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting.

Il confronto di questi diversi tipi di segmenti all’interno dei rapporti e tra i rapporti ti consente di ottimizzare le campagne esistenti e di trovare i segmenti trascurati che potresti voler inviare a una destinazione per il targeting.

## Casi d&#39;uso {#use-cases}

Con il report [!UICONTROL Segment Performance] è possibile:

* Identifica i segmenti di pubblico mappati che stanno guidando la scalabilità o le prestazioni.
* Identifica i segmenti non mappati da introdurre nelle campagne future, in base al contributo di un pubblico alle prestazioni passate.

## Utilizzo del rapporto sulle prestazioni dei segmenti {#using-segment-performance-report}

Consente di passare da **[!UICONTROL Mapped]** a **[!UICONTROL Unmapped]** per selezionare i segmenti mappati o meno su una destinazione. Seleziona **[!UICONTROL All]** per includere tutti i tuoi segmenti nel report.

Utilizza i controlli **Intervallo giorni** e **Da data a** per modificare l&#39;intervallo di look-back. I periodi di lookback di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizzare la casella a discesa **[!UICONTROL Line Item]** per selezionare le proprietà Web per le quali si desidera restituire le informazioni.

Nella casella a discesa **[!UICONTROL Segment Data Source]** selezionare le origini dati contenenti i segmenti che si desidera visualizzare nel report.

Utilizza la casella a discesa **[!UICONTROL Segment]** per selezionare i segmenti da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Line Item IDs], come descritto nel passaggio 3 di [Importare file di dati di Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo si assicura che il report specifichi la proprietà Web come [!UICONTROL Line Item] invece di [!UICONTROL Line Item ID].

## Interpretazione dei risultati {#interpreting-results}

Il report [!UICONTROL Segment Performance] potrebbe essere simile a quello riportato di seguito. Nel rapporto, fai clic su una bolla per visualizzare i dati sottostanti. Per ulteriori informazioni, consulta la descrizione nella tabella seguente il rapporto di esempio.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Segmento </p> </td> 
   <td colname="col2"> <p>Il nome alfanumerico assegnato a questo segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID segmento </p> </td> 
   <td colname="col2"> <p>ID univoco di questo segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Voce </p> </td> 
   <td colname="col2"> <p>La proprietà web per la quale stai visualizzando questo rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clic </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica hanno fatto clic su elementi nella proprietà Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressioni </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica sono stati esposti al tuo inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tasso di click-through </p> </td> 
   <td colname="col2"> <p>Percentuale di click-through. </p> <p>Questa metrica inoltra la percentuale di impression seguita da clic. Per ottenere questa metrica, dividi i clic per impression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Popolazione del segmento in tempo reale </p> </td> 
   <td colname="col2"> <p>Numero effettivo di visitatori univoci visualizzati in tempo reale per l'intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visualizzati da <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come leggere i risultati dei segmenti mappati {#read-mapped-segment}

La posizione dei segmenti mappati in un rapporto può indicarti molto quali segmenti hanno prestazioni migliori e dove potresti dover apportare alcune modifiche.

Per leggere il rapporto, è utile dividere i risultati in quattro sezioni con linee immaginarie (in rosso) e le categorie mostrate nel rapporto di esempio seguente. Le etichette nell’esempio possono aiutarti a comprendere le prestazioni dei segmenti e come rispondere a questi risultati.

![](assets/publisher_segment_performance_mapped.png)

## Come leggere i risultati dei segmenti non mappati {#read-unmapped-segment}

Osservare i segmenti non mappati in un report [!UICONTROL Segment Performance] è un ottimo modo per trovare nuovi segmenti che non hai considerato per il targeting. Infatti, alcuni di questi segmenti potrebbero avere prestazioni superiori a quelle dei segmenti mappati.

Per leggere questo rapporto, è utile dividere i risultati in quattro sezioni con linee immaginarie (in rosso) e categorie visualizzate nel rapporto di esempio seguente.

![](assets/publisher_segment_performance_unmapped.png)
