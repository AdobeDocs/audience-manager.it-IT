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

Crea segmenti di test mutualmente esclusivi in [!UICONTROL Segment Test Groups] modo da confrontare e misurare l&#39;efficacia di diverse destinazioni. Puoi impostare un gruppo di controllo e dividere il segmento in percentuali di un intero, per testare l&#39;efficacia.

## Panoramica {#audience-lab-overview}

[!UICONTROL Audience Lab] utilizza [Collegamento](../../features/profile-merge-rules/merge-rules-overview.md) profilo per abilitare la verifica cross-device. Questo consente di garantire che un utente sia idoneo per lo stesso segmento di test e riceva lo stesso trattamento tra i dispositivi. I segmenti di prova nei gruppi di test erediteranno la [regola](../../features/profile-merge-rules/merge-rules-dashboard.md) Unione profilo assegnata al segmento di base.

La [!UICONTROL Audience Lab] visualizzazione predefinita visualizza una scheda per ciascun gruppo di test. Fate clic su una scheda per accedere alla **[!UICONTROL Test Group]** visualizzazione. Questa vista include le informazioni seguenti:

* **[Test Group Information (Informazioni gruppo di test)](../../features/audience-lab/audience-lab-information-view.md)**
* **[Test dei rapporti di gruppo](../../features/audience-lab/audience-lab-reporting-view.md)**

Potete creare **fino a 10 gruppi di test**, ciascuno con **fino a 15 segmenti di test**.

![](assets/test-groups-view.PNG)

## Cercare e filtrare i gruppi di test {#search-and-filter}

Dopo aver iniziato a creare più gruppi di test con più segmenti di test, potrebbe essere più semplice utilizzare la casella di ricerca per trovare un gruppo di test specifico. Potete cercare un gruppo di test:

* Nome del gruppo di prova;
* Il nome di uno qualsiasi dei segmenti di prova nel gruppo di test;
* Descrizione del gruppo di test.

![](assets/search_and_filter_audience_lab.png)

Potete anche filtrare i gruppi di test per stato. Tutti gli stati disponibili sono descritti nella sezione [Stato](../../features/audience-lab/audience-lab.md#status) di seguito.

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
   <td colname="col2"> <p>Un gruppo di test <i>attivo</i> indica che i dati vengono attualmente inviati alle destinazioni. Premete <b><span class="uicontrol"> Pausa test </span></b> nella scheda Gruppo <b><span class="uicontrol"></span></b> di test per sospendere l'invio di dati alle destinazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pianificato </span></b> </p> </td> 
   <td colname="col2"> <p>Un <i>gruppo</i> di test pianificato non è ancora attivo, ma non può più essere modificato. Verrà attivato alla data di inizio selezionata nella procedura guidata <b>Crea gruppi</b> di test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> In pausa </span></b> </p> </td> 
   <td colname="col2"> <p>Al momento, un <i>gruppo</i> di test in pausa non invia dati alle destinazioni. Premete <b><span class="uicontrol"> Rendi attivo </span></b> nella scheda Gruppo <b><span class="uicontrol"></span></b> di test per riprendere l'invio delle caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bozza </span></b> </p> </td> 
   <td colname="col2"> <p>Un <i>gruppo</i> di test di bozza non è ancora attivo e può ancora essere modificato. Non invia ancora dati alle destinazioni mappate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completato </span></b> </p> </td> 
   <td colname="col2"> <p>Un <i>gruppo</i> di test completato ha raggiunto la data di fine selezionata nella procedura guidata <b><span class="uicontrol"> Crea gruppi </span></b> di test e ha interrotto l'invio di dati di reporting. </p> </td>
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
   <td colname="col2"> <p>Disponibile <b>solo</b> per i gruppi di bozza di bozza. Consente di riprendere la procedura guidata <b><span class="uicontrol"> Crea nuovo gruppo </span></b> di test. </p> </td>
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