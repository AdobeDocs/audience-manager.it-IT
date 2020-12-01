---
description: Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati in base alle impression e alle analisi dei segmenti in tempo reale. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confrontando questi diversi tipi di segmenti all'interno e tra i rapporti è possibile ottimizzare le campagne esistenti e individuare i segmenti trascurati che è possibile inviare a una destinazione per il targeting.
seo-description: Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati in base alle impression e alle analisi dei segmenti in tempo reale. Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting. Confrontando questi diversi tipi di segmenti all'interno e tra i rapporti è possibile ottimizzare le campagne esistenti e individuare i segmenti trascurati che è possibile inviare a una destinazione per il targeting.
seo-title: Rapporto sulle prestazioni dei segmenti
solution: Audience Manager
title: Rapporto sulle prestazioni dei segmenti
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 2%

---


# Rapporto sulle prestazioni dei segmenti{#segment-performance-report}

Il rapporto Prestazioni segmento confronta i segmenti mappati e non mappati in base alle impression e alle analisi dei segmenti in tempo reale.

Un segmento mappato è un segmento creato e inviato a una destinazione per il targeting. Un segmento non mappato è un segmento creato ma non inviato a una destinazione per il targeting.

Confrontando questi diversi tipi di segmenti all&#39;interno e tra i rapporti è possibile ottimizzare le campagne esistenti e individuare i segmenti trascurati che è possibile inviare a una destinazione per il targeting.

## Casi d&#39;uso {#use-cases}

Il rapporto [!UICONTROL Segment Performance] consente di:

* Identificare i segmenti di pubblico mappati che determinano scala o prestazioni.
* Identificare i segmenti non mappati da introdurre nelle campagne future, in base al contributo di un&#39;audience alle prestazioni passate.

## Utilizzo del report Prestazioni segmento {#using-segment-performance-report}

Passa da **[!UICONTROL Mapped]** a **[!UICONTROL Unmapped]** per selezionare o meno i segmenti mappati a una destinazione. Selezionare **[!UICONTROL All]** per includere tutti i segmenti nel rapporto.

Utilizzare i controlli **Intervallo di giorni** e **Date Through** per regolare l&#39;intervallo di look-back. I periodi di lookback di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizzate la casella a discesa **[!UICONTROL Line Item]** per selezionare le proprietà Web per le quali desiderate restituire informazioni.

Nella casella a discesa **[!UICONTROL Segment Data Source]**, seleziona le origini dati contenenti i segmenti che desideri vedere nel rapporto.

Utilizzate la casella a discesa **[!UICONTROL Segment]** per selezionare i segmenti da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Line Item IDs], come descritto nel passaggio 3 di [Importa file di dati Google Ad Manager (precedentemente DFP) in  Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). A questo scopo, assicuratevi che il rapporto descriva la proprietà Web come [!UICONTROL Line Item] anziché come [!UICONTROL Line Item ID].

## Interpretazione dei risultati {#interpreting-results}

Il report [!UICONTROL Segment Performance] potrebbe essere simile a quello riportato di seguito. Nel rapporto, fai clic su una bolla per visualizzare i dati sottostanti. Vedere le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

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
   <td colname="col2"> <p>ID univoco del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Voce </p> </td> 
   <td colname="col2"> <p>Proprietà Web per la quale viene visualizzato il rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clic </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica hanno fatto clic sugli elementi nella proprietà Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressioni </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica sono stati esposti al tuo inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Frequenza di click-through. </p> <p>Questa metrica invia la percentuale di impression seguita da clic. Dividi clic per impression per ottenere questa metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Popolazione segmento Real-time </p> </td> 
   <td colname="col2"> <p>Il numero effettivo di visitatori univoci visti in tempo reale per l'intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti da <span class="keyword">  Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come leggere i risultati del segmento mappato {#read-mapped-segment}

La posizione dei segmenti mappati in un report può fornire informazioni dettagliate sui segmenti che ottengono buoni risultati e sui punti in cui potrebbe essere necessario apportare alcune modifiche.

Per leggere il rapporto, è utile suddividere i risultati in quattro sezioni con linee immaginarie (in rosso) e le categorie indicate nel rapporto campione riportato di seguito. Le etichette nell&#39;esempio consentono di comprendere le prestazioni dei segmenti e come rispondere a tali risultati.

![](assets/publisher_segment_performance_mapped.png)

## Come leggere i risultati del segmento non mappato {#read-unmapped-segment}

Osservare i segmenti non mappati in un report [!UICONTROL Segment Performance] è un ottimo modo per trovare nuovi segmenti che non hai considerato per il targeting. In realtà, alcuni di questi segmenti potrebbero superare i segmenti mappati.

Per leggere questo rapporto, è utile dividere i risultati in quattro sezioni con linee immaginarie (in rosso) e categorie mostrate nel rapporto di esempio seguente.

![](assets/publisher_segment_performance_unmapped.png)
