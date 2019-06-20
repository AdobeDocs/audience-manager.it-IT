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


# File di dati per report di ottimizzazione pubblico{#data-files-for-audience-optimization-reports}

Un file di dati contiene dati di impression, clic o conversione. Una volta formattati correttamente, puoi importarli in Audience Manager e visualizzarli nei report Ottimizzazione pubblico. Formattare i file di dati in base alle seguenti specifiche in questa sezione.

## Panoramica {#overview}

Un file di dati correttamente denominato e formattato consente di importare dati di impression, clic o conversione nei report Ottimizzazione [pubblico](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Questo è utile quando lavorate con un partner che non è integrato [!DNL Audience Manager] e desiderate lavorare con i loro dati in quella suite di rapporti. Questo processo richiede file separati per i dati impression, clic e conversione. Non combinarli in un unico file.

Un file di dati deve essere accompagnato da un file di metadati. I contenuti dei file di metadati corrispondono alle informazioni sui file di dati per etichette pertinenti e comprensibili all&#39;utente nei menu dei rapporti. Per ulteriori informazioni, consultate [Panoramica e mappature per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Convenzioni di denominazione per i file di dati {#naming-conventions}

La sintassi seguente definisce la struttura di un nome di file dati ben formattato. Nota: *il corsivo* indica un segnaposto variabile che cambia a seconda del contenuto del file.

**Sintassi:** <pre><code><i>event type</i>_<i>yyyymmdd</i></code></pre>

Nel nome di un file:

* Il tipo di evento indica che il file contiene impression, clic o conversioni. Create un file separato per ogni tipo di evento.
* Un carattere di sottolineatura separa il tipo di evento e un indicatore di data/mese.
* Prima di caricare, comprimete i file utilizzando gzip e salvateli con l&#39;estensione `.gz` del file.

In base a tali requisiti, denominate i file di dati in base al loro contenuto:

* Dati impression: <pre><code>impression_<i>yyyymmdd<i>.gz</code></pre>
* Fate clic su dati: <pre><code>click_<i>yyyymmdd</i>.gz</code></pre>
* Dati conversione: <pre><code>conversions_<i>yyyymmdd</i>.gz</code></pre>

## Formato contenuto per i file di dati {#content-format}

La sintassi seguente definisce la struttura del contenuto nel file di dati corretto. Nota, *il corsivo* indica un segnaposto variabile e viene sostituito con un&#39;etichetta in un file di dati effettivo.

**Sintassi:** <pre><code><i>label label 1</i> | <i>label label label 2</i> … <i>header label n</i> | <i>version</i></code></pre>

Nel contenuto del file:

* Le etichette dell&#39;intestazione devono essere visualizzate nell&#39;ordine come illustrato nella tabella seguente. Le impression e i clic usano le stesse etichette. I file di conversione contengono intestazioni aggiuntive.
* Se non si dispone di dati per una particolare colonna, compilare il campo con un `NULL` oggetto o `-1`.

* I file ** devono terminare con un numero di versione. La versione corrente è 1.1.
* Separate intestazioni e contenuti con il carattere ASCII 001 non stampabile. Se non è possibile utilizzare ASCII 001, separate le intestazioni e i dati con un delimitatore tabulazione. Poiché questi sono caratteri non stampabili, l&#39;esempio di sintassi riportato sopra mostra un canale `"|"` esclusivamente a scopo di visualizzazione.

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
   <td colname="col2"> <p>Una data e un'ora UTC per l'evento di impression, clic o conversione. Utilizzate <code> aaaa-dd-mm hh: mm:</code> formato ss. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID utente </p> </td> 
   <td colname="col2"> <p>L'ID per un visitatore del sito, noto anche come ID utente univoco di <span class="term"> data provider</span> o DPUUID. </p> </td> 
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

## Metodi di consegna per i file di dati {#delivery-methods}

Caricate i file di dati impression, clic o conversione in una directory Amazon S 3 per l&#39; [!DNL Audience Manager] account. Fate riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

**Sintassi percorso di consegna ed Esempi**

I dati vengono memorizzati in uno spazio nomi separato per ogni cliente in una directory Amazon S 3. Il percorso del file segue la sintassi mostrata di seguito. Nota, *il corsivo* indica un segnaposto variabile. Altri elementi sono costanti o chiavi e non cambiano.

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
   <td colname="col2"> <p>Questa coppia chiave-valore contenente l' <span class="keyword"> ID</span> cliente di Audience Manager. </p> </td> 
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

Per aggiornare i dati, inviarli in un file contenente tutte le impression, i clic o le conversioni per un giorno particolare. In questo caso, un giorno corrisponde al periodo di 24 ore da una mezzanotte a quella successiva. Come procedura ottimale, puoi usare ora UTC per definire l&#39;intervallo di giorni.

## Passaggi successivi {#next-steps}

Esaminate i requisiti per la denominazione e la creazione di file di metadati. Per iniziare, consultate [Panoramica e mappature per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
