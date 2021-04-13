---
description: Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati per impression e analisi dei segmenti in tempo reale. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confrontando questi diversi tipi di segmenti all’interno dei rapporti e tra di essi è possibile ottimizzare le campagne esistenti e trovare segmenti trascurati che è possibile inviare a una destinazione per il targeting.
seo-description: Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati per impression e analisi dei segmenti in tempo reale. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confrontando questi diversi tipi di segmenti all’interno dei rapporti e tra di essi è possibile ottimizzare le campagne esistenti e trovare segmenti trascurati che è possibile inviare a una destinazione per il targeting.
seo-title: Rapporto sulle prestazioni dei segmenti
solution: Audience Manager
title: Rapporto sulle prestazioni dei segmenti per gli editori
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Rapporti di Audience Optimization
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# Rapporto sulle prestazioni dei segmenti{#segment-performance-report}

Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati per impression e analisi dei segmenti in tempo reale.

Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting.

Confrontando questi diversi tipi di segmenti all’interno dei rapporti e tra di essi è possibile ottimizzare le campagne esistenti e trovare segmenti trascurati che è possibile inviare a una destinazione per il targeting.

## Casi d&#39;uso {#use-cases}

Con il rapporto [!UICONTROL Segment Performance] puoi:

* Identifica i segmenti di pubblico mappati che determinano scala o prestazioni.
* Identifica i segmenti non mappati da introdurre nelle campagne future, in base al contributo di un pubblico alle prestazioni passate.

## Utilizzo del rapporto Prestazioni segmento {#using-segment-performance-report}

Passa da **[!UICONTROL Mapped]** a **[!UICONTROL Unmapped]** per selezionare i segmenti mappati a una destinazione o meno. Seleziona **[!UICONTROL All]** per includere tutti i segmenti nel rapporto.

Utilizza i controlli **Intervallo giorno** e **Date Through** per regolare l&#39;intervallo di look-back. I periodi di look-back di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizza la casella a discesa **[!UICONTROL Line Item]** per selezionare le proprietà Web per le quali desideri restituire informazioni.

Nella casella a discesa **[!UICONTROL Segment Data Source]** , seleziona le origini dati contenenti i segmenti che desideri visualizzare nel rapporto.

Utilizza la casella a discesa **[!UICONTROL Segment]** per selezionare i segmenti da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando abiliti [!UICONTROL Audience Optimization for Publishers], devi includere metadati descrittivi per [!UICONTROL Line Item IDs], come descritto nel passaggio 3 di [Importa file di dati Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo, assicurati che il report descriva la proprietà Web come [!UICONTROL Line Item] invece del [!UICONTROL Line Item ID].

## Interpretazione dei risultati {#interpreting-results}

Il rapporto [!UICONTROL Segment Performance] potrebbe essere simile a quello riportato di seguito. Nel rapporto fare clic su una bolla per visualizzare i dati sottostanti. Vedi le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto di esempio.

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
   <td colname="col2"> <p>Nome alfanumerico assegnato al segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID segmento </p> </td> 
   <td colname="col2"> <p>ID univoco del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Voce </p> </td> 
   <td colname="col2"> <p>La proprietà Web per la quale viene visualizzato questo rapporto. </p> </td> 
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
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Frequenza di click-through. </p> <p>Questa metrica inoltra la percentuale di impression seguita dai clic. Dividi clic per impression per ottenere questa metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Popolazione di segmenti in tempo reale </p> </td> 
   <td colname="col2"> <p>Il numero effettivo di visitatori unici visti in tempo reale per l'intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti da <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come leggere i risultati del segmento mappato {#read-mapped-segment}

La posizione dei segmenti mappati in un rapporto può dirvi molto su quali segmenti stanno ottenendo buoni risultati e dove potrebbe essere necessario apportare alcune modifiche.

Per leggere il rapporto, aiuta a dividere i risultati in quattro sezioni con linee immaginarie (in rosso) e le categorie mostrate nel rapporto di esempio sottostante. Le etichette nell’esempio possono aiutarti a comprendere le prestazioni dei segmenti e come rispondere a questi risultati.

![](assets/publisher_segment_performance_mapped.png)

## Come leggere i risultati dei segmenti non mappati {#read-unmapped-segment}

Osservare i segmenti non mappati in un rapporto [!UICONTROL Segment Performance] è un ottimo modo per trovare nuovi segmenti che non hai considerato per il targeting. Infatti, alcuni di questi segmenti possono superare i segmenti mappati.

Per leggere questo rapporto, aiuta a dividere i risultati in quattro sezioni con linee immaginarie (in rosso) e categorie mostrate nel rapporto di esempio sottostante.

![](assets/publisher_segment_performance_unmapped.png)
