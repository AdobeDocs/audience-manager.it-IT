---
description: Crea segmenti di test che si escludono a vicenda in Gruppi di test dei segmenti per confrontare e misurare l’efficacia delle diverse destinazioni. È possibile impostare un gruppo di controllo e suddividere il segmento in percentuali di un intero, al fine di verificare l'efficacia.
seo-description: Crea segmenti di test che si escludono a vicenda in Gruppi di test dei segmenti per confrontare e misurare l’efficacia delle diverse destinazioni. È possibile impostare un gruppo di controllo e suddividere il segmento in percentuali di un intero, al fine di verificare l'efficacia.
seo-title: 'Audience Lab '
solution: Audience Manager
title: 'Audience Lab '
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 3%

---


# [!UICONTROL Audience Lab] {#audience-lab}

Crea segmenti di test che si escludono a vicenda in [!UICONTROL Segment Test Groups] per confrontare e misurare l&#39;efficacia delle diverse destinazioni. È possibile impostare un gruppo di controllo e suddividere il segmento in percentuali di un intero, al fine di verificare l&#39;efficacia.

## Panoramica {#audience-lab-overview}

[!UICONTROL Audience Lab] utilizza  [Profile ](../../features/profile-merge-rules/merge-rules-overview.md) Linkto per il test cross-device. In questo modo l&#39;utente si qualifica per lo stesso segmento di test e riceve lo stesso trattamento tra i dispositivi. I segmenti di test nei gruppi di test erediteranno la [Regola di unione dei profili](../../features/profile-merge-rules/merge-rules-dashboard.md) assegnata al segmento di base.

La vista predefinita [!UICONTROL Audience Lab] visualizza una scheda per ciascuno dei gruppi di test. Fate clic su una scheda per accedere alla vista **[!UICONTROL Test Group]**. Questa visualizzazione include le informazioni seguenti:

* **[Informazioni sui gruppi di test](../../features/audience-lab/audience-lab-information-view.md)**
* **[Reporting sui gruppi di test](../../features/audience-lab/audience-lab-reporting-view.md)**

È possibile creare fino a 10 gruppi di test **ciascuno con** fino a 15 segmenti di test **.**

![](assets/test-groups-view.PNG)

## Gruppi di test di ricerca e filtro {#search-and-filter}

Dopo aver iniziato a creare più gruppi di test con più segmenti, potrebbe essere più semplice utilizzare la casella di ricerca per trovare un gruppo di test specifico. Potete cercare un gruppo di test per:

* il nome del gruppo di prova;
* Il nome di uno qualsiasi dei segmenti di test nel gruppo di test;
* Descrizione del gruppo di test.

![](assets/search_and_filter_audience_lab.png)

Potete anche filtrare i gruppi di test per stato. Tutti gli stati disponibili sono descritti nella sezione [Stato](../../features/audience-lab/audience-lab.md#status) seguente.

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
   <td colname="col2"> <p>Un gruppo di test <i>attivo</i> indica che i dati sono attualmente inviati alle destinazioni. Premere <b><span class="uicontrol"> Sospendi test </span></b> nella scheda <b><span class="uicontrol"> Gruppo di test </span></b> per sospendere l'invio di dati alle destinazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pianificato </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>pianificato</i> non è ancora attivo ma non può essere modificato. Diventerà attivo alla data di inizio selezionata nella procedura guidata <b>Crea gruppi di test</b>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> In pausa  </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>pause</i> attualmente non invia dati alle destinazioni. Premere <b><span class="uicontrol"> Rendi attivo </span></b> nella scheda <b><span class="uicontrol"> Gruppo di test </span></b> per riprendere le caratteristiche di invio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bozza </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>draft</i> non è ancora attivo e può essere modificato. Non invia ancora dati alle destinazioni mappate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completato </span></b> </p> </td> 
   <td colname="col2"> <p>Un gruppo di test <i>completato</i> ha raggiunto la data di fine selezionata nella procedura guidata <b><span class="uicontrol"> Crea gruppi di test </span></b> e ha interrotto l'invio dei dati di reporting. </p> </td>
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
   <td colname="col2"> <p>Disponibile <b>solo</b> per i gruppi di prova delle bozze. Consente di riprendere la procedura guidata <b><span class="uicontrol"> Crea nuovo gruppo di test </span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausa  </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per i gruppi di test attivi. Consente di mettere in pausa l’invio dei segmenti di test alle destinazioni. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rendi attivo  </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per i gruppi di test messi in pausa. Consente di riprendere l'invio dei segmenti di test alle destinazioni. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Visualizzazione </span></b> </p> </td>
   <td colname="col2"> <p>Disponibile per i gruppi di test completati. Consente di visualizzare le informazioni di reporting generate dal test. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplica  </span></b> </p> </td>
   <td colname="col2"> <p>Consente di creare un nuovo gruppo di test con la stessa configurazione di quello che si sta duplicando. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Elimina </span></b> </p> </td>
   <td colname="col2"> <p>Consente di eliminare un gruppo di test. I segmenti di test non saranno mappati dalle destinazioni, il segmento della linea di base e le caratteristiche di conversione associate al gruppo di test sono completamente modificabili. Viene visualizzato un avviso che richiede di scaricare il file CSV quando eliminate un gruppo di test per salvare il rapporto, se lo desiderate. </p> </td>
  </tr>
 </tbody>
</table>