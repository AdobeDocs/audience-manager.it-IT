---
description: Descrive i campi obbligatori, la sintassi, le convenzioni di denominazione e le dimensioni dei file da seguire per l’invio dei dati ad Audience Manager. Imposta nomi e dimensioni dei file in base a queste specifiche quando invii dati a una directory FTP di Audience Manager.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Requisiti FTP di nome e dimensione file per i file di dati in entrata
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 3%

---

# [!DNL FTP] Requisiti di nome e dimensione file per i file di dati in entrata {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Descrive i campi obbligatori, la sintassi, le convenzioni di denominazione e le dimensioni dei file da seguire per l&#39;invio dei dati a [!DNL Audience Manager]. Impostare i nomi e le dimensioni dei file in base a queste specifiche quando si inviano dati a una directory Audience Manager [!DNL FTP].

>[!WARNING]
>
>Stiamo gradualmente eliminando il supporto per le configurazioni [!DNL FTP]. Anche se l&#39;acquisizione di file di dati in entrata è ancora supportata nelle integrazioni esistenti di [!DNL FTP], si consiglia vivamente di utilizzare [!DNL Amazon S3] per l&#39;onboarding di dati offline per nuove integrazioni. Per informazioni dettagliate, consulta [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi quadre `[ ]` `( )` e così via) in questo documento indicano elementi e opzioni di codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Sintassi dei nomi dei file {#file-name-syntax}

I nomi di file [!DNL FTP] contengono i seguenti elementi obbligatori e facoltativi:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Per gli altri formati di file accettati, vedere [Integrazioni partner personalizzate](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] elabora solo [!DNL ASCII] e [!DNL UTF-8] file codificati.

### Elementi nome

La tabella definisce gli elementi in un nome di file [!DNL FTP].

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
   <td colname="col2"> <p>Percorso e nome della directory FTP di Audience Manager<span class="keyword"> </span>. Contatta il tuo Account Manager per la directory FTP e le credenziali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un ID che comunica a <span class="keyword"> Audience Manager</span> se un file di dati contiene i tuoi ID utente, gli ID Android, gli ID iOS o altri ID appartenenti a <a href="/help/using/features/global-data-sources.md"> origini dati globali</a>. Accetta le seguenti opzioni:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID Data Source (noto anche come ID provider dati):</b> Questo è un ID univoco che Audience Manager assegna a un'origine dati (fai riferimento all'indice Audience Manager <a href="/help/using/reference/ids-in-aam.md"> degli ID </a>). Utilizza questo ID assegnato in un nome file quando invii dati che contengono i tuoi ID utente. Ad esempio, <code>...ftp_dpm_21_123456789.sync</code> comunica a <span class="keyword"> Audience Manager</span> di integrare i dati negli ID appartenenti all'origine dati 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID Android (GAID):</b> Utilizzare il 20914 ID in un nome di file di dati se contiene ID Android. Utilizzare il campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> quando si utilizzano gli Android ID. Ad esempio, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> comunica a <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID Android e che gli ID devono essere idonei per le caratteristiche appartenenti all'origine dati <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA):</b> Utilizzare il 20915 ID in un nome di file di dati se contiene ID iOS. Utilizzare il campo <code><i>_DPID_TARGET_DATA_OWNER</i></code> quando si utilizzano gli iOS ID. Ad esempio, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> comunica a <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID iOS e che gli ID devono essere idonei per le caratteristiche appartenenti all'origine dati <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li>
     <li> <b>ID appartenenti ad altre origini dati globali</b>: è possibile integrare gli ID Roku per Advertising (RIDA), Advertising ID di Microsoft (MAID) e altri ID. Utilizzare l'ID corrispondente a ciascuna origine dati, come descritto nell'articolo <a href="/help/using/features/global-data-sources.md"> delle origini dati globali</a>.</li> 
    </ul> <p> <p>Nota: non combinare i tipi di ID nei file di dati. Ad esempio, se il nome del file include l’identificatore Android, non inserire ID iOS o ID personalizzati nel file di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Questo campo indica ad Audience Manager a quale origine dati integrare i dati. Questo campo è obbligatorio se imposti il DPID su un Android ID o iOS ID o su un altro ID appartenente alle origini dati globali. Questo consente a <span class="keyword"> Audience Manager</span> di collegare nuovamente i dati del file alla tua organizzazione. <br> L'origine dati di destinazione deve essere di proprietà della società. Ai fini della condivisione dei dati di seconde parti, per acquisire i dati in un’origine dati di destinazione appartenente a un’altra società è necessario disporre di una mappatura di accesso tra la società e l’origine dati di destinazione. Contatta il tuo consulente Adobe o il Supporto clienti per configurare la mappatura.</p><p><b>Nota importante:</b> <i>non</i> è necessario richiedere una mappatura per le relazioni di condivisione dei dati esistenti (per le origini dati di destinazione appartenenti ad altre società in cui sono stati caricati i dati prima del 14 marzo 2022). Inoltre, la mappatura non è necessaria quando si inseriscono dati in origini dati di destinazione che appartengono al tuo PID. </p> <p>Ad esempio: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> comunica ad Audience Manager che stai qualificando gli ID cliente appartenenti all'origine dati 33 per caratteristiche o segnali appartenenti all'origine dati 21. </li> 
     <li> <b>ID Android (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> comunica a <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID Android e che gli ID devono essere idonei per le caratteristiche appartenenti all'origine dati 21.</li> 
     <li> <b>ID iOS (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> comunica a <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID iOS e che gli ID devono essere idonei per le caratteristiche appartenenti all'origine dati 21.</li>
     <li> <b>ID appartenenti ad altre origini dati globali</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> comunica a <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID Roku e che gli ID devono essere idonei per le caratteristiche appartenenti all'origine dati 21. Utilizzare l'ID corrispondente a ciascuna origine dati, come descritto nell'articolo <a href="/help/using/features/global-data-sources.md"> delle origini dati globali</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opzioni di sincronizzazione che includono: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: scenario normale in cui fornitori di dati di terze parti inviano caratteristiche in base all'utente da aggiungere o rimuovere nel sistema Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: consente ai clienti e ai provider di dati di inviare un elenco di caratteristiche per singolo utente che dovrebbe sovrascrivere tutte le caratteristiche esistenti dell'utente per una determinata origine dati in Audience Manager. Non è necessario includere tutti gli utenti in un file di sovrascrittura. Includi solo gli utenti che desideri modificare. Le caratteristiche non assegnate all’origine dati di destinazione non verranno cancellate. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si dividono file di grandi dimensioni in più parti per migliorare i tempi di elaborazione. Il numero indica quale parte del file originale si sta inviando. </p> <p>Per un’elaborazione efficiente dei file, suddividi i file di dati come indicato di seguito: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compresso: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compresso: 200-300 MB </li> 
    </ul> <p>Vedi i primi 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> esempi di nomi di file</a> di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Timestamp UNIX UTC a 10 cifre in secondi. La marca temporale consente di rendere univoco ogni nome di file. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip è il formato di compressione consentito per un nome di file FTP. Se utilizzate la compressione file, accertatevi che il nome del file abbia l'estensione corretta. </p> <p>I file compressi devono essere di almeno 3 GB. Se i file sono più grandi, contatta l’Assistenza clienti. Anche se Audience Manager è in grado di gestire file di grandi dimensioni, può aiutarti a ridurne le dimensioni e a rendere più efficienti i trasferimenti di dati. Vedere <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a>. </p> </td> 
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

[Scarica](assets/ftp_dpm_1234_1445374061.overwrite) il file di esempio se hai bisogno di ulteriori esempi. Il file è stato salvato con l&#39;estensione `.overwrite`. Aprilo con un semplice editor di testo.

## Dimensioni file accettate {#accepted-file-sizes}

Quando si inviano dati a una directory [!DNL Audience Manager] / [!DNL FTP], prendere in considerazione le figure riportate di seguito per l&#39;elaborazione più rapida/meno recente dei file e per le limitazioni relative alle dimensioni dei file.

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
