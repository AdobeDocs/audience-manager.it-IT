---
description: Crea segmenti di test reciprocamente esclusivi nei gruppi di test dei segmenti per confrontare e misurare l’efficacia di destinazioni diverse. È possibile impostare un gruppo di controllo e dividere il segmento in percentuali di un intero, al fine di verificare l'efficacia.
seo-description: Crea segmenti di test reciprocamente esclusivi nei gruppi di test dei segmenti per confrontare e misurare l’efficacia di destinazioni diverse. È possibile impostare un gruppo di controllo e dividere il segmento in percentuali di un intero, al fine di verificare l'efficacia.
seo-title: 'Audience Lab '
solution: Audience Manager
title: 'Audience Lab '
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: 'Audience Lab '
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 4%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Crea segmenti di test reciprocamente esclusivi in [!UICONTROL Segment Test Groups] per confrontare e misurare l’efficacia di destinazioni diverse. È possibile impostare un gruppo di controllo e dividere il segmento in percentuali di un intero, al fine di verificare l&#39;efficacia.

## Panoramica {#audience-lab-overview}

[!UICONTROL Audience Lab] utilizza  [il ](../../features/profile-merge-rules/merge-rules-overview.md) collegamento profilo per alimentare i test tra dispositivi. In questo modo un utente si qualifica per lo stesso segmento di test e riceve lo stesso trattamento tra i dispositivi. I segmenti di test nei gruppi di test erediteranno la [regola di unione profili](../../features/profile-merge-rules/merge-rules-dashboard.md) che il segmento di base gli è stato assegnato.

La visualizzazione predefinita [!UICONTROL Audience Lab] visualizza una scheda per ciascuno dei gruppi di test. Fai clic su una scheda per accedere alla visualizzazione **[!UICONTROL Test Group]**. Questa visualizzazione include le seguenti informazioni:

* **[Informazioni sui gruppi di test](../../features/audience-lab/audience-lab-information-view.md)**
* **[Reporting sui gruppi di test](../../features/audience-lab/audience-lab-reporting-view.md)**

Puoi creare **fino a 10 gruppi di test**, ciascuno con **fino a 15 segmenti di test**.

![](assets/test-groups-view.PNG)

## Gruppi di test di ricerca e filtro {#search-and-filter}

Una volta avviata la creazione di più gruppi di test con più segmenti di test, potrebbe essere più semplice utilizzare la casella di ricerca per trovare un gruppo di test specifico. Puoi cercare un gruppo di test per:

* il nome del gruppo di prova;
* Nome di uno qualsiasi dei segmenti di test nel gruppo di test;
* Descrizione del gruppo di prova.

![](assets/search_and_filter_audience_lab.png)

Puoi anche filtrare i gruppi di test per stato. Tutti gli stati disponibili sono descritti nella sezione [Stato](../../features/audience-lab/audience-lab.md#status) di seguito.

## [!UICONTROL Status] {#status}

Lo stato di un gruppo di test può essere attivo, pianificato, messo in pausa, bozza o completato. Ulteriori informazioni su ciascuno di essi nella tabella seguente:

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
   <td colname="col2"> <p>Un gruppo di test <i>attivo</i> indica che i dati sono attualmente inviati alle destinazioni. Premi <b><span class="uicontrol"> Sospendi test </span></b> nella scheda <b><span class="uicontrol"> Gruppo di test </span></b> per sospendere l’invio di dati alle destinazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pianificato </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>pianificato</i> non è ancora attivo ma non può più essere modificato. Diventerà attivo alla data di inizio selezionata nella procedura guidata <b>Crea gruppi di test</b>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> In pausa  </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>messo in pausa</i> al momento non invia dati alle destinazioni. Premi <b><span class="uicontrol"> Rendi attivo </span></b> nella scheda <b><span class="uicontrol"> Gruppo di test </span></b> per riprendere le caratteristiche di invio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bozza </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>bozza</i> non è ancora attivo e può essere modificato. Non invia ancora dati alle destinazioni mappate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completato </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>completato</i> ha raggiunto la data di fine selezionata nella procedura guidata <b><span class="uicontrol"> Crea gruppi di test </span></b> e ha interrotto l’invio dei dati di reporting. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

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
   <td colname="col2"> <p>Disponibile <b>solo</b> per gruppi di test bozza. Consente di riprendere la procedura guidata <b><span class="uicontrol"> Crea nuovo gruppo di test </span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausa  </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per i gruppi di test attivi. Consente di mettere in pausa l’invio dei segmenti di test alle destinazioni. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rendi attivo  </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per gruppi di test in pausa. Consente di riprendere l’invio dei segmenti di test alle destinazioni. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Visualizzazione </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per i gruppi di test completati. Consente di visualizzare le informazioni di reporting generate dal test. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplica  </span></b> </p> </td>
   <td colname="col2"> <p>Ti consente di creare un nuovo gruppo di test con la stessa configurazione di quello che stai duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Elimina </span></b> </p> </td>
   <td colname="col2"> <p>Consente di eliminare un gruppo di test. I segmenti di test non saranno mappati dalle destinazioni, il segmento della linea di base e le caratteristiche di conversione associate al gruppo di test sono completamente modificabili. Se lo desideri, viene richiesto di scaricare il file CSV quando elimini un gruppo di test per salvare il rapporto. </p> </td>
  </tr>
 </tbody>
</table>
