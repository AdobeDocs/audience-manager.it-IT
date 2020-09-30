---
description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l'invio dei dati a  Audience Manager. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una directory FTP  Audience Manager.
seo-description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l'invio dei dati a  Audience Manager. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una directory FTP  Audience Manager.
seo-title: Requisiti FTP di nome e dimensione file per i file di dati in entrata
solution: Audience Manager
title: Requisiti FTP di nome e dimensione file per i file di dati in entrata
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: f037a12af641da44ed67e62a249c41487da7ac07
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 8%

---


# [!DNL FTP]Requisiti di nome e dimensione file per i file di dati in entrata{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l&#39;invio dei dati a [!DNL Audience Manager]. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una [!DNL FTP] directory di Audience Manager .

>[!WARNING]
>
>We are gradually phasing out support for [!DNL FTP] configurations. While inbound data file ingestion is still supported in existing [!DNL FTP] integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. Per informazioni dettagliate, consulta [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicano gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Sintassi nome file {#file-name-syntax}

[!DNL FTP] i nomi dei file contengono i seguenti elementi obbligatori e facoltativi:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Per altri formati di file accettati, consulta Integrazioni [partner](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personalizzate.

>[!NOTE]
>
>[!DNL Audience Manager] elabora solo file [!DNL ASCII] e file [!DNL UTF-8] codificati.

### Elementi nome

La tabella definisce gli elementi in un nome di [!DNL FTP] file.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento nome file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Percorso e nome della directory FTP del Audience Manager <span class="keyword"></span> . Contatta il tuo Account Manager per conoscere la directory e le credenziali dell'FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID che indica <span class="keyword"> Audience Manager</span> se un file di dati contiene ID utente, ID Android, ID iOS o altri ID che appartengono a origini <a href="/help/using/features/global-data-sources.md"> dati</a>globali. Accetta le seguenti opzioni:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID origine dati (noto anche come ID provider dati):</b> Si tratta di un ID univoco che  Audience Manager assegna a un'origine dati (fare riferimento all'indice del Audience Manager  <a href="/help/using/reference/ids-in-aam.md"> degli ID </a>). Utilizzate questo ID assegnato in un nome file per l'invio di dati che contengono i vostri ID utente. Ad esempio, <code>...ftp_dpm_21_123456789.sync</code> indica a <span class="keyword"> Audience Manager</span> i dati di bordo agli ID appartenenti all’origine dati 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID Android (GAID):</b> Utilizzate ID 20914 in un nome file di dati se contiene ID Android. È necessario utilizzare il campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> quando si utilizzano gli ID Android. Ad esempio, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> indica <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID Android e gli ID devono essere idonei per le caratteristiche appartenenti all'origine <code><i>_DPID_TARGET_DATA_OWNER</i></code> dati.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA):</b> Usa l'ID 20915 in un nome file di dati se contiene ID iOS. È necessario utilizzare il campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> quando si utilizzano gli ID iOS. Ad esempio, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> indica <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID iOS e gli ID devono essere idonei per le caratteristiche appartenenti all'origine <code><i>_DPID_TARGET_DATA_OWNER</i></code> dati.</li>
     <li> <b>ID appartenenti ad altre origini</b>dati globali: Potete utilizzare gli ID Roku per la pubblicità (RIDA), gli ID pubblicitari Microsoft (MAID) e altri ID. Utilizzare l'ID corrispondente a ciascuna origine dati, come descritto nell'articolo <a href="/help/using/features/global-data-sources.md"> origini dati</a>globali.</li> 
    </ul> <p> <p>Nota:  Non utilizzare tipi di ID misti nei file di dati. Ad esempio, se il nome file include l'identificatore Android, non inserire gli ID iOS o i tuoi ID nel file di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Questo campo indica  Audience Manager a quale origine dati includere i dati a bordo. Questo campo è obbligatorio se imposti il DPID su un ID Android o iOS o su un altro ID appartenente a origini dati globali. Questo consente <span class="keyword"> Audience Manager</span> di ricollegare i dati del file alla propria organizzazione. </p> <p>Ad esempio: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> indica  Audience Manager che gli ID cliente qualificati appartengono all'origine dati 33 per caratteristiche o segnali appartenenti all'origine dati 21. </li> 
     <li> <b>ID Android (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> indica <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID Android e gli ID devono essere idonei per le caratteristiche appartenenti all'origine dati 21.</li> 
     <li> <b>ID iOS (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> indica <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID iOS e gli ID devono essere idonei per le caratteristiche appartenenti all'origine dati 21.</li>
     <li> <b>ID appartenenti ad altre origini</b>dati globali: <code>...ftp_dpm_121963_21_1234567890.sync</code> indica <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID Roku e che gli ID devono essere idonei per le caratteristiche appartenenti all'origine dati 21. Utilizzare l'ID corrispondente a ciascuna origine dati, come descritto nell'articolo <a href="/help/using/features/global-data-sources.md"> origini dati</a>globali.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opzioni di sincronizzazione che includono: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scenario normale in cui i fornitori di dati di terze parti inviano caratteristiche in base all'utente da aggiungere o rimuovere nel Audience Manager . </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Consente a clienti e fornitori di dati di inviare un elenco di caratteristiche in base agli utenti, che dovrebbero sovrascrivere tutte le caratteristiche esistenti di questo utente per una determinata origine dati in  Audience Manager. Non è necessario includere tutti gli utenti in un file di sovrascrittura. Includete solo gli utenti che desiderate modificare. Le caratteristiche non assegnate all'origine dati di destinazione non verranno cancellate. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si suddividono file di grandi dimensioni in più parti per migliorare i tempi di elaborazione. Il numero indica quale parte del file originale viene inviata. </p> <p>Per un'elaborazione efficiente dei file, suddividere i file di dati come indicato: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compresso: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compresso: 200-300 MB </li> 
    </ul> <p>Vedere i primi due esempi <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"></a> di nome file riportati di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Marca temporale UTC di 10 cifre in secondi. La marca temporale consente di rendere univoco ciascun nome file. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip è il formato di compressione consentito per il nome di un file FTP. Se utilizzate la compressione file, accertatevi che il nome del file abbia l'estensione corretta. </p> <p>I file compressi devono essere di almeno 3 GB. Se i file sono più grandi, rivolgiti all'Assistenza clienti. Anche se  Audience Manager può gestire file di grandi dimensioni, possiamo aiutarti a ridurre le dimensioni dei file e rendere più efficiente il trasferimento dei dati. Consulta <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">File Compression for Inbound Data Transfer Files</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di nomi file {#file-name-examples}

Gli esempi seguenti mostrano nomi di file formattati correttamente. I nomi dei file potrebbero essere simili.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Scaricate](assets/ftp_dpm_1234_1445374061.overwrite) il file di esempio se avete bisogno di ulteriori esempi. Questo file viene salvato con l&#39;estensione del `.overwrite` file. Aprite l’applicazione con un semplice editor di testo.

## Dimensioni file accettate {#accepted-file-sizes}

Considerare le figure riportate di seguito per l&#39;elaborazione più rapida/rapida dei file e per i limiti di dimensione dei file quando si inviano dati a una [!DNL Audience Manager] / [!DNL FTP] directory.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo file </th> 
   <th colname="col2" class="entry"> Dimensione ottimale </th> 
   <th colname="col3" class="entry"> Dimensione massima </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Compresso</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Non compresso</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Requisiti di nome di Amazon S3 per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

