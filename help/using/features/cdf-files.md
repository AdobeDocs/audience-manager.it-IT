---
description: Informazioni di base sui file Feed dati cliente (CDF) e istruzioni su come iniziare. Iniziate qui se siete interessati a ricevere i file CDF o solo a desiderate ulteriori informazioni.
keywords: dati di seconda parte; 2 nd party; dati di 2 nd party; seconda parte
seo-description: Informazioni di base sui file Feed dati cliente (CDF) e istruzioni su come iniziare. Iniziate qui se siete interessati a ricevere i file CDF o solo a desiderate ulteriori informazioni.
seo-title: Feed dati cliente
solution: Audience Manager
title: Feed dati cliente
uuid: a 5 de 1630-2 c 7 a -4862-9 ba 0-f 8343 cdd 2782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feeds {#customer-data-feeds}

Basic information about [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) files and instructions on how to get started. Start here if you're interested in receiving [!UICONTROL CDF] files or just want more information.

## File Contents and Purpose {#file-contents-purpose}

<!-- cdf-intro.xml -->

A [!UICONTROL CDF] file contains the same data that an [!DNL Audience Manager] event call ( `/event`) sends to our servers. Ciò include dati come ID utente, ID caratteristica, ID segmento e tutti gli altri parametri acquisiti da una chiamata dell'evento. Internal [!DNL Audience Manager] systems processes event data into a [!UICONTROL CDF] file with content organized into fields that appear in a set order. [!DNL Audience Manager] tenta di generare [!UICONTROL CDF] i file oraria e li memorizza in un bucket sicuro per un cliente su un [!DNL Amazon S3] server. We provide these files so you can work with [!DNL Audience Manager] data outside of the limits imposed by our user interface.

>[!NOTE]
>
>You should not use [!UICONTROL CDF] files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.

## Introduzione {#getting-started}

There is no self-service process to start [!UICONTROL CDF] file delivery. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL Audience Manager] representative will:

* Set up your [!DNL Amazon S3] storage bucket.
* Provide read-only [!DNL S3] authentication credentials to your file storage bucket. Non potrete visualizzare o accedere a directory e file appartenenti ad altri clienti.

File notifications and [!UICONTROL CDF] files will appear in your [!DNL S3] bucket when they're ready for download. You're responsible for monitoring and downloading files from your assigned [!DNL S3] directory. See [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## Passaggi successivi {#next-steps}

The sections below and the [Customer Data Feed FAQ](../faq/faq-cdf.md) can help you become more familiar with this service.

## Customer Data Feed Contents Defined {#cdf-defined}

Lists and defines the data elements and arrays in a [!UICONTROL CDF] file, by order of appearance. Definitions include data types, but this information is not part of a [!UICONTROL CDF] file.

## Definizioni {#definitions}

<!-- cdf-contents-defined.xml -->

A [!UICONTROL CDF] file includes some or all of the fields defined below. For information about internal file organization, see [Customer Data Feed File Structure](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo di dati </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Ora evento</code> </p> </td> 
   <td colname="col2"> <p>Marca temporale </p> </td> 
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">L'ora dell'evento pagina o della chiamata dell'evento, anche se potrebbe essere vicino a tali orari. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Correlato all'ora DCS nel nome del file. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Dispositivo</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. See also, <a href="../reference/ids-in-aam.md"> Index of IDs in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> ID contenitore</code> </p> </td> 
   <td colname="col2"> <p>Numeriche </p> </td> 
   <td colname="col3"> <p>L'ID del contenitore che attiva le sincronizzazioni ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Caratteristiche realizzate</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID caratteristiche che contiene tutte le caratteristiche realizzate (qualificate per) nella chiamata dell'evento. </p> <p>Notate che l'array può contenere caratteristiche per le quali il visitatore aveva diritto prima e per cui riqualificano tramite questa chiamata dell'evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Segmenti realizzati</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID segmento che contiene tutti i segmenti realizzati (qualificati per) nella chiamata dell'evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Parametri di richiesta</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Stringa che acquisisce tutti i parametri (variabili, ID, coppie chiave-valore, ecc.) trasmesso sulla chiamata dell'evento. </p> <p>Esempio abbreviato: </p> <p> <code> d_ rtbd: json, c_ contextdata. a. carriername: mobile, c_ contextdata. a. adid: 92 D 56353-49 C 5-431 E-B 474-FC 528 D 585810, c_ contextdata. a, runmode: Applicazione, c_ contextdata. a. dayssincelastupgrade: 61, d_ cid_ ic: xid % 01 EACB 6 E 40-AC 65-4012-9 FE 9-ABD 59965 E 9 C 4% 011, c_ contextdata. a. prevsessionlength: 583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tipo dati referente</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>L'URL non codificato della pagina di provenienza (se presente). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tipo dati IP</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>L'indirizzo IP del visitatore acquisito nella chiamata dell'evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Mcdevice </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) assigned to the site visitor. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tutti i segmenti</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Array di ID segmento che contiene segmenti precedentemente considerati e nuovi segmenti per i quali il visitatore è qualificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Tutte le caratteristiche</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Array di ID tratti iniziali e terze parti che contiene caratteristiche precedentemente realizzate e nuove caratteristiche idonee a partire dall'ultimo feed di dati generato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Structure {#cdf-file-structure}

Lists and defines the data structure of a [!UICONTROL CDF] file. Comprende sequenza di dati, delimitatori di campo e separatori, una mappa di file dati e file di esempio.

## Data Field Identifiers and Sequence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] i file non contengono colonne etichettate o intestazioni campo. Instead, a [!UICONTROL CDF] file defines fields and arrays with non-printing [!DNL ASCII] characters. Also, the [!UICONTROL CDF] file lists each field and array in a specific order. La comprensione degli identificatori dei campi e dell'ordine facilita la corretta analisi del file.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento file CDF </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Separatori di campo e delimitatori </p> </td> 
   <td colname="col2"> <p>Questi caratteri non stampabili definiscono gli elementi e la struttura del file CDF: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> or <code> ^A</code>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> or <code> ^B</code>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> or <code> ^C</code>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequenza campi </p> </td> 
   <td colname="col2"> <p> <p>Important: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. Questo significa che la progettazione tecnica del sistema di analisi dei file non deve presupporre un numero fisso di colonne, ma può presupporsi un ordine fisso per le colonne esistenti. </p> </p> <p>I dati nel file CDF vengono visualizzati nell'ordine indicato di seguito. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Ora evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Dispositivo </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID contenitore </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Caratteristiche realizzate </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmenti realizzati </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parametri di richiesta </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referente </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Indirizzo IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID dispositivo Experience Cloud (MID). See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Tutti i segmenti </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Tutte le caratteristiche </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF File Map {#cdf-file-map}

[!UICONTROL CDF] i dati del file vengono visualizzati nell'ordine indicato di seguito.

![](assets/sequence-map.png)

## Identificazione degli array

Arrays in a [!UICONTROL CDF] file start and end with the `Ctrl + a` field separator. Questo rende il primo elemento di un array come un campo di dati standalone. For example, the realized traits array starts with `^A1234`. The array delimiter and ID `^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with `^B`). Questo non è il caso, per questo è necessario avere familiarità con la sequenza e la struttura di un file di dati. Even though the first element in the realized trait array (or any of the other arrays in a [!UICONTROL CDF] file) starts with `^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by `^A`.

## Sample CDF File {#sample-file}

A sample [!UICONTROL CDF] file could look similar to the following. Abbiamo inserito interruzioni di riga in questo esempio per adattarla alla pagina.

![](assets/CDF-sample.png)

## Customer Data Feed File Naming Conventions {#cdf-naming-conventions}

The sections below list and define the elements in your [!UICONTROL CDF] file name.

## CDF File Name: Syntax and Example {#cdf-file-name}

<!-- cdf-file-name.xml -->

A typical [!UICONTROL CDF] file name contains the elements listed below. Note, *italics* indicates a variable placeholder:

* **Sintassi**

<pre><code>s 3: //aam-cdf/your<i>s 3 bucket name</i>/day =<i>yyyy-mm-gg</i>/hour =<i>hh</i>/<i>AAM_ CDF_ partner ID_ AAM process ID</i>_0.gz</code>
</pre>

* **Esempio**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In your [!DNL S3] storage bucket, files are sorted in ascending order by Partner ID ([!UICONTROL PID]), day, and hour.

## CDF File Name Elements Defined {#cdf-file-name-elements}

The following table lists and defines the elements in a [!UICONTROL CDF] file name.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento nome file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s 3: //aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Questo è il bug predefinito archivio principale per il file CDF su un server Amazon S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>your S 3 bucket name</i></code> </p> </td> 
   <td colname="col2"> <p>Nome del bucket di sola lettura, S 3 bucket che contiene i file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day =<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour =<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Un valore di tempo espresso nella notazione di 24 ore e impostato nel fuso orario UTC. See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID partner</i></code> </p> </td> 
   <td colname="col2"> <p>Il tuo ID partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>ID processo AAM</i>_ 0</code> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Un'estensione di file gzip. I file CDF sono compressi gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Processing Notifications {#cdf-file-processing-notifications}

[!DNL Audience Manager] scrive un `.info` file nella [!DNL S3] directory per segnalare quando ( [!UICONTROL Customer Data File][!UICONTROL CDF]) è pronto per il download. `.info` Il file include [!DNL JSON] anche metadati formattati sui contenuti dei [!UICONTROL CDF] file. Consultate questa sezione per informazioni sulla sintassi e sui campi utilizzati dal file di notifica.

## Sample Info File {#sample-info-file}

<!-- cdf-notifications.xml -->

Each `.info` file contains a `Files` and `Totals` section. The `Files` section contains an array that holds specific metrics for each hourly file. The `Totals` section contains metrics aggregated across all your [!UICONTROL CDF] files for a particular day. The contents of your `.info` file could look similar to the following example.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Info File Fields Defined {#info-file-fields-defined}

The following tables list and define the elements in a [!UICONTROL CDF] `.info` file.

### Oggetto file

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> File</code> </p> </td> 
   <td colname="col2"> <p>Avvia l'array che contiene i metadati sui file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione file in byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>The Amazon S 3 etag. Il numero che segue il trattino mostra il numero di parti utilizzate per creare il file durante il caricamento multiparte. <code> Etag</code> non è identico al checksum MD 5 del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>Il nome del file. See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filesequencenumber</code> </p> </td> 
   <td colname="col2"> <p>Un numero indice per ciascun file. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Oggetto Totals

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totali</code> </p> </td> 
   <td colname="col2"> <p>Avvia l'oggetto che contiene dati aggregati su tutti i file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Giorno</code> </p> </td> 
   <td colname="col2"> <p>Il giorno per il quale sono disponibili i dati. Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Ora</code> </p> </td> 
   <td colname="col2"> <p>L'ora per cui sono disponibili i dati. Utilizza un formato di 24 ore impostato nel fuso orario UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione totale di tutti i file CDF per quella data, in byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>Numero totale dei file caricati nella directory S 3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Name Times and File Content Times are Different {#different-processing-times}

[!UICONTROL CDF] Il file contiene marche temporali nel nome file e nel contenuto del file. These timestamps record different event processes for the same [!UICONTROL CDF] file. Non è raro visualizzare marche temporali diverse nel nome e nel contenuto dello stesso file. La comprensione di ogni marca temporale può aiutarti a evitare errori comuni quando si lavora con tali dati o si tenta di ordinarlo in base a tale data.

## Locating CDF File Timestamps {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] i file registrano in modo diverso in 2 posizioni separate.

![](assets/cdf-timestamp.png)

## Understanding the Difference Between Timestamps {#understanding-timestamps}

The following table provides additional details about your [!UICONTROL CDF] file timestamps along with information about how to use them properly.

| Posizione marca temporale | Descrizione |
|--- |--- |
| Nome file | The timestamp in your CDF file name marks the time when [!DNL Audience Manager] started preparing your file for delivery. Questa marca temporale è impostata nel fuso orario UTC. It uses the `hour=` parameter, with time formatted as a 2-digit hour in 24-hour notation. Questa volta può essere diversa dall'ora dell'evento registrata nel contenuto del file. Breakwhen in caso di file CDF, a volte si noterà che il bucket S 3 è vuoto per un'ora particolare. Un esempio di bucket vuoto può significare una delle seguenti:<ul><li>Non sono disponibili dati per quell'ora particolare. </li><li> I server sono in carico e non possono elaborare i file per un'ora particolare. Quando il server viene arrestato, inserisce i file che dovrebbero trascorrere in un determinato intervallo di tempo in un bucket con un valore successivo. For example, you'll see this when a file that should have been in the hour 17 bucket appear in the hour 18 bucket (with `hour=18` in the file name). In questo caso, il server ha iniziato a elaborare il file nell'ora 17 ma non è stato possibile completarlo entro tale intervallo. Al contrario, il file viene inviato all'intervallo orario successivo.</li></ul><br>**Importante**: Non utilizzare la marca temporale del nome file per raggruppare gli eventi per volta. If you need to group by time, use the `EventTime` timestamp in the file contents. |
| Contenuto file | Il timestamp nel contenuto del file CDF contrassegna l'ora in cui i server di raccolta dati hanno iniziato a elaborare il file. Questa marca temporale è impostata nel fuso orario UTC. It uses the `EventTime` field, with time formatted as *`yyyy-mm-dd hh:mm:ss`*. This time is close to the actual time of the event on the page, but it can be different than the hour indicator in the file name. <br> **Suggerimento**: A differenza della `hour=` marca temporale nel nome del file, potete utilizzare `EventTime` per raggruppare i dati per volta. |

>[!MORE_ LIKE_ THIS]
>
>* [Domande frequenti sui feed dei dati cliente](../faq/faq-cdf.md)

