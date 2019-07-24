---
description: La directory di stato S 3 contiene un file.info con informazioni di successo e non riuscita sui file caricati. Il file contiene dati in formato JSON con stato di stato in un array.
seo-description: La directory di stato S 3 contiene un file.info con informazioni di successo e non riuscita sui file caricati. Il file contiene dati in formato JSON con stato di stato in un array.
seo-title: Aggiornamenti dello stato per i file di metadati
solution: Audience Manager
title: Aggiornamenti dello stato per i file di metadati
uuid: 56 a 1 e 88 a -41 da -4 d 51-a 21 e -2 be 98 cca 7 fa 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Status Updates for Metadata Files{#status-updates-for-metadata-files}

The S3 status directory holds a `.info` file with success and failure information about your uploaded files. Il file contiene dati in formato JSON con stato di stato in un array.

The contents of your `.info` file will look similar to this example.

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

## Metadata Key-Value Pairs Defined {#key-value-pairs}

The following tables list and define the keys in the `Files` and `Summary` sections of a metadata status file.

**Tasti nell'Array file**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chiave </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Descrizione</code> </p> </td> 
   <td colname="col2"> <p>Contiene una breve descrizione del motivo per cui l'elaborazione non è riuscita. Questo campo è vuoto quando l'elaborazione ha esito positivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione file in byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>The MD 5 checksum for the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>The name of the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Metadatatype</code> </p> </td> 
   <td colname="col2"> <p>Il nome leggibile dal tipo di dati contiene. Si basa sull'ID secondario nel nome del file. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elemento padre</code> </p> </td> 
   <td colname="col2"> <p>Il nome leggibile dal tipo di dati contiene. Si basa sull'ID principale nel nome del file. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Stato</code> </p> </td> 
   <td colname="col2"> <p>Restituisce 2 valori di testo che descrivono lo stato di elaborazione del file di metadati: </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Tasti nell'oggetto Riepilogo**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chiave </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Giorno</code> </p> </td> 
   <td colname="col2"> <p>File processing date in <code><i>yyyy-mm-dd</i></code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Globalstatus</code> </p> </td> 
   <td colname="col2"> <p>Restituisce 2 valori di testo che descrivono lo stato di elaborazione per tutti i file per un giorno intero: </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numberfailure</code> </p> </td> 
   <td colname="col2"> <p>Numero di file elaborati senza successo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numbersuccess</code> </p> </td> 
   <td colname="col2"> <p>Numero di file elaborati con successo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Restituisce un indicatore ora leggibile per i tempi di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Processingtimeposix</code> </p> </td> 
   <td colname="col2"> <p>Un indicatore ora UNIX per l'ora di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Numero totale di byte per tutti i file di metadati del giorno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>Numero totale di tutti i file elaborati per giorno. </p> </td> 
  </tr> 
 </tbody> 
</table>
