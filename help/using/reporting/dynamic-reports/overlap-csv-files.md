---
description: È possibile richiedere un file .csv per rapporti di sovrapposizione quando tale rapporto raggiunge il limite di 1 milione di record. Un report potrebbe aver raggiunto questo limite quando viene visualizzato un messaggio di errore imprevisto. Contatta l’Assistenza clienti per richiedere un file .csv compresso, che puoi importare e utilizzare nel tuo sistema di database. I file sono disponibili per i rapporti di sovrapposizione segmento a segmento, segmento a tratto e tratto.
seo-description: È possibile richiedere un file .csv per rapporti di sovrapposizione quando tale rapporto raggiunge il limite di 1 milione di record. Un report potrebbe aver raggiunto questo limite quando viene visualizzato un messaggio di errore imprevisto. Contatta l’Assistenza clienti per richiedere un file .csv compresso, che puoi importare e utilizzare nel tuo sistema di database. I file sono disponibili per i rapporti di sovrapposizione segmento a segmento, segmento a tratto e tratto.
seo-title: File CSV per rapporti di sovrapposizione
solution: Audience Manager
title: File CSV per rapporti di sovrapposizione
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
translation-type: tm+mt
source-git-commit: d13b32999c5af4d20f33a92dfa805d7fe0babb2d

---


# File CSV per rapporti di sovrapposizione{#csv-files-for-overlap-reports}

È possibile richiedere un file .csv per rapporti di sovrapposizione quando tale rapporto raggiunge il limite di 1 milione di record. Un report potrebbe aver raggiunto questo limite quando viene visualizzato un messaggio di errore imprevisto. Contatta l’Assistenza clienti per richiedere un file .csv compresso, che puoi importare e utilizzare nel tuo sistema di database. I file sono disponibili per i rapporti di sovrapposizione segmento a segmento, segmento a tratto e tratto.

## Metadati nome file {#file-name-metadata}

Nella tabella seguente sono elencate le convenzioni di denominazione dei file e le estensioni di file utilizzate in un file .csv che si sovrappone. Negli esempi, il *corsivo* indica un segnaposto variabile.

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
   <td colname="col2"> <p>I file dei rapporti di sovrapposizione sono compressi con gzip e hanno un'estensione <code> .gz</code> . È necessario aggiungere l'estensione <code> .csv</code> al file dopo la decompressione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome file </p> </td> 
   <td colname="col2"> <p>Sintassi nome file: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">File segmento-segmento: <code>S2S_Sovrapposizione_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">File Segment-to-Trait: <code>S2T_Sovrapposizione_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">File di caratteristiche-caratteristiche: <code>T2T_Sovrapposizione_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo date </p> </td> 
   <td colname="col2"> <p>L'intervallo di date per un rapporto è un ID di 5 cifre che include: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> per una relazione di 7 giorni. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> per una relazione di 30 giorni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Più file </p> </td> 
   <td colname="col2"> <p>L'ultima cifra nel nome del file viene incrementata se un rapporto contiene più file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esempi </p> </td> 
   <td colname="col2"> <p>Esempi di nomi file per un singolo rapporto: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">File singolo di 7 giorni: <code> S2S_Sovrapposizione_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">File singolo di 30 giorni: <code> S2S_Sovrapposizione_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Esempi di nomi di file per un rapporto con più file: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_Sovrapposizione_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_Sovrapposizione_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_Sovrapposizione_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contenuto file {#file-contents}

Nel file, i dati stringa sono racchiusi tra virgolette doppie. Vedi i dati originali di seguito. Questa operazione è stata troncata per semplificare e adattare lo schermo.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Record di report Segment-to-Segment {#segment-segment-records}

Un file di dati per il report [di sovrapposizione](segment-segment-overlap-report.md) segmento-segmento contiene i seguenti record.

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
   <td colname="col2"> <p>ID del segmento che si sta confrontando con il segmento della linea di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>Nome del segmento confrontato con i segmenti della linea di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>ID del segmento della linea di base. Il segmento della linea di base è il segmento da confrontare con altri segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>Nome del segmento della linea di base che si sta confrontando con altri segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Potete ottenere rapporti per intervalli di look-back di 7 e 30 giorni. Il valore <code> rangeid</code> corrisponde agli intervalli di tempo indicati di seguito. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 giorni </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione per un report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci nel segmento che si sta confrontando con il segmento della linea di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>Numero di utenti univoci nel segmento della linea di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Sovrapposizione_uniques</code> </p> </td> 
   <td colname="col2"> <p>Conteggio totale della sovrapposizione di utenti univoci tra il segmento della linea di base e gli altri segmenti selezionati per il confronto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>Sovrapposizione % di utenti univoci tra il segmento della linea di base e gli altri segmenti selezionati per il confronto. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Record di report Segment-to-Trait {#segment-trait-records}

Un file di dati per il report [di sovrapposizione](segment-trait-overlap-report.md) segmento-caratteristica contiene i seguenti record.

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
   <td colname="col2"> <p> ID caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nome caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>ID del provider di dati. Gli ID includono: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1a parte</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> terza parte</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p> Nome del provider di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Potete ottenere rapporti per intervalli di look-back di 7 e 30 giorni. Il valore <code> rangeid</code> corrisponde agli intervalli di tempo indicati di seguito. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 giorni </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione per un report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>Numero di utenti univoci nel segmento selezionato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Numero di utenti univoci in una caratteristica. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Sovrapposizione_uniques</code> </p> </td> 
   <td colname="col2"> <p>Numero di utenti univoci condivisi tra i segmenti e le caratteristiche selezionati. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_Sovrapposizione_perc</code> </p> </td> 
   <td colname="col2"> <p>% di utenti univoci che si sovrappongono tra la caratteristica e il segmento. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_Sovrapposizione_perc</code> </p> </td> 
   <td colname="col2"> <p>% di utenti univoci che si sovrappongono tra segmento e caratteristica. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Record dei report sulle caratteristiche {#trait-trait-records}

Un file di dati per il rapporto [](trait-trait-overlap-report.md) di sovrapposizione caratteristiche-caratteristiche contiene i seguenti record.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Sovrapposizione_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID della caratteristica che si sta confrontando con la caratteristica di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nome_tratto_sovrapposizione</code> </p> </td> 
   <td colname="col2"> <p>Nome della caratteristica che si sta confrontando con la caratteristica di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID della caratteristica di base. La caratteristica di base è la caratteristica che si desidera confrontare con altre caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nome della caratteristica della linea di base che si sta confrontando con altre caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>ID del provider di dati. Gli ID includono: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1a parte</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> terza parte</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p> Nome del provider di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Potete ottenere rapporti per intervalli di look-back di 7 e 30 giorni. Il valore <code> rangeid</code> corrisponde agli intervalli di tempo indicati di seguito. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 giorni </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione per un report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Sovrapposizione_tratto_uniques</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci condivisi tra le caratteristiche selezionate. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Numero di utenti univoci in una caratteristica base. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Sovrapposizione_uniques</code> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti univoci condivisi tra le caratteristiche selezionate. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Sovrapposizione_tratto_uniques_sovrapposizione_perc</code> </p> </td> 
   <td colname="col2"> <p>% di utenti univoci che si sovrappongono tra le caratteristiche selezionate. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_Sovrapposizione_perc</code> </p> </td> 
   <td colname="col2"> <p>% di utenti univoci che si sovrappongono tra le caratteristiche selezionate. Nel rapporto dell'interfaccia utente, questo numero viene visualizzato nella finestra a comparsa quando si passa il mouse su una caratteristica nei risultati della mappa di calore. </p> </td> 
  </tr> 
 </tbody> 
</table>
