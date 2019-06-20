---
description: Inviare o aggiornare i file di metadati inviandoli a una particolare directory Amazon S 3 per l'account Audience Manager. Fate riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-description: Inviare o aggiornare i file di metadati inviandoli a una particolare directory Amazon S 3 per l'account Audience Manager. Fate riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-title: Metodi di consegna per i file di metadati
solution: Audience Manager
title: Metodi di consegna per i file di metadati
uuid: 5199 ee 9 b -920 d -423 d -8070-05 a 017 ecd 562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Metodi di consegna per i file di metadati{#delivery-methods-for-metadata-files}

Inviare o aggiornare i file di metadati inviandoli a una particolare directory Amazon S 3 per l&#39;account Audience Manager. Fate riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

## Sintassi percorso di consegna ed Esempi {#syntax}

I dati vengono archiviati in spazi nomi separati per ogni cliente in una directory Amazon S 3. Il percorso del file segue la sintassi mostrata di seguito. Nota, *il corsivo* indica un segnaposto variabile. Le parentesi quadre `[ ]` indicano parametri facoltativi. Gli altri elementi sono costanti e non cambiano.

**Sintassi:**
<pre><code>…/log_ assimilion/pid =<i>AAM ID</i>/dpid = <i>d_ src</i>/[meta | status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

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
   <td colname="col2"> <p>Questa coppia chiave-valore contiene l'ID di origine dati trasmesso in una chiamata evento. L'ID di origine dati è il valore che associa tutto il contenuto del file ai dati effettivi a cui appartiene. </p> <p>Ad esempio, supponiamo che sia presente un creativi con ID 123 e il nome «Advertiser Creative A.» Come una chiamata dell'evento trasmette solo l'ID per includere «Advertiser Creative A» nel file metadati. La campagna e i creativi appartengono a un'origine dati. L'ID di origine dati è ciò che collega questi insieme e ci consente di associare con precisione i contenuti del file a un ID inviato in una chiamata dell'evento. Vedi <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> Come ID di chiamata evento determinano nomi file, contenuti e percorsi di consegna</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> è una directory di caricamento/archiviazione di file. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> è</code> un percorso a una directory che contiene informazioni di successo o non riuscite sui file elaborati. Una volta elaborati il file, visualizzerai un file <code> .info</code> con il titolo <code> della</code> marca temporale yyyymmdd. I file di stato contengono dati in un oggetto JSON. Consultate <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Aggiornamenti dello stato per i file di metadati</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>Questo è il nome del file. Consultate <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Convenzioni di denominazione per i file di metadati</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Percorsi di caricamento e stato di esempio**

Per caricare un file di metadati o [controllarne lo stato](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), i percorsi dei file saranno simili a quelli seguenti:

* Percorso di caricamento: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Percorso di stato elaborazione: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## Tempi e aggiornamenti di elaborazione file {#processing-times}

I file di metadati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i record di metadati, è sufficiente inviare un file contenente nuove informazioni. Non devi inviare aggiornamenti completi ogni volta.
