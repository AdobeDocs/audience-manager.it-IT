---
description: Il rapporto Performance Performance (Prestazioni segmento) confronta i segmenti mappati e non mappati con impression e con Uniques segmento Real-Time. Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting. Il confronto tra questi tipi di segmenti diversi all'interno e tra i rapporti consente di ottimizzare le campagne esistenti e individuare segmenti trascurati che potresti desiderare inviare a una destinazione per il targeting.
seo-description: Il rapporto Performance Performance (Prestazioni segmento) confronta i segmenti mappati e non mappati con impression e con Uniques segmento Real-Time. Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting. Il confronto tra questi tipi di segmenti diversi all'interno e tra i rapporti consente di ottimizzare le campagne esistenti e individuare segmenti trascurati che potresti desiderare inviare a una destinazione per il targeting.
seo-title: Report sulle prestazioni dei segmenti
solution: Audience Manager
title: Report sulle prestazioni dei segmenti
uuid: c 9 a 1 e 9 ad -4 f 3 f -4334-a 3 ff -0 f 241 c 7303 c 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Report sulle prestazioni dei segmenti{#segment-performance-report}

Il rapporto Performance Performance (Prestazioni segmento) confronta i segmenti mappati e non mappati con impression e con Uniques segmento Real-Time.

Un segmento mappato è un segmento che crei e invia a una destinazione per il targeting. Un segmento non mappato è un segmento che hai creato ma non è stato inviato a una destinazione per il targeting.

Il confronto tra questi tipi di segmenti diversi all&#39;interno e tra i rapporti consente di ottimizzare le campagne esistenti e individuare segmenti trascurati che potresti desiderare inviare a una destinazione per il targeting.

## Casi d&#39;uso {#use-cases}

Con il [!UICONTROL Segment Performance] rapporto potete:

* Identifica segmenti di pubblico mappati che stimolano la scala o le prestazioni.
* Identifica i segmenti non mappati da introdurre in campagne future, in base al contributo di un pubblico alle prestazioni passate.

## Utilizzo del rapporto Prestazioni segmento {#using-segment-performance-report}

Alterna **[!UICONTROL Mapped]** e **[!UICONTROL Unmapped]** seleziona i segmenti mappati a una destinazione o meno. Seleziona **[!UICONTROL All]** per includere tutti i segmenti nel rapporto.

Utilizza i **controlli Intervallo** giorno e **Data mediante** per regolare l&#39;intervallo di look-back. I periodi di look-back di 7 giorni e 30 giorni sono disponibili solo per le date domenica.

Utilizzate il **[!UICONTROL Line Item]** menu a discesa per selezionare le proprietà Web per le quali desiderate restituire le informazioni.

Nel menu **[!UICONTROL Segment Data Source]** a discesa, seleziona le origini dati contenenti i segmenti che desideri vedere nel rapporto.

Utilizza il **[!UICONTROL Segment]** menu a discesa per selezionare i segmenti da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando abilitate [!UICONTROL Audience Optimization for Publishers], dovete includere metadati descrittivi per [!UICONTROL Line Item IDs], come descritto nel Passaggio 3 di [Importa file di dati DFP in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In tal modo, assicuratevi che il report contenga la proprietà Web come [!UICONTROL Line Item] invece [!UICONTROL Line Item ID]della proprietà.

## Interpretazione dei risultati {#interpreting-results}

[!UICONTROL Segment Performance] Il rapporto potrebbe essere simile a quello di seguito. Nel rapporto, fai clic su una bolla per visualizzare i dati sottostanti. Vedere descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

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
   <td colname="col2"> <p>L'ID univoco di questo segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elemento linea </p> </td> 
   <td colname="col2"> <p>La proprietà Web per la quale stai visualizzando il rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clic </p> </td> 
   <td colname="col2"> <p>Numero di volte in cui i membri di questa caratteristica hanno fatto clic sugli elementi nella proprietà Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressioni </p> </td> 
   <td colname="col2"> <p>Numero di volte in cui i membri di questa caratteristica sono stati esposti alle scorte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Tasso di click-through. </p> <p>Questa metrica rimuove la percentuale di impression seguito dai clic. Divide i clic per impression per ottenere questa metrica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Popolazione segmenti in tempo reale </p> </td> 
   <td colname="col2"> <p>Il numero effettivo di visitatori unici visti in tempo reale per l'intervallo di tempo specificato e che sono stati qualificati per il segmento nel momento in cui sono stati visti <span class="keyword"> da Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come leggere i risultati dei segmenti mappati {#read-mapped-segment}

La posizione dei segmenti mappati in un rapporto può indicare molto sui segmenti che funzionano bene e dove potrebbe essere necessario apportare alcune modifiche.

Per leggere il rapporto, è utile dividere i risultati in quattro sezioni con righe immaginarie (in rosso) e le categorie mostrate nel rapporto di esempio sottostante. Le etichette dell&#39;esempio possono aiutarti a comprendere le prestazioni dei segmenti e a come rispondere a tali risultati.

![](assets/publisher_segment_performance_mapped.png)

## Come leggere i risultati dei segmenti non mappati {#read-unmapped-segment}

L&#39;aspetto dei segmenti non mappati in un [!UICONTROL Segment Performance] rapporto è un modo eccellente per trovare nuovi segmenti che non sono considerati per il targeting. In effetti, alcuni di questi segmenti possono prevalere sui segmenti mappati.

Per leggere questo rapporto, è utile dividere i risultati in quattro sezioni con righe immaginarie (in rosso) e categorie mostrate nel rapporto di esempio sottostante.

![](assets/publisher_segment_performance_unmapped.png)
