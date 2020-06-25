---
description: La directory di stato S3 contiene un file .info con informazioni di successo e di errore sui file caricati. Il file contiene dati in formato JSON con lo stato restituisce un array.
seo-description: La directory di stato S3 contiene un file .info con informazioni di successo e di errore sui file caricati. Il file contiene dati in formato JSON con lo stato restituisce un array.
seo-title: Aggiornamenti di stato per i file di metadati
solution: Audience Manager
title: Aggiornamenti di stato per i file di metadati
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 1%

---


# Aggiornamenti di stato per i file di metadati{#status-updates-for-metadata-files}

La directory di stato S3 contiene un `.info` file con informazioni di successo e di errore sui file caricati. Il file contiene dati in formato JSON con lo stato restituisce un array.

Il contenuto del `.info` file sarà simile a questo esempio.

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## Coppie Chiave-Valore Metadati Definite {#key-value-pairs}

Le tabelle seguenti elencano e definiscono le chiavi nelle `Files` sezioni e nelle `Summary` sezioni di un file di stato dei metadati.

**Tasti nell&#39;array dei file**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chiave </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Description</code> </p> </td> 
   <td colname="col2"> <p>Contiene una breve descrizione del motivo per cui l'elaborazione non è riuscita. Questo campo è vuoto se l'elaborazione ha esito positivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione del file in byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Il checksum MD 5 per il file di metadati caricato nella <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Nome del file di metadati caricato nella <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>Nome leggibile per il tipo di dati contenuto nel file. Si basa sull’ID figlio nel nome del file. </p> <p>Consultate <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Convenzioni di denominazione per i file</a>di metadati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>Nome leggibile per il tipo di dati contenuto nel file. Si basa sull’ID principale nel nome del file. </p> <p>Consultate <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Convenzioni di denominazione per i file</a>di metadati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>Restituisce 2 valori di testo che descrivono lo stato di elaborazione del file di metadati: </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Tasti nell&#39;oggetto di riepilogo**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chiave </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione file in <code><i>yyyy-mm-dd</i></code> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>Restituisce 2 valori di testo che descrivono lo stato di elaborazione di tutti i file per un'intera giornata: </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>Numero di file elaborati non correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>Numero di file elaborati correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Restituisce un timestamp leggibile dall'utente per l'elaborazione degli orari di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>Timestamp UNIX per l'elaborazione delle ore di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Numero totale di byte per tutti i file di metadati del giorno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Numero totale di tutti i file elaborati per il giorno. </p> </td> 
  </tr> 
 </tbody> 
</table>
