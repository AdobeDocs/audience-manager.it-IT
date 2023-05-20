---
description: Informazioni di base sui file Customer Data Feed (CDF) e istruzioni su come iniziare. Inizia qui se sei interessato a ricevere file CDF o semplicemente desideri ulteriori informazioni.
keywords: dati di seconde parti;dati di seconde parti;dati di seconde parti;seconde parti
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Customer Data Feeds
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 2%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Informazioni di base su [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) file e istruzioni su come iniziare. Inizia qui se sei interessato a ricevere [!UICONTROL CDF] o semplicemente per ottenere ulteriori informazioni.

## Contenuto e finalità del file {#file-contents-purpose}

Un file [!UICONTROL CDF] contiene gli stessi dati che una chiamata evento di [!DNL Audience Manager] (`/event`) invia ai nostri server. Ciò include dati come gli ID utente, [!UICONTROL trait IDs], [!UICONTROL segment IDs]e tutti gli altri parametri acquisiti da una chiamata evento. Interno [!DNL Audience Manager] system elabora i dati evento in una [!UICONTROL CDF] file con contenuto organizzato in campi che vengono visualizzati in un ordine preimpostato. [!DNL Audience Manager] tenta di generare [!UICONTROL CDF] file ogni ora e li memorizza in un bucket sicuro specifico per il cliente su un [!DNL Amazon S3] server. Forniamo questi file in modo che tu possa utilizzare [!DNL Audience Manager] dati al di fuori dei limiti imposti dalla nostra interfaccia utente.

>[!IMPORTANT]
>
>Durante l&#39;utilizzo dei file CDF, tenete presente le seguenti limitazioni:
>
>* Prima di configurare la consegna dei file CDF, assicurati di disporre delle autorizzazioni appropriate da parte dei provider di dati di terze parti per l’esportazione di caratteristiche di terze parti. Audience Manager al momento non supporta la funzionalità nell’interfaccia utente di richiesta dell’autorizzazione di esportazione per la consegna dei file CDF da parte di provider di dati di terze parti, pertanto contatta tali provider in modo indipendente.
>* Non deve usare [!UICONTROL CDF] file come proxy per monitorare il traffico di pagina, risolvere le discrepanze nei rapporti, per la fatturazione, ecc.


## Introduzione {#getting-started}

Nessun processo self-service da avviare [!UICONTROL CDF] consegna dei file. Contatta il tuo [!DNL Audience Manager] consulente o assistenza clienti. Durante l&#39;implementazione, [!DNL Audience Manager] il rappresentante:

* Configurare [!DNL Amazon S3] bucket di archiviazione.
* Fornisci sola lettura [!DNL S3] credenziali di autenticazione per il bucket di archiviazione file. Non potrai visualizzare o accedere alle directory e ai file che appartengono ad altri clienti.

Notifiche sui file e [!UICONTROL CDF] i file verranno visualizzati nel [!DNL S3] quando sono pronti per il download. Sei responsabile del monitoraggio e del download dei file dal tuo [!DNL S3] directory. Consulta [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## Passaggi successivi {#next-steps}

Le sezioni seguenti e [Domande frequenti sui feed di dati cliente](../faq/faq-cdf.md) può aiutarti a acquisire maggiore familiarità con questo servizio.

## [!UICONTROL Customer Data Feed] Contenuto definito {#cdf-defined}

Elenca e definisce gli elementi dati e gli array in una [!UICONTROL CDF] file, in ordine di visualizzazione. Le definizioni includono i tipi di dati, ma queste informazioni non fanno parte di un [!UICONTROL CDF] file.

>[!IMPORTANT]
>
>I pixel degli eventi sono esclusi per impostazione predefinita nelle configurazioni CDF. Assicurati di specificare nella richiesta all’assistenza clienti se desideri includere i pixel dell’evento nei file CDF. Ogni pixel dell’evento viene compilato come riga univoca nei file CDF.

## Definizioni {#definitions}

A [!UICONTROL CDF] Il file include alcuni o tutti i campi definiti di seguito. Per informazioni sull&#39;organizzazione interna dei file, vedere [Struttura del file di feed dati del cliente](#cdf-file-structure).

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
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>Timestamp </p> </td> 
   <td colname="col3"> <p>Ora in cui un file CDF è stato elaborato da <span class="wintitle"> Server di raccolta dati</span> (DCS) La marca temporale utilizza <i>aaaa-mm-gg hh:mm:ss</i> ed è impostato nel fuso orario UTC. </p> <p> <p>Nota: l'ora dell'evento <i>non è</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">L’ora dell’evento della pagina o della chiamata stessa dell’evento, anche se potrebbe essere vicina a tali ore. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Correlato all’ora DCS nel nome file. Vedi anche, <a href="#different-processing-times"> Nome file feed dati cliente Tempi e contenuto file...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Questo è il <span class="wintitle"> ID utente univoco</span> (UUID), che è un ID dispositivo di 38 cifre per il visitatore del sito. Vedi anche, <a href="../reference/ids-in-aam.md"> Indice degli ID in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numeriche </p> </td> 
   <td colname="col3"> <p>ID del contenitore che attiva le sincronizzazioni ID. Questo campo viene compilato solo se imposti l’ID contenitore nel <i>d_nsid</i> all'interno dell'implementazione del sito. In caso contrario, il valore predefinito 0 non verrà incluso nei file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID di caratteristiche che contiene tutte le caratteristiche realizzate (qualificate) da un visitatore nella chiamata dell’evento. </p> <p>L’array può contenere caratteristiche per le quali il visitatore si era qualificato in precedenza e che sono state riqualificate tramite questa chiamata dell’evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID segmento che contiene tutti i segmenti realizzati (qualificati per) da un visitatore nella chiamata dell’evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Una stringa che acquisisce tutti i parametri (variabili, ID, coppie chiave-valore, ID dispositivo pubblicitario, ecc.) passato alla chiamata evento. </p> <p>Esempio abbreviato: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>URL non codificato della pagina di riferimento (se presente). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>L’indirizzo IP del visitatore acquisito nella chiamata dell’evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Il <span class="keyword"> Experience Cloud</span> ID (MID) assegnato al visitatore del sito. Vedi anche, <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e il servizio Adobe Experience Platform Identity</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID segmento che contiene segmenti realizzati in precedenza e nuovi segmenti per i quali il visitatore è qualificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID di prima e terze parti delle caratteristiche che contiene caratteristiche realizzate in precedenza e nuove caratteristiche per le quali il visitatore è qualificato dall’ultimo feed di dati generato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Struttura dei file {#cdf-file-structure}

Elenca e definisce la struttura dati di un [!UICONTROL CDF] file. Ciò include sequenza di dati, delimitatori di campo e separatori, una mappa del file di dati e un file di esempio.

## Identificatori e sequenza dei campi dati {#identifiers-and-sequence}

[!UICONTROL CDF] i file non contengono colonne con etichetta o intestazioni di campo. Invece, un’ [!UICONTROL CDF] file definisce campi e array senza funzionalità di stampa [!DNL ASCII] caratteri. Inoltre, il [!UICONTROL CDF] file elenca ogni campo e matrice in un ordine specifico. Comprendere gli identificatori e l’ordine dei campi ti aiuterà ad analizzare correttamente il file.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento file CDF </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Separatori di campi e delimitatori </p> </td> 
   <td colname="col2"> <p>Questi caratteri non stampabili definiscono gli elementi e la struttura del file CDF: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + A (ASCII) <code> 001</code> o <code> ^A</code>) separa i dati nei singoli campi con un indicatore di spazio non stampabile. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + B (ASCII) <code> 002</code> o <code> ^B</code>) separa i dati, un array e i parametri di richiesta. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + C (ASCII) <code> 003</code> o <code> ^C</code>) definisce coppie chiave-valore. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequenza campi </p> </td> 
   <td colname="col2"> <p> <p>Importante: <span class="keyword"> Audience Manager</span> si riserva il diritto di aggiungere nuovi campi alla fine del file CDF nelle versioni future. Ciò significa che la progettazione tecnica del file parsing system non deve presupporre un numero fisso di colonne (anche se potrebbe presupporre un ordine fisso per le colonne esistenti).</p> </p> <p>I dati nel file CDF vengono visualizzati nell’ordine mostrato di seguito. /N può essere visualizzato al posto di uno qualsiasi di questi campi, indicando un valore nullo.</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Ora evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Dispositivo </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID contenitore </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Caratteristiche realizzate </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmenti realizzati </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parametri di richiesta </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Indirizzo IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID dispositivo di Experience Cloud (o MID). Vedi anche, <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e il servizio Adobe Experience Platform Identity</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Tutti i segmenti </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Tutte le caratteristiche </li> 
     </ol> </p> <p>Per le descrizioni dei campi, vedi <a href="#cdf-defined"> Contenuto feed dati cliente definito</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Mappa file {#cdf-file-map}

[!UICONTROL CDF] i dati del file vengono visualizzati nell&#39;ordine indicato di seguito.

![](assets/sequence-map.png)

## Identificazione degli array

Array in un [!UICONTROL CDF] inizio e fine file con `Ctrl + a` separatore di campo. In questo modo il primo elemento di un array viene visualizzato come un campo dati autonomo. Ad esempio, il [!UICONTROL traits] l’array inizia con `^A1234`. Il delimitatore e l’ID della matrice `^B5678` segue questa voce. Di conseguenza, si potrebbe essere tentati di pensare che il primo elemento nel realizzato [!UICONTROL traits] l&#39;array è l&#39;ID 5678 (perché inizia con `^B`). In caso contrario, ecco perché è necessario avere familiarità con la sequenza e la struttura di un file di dati. Anche se il primo elemento nella [!UICONTROL trait] array (o uno qualsiasi degli altri array in un [!UICONTROL CDF] file) inizia con `^A`, l&#39;ordine di visualizzazione o la posizione nel file definisce l&#39;inizio di un array. Il primo elemento di un array è sempre separato dalla voce precedente da `^A`.

## Esempio [!UICONTROL CDF] File {#sample-file}

Un esempio [!UICONTROL CDF] potrebbe avere un aspetto simile al seguente. Abbiamo inserito interruzioni di riga in questo esempio per adattarlo alla pagina.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Convenzioni di denominazione dei file {#cdf-naming-conventions}

Le sezioni seguenti elencano e definiscono gli elementi nel [!UICONTROL CDF] nome file.

## [!UICONTROL CDF] Nome file: sintassi ed esempio {#cdf-file-name}

Un tipico [!UICONTROL CDF] il nome file contiene gli elementi elencati di seguito. Nota: *corsivo* indica un segnaposto variabile:

### Sintassi

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### Esempio

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

Nel tuo [!DNL S3] bucket di archiviazione, i file vengono ordinati in ordine crescente per ID partner ([!UICONTROL PID]), giorno e ora.

## [!UICONTROL CDF] Elementi nome file definiti {#cdf-file-name-elements}

Nella tabella seguente sono elencati e definiti gli elementi di un [!UICONTROL CDF] nome file.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento nome file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Questo è il bucket di archiviazione principale predefinito per il file CDF su un server Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Nome del bucket S3 di sola lettura contenente i file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Un valore di ora espresso in notazione di 24 ore e impostato nel fuso orario UTC. Vedi anche, <a href="#different-processing-times"> Nome file feed dati cliente Tempi e contenuto file...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>ID partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Valori che identificano la sequenza di file. La sequenza viene incrementata come segue: 0_0_0 , 0_1_0, 0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Estensione di file gzip. I file CDF sono compressi con Gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Notifiche elaborazione file {#cdf-file-processing-notifications}

[!DNL Audience Manager] scrive un `.info` file nel tuo [!DNL S3] directory per comunicare quando [!UICONTROL Customer Data File] ([!UICONTROL CDF]) è pronto per il download. Il `.info` Il file include anche [!DNL JSON] metadati formattati sul contenuto del [!UICONTROL CDF] file. Consulta questa sezione per informazioni sulla sintassi e i campi utilizzati da questo file di notifica.

## File di informazioni di esempio {#sample-info-file}

Ogni `.info` il file contiene un `Files` e `Totals` sezione. Il `Files` contiene un array che contiene metriche specifiche per ciascun file orario. Il `Totals` contiene metriche aggregate in tutte le [!UICONTROL CDF] per un giorno specifico. Contenuto della `.info` potrebbe essere simile all&#39;esempio seguente.

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

## Campi file informazioni definiti {#info-file-fields-defined}

Le tabelle seguenti elencano e definiscono gli elementi in un [!UICONTROL CDF] `.info` file.

### Oggetto Files

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>Avvia l’array che contiene i metadati sui file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione file in byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. Il numero che segue il trattino mostra il numero di parti utilizzate per creare il file durante il caricamento in più parti. Il <code> ETag</code> non è identico al checksum MD5 del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Il nome del file. Consulta <a href="#cdf-naming-conventions"> Convenzioni di denominazione dei file dei feed di dati del cliente</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Un numero di indice per ciascun file. </p> </td> 
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
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>Avvia l'oggetto che contiene dati aggregati su tutti i file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Il giorno per il quale i dati sono disponibili. Usa <i>aaaa-mm-gg</i> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>L’ora per la quale sono disponibili i dati. Utilizza il formato 24 ore impostato nel fuso orario UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione totale di tutti i file CDF per tale data in byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Numero totale di file caricati nella directory S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] I tempi del nome file e del contenuto file sono diversi {#different-processing-times}

Il tuo [!UICONTROL CDF] il file contiene marche temporali nel nome e nel contenuto del file. Queste marche temporali registrano diversi processi evento per lo stesso [!UICONTROL CDF] file. Non è raro vedere marche temporali diverse nel nome e nel contenuto dello stesso file. Comprendere ogni marca temporale può aiutarti a evitare errori comuni quando lavori con questi dati o provi a ordinarli in base all’ora.

## Individuazione [!UICONTROL CDF] Timestamp file {#locating-timestamps}

[!UICONTROL CDF] i file registrano il tempo in modo diverso in 2 posizioni separate.

![](assets/cdf-timestamp.png)

## Comprensione della differenza tra marche temporali {#understanding-timestamps}

La tabella seguente fornisce ulteriori dettagli sul [!UICONTROL CDF] archiviare i timestamp insieme alle informazioni su come utilizzarli correttamente.

| Posizione marca temporale | Descrizione |
|--- |--- |
| Nome file | Il timestamp nel tuo [!DNL CDF] nome file indica il momento in cui [!DNL Audience Manager] ha iniziato a preparare il file per la consegna. Questa marca temporale è impostata in [!DNL UTC] fuso orario. Utilizza il `hour=` parametro, con ora formattata come ora a 2 cifre in formato 24 ore. Questa ora può essere diversa da quella dell’evento registrata nel contenuto del file. Quando si utilizzano [!DNL CDF] file, a volte noterai che il tuo [!DNL S3] il bucket è vuoto per un’ora specifica. Un bucket vuoto indica una delle seguenti situazioni:<ul><li>Non ci sono dati per quell&#39;ora particolare. </li><li> I nostri server sono soggetti a carichi pesanti e non sono in grado di elaborare i file per un&#39;ora specifica. Quando il server recupera, inserisce i file che avrebbero dovuto essere inseriti in un bucket precedente in un bucket con un valore temporale successivo. Ad esempio, questo si verifica quando un file che avrebbe dovuto essere nel bucket ore 17 viene visualizzato nel bucket ore 18 (con `hour=18` nel nome del file). In questo caso, è probabile che il server abbia iniziato l&#39;elaborazione del file nell&#39;ora 17, ma non è riuscito a completarlo entro tale intervallo di tempo. Viene invece eseguito il push del file al periodo fisso orario successivo.</li></ul><br>**Importante**: non utilizzare il timestamp del nome file per raggruppare gli eventi in base all’ora. Se è necessario eseguire il raggruppamento in base all&#39;ora, utilizzare `EventTime` timestamp nel contenuto del file. |
| Contenuto file | Il timestamp nel tuo [!DNL CDF] contenuto del file indica l&#39;ora [!DNL Data Collection Servers] ha iniziato l’elaborazione del file. Questa marca temporale è impostata in [!DNL UTC] fuso orario. Utilizza il `EventTime` campo, con ora formattata come *`yyyy-mm-dd hh:mm:ss`*. Questo tempo è vicino all’ora effettiva dell’evento sulla pagina, ma può essere diverso dall’indicatore delle ore nel nome del file. <br> **Suggerimento**: a differenza di `hour=` timestamp nel nome del file, puoi utilizzare `EventTime` per raggruppare i dati in base all&#39;ora. |

>[!MORELIKETHIS]
>
>* [Domande frequenti sui feed di dati cliente](../faq/faq-cdf.md)

