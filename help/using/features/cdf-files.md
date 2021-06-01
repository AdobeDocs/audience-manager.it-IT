---
description: Informazioni di base sui file CDF (Customer Data Feed) e su come iniziare. Inizia da qui se sei interessato a ricevere i file CDF o vuoi solo maggiori informazioni.
keywords: dati di seconde parti;dati di seconde parti;dati di seconde parti;dati di seconde parti
seo-description: Informazioni di base sui file CDF (Customer Data Feed) e su come iniziare. Inizia da qui se sei interessato a ricevere i file CDF o vuoi solo maggiori informazioni.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Feed dati cliente
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Feed dati cliente
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1935'
ht-degree: 4%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Informazioni di base sui file [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) e istruzioni su come iniziare. Inizia da qui se sei interessato a ricevere i file [!UICONTROL CDF] o se desideri solo ulteriori informazioni.

## Contenuto e scopo del file {#file-contents-purpose}

Un file [!UICONTROL CDF] contiene gli stessi dati che una chiamata evento di [!DNL Audience Manager] (`/event`) invia ai nostri server. Ciò include dati come ID utente, [!UICONTROL trait IDs], [!UICONTROL segment IDs] e tutti gli altri parametri acquisiti da una chiamata evento. I sistemi [!DNL Audience Manager] interni elaborano i dati evento in un file [!UICONTROL CDF] con il contenuto organizzato in campi che vengono visualizzati in un ordine impostato. [!DNL Audience Manager] tenta di generare  [!UICONTROL CDF] i file ogni ora e li memorizza in un bucket sicuro specifico per il cliente su un  [!DNL Amazon S3] server. Forniamo questi file in modo che tu possa lavorare con i dati [!DNL Audience Manager] al di fuori dei limiti imposti dalla nostra interfaccia utente.

>[!IMPORTANT]
>
>Tieni presente le seguenti restrizioni quando lavori con i file CDF:
>
>* Prima di configurare la distribuzione di file CDF, assicurati di disporre delle autorizzazioni appropriate da parte di fornitori di dati terzi per l’esportazione di caratteristiche di terze parti. Al momento, Audience Manager non supporta le funzionalità dell’interfaccia utente per richiedere l’autorizzazione di esportazione per la consegna di file CDF da Fornitori di dati di terze parti, quindi contatta l’utente in modo indipendente.
>* Non utilizzare i file [!UICONTROL CDF] come proxy per monitorare il traffico della pagina, riconciliare le discrepanze di report, o per la fatturazione, ecc.


## Introduzione {#getting-started}

Non esiste un processo self-service per avviare la consegna dei file [!UICONTROL CDF]. Contatta il tuo consulente [!DNL Audience Manager] o l&#39;Assistenza clienti per iniziare. Durante l&#39;implementazione, il tuo [!DNL Audience Manager] rappresentante :

* Imposta il bucket di archiviazione [!DNL Amazon S3].
* Immetti le credenziali di autenticazione di sola lettura [!DNL S3] nel bucket di archiviazione dei file. Non potrai visualizzare o accedere a directory e file appartenenti ad altri clienti.

Le notifiche dei file e i file [!UICONTROL CDF] verranno visualizzati nel bucket [!DNL S3] quando sono pronti per il download. Sei responsabile del monitoraggio e del download dei file dalla directory [!DNL S3] assegnata. Consulta [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## Passaggi successivi {#next-steps}

Le sezioni seguenti e le [Domande frequenti sui feed di dati cliente](../faq/faq-cdf.md) possono aiutarti a acquisire maggiore familiarità con questo servizio.

## [!UICONTROL Customer Data Feed] Contenuto definito  {#cdf-defined}

Elenca e definisce gli elementi e gli array di dati in un file [!UICONTROL CDF] in base all’ordine di aspetto. Le definizioni includono tipi di dati, ma queste informazioni non fanno parte di un file [!UICONTROL CDF].

## Definizioni {#definitions}

Un file [!UICONTROL CDF] include alcuni o tutti i campi definiti di seguito. Per informazioni sull&#39;organizzazione interna dei file, vedere [Struttura dei file dei feed di dati cliente](#cdf-file-structure).

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
   <td colname="col3"> <p>L'ora in cui un file CDF è stato elaborato da <span class="wintitle"> Data Collection Servers</span> (DCS). La marca temporale utilizza il formato <i>aaaa-mm-gg hh:mm:ss</i> ed è impostata nel fuso orario UTC. </p> <p> <p>Nota: L'ora evento <i>non è</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">L’ora dell’evento pagina o dell’evento si chiama da sola, anche se potrebbe essere vicina a tali ore. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Correlato all’ora DCS nel nome file. Vedi anche <a href="#different-processing-times"> Customer Data Feed File Name Times e File Content Times..</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Si tratta dell’ <span class="wintitle"> ID utente univoco</span> (UUID), che è un ID dispositivo a 38 cifre per il visitatore del sito. Vedi anche <a href="../reference/ids-in-aam.md"> Indice degli ID in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numeriche </p> </td> 
   <td colname="col3"> <p>ID del contenitore che attiva la sincronizzazione degli ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Array numerico </p> </td> 
   <td colname="col3"> <p>Array di ID di caratteristiche che contiene tutte le caratteristiche realizzate (idonee) da un visitatore nella chiamata dell’evento. </p> <p>L’array può contenere caratteristiche per le quali il visitatore si è qualificato in precedenza e per le quali è stato riqualificato tramite questa chiamata dell’evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Array numerico </p> </td> 
   <td colname="col3"> <p>Array di ID segmento che contiene tutti i segmenti realizzati da un visitatore (qualificato per ) nella chiamata dell’evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Una stringa che acquisisce tutti i parametri (variabili, ID, coppie chiave-valore, ID pubblicità dispositivo, ecc.) passato nella chiamata dell'evento. </p> <p>Esempio abbreviato: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
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
   <td colname="col3"> <p>L’ <span class="keyword"> Experience Cloud</span> ID (MID) assegnato al visitatore del sito. Consulta anche <a href="https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e il servizio Adobe Experience Platform Identity</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Array numerico </p> </td> 
   <td colname="col3"> <p>Array di ID segmento che contiene i segmenti realizzati in precedenza e i nuovi segmenti per i quali il visitatore è qualificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Array numerico </p> </td> 
   <td colname="col3"> <p>Array di ID di caratteristiche di prime e terze parti contenenti caratteristiche realizzate in precedenza e nuove caratteristiche per le quali il visitatore si è qualificato dall’ultimo feed di dati generato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Struttura dei file  {#cdf-file-structure}

Elenca e definisce la struttura dati di un file [!UICONTROL CDF]. Sono inclusi sequenza di dati, delimitatori e separatori di campi, una mappa file di dati e un file di esempio.

## Identificatori dei campi dati e sequenza {#identifiers-and-sequence}

[!UICONTROL CDF] i file non contengono colonne o intestazioni di campo con etichetta. Al contrario, un file [!UICONTROL CDF] definisce campi e array con caratteri [!DNL ASCII] non stampabili. Inoltre, il file [!UICONTROL CDF] elenca ogni campo e matrice in un ordine specifico. La comprensione degli identificatori e dell’ordine dei campi consente di analizzare correttamente il file.

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
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> o <code> ^A</code>) separa i dati dei singoli campi con un indicatore di spazio non stampabile. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> o <code> ^B</code>) separa i dati da un array e richiede parametri. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> o <code> ^C</code>) definisce coppie chiave-valore. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequenza campi </p> </td> 
   <td colname="col2"> <p> <p>Importante: <span class="keyword"> Audience Manager</span> si riserva il diritto di aggiungere nuovi campi alla fine del file CDF nelle versioni future. Ciò significa che la progettazione tecnica del sistema di analisi dei file non deve assumere un numero fisso di colonne (anche se può assumere un ordine fisso per le colonne esistenti). </p> </p> <p>I dati nel file CDF vengono visualizzati nell’ordine indicato di seguito. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Ora evento </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Dispositivo </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID contenitore </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Caratteristiche realizzate </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Segmenti realizzati </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parametri di richiesta </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referente </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Indirizzo IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID dispositivo di Experience Cloud (o MID). Consulta anche <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e il servizio Adobe Experience Platform Identity</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Tutti i segmenti </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Tutte le caratteristiche </li> 
     </ol> </p> <p>Per le descrizioni dei campi, vedere <a href="#cdf-defined"> Contenuto del feed di dati cliente definito</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Mappa dei file  {#cdf-file-map}

[!UICONTROL CDF] i dati del file vengono visualizzati nell’ordine indicato di seguito.

![](assets/sequence-map.png)

## Identificazione di array

Gli array in un file [!UICONTROL CDF] iniziano e terminano con il separatore di campo `Ctrl + a`. In questo modo il primo elemento di un array viene visualizzato come un campo dati autonomo. Ad esempio, l&#39;array realizzato [!UICONTROL traits] inizia con `^A1234`. Il delimitatore e l&#39;ID della matrice `^B5678` seguono questa voce. Di conseguenza, si potrebbe essere tentati di pensare che il primo elemento dell&#39;array realizzato [!UICONTROL traits] sia ID 5678 (perché inizia con `^B`). Questo non è il caso, ed è per questo che devi avere familiarità con la sequenza e la struttura di un file di dati. Anche se il primo elemento dell&#39;array [!UICONTROL trait] realizzato (o di qualsiasi altro array in un file [!UICONTROL CDF]) inizia con `^A`, l&#39;ordine di aspetto o di posizione nel file definisce l&#39;inizio di un array. Inoltre, il primo elemento di un array è sempre separato dalla voce precedente da `^A`.

## Esempio di file [!UICONTROL CDF] {#sample-file}

Un file di esempio [!UICONTROL CDF] potrebbe avere un aspetto simile al seguente. In questo esempio sono state inserite interruzioni di riga per adattarle alla pagina.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Convenzioni di denominazione dei file  {#cdf-naming-conventions}

Le sezioni seguenti elencano e definiscono gli elementi nel nome del file [!UICONTROL CDF].

## [!UICONTROL CDF] Nome file: Sintassi ed esempio  {#cdf-file-name}

Un nome file [!UICONTROL CDF] tipico contiene gli elementi elencati di seguito. Nota: *corsivo* indica un segnaposto variabile:

### Sintassi

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Esempio

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

Nel bucket di archiviazione [!DNL S3], i file vengono ordinati in ordine crescente in base all&#39;ID partner ([!UICONTROL PID]), al giorno e all&#39;ora.

## [!UICONTROL CDF] Elementi del nome file definiti  {#cdf-file-name-elements}

Nella tabella seguente sono elencati e definiti gli elementi in un nome di file [!UICONTROL CDF].

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nome file </th> 
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
   <td colname="col2"> <p>Il nome del bucket S3 di sola lettura che contiene i file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Data di elaborazione del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Un valore di ora espresso in notazione 24 ore e impostato nel fuso orario UTC. Vedi anche <a href="#different-processing-times"> Customer Data Feed File Name Times e File Content Times..</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Il tuo ID partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Un ID di processo interno <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Estensione del file gzip. I file CDF sono compressi con Gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Notifiche di elaborazione dei file  {#cdf-file-processing-notifications}

[!DNL Audience Manager] scrive un  `.info` file nella tua  [!DNL S3] directory per informarti quando il tuo  [!UICONTROL Customer Data File] ([!UICONTROL CDF]) è pronto per il download. Il file `.info` include anche [!DNL JSON] metadati formattati sul contenuto dei file [!UICONTROL CDF]. Leggi questa sezione per informazioni sulla sintassi e i campi utilizzati da questo file di notifica.

## File di informazioni di esempio {#sample-info-file}

Ogni file `.info` contiene una sezione `Files` e `Totals`. La sezione `Files` contiene un array che contiene metriche specifiche per ciascun file ogni ora. La sezione `Totals` contiene metriche aggregate per tutti i file [!UICONTROL CDF] di un giorno specifico. Il contenuto del file `.info` potrebbe avere un aspetto simile al seguente esempio.

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

## Campi file di informazioni definiti {#info-file-fields-defined}

Le tabelle seguenti elencano e definiscono gli elementi in un file [!UICONTROL CDF] `.info` .

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
   <td colname="col2"> <p>Avvia la matrice che contiene i metadati sui file CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione del file in byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. Il numero che segue il trattino mostra il numero di parti utilizzate per creare il file durante il caricamento in più parti. Il <code> ETag</code> non è identico al checksum MD5 del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Nome del file. Consulta <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
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
   <td colname="col2"> <p>Il giorno per cui i dati sono disponibili. Utilizza il formato <i>aaaa-mm-gg</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>L’ora per la quale i dati sono disponibili. Utilizza il formato 24 ore impostato nel fuso orario UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dimensione totale in byte di tutti i file CDF per quella data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Numero totale di file caricati nella directory S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] I tempi e i tempi del contenuto dei file sono diversi  {#different-processing-times}

Il file [!UICONTROL CDF] contiene timestamp nel nome del file e nel contenuto del file. Queste marche temporali registrano diversi processi evento per lo stesso file [!UICONTROL CDF]. Non è raro visualizzare marche temporali diverse nel nome e nel contenuto dello stesso file. La comprensione di ogni marca temporale può aiutarti a evitare errori comuni quando lavori con questi dati o provi a ordinarli per tempo.

## Individuazione di [!UICONTROL CDF] timestamp file {#locating-timestamps}

[!UICONTROL CDF] i file registrano il tempo in modo diverso in 2 posizioni separate.

![](assets/cdf-timestamp.png)

## Differenza tra marche temporali {#understanding-timestamps}

La tabella seguente fornisce ulteriori dettagli sulle marche temporali del file [!UICONTROL CDF] insieme a informazioni su come utilizzarle correttamente.

| Posizione timestamp | Descrizione |
|--- |--- |
| Nome file | La marca temporale nel nome del file [!DNL CDF] indica l’ora in cui [!DNL Audience Manager] ha iniziato a preparare il file per la consegna. Questa marca temporale è impostata nel fuso orario [!DNL UTC]. Utilizza il parametro `hour=`, con il tempo formattato come ora a 2 cifre nella notazione a 24 ore. Questa ora può essere diversa da quella registrata nel contenuto del file. Quando lavori con i file [!DNL CDF], a volte noterai che il tuo bucket [!DNL S3] è vuoto per un’ora specifica. Un bucket vuoto indica che può indicare uno dei seguenti elementi:<ul><li>Non ci sono dati per quell&#39;ora in particolare. </li><li> I nostri server sono sotto carichi pesanti e non possono elaborare i file per un&#39;ora specifica. Quando il server raggiunge, inserisce i file che avrebbero dovuto essere presenti in un file bucket di una data precedente in un bucket con un valore di tempo successivo. Ad esempio, lo vedrai quando un file che dovrebbe essere stato nel bucket ore 17 verrà visualizzato nel bucket ore 18 (con `hour=18` nel nome del file). In questo caso, probabilmente il server ha iniziato l&#39;elaborazione del file nell&#39;ora 17 ma non è riuscito a completarlo entro tale intervallo di tempo. Al contrario, il file viene inviato al bucket ora oraria successivo.</li></ul><br>**Importante**: Non utilizzare la marca temporale del nome file per raggruppare gli eventi per ora. Se devi raggruppare per ora, utilizza la marca temporale `EventTime` nel contenuto del file. |
| Contenuto del file | La marca temporale nel contenuto del file [!DNL CDF] indica il momento in cui [!DNL Data Collection Servers] ha iniziato a elaborare il file. Questa marca temporale è impostata nel fuso orario [!DNL UTC]. Utilizza il campo `EventTime`, con il tempo formattato come *`yyyy-mm-dd hh:mm:ss`*. Questa ora è vicina all&#39;ora effettiva dell&#39;evento sulla pagina, ma può essere diversa dall&#39;indicatore dell&#39;ora nel nome del file. <br> **Suggerimento**: A differenza della  `hour=` marca temporale nel nome del file, è possibile utilizzare  `EventTime` per raggruppare i dati per ora. |

>[!MORELIKETHIS]
>
>* [Domande frequenti sui feed di dati cliente](../faq/faq-cdf.md)

