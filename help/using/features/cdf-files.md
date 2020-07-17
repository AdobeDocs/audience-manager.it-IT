---
description: Informazioni di base sui file CDF (Customer Data Feed) e istruzioni su come iniziare. Iniziate da qui se siete interessati a ricevere i file CDF o volete solo ulteriori informazioni.
keywords: second party data;2nd party;2nd party data;second party
seo-description: Informazioni di base sui file CDF (Customer Data Feed) e istruzioni su come iniziare. Iniziate da qui se siete interessati a ricevere i file CDF o volete solo ulteriori informazioni.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Customer Data Feeds
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 4%

---


# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Informazioni di base sui [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) file e istruzioni su come iniziare. Iniziate da qui se siete interessati a ricevere [!UICONTROL CDF] file o volete solo ulteriori informazioni.

## Contenuto file e scopo {#file-contents-purpose}

Un file [!UICONTROL CDF] contiene gli stessi dati che una chiamata evento di [!DNL Audience Manager] (`/event`) invia ai nostri server. This includes data like user IDs, [!UICONTROL trait IDs], [!UICONTROL segment IDs], and all the other parameters captured by an event call. I [!DNL Audience Manager] sistemi interni elaborano i dati evento in un [!UICONTROL CDF] file con il contenuto organizzato in campi che vengono visualizzati in un ordine impostato. [!DNL Audience Manager] tenta di generare [!UICONTROL CDF] i file ogni ora e li memorizza in un bucket sicuro e specifico per il cliente su un [!DNL Amazon S3] server. Forniamo questi file in modo che possiate lavorare con [!DNL Audience Manager] i dati al di fuori dei limiti imposti dalla nostra interfaccia utente.

>[!NOTE]
>
>Non utilizzare [!UICONTROL CDF] i file come proxy per monitorare il traffico delle pagine, riconciliare le discrepanze dei rapporti, o per la fatturazione, ecc.

## Introduzione {#getting-started}

Non esiste un processo self-service per avviare la consegna dei [!UICONTROL CDF] file. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. Durante l&#39;implementazione, il tuo [!DNL Audience Manager] rappresentante:

* Configurare il bucket [!DNL Amazon S3] di archiviazione.
* Fornire le credenziali di autenticazione di sola lettura [!DNL S3] al bucket di archiviazione file. Non potrai vedere né accedere a directory e file appartenenti ad altri clienti.

Le notifiche e [!UICONTROL CDF] i file vengono visualizzati nel [!DNL S3] bucket quando sono pronti per il download. Siete responsabili del monitoraggio e del download dei file dalla [!DNL S3] directory assegnata. Consulta [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## Passaggi successivi {#next-steps}

Le sezioni seguenti e le domande frequenti sui feed di dati [cliente](../faq/faq-cdf.md) possono aiutarti a familiarizzare con questo servizio.

## [!UICONTROL Customer Data Feed] Contenuto definito {#cdf-defined}

Elenca e definisce gli elementi e gli array di dati in un [!UICONTROL CDF] file, in base all&#39;ordine di aspetto. Le definizioni includono i tipi di dati, ma queste informazioni non fanno parte di un [!UICONTROL CDF] file.

## Definizioni {#definitions}

Un [!UICONTROL CDF] file include alcuni o tutti i campi definiti di seguito. Per informazioni sull&#39;organizzazione interna dei file, vedere Struttura [dei file dei feed di dati](#cdf-file-structure)cliente.

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
   <td colname="col3"> <p>L'ora in cui un file CDF è stato elaborato dai server <span class="wintitle"> di raccolta</span> dati (DCS). Il timestamp utilizza il formato <i>yyyy-mm-dd hh:mm:ss</i> ed è impostato nel fuso orario UTC. </p> <p> <p>Nota: L'ora evento non <i>è</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">L'ora dell'evento pagina o l'evento si chiama da sola, anche se potrebbe essere vicino a tali ore. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relativo all’ora DCS nel nome del file. Vedi anche: <a href="#different-processing-times"> Data Feed File Time Nome e File Content Times..</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Si tratta dell’ <span class="wintitle"> ID</span> utente univoco (UUID), un ID dispositivo di 38 cifre per il visitatore del sito. See also, <a href="../reference/ids-in-aam.md"> Index of IDs in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numeriche </p> </td> 
   <td colname="col3"> <p>ID del contenitore che attiva la sincronizzazione ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID caratteristica che contiene tutte le caratteristiche realizzate (qualificate) da un visitatore nella chiamata all’evento. </p> <p>L’array può contenere caratteristiche per le quali il visitatore ha già acquisito i requisiti necessari e per le quali ha ottenuto i requisiti per questa chiamata dell’evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID di segmento che contiene tutti i segmenti realizzati (qualificati) da un visitatore nella chiamata all’evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Una stringa che acquisisce tutti i parametri (variabili, ID, coppie chiave-valore, ID pubblicità dispositivo, ecc.) passato alla chiamata dell’evento. </p> <p>Esempio abbreviato: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>L’URL non codificato della pagina di riferimento (se presente). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>L’indirizzo IP del visitatore acquisito nella chiamata dell’evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>L’ <span class="keyword"> ID Experience Cloud</span> (MID)  assegnato al visitatore del sito. Vedi anche <a href="https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies e Adobe  Experience Platform Identity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID di segmento che contiene segmenti realizzati in precedenza e nuovi segmenti per i quali il visitatore è qualificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Matrice numerica </p> </td> 
   <td colname="col3"> <p>Un array di ID di caratteristiche di prime e terze parti che contiene caratteristiche realizzate in precedenza e caratteristiche nuove per le quali il visitatore si è qualificato dall’ultimo feed di dati generato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Struttura file {#cdf-file-structure}

Elenca e definisce la struttura dati di un [!UICONTROL CDF] file. Sono inclusi sequenza di dati, delimitatori e separatori di campi, una mappa di file di dati e un file di esempio.

## Identificatori dei campi dati e sequenza {#identifiers-and-sequence}

[!UICONTROL CDF] i file non contengono colonne con etichetta o intestazioni di campo. Al contrario, un [!UICONTROL CDF] file definisce campi e array con [!DNL ASCII] caratteri non stampabili. Inoltre, il [!UICONTROL CDF] file elenca ciascun campo e array in un ordine specifico. La comprensione degli identificatori e dell&#39;ordine dei campi facilita l&#39;analisi del file.

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> o <code> ^A</code>) separa i dati di singoli campi con un indicatore dello spazio non stampabile. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> o <code> ^B</code>) separa i dati da un array e richiede i parametri. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> o <code> ^C</code>) definisce le coppie chiave-valore. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequenza campi </p> </td> 
   <td colname="col2"> <p> <p>Importante: <span class="keyword">  Audience Manager</span> si riserva il diritto di aggiungere nuovi campi alla fine del file CDF nelle release future. Ciò significa che la progettazione tecnica del sistema di analisi dei file non deve assumere un numero fisso di colonne (anche se può assumere un ordine fisso per le colonne esistenti). </p> </p> <p>I dati nel file CDF vengono visualizzati nell'ordine indicato di seguito. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Ora evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Dispositivo </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID contenitore </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Caratteristiche realizzate </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmenti Realizzati </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parametri di richiesta </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referente </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Indirizzo IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8"> ID dispositivo Experience Cloud (o MID). See also, <a href="https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Adobe Experience Platform Identity Service</a> </li> 
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

Gli array di un [!UICONTROL CDF] file iniziano e terminano con il separatore di `Ctrl + a` campo. In questo modo il primo elemento di una matrice viene visualizzato come un campo di dati standalone. Ad esempio, l&#39; [!UICONTROL traits] array realizzato inizia con `^A1234`. Il delimitatore e l&#39;ID della matrice `^B5678` seguono questa voce. Di conseguenza, potreste essere tentati di pensare che il primo elemento nell&#39;array realizzato sia [!UICONTROL traits] ID 5678 (perché inizia con `^B`). Questo non è il caso, motivo per cui è necessario avere familiarità con la sequenza e la struttura di un file di dati. Anche se il primo elemento dell&#39;array realizzato [!UICONTROL trait] (o qualsiasi altro array di un [!UICONTROL CDF] file) inizia con `^A`, l&#39;ordine di aspetto o di posizione nel file definisce l&#39;inizio di una matrice. Inoltre, il primo elemento di un array è sempre separato dalla voce precedente per `^A`.

## Sample [!UICONTROL CDF] File {#sample-file}

Un [!UICONTROL CDF] file di esempio potrebbe essere simile al seguente. In questo esempio sono state inserite interruzioni di riga per adattarle alla pagina.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Convenzioni di denominazione dei file {#cdf-naming-conventions}

Le sezioni seguenti elencano e definiscono gli elementi nel nome del [!UICONTROL CDF] file.

## [!UICONTROL CDF] Nome file: Sintassi ed esempio {#cdf-file-name}

Un nome [!UICONTROL CDF] file tipico contiene gli elementi elencati di seguito. Note, *italics* indicates a variable placeholder:

### Sintassi

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Esempio

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

Nel periodo di [!DNL S3] archiviazione, i file vengono ordinati in ordine crescente in base all&#39;ID partner ([!UICONTROL PID]), al giorno e all&#39;ora.

## [!UICONTROL CDF] Elementi nome file definiti {#cdf-file-name-elements}

Nella tabella seguente sono elencati e definiti gli elementi presenti nel nome di un [!UICONTROL CDF] file.

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
   <td colname="col2"> <p>Si tratta del bucket di memorizzazione principale predefinito per il file CDF su un server Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Il nome del bucket S3 di sola lettura che contiene i file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Un valore di ora espresso in notazione a 24 ore e impostato nel fuso orario UTC. Vedi anche: <a href="#different-processing-times"> Data Feed File Time Nome e File Content Times..</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Il tuo ID partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Un ID di processo Audience Manager <span class="keyword"></span>  interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Estensione del file gzip. I file CDF vengono compressi con gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Notifiche di elaborazione dei file {#cdf-file-processing-notifications}

[!DNL Audience Manager] scrive un `.info` file nella [!DNL S3] directory per informarvi quando [!UICONTROL Customer Data File] ([!UICONTROL CDF]) è pronto per il download. Il `.info` file include anche metadati [!DNL JSON] formattati relativi al contenuto dei [!UICONTROL CDF] file. Leggere questa sezione per informazioni sulla sintassi e i campi utilizzati da questo file di notifica.

## Esempio di file {#sample-info-file}

Ogni `.info` file contiene una `Files` sezione e `Totals` . La `Files` sezione contiene un array che contiene metriche specifiche per ciascun file ogni ora. La `Totals` sezione contiene metriche aggregate per tutti i [!UICONTROL CDF] file per un giorno particolare. Il contenuto del `.info` file potrebbe essere simile al seguente esempio.

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

## Campi di file Info definiti {#info-file-fields-defined}

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
   <td colname="col2"> <p>Avvia la matrice che contiene i metadati relativi ai file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione del file in byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. Il numero che segue il trattino mostra il numero di parti utilizzate per creare il file durante il caricamento di più parti. Il valore non <code> ETag</code> è identico al checksum MD5 del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Nome del file. See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Numero di indice per ciascun file. </p> </td> 
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
   <td colname="col2"> <p>Il giorno per il quale i dati sono disponibili. Utilizza il formato <i>yyyy-mm-dd</i> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>L'ora per la quale i dati sono disponibili. Utilizza il formato 24 ore impostato nel fuso orario UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione totale in byte di tutti i file CDF per tale data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Numero totale di file caricati nella directory S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] I tempi dei nomi dei file e i tempi dei contenuti dei file sono diversi {#different-processing-times}

Il [!UICONTROL CDF] file contiene marche temporali nel nome del file e nel contenuto del file. Tali marche temporali registrano diversi processi di evento per lo stesso [!UICONTROL CDF] file. Non è raro che il nome e il contenuto dello stesso file contengano marche temporali diverse. La comprensione di ciascuna marca temporale può aiutarti a evitare errori comuni quando lavori con questi dati o cerchi di ordinarli per ora.

## Individuazione delle marche temporali [!UICONTROL CDF] del file {#locating-timestamps}

[!UICONTROL CDF] i file registrano il tempo in modo diverso in 2 posizioni separate.

![](assets/cdf-timestamp.png)

## Comprendere la differenza tra le marche temporali {#understanding-timestamps}

La tabella seguente fornisce ulteriori dettagli sulle marche temporali [!UICONTROL CDF] del file e informazioni su come utilizzarle correttamente.

| Posizione timestamp | Descrizione |
|--- |--- |
| Nome file | La marca temporale nel nome del [!DNL CDF] file indica l’ora in cui è [!DNL Audience Manager] iniziata la preparazione del file per la consegna. Questa marca temporale è impostata nel fuso [!DNL UTC] orario. Utilizza il `hour=` parametro, con il tempo formattato come ora a 2 cifre nella notazione a 24 ore. Questa ora può essere diversa dall&#39;ora dell&#39;evento registrata nel contenuto del file. Quando lavorate con [!DNL CDF] i file, talvolta noterete che il [!DNL S3] bucket è vuoto per un&#39;ora particolare. Un bucket vuoto può indicare una delle seguenti situazioni:<ul><li>Non ci sono dati per quella particolare ora. </li><li> I nostri server sono sottoposti a carichi pesanti e non possono elaborare i file per un&#39;ora particolare. Quando il server raggiunge, inserisce i file che avrebbero dovuto passare in un bucket di tempo precedente in un bucket con un valore di ora successivo. Ad esempio, questo verrà visualizzato quando un file che avrebbe dovuto essere nel bucket ore 17 viene visualizzato nel bucket ore 18 (con `hour=18` nel nome del file). In questo caso, il server probabilmente ha iniziato l&#39;elaborazione del file nell&#39;ora 17 ma non è stato possibile completarlo entro tale intervallo di tempo. Al contrario, il file viene inviato al bucket orario successivo.</li></ul><br>**Importante **: Non utilizzate la marca temporale del nome del file per raggruppare gli eventi per ora. Per raggruppare in base all’ora, usate la`EventTime`marca temporale nel contenuto del file. |
| Sommario file | La marca temporale nel contenuto del [!DNL CDF] file indica l&#39;ora in cui il file è stato [!DNL Data Collection Servers] avviato. Questa marca temporale è impostata nel fuso [!DNL UTC] orario. Utilizza il `EventTime` campo, con il tempo formattato come *`yyyy-mm-dd hh:mm:ss`*. Questa ora è vicina all&#39;ora effettiva dell&#39;evento sulla pagina, ma può essere diversa dall&#39;indicatore dell&#39;ora nel nome del file. <br> **Suggerimento**: A differenza della `hour=` marca temporale nel nome del file, è possibile raggruppare i dati `EventTime` per ora. |

>[!MORELIKETHIS]
>
>* [Domande frequenti sui feed di dati cliente](../faq/faq-cdf.md)

