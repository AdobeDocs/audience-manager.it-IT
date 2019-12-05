---
description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l'invio di dati ad Audience Manager. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una directory FTP di Audience Manager.
seo-description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l'invio di dati ad Audience Manager. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una directory FTP di Audience Manager.
seo-title: Requisiti di nome e dimensione file FTP per i file di dati in entrata
solution: Audience Manager
title: Requisiti di nome e dimensione file FTP per i file di dati in entrata
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
translation-type: tm+mt
source-git-commit: 881ccf512e9776948e4507e321e972dd2079e21a

---


# Requisiti di nome e dimensione file FTP per i file di dati in entrata{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l'invio di dati ad Audience Manager. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una [!DNL FTP] directory Audience Manager.

>[!WARNING]
>
>Stiamo gradualmente eliminando il supporto per le configurazioni FTP. Anche se l'assimilazione dei file di dati in entrata è ancora supportata nelle integrazioni FTP esistenti, si consiglia vivamente di utilizzare Amazon S3 per incorporare dati offline per nuove integrazioni. Per informazioni dettagliate, consultate [Amazon S3 Name and File Size Requirements for Inbound Data Files (Requisiti di nome e dimensione file Amazon S3 per i file](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) in entrata).

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicano gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Sintassi nome file {#file-name-syntax}

[!DNL FTP] i nomi dei file contengono i seguenti elementi obbligatori e facoltativi:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Per altri formati di file accettati, consulta Integrazioni [partner](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personalizzate.

>[!NOTE] {important="high"}
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
   <td colname="col2"> <p>Percorso e nome della directory FTP di <span class="keyword"> Audience Manager</span> . Contatta il tuo Account Manager per conoscere la directory e le credenziali FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID che informa <span class="keyword"> Audience Manager</span> se un file di dati contiene gli ID utente o gli ID Android o iOS personali. Accetta le seguenti opzioni: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b></b> ID partner dati: Si tratta di un ID univoco assegnato da Audience Manager alla tua società o organizzazione. Utilizzate questo ID assegnato in un nome file quando inviate dati che contengono i vostri ID utente. Ad esempio, <code>...ftp_dpm_21_123456789.sync</code> indica <span class="keyword"> ad Audience Manager</span> che un partner con ID 21 ha inviato il file e contiene gli ID utente assegnati da tale partner. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b></b> ID Android (GAID): Usa l'ID 20914 in un nome file di dati se contiene un ID Android. Ad esempio, <code>...ftp_dpm_20914_123456789.sync</code> indica <span class="keyword"> ad Audience Manager</span> che il file di dati contiene solo ID Android. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b></b> ID iOS (IDFA): Usa l'ID 20915 in un nome file di dati se contiene ID iOS. Ad esempio, <code>...ftp_dpm_20915_123456789.sync</code> indica <span class="keyword"> ad Audience Manager</span> che il file di dati contiene solo ID iOS. </li> 
    </ul> <p> <p>Nota:  Non utilizzare tipi di ID misti nei file di dati. Ad esempio, se il nome file include l'identificatore Android, non inserire gli ID iOS o i tuoi ID nel file di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Un segnaposto per un ID. Ad esempio, puoi impostarlo sull’ID <span class="keyword"> Audience Manager</span> se imposti il DPID su un ID origine dati o su un ID Android o iOS. In questo modo <span class="keyword"> Audience Manager</span> collega i dati del file alla tua organizzazione. </p> <p>Ad esempio: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> mostra che un partner con ID 21 ha inviato dati da un'origine dati che utilizza ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> mostra che un partner con ID 21 ha inviato dati che contengono ID Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> mostra che un partner con ID 21 ha inviato dati che contengono ID iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opzioni di sincronizzazione che includono: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scenario normale in cui i fornitori di dati di terze parti inviano caratteristiche in base all’utente da aggiungere o rimuovere nel sistema Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Consente a clienti e fornitori di dati di inviare un elenco di caratteristiche in base agli utenti, che dovrebbero sovrascrivere tutte le caratteristiche esistenti di questo utente per una determinata origine dati in Audience Manager. Non è necessario includere tutti gli utenti in un file di sovrascrittura. Includete solo gli utenti che desiderate modificare. Le caratteristiche non assegnate all'origine dati di destinazione non verranno cancellate. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si suddividono file di grandi dimensioni in più parti per migliorare i tempi di elaborazione. Il numero indica quale parte del file originale viene inviata. </p> <p>Per un'elaborazione efficiente dei file, suddividere i file di dati come indicato: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compresso: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compresso: 200-300 MB </li> 
    </ul> <p>Vedere i primi due esempi <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"></a> di nome file riportati di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Marca temporale UTC di 10 cifre in secondi. La marca temporale consente di rendere univoco ciascun nome file. </p> 
    <draft-comment> 
     <p> <p>Nota:  Audience Manager non utilizza la marca temporale durante l'elaborazione dei file in ingresso. La marca temporale nel nome del file è stata rimossa da Audience Manager ma è comunque necessaria per la compatibilità con le versioni precedenti. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip è il formato di compressione consentito per il nome di un file FTP. Se utilizzate la compressione file, accertatevi che il nome del file abbia l'estensione corretta. </p> <p>I file compressi devono essere di almeno 3 GB. Se i file sono più grandi, rivolgiti all'Assistenza clienti. Anche se Audience Manager è in grado di gestire file di grandi dimensioni, potrebbe essere utile ridurre le dimensioni dei file e rendere più efficienti i trasferimenti di dati. Vedere <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Compressione file per i file</a> di trasferimento dati in entrata. </p> </td> 
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

[Scaricate](assets/ftp_dpm_1234_1445374061.overwrite) il file di esempio se avete bisogno di ulteriori esempi. Questo file viene salvato con l'estensione del `.overwrite` file. Aprite l’immagine con un semplice editor di testo.

## Dimensioni file accettate {#accepted-file-sizes}

Considerare le figure riportate di seguito per l'elaborazione più rapida/rapida dei file e per i limiti di dimensione dei file quando si inviano dati a una [!DNL Audience Manager] / [!DNL FTP] directory.

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
   <td colname="col2"> <p> 200-300 MB </p> </td> 
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

