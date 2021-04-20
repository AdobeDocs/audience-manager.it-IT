---
description: Un file di dati contiene dati di impression, clic o conversione. Se formattati correttamente, puoi importare questi dati in Audience Manager e utilizzarli nei rapporti di Audience Optimization e per File di registro fruibili. Formattare i file di dati in base alle specifiche di questa sezione.
seo-description: Un file di dati contiene dati di impression, clic o conversione. Se formattati correttamente, puoi importare questi dati in Audience Manager e utilizzarli nei rapporti di Audience Optimization e per File di registro fruibili. Formattare i file di dati in base alle specifiche di questa sezione.
seo-title: File di dati per report di Audience Optimization e file di registro fruibili
solution: Audience Manager
title: File di dati per report di Audience Optimization e file di registro fruibili
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 4%

---

# File di dati per report di Audience Optimization e file di registro fruibili {#data-files-for-audience-optimization-reports}

Un file di dati contiene dati di impression, clic o conversione. Se formattati correttamente, puoi importare questi dati in Audience Manager per visualizzarli nei [Report di Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) e creare caratteristiche utilizzando i dati tramite [File di registro fruibili](/help/using/integration/media-data-integration/actionable-log-files.md). Formattare i file di dati in base alle specifiche riportate in questa sezione.

## Panoramica {#overview}

Un file di dati con nome e formattato correttamente consente di importare i dati di impression, clic o conversione in [Report di Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Questa funzione è utile quando si lavora con un partner non integrato con [!DNL Audience Manager] e si desidera lavorare con i relativi dati in quella suite di rapporti. Questo processo richiede file separati per i dati di impression, clic e conversione. Non combinare questi eventi in un singolo file.

Un file di dati deve essere accompagnato da un file di metadati. Il contenuto dei file di metadati corrisponde alle informazioni sui file di dati alle relative etichette leggibili dagli utenti nei menu dei rapporti. Per ulteriori informazioni, consulta [Panoramica e mappature per file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Convenzioni di denominazione per i file di dati {#naming-conventions}

La sintassi seguente definisce la struttura di un nome file dati ben formato. Nota: *corsivo* indica un segnaposto variabile che cambia a seconda del contenuto del file.

**Sintassi:** <pre><i>tipo di evento</i>_<i>aaaammgg</i></code></pre>

In un nome file:

* Il tipo di evento indica che il file contiene impression, clic o conversioni. Crea un file separato per ciascun tipo di evento.
* Un carattere di sottolineatura separa il tipo di evento e la marca temporale di un mese.
* Prima di caricare, comprimi i file utilizzando gzip e salvali con l&#39;estensione file `.gz`.

Dati questi requisiti, dai un nome ai file di dati in base al loro contenuto come riportato di seguito:

* Dati impression: <pre>impression_<i>aaaammgd</i>.gz</code></pre>
* Fare clic sui dati: <pre>click_<i>aaaammgd</i>.gz</code></pre>
* Dati di conversione: <pre>conversioni_<i>aaaammgg</i>.gz</code></pre>

## Formato del contenuto dei file di dati {#content-format}

La sintassi seguente definisce la struttura del contenuto in un file di dati ben formato. Nota: *corsivo* indica un segnaposto variabile e viene sostituito con un&#39;etichetta in un file di dati effettivo.

**Sintassi:** <pre><i>etichetta di intestazione 1</i> | etichetta di  <i>intestazione 2</i> ... etichetta di  <i>intestazione n</i>  |  <i>versione</i></code></pre>

Nel contenuto del file:

* Le etichette di intestazione devono essere visualizzate nell’ordine indicato nella tabella seguente. Le impressioni e i clic utilizzano le stesse etichette. I file di conversione contengono intestazioni aggiuntive.
* Se non disponi di dati per una particolare colonna, compila tale campo con un `-1`.

* I file *devono* terminare con un numero di versione. La versione corrente è 1.1.
* Separare le intestazioni e i contenuti dei file con il carattere ASCII 001 non stampabile. Se non è possibile utilizzare ASCII 001, separare le intestazioni e i dati con un delimitatore di tabulazione. Poiché si tratta di caratteri non stampabili, l&#39;esempio di sintassi riportato sopra mostra una barra verticale `"|"` solo a scopo di visualizzazione.

**Etichette campo**

La tabella seguente elenca e descrive le intestazioni di colonna per il file di dati. Le intestazioni sono sensibili all’uso di maiuscole e minuscole e devono essere visualizzate come ordinato nella tabella. Tutti i tipi di dati sono numeri interi (INT), salvo diversa indicazione.

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
   <td colname="col2"> <p>Una data e un’ora UTC per l’evento impression, click o conversione. Utilizzare il formato <code> yyyy-MM-dd HH:mm:ss</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID utente </p> </td> 
   <td colname="col2"> <p>Il tuo ID per un visitatore del sito, noto anche come ID utente univoco del provider di dati <span class="term"></span> o DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>L'ID dell'origine dati o il codice di integrazione per l'inserzionista. </p> </td> 
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
   <td colname="col2"> <p> ID di posizionamento numerico dal server di annunci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inserimento-Order-ID </p> </td> 
   <td colname="col2"> <p>ID ordine di inserimento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID tattico </p> </td> 
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
   <td colname="col1"> <p>Tipo evento </p> </td> 
   <td colname="col2"> <p>Tipo di conversione. Indica se una conversione corrisponde o meno. Le opzioni includono: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impressioni </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Clic </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Non attribuiti o sconosciuti </li> 
    </ul> <p> <i>Solo per i file di dati di conversione.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione </p> </td> 
   <td colname="col2"> <p>Numero di versione richiesto che viene visualizzato alla fine di ogni riga in un file di dati di impression, click o conversione. La versione corrente è 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Metodi di consegna dei file di dati {#delivery-methods}

Carica i file di dati di impression, clic o conversione in una directory Amazon S3 per il tuo account [!DNL Audience Manager]. Fai riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

>[!IMPORTANT]
>
> Contatta il tuo consulente di Audience Manager o l’Assistenza clienti per iniziare e impostare una directory [!DNL Amazon S3] per i file di dati.

**Sintassi ed esempi del percorso di consegna**

I dati vengono memorizzati in uno spazio dei nomi separato per ciascun cliente in una directory [!DNL Amazon S3] . Il percorso del file segue la sintassi mostrata di seguito. Nota: *corsivo* indica un segnaposto variabile. Gli altri elementi sono costanti o chiavi e non cambiano.

**Sintassi:** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>tipo di file</i>_<i>aaaammmdd</i></code></pre>

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
   <td colname="col2"> <p>Questo è l'inizio del percorso di archiviazione della directory. Riceverai il percorso completo quando tutto è configurato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore contiene il tuo ID cliente <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore contiene l'ID origine dati trasmesso in una chiamata evento. Identifica l'agenzia da cui provengono i dati e collega questi dati a un file di metadati di supporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Una directory di livello superiore per i file di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Nome del tipo di file che indica il tipo di dati in esso contenuto e una marca temporale di consegna. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Percorso e nome del file di caricamento di esempio**

Quando carichi un file, il percorso sarà simile al seguente:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Tempi e aggiornamenti dell’elaborazione dei file**

I file di dati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i dati, invia un file contenente tutte le impression, i clic o le conversioni per un giorno specifico. In questo caso, un giorno è il periodo di 24 ore da una mezzanotte all’altra. Come best practice, è possibile utilizzare l’ora UTC per definire l’intervallo di giorni.

## Passaggi successivi {#next-steps}

Esamina i requisiti per la denominazione e la creazione di file di metadati. Per iniziare, consulta [Panoramica e mappature per file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
