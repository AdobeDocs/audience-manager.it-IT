---
description: Crea segmenti di test mutualmente esclusivi nei gruppi di test segmenti per confrontare e misurare l'efficacia di diverse destinazioni. Puoi impostare un gruppo di controllo e dividere il segmento in percentuali di un intero, per testare l'efficacia.
seo-description: Crea segmenti di test mutualmente esclusivi nei gruppi di test segmenti per confrontare e misurare l'efficacia di diverse destinazioni. Puoi impostare un gruppo di controllo e dividere il segmento in percentuali di un intero, per testare l'efficacia.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: API DIL
uuid: aaee 820 c -1 e 78-4 fd 4-bd 8 f -2629085 d 78 e 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. Puoi impostare un gruppo di controllo e dividere il segmento in percentuali di un intero, per testare l'efficacia.

## Panoramica {#audience-lab-overview}

[!UICONTROL Audience Lab] utilizza [Collegamento](../../features/profile-merge-rules/merge-rules-overview.md) profilo per abilitare la verifica cross-device. Questo consente di garantire che un utente sia idoneo per lo stesso segmento di test e riceva lo stesso trattamento tra i dispositivi. The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

The [!UICONTROL Audience Lab] default view displays a card for each of the test groups. Click a card to access the **[!UICONTROL Test Group]** view. Questa vista include le informazioni seguenti:

* **[Test Group Information (Informazioni gruppo di test)](../../features/audience-lab/audience-lab-information-view.md)**
* **[Test dei rapporti di gruppo](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

Dopo aver iniziato a creare più gruppi di test con più segmenti di test, potrebbe essere più semplice utilizzare la casella di ricerca per trovare un gruppo di test specifico. Potete cercare un gruppo di test:

* Nome del gruppo di prova;
* Il nome di uno qualsiasi dei segmenti di prova nel gruppo di test;
* Descrizione del gruppo di test.

![](assets/search_and_filter_audience_lab.png)

Potete anche filtrare i gruppi di test per stato. All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## Stato {#status}

Lo stato di un gruppo di test può essere attivo, pianificato, messo in pausa, bozza o completato. Maggiori informazioni su ciascuno di essi nella tabella seguente:

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Stato </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Attivo </span></b> </p> </td> 
   <td colname="col2"> <p>An <i>active</i> test group means that data is currently being sent to destinations. Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pianificato </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>scheduled</i> test group is not yet active but cannot be edited anymore. It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> In pausa </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>paused</i> test group does not currently send data to destinations. Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bozza </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>draft</i> test group is not yet active and can still be edited. Non invia ancora dati alle destinazioni mappate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completato </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>completed</i> test group has reached the end date you selected in the <b><span class="uicontrol"> Create Test Groups </span></b> wizard and has stopped sending reporting data. </p> </td>
  </tr>
 </tbody>
</table>

## Azioni {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Azioni </th> 
   <th colname="col2" class="entry"> Descrizione </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Modifica </span></b> </p> </td>
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausa </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per gruppi di test attivi. Consente di mettere in pausa l'invio dei segmenti di prova alle destinazioni. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rendi attivo </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per gruppi di test messi in pausa. Consente di riprendere l'invio dei segmenti di prova alle destinazioni. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Visualizzazione </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per gruppi di test completati. Consente di visualizzare le informazioni di reporting generate dal test. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplica </span></b> </p> </td>
   <td colname="col2"> <p>Consente di creare un nuovo gruppo di test con la stessa configurazione di quella che stai duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Elimina </span></b> </p> </td>
   <td colname="col2"> <p>Consente di eliminare un gruppo di test. I segmenti di prova non saranno mappati dalle destinazioni, il segmento della linea di base e le caratteristiche di conversione associate al gruppo di test sono modificabili. Un avviso vi chiede di scaricare il file CSV quando eliminate un gruppo di prova per salvarlo, se lo desiderate. </p> </td>
  </tr>
 </tbody>
</table>