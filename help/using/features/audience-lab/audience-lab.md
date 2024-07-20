---
description: Crea segmenti di test reciprocamente esclusivi nei gruppi di test dei segmenti per confrontare e misurare l’efficacia di destinazioni diverse. È possibile mettere da parte un gruppo di controllo e dividere il segmento in percentuali di un intero, al fine di verificare l’efficacia.
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Creare segmenti di test reciprocamente esclusivi in [!UICONTROL Segment Test Groups] per confrontare e misurare l&#39;efficacia di destinazioni diverse. È possibile mettere da parte un gruppo di controllo e dividere il segmento in percentuali di un intero, al fine di verificare l’efficacia.

## Panoramica {#audience-lab-overview}

[!UICONTROL Audience Lab] utilizza [Collegamento profilo](../../features/profile-merge-rules/merge-rules-overview.md) per eseguire test tra dispositivi diversi. Questo consente a un utente di qualificarsi per lo stesso segmento di test e ricevere lo stesso trattamento tra i dispositivi. I segmenti di test nei gruppi di test erediteranno la [regola di unione profili](../../features/profile-merge-rules/merge-rules-dashboard.md) assegnata al segmento di base.

Nella visualizzazione predefinita [!UICONTROL Audience Lab] viene visualizzata una scheda per ogni gruppo di test. Fare clic su una scheda per accedere alla visualizzazione **[!UICONTROL Test Group]**. Questa visualizzazione include le seguenti informazioni:

* **[Informazioni sui gruppi di test](../../features/audience-lab/audience-lab-information-view.md)**
* **[Reporting sui gruppi di test](../../features/audience-lab/audience-lab-reporting-view.md)**

È possibile creare **fino a 10 gruppi di test**, ciascuno con **fino a 15 segmenti di test**.

![](assets/test-groups-view.PNG)

## Cercare e filtrare gruppi di test {#search-and-filter}

Dopo aver iniziato a creare più gruppi di test con più segmenti di test, può essere più semplice utilizzare la casella di ricerca per trovare un gruppo di test specifico. Puoi cercare un gruppo di test in base a:

* il nome del gruppo di prova;
* Il nome di uno qualsiasi dei segmenti di test nel gruppo di test;
* Descrizione del gruppo di test.

![](assets/search_and_filter_audience_lab.png)

Puoi anche filtrare i gruppi di test per stato. Tutti gli stati disponibili sono descritti nella sezione [Stato](../../features/audience-lab/audience-lab.md#status) seguente.

## [!UICONTROL Status] {#status}

Lo stato di un gruppo di test può essere attivo, pianificato, in pausa, bozza o completato. Ulteriori informazioni su ciascuno di essi nella tabella seguente:

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
   <td colname="col2"> <p>Un gruppo di test <i>attivo</i> indica che i dati sono attualmente inviati alle destinazioni. Premere <b><span class="uicontrol"> Pausa test </span></b> nella scheda <b><span class="uicontrol"> Gruppo di test </span></b> per sospendere l'invio di dati alle destinazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> pianificato </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>pianificato</i> non è ancora attivo ma non può più essere modificato. Diventerà attivo alla data di inizio selezionata nella procedura guidata <b>Crea gruppi di test</b>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ha sospeso </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>messo in pausa</i> al momento non invia dati alle destinazioni. Premere <b><span class="uicontrol"> Rendi attivo </span></b> nella scheda del gruppo di test </span></b> di <b><span class="uicontrol"> per riprendere a inviare caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> bozza </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>bozza</i> non è ancora attivo e può essere modificato. Non invia ancora dati alle destinazioni mappate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> completato </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>completato</i> ha raggiunto la data di fine selezionata nella procedura guidata <b><span class="uicontrol"> per la creazione di gruppi di test </span></b> e ha interrotto l'invio dei dati di reporting. </p> </td>
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
   <td colname="col2"> <p>Disponibile <b>solo</b> per i gruppi di test bozza. Consente di riprendere la procedura guidata Crea nuovo gruppo di test </span></b> di <b><span class="uicontrol">. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausa </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per i gruppi di test attivi. Consente di sospendere l’invio dei segmenti di test alle destinazioni. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rendi attivo </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per i gruppi di test in pausa. Consente di riprendere l’invio dei segmenti di test alle destinazioni. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Visualizzazione </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per i gruppi di test completati. Consente di visualizzare le informazioni di reporting generate dal test. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> duplicato </span></b> </p> </td>
   <td colname="col2"> <p>Consente di creare un nuovo gruppo di test con la stessa configurazione di quello che si sta duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Elimina </span></b> </p> </td>
   <td colname="col2"> <p>Consente di eliminare un gruppo di test. I segmenti di test non verranno mappati dalle destinazioni; i segmenti della linea di base e le caratteristiche di conversione associati al gruppo di test sono completamente modificabili. Se lo desideri, un avviso ti chiederà di scaricare il file CSV quando elimini un gruppo di test per salvare il reporting. </p> </td>
  </tr>
 </tbody>
</table>
