---
description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni dei file richiesti per l’invio dei dati ad Audience Manager. Imposta i nomi e le dimensioni dei file in base a queste specifiche quando invii dati a una directory FTP di Audience Manager.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Requisiti FTP di nome e dimensione file per i file di dati in entrata
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 6%

---

# [!DNL FTP]Requisiti di nome e dimensione file per i file di dati in entrata {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni dei file richiesti per l’invio dei dati a [!DNL Audience Manager]. Impostare i nomi e le dimensioni dei file in base a queste specifiche quando si inviano dati a un Audience Manager [!DNL FTP] directory.

>[!WARNING]
>
>Stiamo gradualmente eliminando il sostegno per [!DNL FTP] configurazioni. Mentre l’acquisizione di file di dati in entrata è ancora supportata in [!DNL FTP] integrazioni, consigliamo vivamente di utilizzare [!DNL Amazon S3] per integrare dati offline per nuove integrazioni. Per informazioni dettagliate, consulta [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicare gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Sintassi nome file {#file-name-syntax}

[!DNL FTP] i nomi dei file contengono i seguenti elementi obbligatori e facoltativi:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Per altri formati di file con nome accettati, vedere [Integrazioni di partner personalizzate](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] solo i processi [!DNL ASCII] e [!DNL UTF-8] file codificati.

### Elementi nome

La tabella definisce gli elementi in un [!DNL FTP] nome file.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nome file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Percorso e nome del <span class="keyword"> Audience Manager</span> Directory FTP. Contatta il tuo Account Manager per conoscere la directory e le credenziali FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID che dice <span class="keyword"> Audience Manager</span> se un file di dati contiene i tuoi ID utente, ID Android, ID iOS o altri ID appartenenti a <a href="/help/using/features/global-data-sources.md"> origini dati globali</a>. Accetta le seguenti opzioni:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID origine dati (noto anche come ID fornitore dati):</b> Si tratta di un ID univoco che Audience Manager assegna a un’origine dati (consulta l’Audience Manager <a href="/help/using/reference/ids-in-aam.md"> indice degli ID </a>). Utilizza questo ID assegnato in un nome file quando invii dati che contengono i tuoi ID utente. Ad esempio: <code>...ftp_dpm_21_123456789.sync</code> racconta <span class="keyword"> Audience Manager</span> per integrare dati in ID appartenenti all’origine dati 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID Android (GAID):</b> Usa l’ID 20914 in un nome file di dati se contiene ID Android. È necessario utilizzare il campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> quando utilizzi gli ID Android. Ad esempio: <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> racconta <span class="keyword"> Audience Manager</span> che il file di dati contenga solo ID Android e che gli ID siano qualificati per le caratteristiche appartenenti al <code><i>_DPID_TARGET_DATA_OWNER</i></code> origine dati.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA):</b> Usa l'ID 20915 in un nome file di dati se contiene iOS ID. È necessario utilizzare il campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> quando utilizzi gli iOS ID. Ad esempio: <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> racconta <span class="keyword"> Audience Manager</span> che il file di dati contenga solo iOS ID e che gli ID siano qualificati per le caratteristiche appartenenti al <code><i>_DPID_TARGET_DATA_OWNER</i></code> origine dati.</li>
     <li> <b>ID appartenenti ad altre origini dati globali</b>: Puoi integrare ID Roku per Advertising (RIDA), Microsoft Advertising ID (MAID) e altri ID. Utilizza l’ID corrispondente a ciascuna origine dati, come descritto nella sezione <a href="/help/using/features/global-data-sources.md"> articolo su origini dati globali</a>.</li> 
    </ul> <p> <p>Nota: Non combinare tipi di ID nei file di dati. Ad esempio, se il nome del file include l'identificatore Android, non inserire gli ID iOS o i tuoi ID nel file di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Questo campo indica ad Audience Manager a quale origine dati si desidera integrare i dati. Questo campo è obbligatorio se imposti il DPID su un ID Android o iOS ID o un altro ID appartenente a origini dati globali. Questo consente <span class="keyword"> Audience Manager</span> collega nuovamente i dati del file alla tua organizzazione. <br> Questa origine dati di destinazione deve essere di proprietà della tua azienda. A scopo di condivisione dei dati di seconde parti, per acquisire dati in un’origine dati di destinazione appartenente a un’altra società, è necessario disporre di una mappatura degli accessi tra la società e l’origine dati di destinazione. Per impostare la mappatura, contatta il tuo consulente di Adobe o l’Assistenza clienti.</p><p><b>Nota importante:</b> You <i>non</i> è necessario richiedere una mappatura per le relazioni di condivisione dei dati esistenti (per le origini dati target appartenenti ad altre società in cui hai effettuato l’onboarding dei dati prima del 14 marzo 2022). La mappatura non è necessaria anche durante l’onboarding dei dati nelle origini dati di destinazione che appartengono al tuo PID. </p> <p>Ad esempio: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> comunica ad Audience Manager che stai qualificando gli ID cliente appartenenti all’origine dati 33 per caratteristiche o segnali appartenenti all’origine dati 21. </li> 
     <li> <b>ID Android (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> racconta <span class="keyword"> Audience Manager</span> che il file di dati contenga solo ID Android e che gli ID siano qualificati per le caratteristiche appartenenti all’origine dati 21.</li> 
     <li> <b>ID iOS (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> racconta <span class="keyword"> Audience Manager</span> che il file di dati contenga solo iOS ID e che gli ID siano qualificati per le caratteristiche appartenenti all’origine dati 21.</li>
     <li> <b>ID appartenenti ad altre origini dati globali</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> racconta <span class="keyword"> Audience Manager</span> che il file di dati contenga solo ID Roku e che gli ID siano qualificati per le caratteristiche appartenenti all’origine dati 21. Utilizza l’ID corrispondente a ciascuna origine dati, come descritto nella sezione <a href="/help/using/features/global-data-sources.md"> articolo su origini dati globali</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opzioni di sincronizzazione che includono: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scenario normale in cui i fornitori di dati di terze parti inviano caratteristiche a livello di singolo utente da aggiungere o rimuovere nel sistema di Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Consente ai clienti e ai fornitori di dati di inviare un elenco di caratteristiche in base all’utente che dovrebbe sovrascrivere in Audience Manager tutte le caratteristiche esistenti dell’utente per una determinata origine dati. Non è necessario includere tutti gli utenti in un file di sovrascrittura. Includi solo gli utenti che desideri modificare. Le caratteristiche non assegnate all’origine dati di destinazione non verranno cancellate. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si suddividono file di grandi dimensioni in più parti per migliorare i tempi di elaborazione. Il numero indica la parte del file originale che si sta inviando. </p> <p>Per un'elaborazione efficiente dei file, suddividi i file di dati come indicato: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compresso: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compresso: 200-300 MB </li> 
    </ul> <p>Vedi i primi 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> esempi di nomi di file</a> sotto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Timestamp UNIX UTC a 10 cifre in secondi. La marca temporale consente di rendere univoco il nome di ciascun file. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip è il formato di compressione consentito per un nome di file FTP. Se utilizzi la compressione file, accertati che il nome del file abbia l’estensione corretta. </p> <p>I file compressi devono essere di 3 GB o più piccoli. Se i file sono più grandi, contatta l’Assistenza clienti. Anche se Audience Manager può gestire file di grandi dimensioni, possiamo aiutarti a ridurre le dimensioni dei tuoi file e rendere i trasferimenti di dati più efficienti. Consulta <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">File Compression for Inbound Data Transfer Files</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di nome file {#file-name-examples}

Gli esempi seguenti mostrano nomi di file formattati correttamente. I nomi dei file potrebbero essere simili.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Scarica](assets/ftp_dpm_1234_1445374061.overwrite) il file di esempio, se hai bisogno di ulteriori esempi. Questo file viene salvato con il `.overwrite` estensione file. Apritelo con un semplice editor di testo.

## Dimensioni file accettate {#accepted-file-sizes}

Considera le figure seguenti per l&#39;elaborazione più rapida/veloce dei tuoi file e per le limitazioni delle dimensioni dei file quando invii dati a un [!DNL Audience Manager] / [!DNL FTP] directory.

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

