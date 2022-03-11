---
description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni dei file richiesti per l’invio dei dati ad Audience Manager. Imposta i nomi e le dimensioni dei file in base a queste specifiche quando invii dati a una directory Audience Manager / Amazon S3.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Amazon S3 Name and File Size Requirements for Inbound Data Files
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: 3e25db0fc74a0b125f4f0ecd0f45f3fb877be099
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 4%

---

# [!DNL Amazon S3] requisiti di nome e dimensione del file per i file di dati in entrata {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni dei file richiesti per l’invio dei dati a [!DNL Audience Manager]. Imposta i nomi e le dimensioni dei file in base a queste specifiche quando invii dati a un [!DNL Audience Manager] / [!DNL Amazon S3] directory.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicare gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Sintassi del nome file {#file-name-syntax}

[!DNL S3] i nomi dei file contengono i seguenti elementi obbligatori e facoltativi:

* **[!DNL S3]Prefisso:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Elementi del nome file:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Per altri formati di file con nome accettati, vedere [Integrazioni di partner personalizzate](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] solo i processi [!DNL ASCII] e [!DNL UTF-8] file codificati.

### Elementi nome

La tabella definisce gli elementi in un [!DNL S3] nome file.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Nome </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Percorso e nome del bucket Amazon S3. Contatta il tuo Account Manager per il nome della directory S3, il percorso e le credenziali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Una marca temporale (basata sull’ora UTC) di quando invii i file al bucket S3. </p> </td> 
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
   <td colname="col2"> <p>Questo campo indica ad Audience Manager a quale origine dati si desidera integrare i dati. Questo campo è obbligatorio se imposti il DPID su un ID Android o iOS ID o un altro ID appartenente a origini dati globali. Questo consente ad Audience Manager di collegare nuovamente i dati del file alla tua organizzazione. <br> Questa origine dati di destinazione deve essere di proprietà della tua azienda. A scopo di condivisione dei dati di seconde parti, per acquisire dati in un’origine dati di destinazione appartenente a un’altra società, è necessario disporre di una mappatura degli accessi tra la società e l’origine dati di destinazione. Per impostare la mappatura, contatta il tuo consulente di Adobe o l’Assistenza clienti.</p> <p>Ad esempio: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> comunica ad Audience Manager che stai qualificando gli ID cliente appartenenti all’origine dati 33 per caratteristiche o segnali appartenenti all’origine dati 21. </li> 
     <li> <b>ID Android (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> racconta <span class="keyword"> Audience Manager</span> che il file di dati contenga solo ID Android e che gli ID siano qualificati per le caratteristiche appartenenti all’origine dati 21.</li> 
     <li> <b>ID iOS (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> racconta <span class="keyword"> Audience Manager</span> che il file di dati contenga solo iOS ID e che gli ID siano qualificati per le caratteristiche appartenenti all’origine dati 21.</li>
     <li> <b>ID appartenenti ad altre origini dati globali</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> racconta <span class="keyword"> Audience Manager</span> che il file di dati contenga solo ID Roku e che gli ID siano qualificati per le caratteristiche appartenenti all’origine dati 21. Utilizza l’ID corrispondente a ciascuna origine dati, come descritto nella sezione <a href="/help/using/features/global-data-sources.md"> articolo su origini dati globali</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Nome società o organizzazione utilizzato in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Timestamp UNIX UTC a 10 cifre in secondi. La marca temporale consente di rendere univoco il nome di ciascun file. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opzioni di sincronizzazione che includono: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scenario normale in cui i fornitori di dati di terze parti inviano caratteristiche a livello di singolo utente da aggiungere o rimuovere nel sistema di Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Consente ai provider di dati di inviare un elenco di caratteristiche in base all’utente che dovrebbe sovrascrivere nell’Audience Manager tutte le caratteristiche di terze parti esistenti dell’utente per questo provider di dati. Non è necessario includere tutti gli utenti in un file di sovrascrittura. Includi solo gli utenti che desideri modificare. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si suddividono file di grandi dimensioni in più parti per migliorare i tempi di elaborazione. Il numero indica la parte del file originale che si sta inviando. </p> <p>Per un'elaborazione efficiente dei file, suddividi i file di dati come indicato: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compresso: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compresso: 200-300 MB </li> 
    </ul> <p>Vedi i primi 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> esempi di nomi di file</a> sotto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Quando invii file ad Amazon S3, utilizza solo la compressione gzip. Quando compressi, questi file ottengono il <code> .gz</code> estensione. Non utilizzare la compressione .zip. </p> <p>I file compressi devono essere di 3 GB o più piccoli. Se i file sono più grandi, contatta l’Assistenza clienti. Anche se Audience Manager può gestire file di grandi dimensioni, possiamo aiutarti a ridurre le dimensioni dei tuoi file e rendere i trasferimenti di dati più efficienti. Consulta <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">File Compression for Inbound Data Transfer Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di nome file {#file-name-examples}

Gli esempi seguenti mostrano nomi di file formattati correttamente. I nomi dei file potrebbero essere simili.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

È possibile [scaricare](assets/ftp_dpm_1234_1445374061.overwrite) il file di esempio, se desideri ulteriori esempi. Questo file è stato salvato con il `.overwrite` estensione file. Apritelo con un semplice editor di testo.

## Dimensioni file accettate {#accepted-file-sizes}

Considera le figure seguenti per l&#39;elaborazione più rapida/veloce dei tuoi file e per le limitazioni delle dimensioni dei file quando invii dati a un [!DNL Audience Manager] / [!DNL Amazon S3] directory.

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


>[!NOTE]
>
>Il processo di convalida dei dati in entrata contrassegna i file vuoti come non validi e non li elabora.

## Limiti di lunghezza delle linee {#line-limits}

I file di dati in entrata hanno un limite di lunghezza di riga di 102400 byte. Le linee che superano questo limite sono escluse dal trasferimento.

>[!MORELIKETHIS]
>
>* [Requisiti di nome FTP per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

