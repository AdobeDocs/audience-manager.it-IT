---
description: Un file di dati contiene dati di impression, clic o conversione. Se formattati correttamente, puoi importare questi dati in Audience Manager e utilizzarli nei rapporti di ottimizzazione dell'audience e per i file di registro fruibili. Formattare i file di dati in base alle specifiche di questa sezione.
seo-description: Un file di dati contiene dati di impression, clic o conversione. Se formattati correttamente, puoi importare questi dati in Audience Manager e utilizzarli nei rapporti di ottimizzazione dell'audience e per i file di registro fruibili. Formattare i file di dati in base alle specifiche di questa sezione.
seo-title: File di dati per report di ottimizzazione dell'audience e file di registro fruibili
solution: Audience Manager
title: File di dati per report di ottimizzazione dell'audience e file di registro fruibili
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
translation-type: tm+mt
source-git-commit: 776aaad0c063a870ef804d166292228f83575f48

---


# File di dati per report di ottimizzazione dell&#39;audience e file di registro fruibili {#data-files-for-audience-optimization-reports}

Un file di dati contiene dati di impression, clic o conversione. Se formattati correttamente, puoi importare questi dati in Audience Manager per visualizzarli nei report [di ottimizzazione dell&#39;](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) audience e creare caratteristiche utilizzando i dati tramite i file [di registro](/help/using/integration/media-data-integration/actionable-log-files.md)fruibili. Formattare i file di dati in base alle seguenti specifiche in questa sezione.

## Panoramica {#overview}

Un file di dati con nome e formattazione corretti consente di importare dati di impression, clic o conversione nei report [di ottimizzazione dell&#39;](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)audience. Questa funzione è utile quando si lavora con un partner non integrato [!DNL Audience Manager] e si desidera lavorare con i propri dati in quella suite di rapporti. Questo processo richiede file separati per ottenere dati di impression, clic e conversione. Non mescolate questi eventi in un singolo file.

Un file di dati deve essere accompagnato da un file di metadati. I contenuti dei file di metadati corrispondono alle informazioni sui file di dati e alle relative etichette leggibili dai menu dei report. Per ulteriori informazioni, consultate [Panoramica e mappature per i file](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)di metadati.

## Convenzioni di denominazione per i file di dati {#naming-conventions}

La sintassi seguente definisce la struttura di un nome file di dati ben formato. Nota: il *corsivo* indica un segnaposto variabile che cambia a seconda del contenuto del file.

**Sintassi:** <pre><i>event type</i>_<i>yyyymmdd</i></code></pre>

In un nome file:

* Il tipo di evento indica che il file contiene impression, clic o conversioni. Create un file separato per ciascun tipo di evento.
* Un carattere di sottolineatura separa il tipo di evento e la marca temporale di un mese.
* Prima di caricare i file, comprimeteli utilizzando il file gzip e salvateli con l’estensione del `.gz` file.

Dati questi requisiti, assegnare ai file di dati un nome in base al contenuto come indicato di seguito:

* Dati di impressione: <pre>impression_<i>yymmdd</i>.gz</code></pre>
* Fare clic su dati: <pre>click_<i>yyyymmdd</i>.gz</code></pre>
* Dati di conversione: <pre>conversioni_<i>yyyymmdd</i>.gz</code></pre>

## Formato contenuto per i file di dati {#content-format}

La sintassi seguente definisce la struttura del contenuto in un file di dati formato correttamente. Nota: il *corsivo* indica un segnaposto variabile e viene sostituito con un&#39;etichetta in un file di dati effettivo.

**Sintassi:** <pre><i>etichetta di intestazione 1</i> | Etichetta <i>intestazione 2</i> ... Etichetta <i>intestazione n</i> | <i>versione</i></code></pre>

Nel contenuto del file:

* Le etichette di intestazione devono essere visualizzate nell&#39;ordine indicato nella tabella seguente. Le impression e i clic utilizzano le stesse etichette. I file di conversione contengono intestazioni aggiuntive.
* Se non si dispone di dati per una particolare colonna, compilare il campo con un `-1`.

* I file *devono* terminare con un numero di versione. La versione corrente è 1.1.
* Intestazioni e contenuti del file separati con il carattere ASCII 001 non stampabile. Se non è possibile utilizzare ASCII 001, separare le intestazioni e i dati con un delimitatore di tabulazione. Poiché si tratta di caratteri non stampabili, l&#39;esempio di sintassi riportato sopra mostra una barra verticale solo `"|"` a scopo di visualizzazione.

**Etichette campo**

La tabella seguente elenca e descrive le intestazioni delle colonne per il file di dati. Le intestazioni sono sensibili alle maiuscole/minuscole e devono essere visualizzate come ordinato nella tabella. Tutti i tipi di dati sono numeri interi (INT), se non diversamente indicato.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Timestamp </p> </td> 
   <td colname="col2"> <p>Una data e un'ora UTC per l'evento di impression, clic o conversione. Utilizzate il <code> yyyy-MM-dd HH:mm:ss</code> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID utente </p> </td> 
   <td colname="col2"> <p>Il tuo ID per un visitatore del sito, noto anche come ID <span class="term"> utente</span> univoco del fornitore di dati o DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>ID origine dati o codice di integrazione per l'inserzionista. </p> </td> 
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
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> ID posizionamento numerico dal server annunci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
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
   <td colname="col2"> <p> Il numero di articoli venduti in un evento di conversione. </p> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ricavi </p> </td> 
   <td colname="col2"> <p>Acquisto o altro importo di conversione. Tipo di dati: Mobile. </p> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Altri dati </p> </td> 
   <td colname="col2"> <p>URL della pagina di destinazione della conversione. Tipo di dati: Stringa. </p> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>Tipo di conversione. Indica se una conversione corrisponde o meno. Le opzioni includono: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impressioni </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Clic </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Non attribuito o sconosciuto </li> 
    </ul> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione </p> </td> 
   <td colname="col2"> <p>Numero di versione richiesto che viene visualizzato alla fine di ogni riga in un file di dati di impression, click o conversione. La versione corrente è 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Metodi di consegna dei file di dati {#delivery-methods}

Caricate i file di dati di impression, clic o conversione in una directory Amazon S3 per il vostro [!DNL Audience Manager] account. Fare riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

>[!IMPORTANT]
>
> Contatta il tuo consulente Audience Manager o l’Assistenza clienti per iniziare e configurare una [!DNL Amazon S3] directory per i file di dati.

**Sintassi percorso di consegna ed esempi**

I dati vengono memorizzati in uno spazio dei nomi separato per ciascun cliente in una [!DNL Amazon S3] directory. Il percorso del file segue la sintassi indicata di seguito. Note, *italics* indicates a variable placeholder. Altri elementi sono costanti o chiavi e non vengono modificati.

**Sintassi:** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>file type</i>_<i>yyyymmdd</i></code></pre>

La tabella seguente definisce ciascuno di questi elementi in un percorso di consegna dei file.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Questo è l'inizio del percorso di memorizzazione della directory. Riceverai il percorso completo quando tutto è configurato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore contiene l'ID cliente <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore contiene l’ID origine dati passato in una chiamata dell’evento. Identifica l'agenzia da cui provengono i dati e associa tali dati a un file di metadati di supporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Una directory di livello superiore per i file di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Un nome di tipo di file che indica il tipo di dati che contiene e una marca temporale di consegna. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Percorso e nome del file di caricamento di esempio**

Quando caricate un file, il percorso sarà simile al seguente:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tempi e aggiornamenti di elaborazione file**

I file di dati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i dati, invia un file contenente tutte le impression, i clic o le conversioni per un giorno particolare. In questo caso, un giorno è il periodo di 24 ore compreso tra una mezzanotte e l’altra. È consigliabile utilizzare l&#39;ora UTC per definire l&#39;intervallo di giorni.

## Passaggi successivi {#next-steps}

Esaminate i requisiti per denominare e creare file di metadati. Per iniziare, consultate [Panoramica e mappature per i file](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)di metadati.
