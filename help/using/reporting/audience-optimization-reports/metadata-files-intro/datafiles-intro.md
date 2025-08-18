---
description: Un file di dati contiene dati su impression, clic o conversione. Una volta formattati correttamente, puoi importare questi dati in Audience Manager e utilizzarli nei rapporti di Audience Optimization e per i file di registro fruibili. Formattare i file di dati in base alle specifiche di questa sezione.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: File di dati per report di Audience Optimization e file di registro fruibili
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 1%

---

# File di dati per report di Audience Optimization e file di registro fruibili {#data-files-for-audience-optimization-reports}

Un file di dati contiene dati su impression, clic o conversione. Se formattati correttamente, puoi importare questi dati in Audience Manager per visualizzarli nei [report di Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) e creare caratteristiche utilizzando i dati tramite [file di registro fruibili](/help/using/integration/media-data-integration/actionable-log-files.md). Formatta i file di dati in base alle specifiche riportate in questa sezione.

## Panoramica {#overview}

Un file di dati formattato e denominato in modo corretto consente di importare dati su impression, clic o conversione nei [report Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Questa funzione è utile quando si lavora con un partner non integrato con [!DNL Audience Manager] e si desidera lavorare con i relativi dati in quella suite di rapporti. Questo processo richiede file separati per i dati di impression, clic e conversione. Non mescolare questi eventi in un singolo file.

Un file di dati deve essere accompagnato da un file di metadati. Il contenuto del file di metadati corrisponde alle informazioni del file di dati con le relative etichette leggibili dall&#39;utente nei menu del report. Per ulteriori informazioni, vedere [Panoramica e mappature dei file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Convenzioni di denominazione per i file di dati {#naming-conventions}

La sintassi seguente definisce la struttura di un nome di file di dati ben formato. *corsivo* indica un segnaposto variabile che cambia a seconda del contenuto del file.

**Sintassi:** <pre><code><i>tipo evento</i>_<i>aaaammgg</i></code></pre>

In un nome di file:

* Il tipo di evento indica che il file contiene impression, clic o conversioni. Crea un file separato per ogni tipo di evento.
* Un trattino basso separa il tipo di evento e una marca temporale anno-mese-data.
* Prima di caricare, comprimi i file utilizzando gzip e salvali con l&#39;estensione `.gz`.

Considerati i requisiti seguenti, assegna ai file di dati un nome in base al loro contenuto, come riportato di seguito:

* Dati impression: <pre><code>impressioni_<i>aaaammgg</i>.gz</code></pre>
* Dati clic: <pre><code>clicks_<i>aaaammgg</i>.gz</code></pre>
* Dati di conversione: <pre><code>conversioni_<i>aaaammgg</i>.gz</code></pre>

## Formato del contenuto dei file di dati {#content-format}

La sintassi seguente definisce la struttura del contenuto in un file di dati ben formato. Nota: *corsivo* indica un segnaposto variabile e viene sostituito con un&#39;etichetta in un file di dati effettivo.

**Sintassi:** <pre><code><i>etichetta intestazione 1</i> | <i>etichetta intestazione 2</i> ... <i>etichetta intestazione n</i> | <i>versione</i></code></pre>

Nel contenuto del file:

* Le etichette di intestazione devono essere visualizzate nell&#39;ordine indicato nella tabella seguente. Le impressioni e i clic utilizzano le stesse etichette. I file di conversione contengono intestazioni aggiuntive.
* Se non si dispone di dati per una colonna particolare, compilare il campo con `-1`.

* I file *must* terminano con un numero di versione. La versione corrente è 1.1.
* Separare le intestazioni e il contenuto dei file con il carattere ASCII 001 non stampabile. Se non è possibile utilizzare ASCII 001, separare le intestazioni e i dati con un delimitatore di tabulazione. Poiché si tratta di caratteri non stampabili, l&#39;esempio di sintassi precedente mostra una barra verticale `"|"` solo a scopo di visualizzazione.

**Etichette campo**

La tabella seguente elenca e descrive le intestazioni di colonna per il file di dati. Le intestazioni fanno distinzione tra maiuscole e minuscole e devono essere visualizzate come ordinato nella tabella. Tutti i tipi di dati sono numeri interi (INT), a meno che non sia indicato diversamente.

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
   <td colname="col2"> <p>Data e ora UTC per l’evento di impression, clic o conversione. Utilizza il formato <code> yyyy-MM-dd HH:mm:ss</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>L'ID per un visitatore del sito, noto anche come ID utente univoco del provider di dati <span class="term"></span> o DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>L’ID sorgente dei dati o il codice di integrazione per l’inserzionista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID Business Unit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>ID campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>ID Creative. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID sito </p> </td> 
   <td colname="col2"> <p>ID sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> ID di posizionamento numerico dall’ad server. </p> </td> 
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
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>ID per un settore verticale o una categoria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantità </p> </td> 
   <td colname="col2"> <p> Il numero di articoli venduti in un evento di conversione. </p> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ricavi </p> </td> 
   <td colname="col2"> <p>Importo di acquisto o altra conversione. Tipo di dati: mobile. </p> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Altri dati </p> </td> 
   <td colname="col2"> <p>URL della pagina di destinazione di conversione. Tipo di dati: String. </p> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>Tipo di conversione. Indica se una conversione corrisponde o meno. Le opzioni includono: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: fare clic su </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: non attribuito o sconosciuto </li> 
    </ul> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione </p> </td> 
   <td colname="col2"> <p>Numero di versione obbligatorio visualizzato alla fine di ogni riga in un file di dati di impression, clic o conversione. La versione corrente è 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Metodi di distribuzione dei file di dati {#delivery-methods}

Carica i file di dati di impression, clic o conversione in una directory Amazon S3 per il tuo account [!DNL Audience Manager]. Fai riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

>[!IMPORTANT]
>
> Contatta il tuo consulente Audience Manager o l&#39;Assistenza clienti per iniziare e configurare una directory [!DNL Amazon S3] per i file di dati.

**Sintassi ed esempi del percorso di consegna**

I dati vengono memorizzati in uno spazio dei nomi separato per ogni cliente in una directory [!DNL Amazon S3]. Il percorso del file segue la sintassi illustrata di seguito. Nota: *corsivo* indica un segnaposto variabile. Gli altri elementi sono costanti o chiavi e non cambiano.

**Sintassi:** <pre><code>.../log_ingestion/pid= <i>ID AAM</i>/dpid= <i>d_src</i>/logs/ <i>tipo di file</i>_<i>aaaammgg</i></code></pre>

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
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Inizio del percorso di archiviazione della directory. Riceverai il percorso completo quando tutto è configurato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore contiene l'ID cliente <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore contiene l'ID origine dati trasmesso in una chiamata evento. Identifica l’agenzia da cui provengono i dati e li collega a un file di metadati di supporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Una directory di livello superiore per i file di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Nome del tipo di file che indica il tipo di dati in esso contenuti e un timestamp di consegna. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Percorso di caricamento di esempio e nome file**

Quando carichi un file, il percorso sarà simile al seguente:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tempi di elaborazione file e aggiornamenti**

I file di dati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i dati, invia un file contenente tutte le impression, i clic o le conversioni per un giorno specifico. In questo caso, un giorno è il periodo di 24 ore che va da una mezzanotte alla successiva. Come best practice, puoi utilizzare l’ora UTC per definire l’intervallo giornaliero.

## Passaggi successivi {#next-steps}

Rivedi i requisiti per la denominazione e la creazione di file di metadati. Per iniziare, vedere [Panoramica e mappature dei file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
