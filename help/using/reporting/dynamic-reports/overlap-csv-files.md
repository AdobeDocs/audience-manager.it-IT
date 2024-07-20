---
description: È possibile richiedere un file .csv per un rapporto di sovrapposizione quando tale rapporto raggiunge il limite di 1 milione di record. Un report potrebbe aver raggiunto questo limite quando viene visualizzato il messaggio "Si è verificato un errore imprevisto". Contatta l’Assistenza clienti per richiedere un file .csv compresso, che puoi importare e utilizzare nel tuo sistema di database. I file sono disponibili per i rapporti di sovrapposizione segmento-segmento, segmento-caratteristica e caratteristica-caratteristica.
seo-description: You can request a .csv file for an Overlap Report when that report reaches its 1-million record limit. A report may have reached this limit when you see an "Unexpected error has occurred" message. Contact Customer Care to request a compressed .csv file, which you can import and work with in your own database system. Files are available for segment-to-segment, segment-to-trait, and trait-to-trait overlap reports.
seo-title: CSV Files for Overlap Reports
solution: Audience Manager
title: File CSV per rapporti di sovrapposizione
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: Overlap Reports
exl-id: 759c39cb-64ec-47dd-a3a4-027408aa6b5e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 2%

---

# File CSV per rapporti di sovrapposizione{#csv-files-for-overlap-reports}

È possibile richiedere un file .csv per un rapporto di sovrapposizione quando tale rapporto raggiunge il limite di 1 milione di record. Un report potrebbe aver raggiunto questo limite quando viene visualizzato il messaggio &quot;Si è verificato un errore imprevisto&quot;. Contatta l’Assistenza clienti per richiedere un file .csv compresso, che puoi importare e utilizzare nel tuo sistema di database. I file sono disponibili per i rapporti di sovrapposizione segmento-segmento, segmento-caratteristica e caratteristica-caratteristica.

## Metadati nome file {#file-name-metadata}

Nella tabella seguente sono elencate e descritte le convenzioni di denominazione e le estensioni utilizzate in un file csv di sovrapposizione. Negli esempi, il *corsivo* indica un segnaposto variabile.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento metadati </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Estensione file </p> </td> 
   <td colname="col2"> <p>I file dei report di sovrapposizione sono compressi con GZIP e hanno estensione <code> .gz</code>. È necessario aggiungere l'estensione <code> .csv</code> al file dopo la decompressione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome file </p> </td> 
   <td colname="col2"> <p>Sintassi nome file: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">File da segmento a segmento: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">File segmento-caratteristica: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">File di caratteristiche: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo date </p> </td> 
   <td colname="col2"> <p>L’intervallo di date per un rapporto è un ID di 5 cifre che include: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> per un rapporto di 7 giorni. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> per un report di 30 giorni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Più file </p> </td> 
   <td colname="col2"> <p>Se un rapporto contiene più file, viene incrementata l’ultima cifra nel nome del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esempi </p> </td> 
   <td colname="col2"> <p>Esempi di nomi di file per un singolo rapporto: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">File singolo di 7 giorni: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Singolo file di 30 giorni: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Esempi di nomi di file per un report con più file: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contenuto file {#file-contents}

Nel file, i dati stringa sono racchiusi tra virgolette doppie. Vedi i dati fittizi di seguito. Questa schermata è stata troncata per brevità e per adattarla allo schermo.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Record dei rapporti segmento-segmento {#segment-segment-records}

Un file di dati per il [report di sovrapposizione segmento-segmento](segment-segment-overlap-report.md) contiene i record seguenti.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>ID del segmento da confrontare con il segmento di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>Nome del segmento che si sta confrontando con i segmenti della linea di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>ID del segmento della linea di base. Il segmento della linea di base è il segmento che desideri confrontare con altri segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>Nome del segmento della linea di base che si sta confrontando con altri segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>È possibile ottenere rapporti per intervalli di look-back di 7 e 30 giorni. <code> rangeid</code> corrisponde agli intervalli di tempo riportati di seguito. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 giorni </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione di un report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci nel segmento da confrontare con il segmento di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci nel segmento della linea di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Un conteggio totale della sovrapposizione di utenti univoci tra il segmento della linea di base e gli altri segmenti selezionati per il confronto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>La percentuale di sovrapposizione di utenti univoci tra il segmento della linea di base e gli altri segmenti selezionati per il confronto. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Record rapporto segmento-caratteristica {#segment-trait-records}

Un file di dati per il [report di sovrapposizione segmento-caratteristica](segment-trait-overlap-report.md) contiene i record seguenti.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nome della caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>ID del provider di dati. Gli ID includono: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nome del provider di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>È possibile ottenere rapporti per intervalli di look-back di 7 e 30 giorni. <code> rangeid</code> corrisponde agli intervalli di tempo riportati di seguito. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 giorni </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione di un report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci nel segmento selezionato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci in una caratteristica. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci condivisi tra i segmenti e le caratteristiche selezionati. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% di utenti univoci che si sovrappongono tra caratteristica e segmento. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% di utenti univoci che si sovrappongono tra il segmento e la caratteristica. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Record di rapporti caratteristica-caratteristica {#trait-trait-records}

Un file di dati per il [rapporto di sovrapposizione caratteristica-caratteristica](trait-trait-overlap-report.md) contiene i record seguenti.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID della caratteristica da confrontare con la caratteristica linea di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nome della caratteristica da confrontare con la caratteristica linea di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID della caratteristica linea di base. La caratteristica linea di base è la caratteristica che desideri confrontare con altre caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nome della caratteristica linea di base da confrontare con altre caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>ID del provider di dati. Gli ID includono: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nome del provider di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>È possibile ottenere rapporti per intervalli di look-back di 7 e 30 giorni. <code> rangeid</code> corrisponde agli intervalli di tempo riportati di seguito. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 giorni </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione di un report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci condivisi tra le caratteristiche selezionate. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci in una caratteristica di base. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci condivisi tra le caratteristiche selezionate. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% di utenti univoci con sovrapposizione tra le caratteristiche selezionate. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% di utenti univoci con sovrapposizione tra le caratteristiche selezionate. Nel rapporto dell’interfaccia utente, questo numero viene visualizzato nella finestra pop-up quando passi il cursore su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
 </tbody> 
</table>
