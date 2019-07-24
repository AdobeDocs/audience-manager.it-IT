---
description: Un file di dati contiene dati di impression, clic o conversione. Una volta formattati correttamente, puoi importarli in Audience Manager e visualizzarli nei report Ottimizzazione pubblico. Formattare i file di dati in base alle seguenti specifiche in questa sezione.
seo-description: Un file di dati contiene dati di impression, clic o conversione. Una volta formattati correttamente, puoi importarli in Audience Manager e visualizzarli nei report Ottimizzazione pubblico. Formattare i file di dati in base alle seguenti specifiche in questa sezione.
seo-title: File di dati per report di ottimizzazione pubblico
solution: Audience Manager
title: File di dati per report di ottimizzazione pubblico
uuid: c 19 eb 0 c 7-47 c 1-4 cdf -8 a 6 c-cd 15 fe 04 c 379
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

Un file di dati contiene dati di impression, clic o conversione. Una volta formattati correttamente, puoi importarli in Audience Manager e visualizzarli nei report Ottimizzazione pubblico. Formattare i file di dati in base alle seguenti specifiche in questa sezione.

## Panoramica {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. Questo processo richiede file separati per i dati impression, clic e conversione. Non combinarli in un unico file.

Un file di dati deve essere accompagnato da un file di metadati. I contenuti dei file di metadati corrispondono alle informazioni sui file di dati per etichette pertinenti e comprensibili all'utente nei menu dei rapporti. For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

La sintassi seguente definisce la struttura di un nome di file dati ben formattato. Note, *italics* indicates a variable placeholder that changes depending on the file contents.

**Sintassi:** <pre><code><i>event type</i>_<i>yyyymmdd</i></code></pre>

Nel nome di un file:

* Il tipo di evento indica che il file contiene impression, clic o conversioni. Create un file separato per ogni tipo di evento.
* Un carattere di sottolineatura separa il tipo di evento e un indicatore di data/mese.
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

In base a tali requisiti, denominate i file di dati in base al loro contenuto:

* Dati impression: <pre><code>impression_<i>yyyymmdd<i>.gz</code></pre>
* Fate clic su dati: <pre><code>click_<i>yyyymmdd</i>.gz</code></pre>
* Dati conversione: <pre><code>conversions_<i>yyyymmdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

La sintassi seguente definisce la struttura del contenuto nel file di dati corretto. Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**Sintassi:** <pre><code><i>label label 1</i> | <i>label label label 2</i> … <i>header label n</i> | <i>version</i></code></pre>

Nel contenuto del file:

* Le etichette dell'intestazione devono essere visualizzate nell'ordine come illustrato nella tabella seguente. Le impression e i clic usano le stesse etichette. I file di conversione contengono intestazioni aggiuntive.
* If you don't have data for a particular column, populate that field with a `NULL` object or `-1`.

* Files *must* end with a version number. La versione corrente è 1.1.
* Separate intestazioni e contenuti con il carattere ASCII 001 non stampabile. Se non è possibile utilizzare ASCII 001, separate le intestazioni e i dati con un delimitatore tabulazione. As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**Etichette dei campi**

La tabella seguente elenca e descrive le intestazioni delle colonne del file di dati. Le intestazioni fanno distinzione tra maiuscole e minuscole e devono essere visualizzate come ordinate nella tabella. Tutti i tipi di dati sono numeri interi (INT), se non diversamente indicato.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Marca temporale </p> </td> 
   <td colname="col2"> <p>Una data e un'ora UTC per l'evento di impression, clic o conversione. Use the <code> yyyy-dd-mm hh:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID utente </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>L'ID di origine dati o il codice di integrazione per l'inserzionista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID unità aziendale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>ID campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>ID creativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID sito </p> </td> 
   <td colname="col2"> <p>ID sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID posizionamento </p> </td> 
   <td colname="col2"> <p> ID posizionamento numerico dall'ad server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-Order-ID </p> </td> 
   <td colname="col2"> <p>ID ordine di inserimento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>ID tattico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID verticale </p> </td> 
   <td colname="col2"> <p>ID per un settore verticale o categoria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantità </p> </td> 
   <td colname="col2"> <p> Il numero di elementi venduti in un evento di conversione. </p> <p> <i>Solo per i file di dati conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ricavi </p> </td> 
   <td colname="col2"> <p>Acquisto o altro importo di conversione. Tipo di dati: Mobile. </p> <p> <i>Solo per i file di dati conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Altri dati </p> </td> 
   <td colname="col2"> <p>URL della pagina di destinazione conversione. Tipo di dati: Stringa. </p> <p> <i>Solo per i file di dati conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo evento </p> </td> 
   <td colname="col2"> <p>Tipo di conversione. Indica se corrisponde o meno a una conversione. Le opzioni includono: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Clic </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Non attribuito o sconosciuto </li> 
    </ul> <p> <i>Solo per i file di dati conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione </p> </td> 
   <td colname="col2"> <p>Numero di versione richiesto che viene visualizzato alla fine di ogni riga in un file di dati impression, clic o conversione. La versione corrente è 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. Fate riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

**Sintassi percorso di consegna ed Esempi**

I dati vengono memorizzati in uno spazio nomi separato per ogni cliente in una directory Amazon S 3. Il percorso del file segue la sintassi mostrata di seguito. Note, *italics* indicates a variable placeholder. Altri elementi sono costanti o chiavi e non cambiano.

**Sintassi:** <pre><code>…/log_ assimilion/pid = <i>AAM ID<i>/dpid = <i>d_ src</i>/logs/ <i>file type</i>_<i>yyyymmdd</i></code></pre>

La tabella seguente definisce ciascuno di questi elementi in un percorso di consegna file.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> …/log_ assimilion/</code> </p> </td> 
   <td colname="col2"> <p>Questo è l'inizio del percorso di memorizzazione della directory. Quando tutto viene configurato, riceverai il percorso completo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid =<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid =<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore contiene l'ID di origine dati trasmesso in una chiamata evento. Identifica l'agenzia da cui proviene e associa tali dati a un file di metadati supportato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> registri</code> </p> </td> 
   <td colname="col2"> <p> Una directory di livello superiore per i file di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Un nome di tipo tipo di file che indica il tipo di dati contiene e un timestamp di consegna. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Percorso di caricamento e nome file campione**

Quando caricate un file, il percorso sarà simile al seguente:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tempi e aggiornamenti di elaborazione file**

I file di dati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i dati, inviarli in un file contenente tutte le impression, i clic o le conversioni per un giorno particolare. In questo caso, un giorno corrisponde al periodo di 24 ore da una mezzanotte a quella successiva. Come procedura ottimale, puoi usare ora UTC per definire l'intervallo di giorni.

## Passaggi successivi {#next-steps}

Esaminate i requisiti per la denominazione e la creazione di file di metadati. To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
