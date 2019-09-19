---
description: Inviate o aggiornate i file di metadati inviandoli a una directory Amazon S3 speciale per il vostro account Audience Manager. Fare riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-description: Inviate o aggiornate i file di metadati inviandoli a una directory Amazon S3 speciale per il vostro account Audience Manager. Fare riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-title: Metodi di consegna per i file di metadati
solution: Audience Manager
title: Metodi di consegna per i file di metadati
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Metodi di consegna per i file di metadati{#delivery-methods-for-metadata-files}

Inviate o aggiornate i file di metadati inviandoli a una directory Amazon S3 speciale per il vostro account Audience Manager. Fare riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

## Sintassi percorso di consegna ed esempi {#syntax}

I dati vengono memorizzati in uno spazio dei nomi separato per ciascun cliente in una directory Amazon S3. Il percorso del file segue la sintassi indicata di seguito. Note, *italics* indicates a variable placeholder. Le parentesi `[ ]` indicano i parametri facoltativi. Gli altri elementi sono costanti e non cambiano.

**Sintassi:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyymmdd</i>_ ID <i>_</i>parent ID <i>_child ID</i></code></pre>

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
   <td colname="col1"> <p> <code>pid=ID<i>AAM</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore che contiene l'ID cliente <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Questa coppia chiave-valore contiene l’ID origine dati passato in una chiamata dell’evento. L'ID origine dati è il valore che lega tutto il contenuto del file ai dati effettivi a cui appartiene. </p> <p>Ad esempio, supponete di avere un creativo con l’ID 123 e il nome "Advertiser Creative A". Poiché una chiamata evento passa solo l’ID, è necessario includere "Advertiser Creative A" nel file di metadati. La campagna e la creatività appartengono a un'origine dati. L’ID origine dati è ciò che li collega insieme e ci consente di associare accuratamente il contenuto del file a un ID inviato in una chiamata dell’evento. Consulta <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> Modalità di determinazione dei nomi dei file, dei contenuti e dei percorsi</a>di consegna da parte degli ID delle chiamate evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> è una directory di caricamento/memorizzazione di file. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> è un percorso a una directory che contiene informazioni di successo o di errore sui file elaborati. Dopo l'elaborazione del file, vedrete un file <code> .info</code> con il titolo della marca temporale <code> yymmdd</code> . I file di stato contengono dati in un oggetto JSON. Consultate <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Aggiornamenti di stato per i file</a>di metadati. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ID <i>yyyymmdd</i>_<i>parent ID</i>_<i>child</i></code> </p> </td> 
   <td colname="col2"> <p>Questo è il nome del file. Consultate <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Convenzioni di denominazione per i file</a>di metadati. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Percorsi di caricamento e stato di esempio**

Per caricare un file di metadati o [controllarne lo stato](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), i percorsi dei file saranno simili ai seguenti:

* Percorso di caricamento: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Percorso stato elaborazione: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## Tempi e aggiornamenti di elaborazione file {#processing-times}

I file di metadati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i record di metadati, è sufficiente inviare un file contenente nuove informazioni. Non è necessario inviare aggiornamenti completi ogni volta.
