---
description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file necessari per l'invio di dati ad Audience Manager. Quando invii dati a una directory FTP di Audience Manager, imposta i nomi e le dimensioni dei file in base alle seguenti specifiche.
seo-description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file necessari per l'invio di dati ad Audience Manager. Quando invii dati a una directory FTP di Audience Manager, imposta i nomi e le dimensioni dei file in base alle seguenti specifiche.
seo-title: Requisiti di nome FTP e dimensione file per i file di dati in entrata
solution: Audience Manager
title: Requisiti di nome FTP e dimensione file per i file di dati in entrata
uuid: 49 eaafac -5 cb 0-482 f -872 a -84 c 056016 bdb
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Requisiti di nome FTP e dimensione file per i file di dati in entrata{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file necessari per l&#39;invio di dati ad Audience Manager. Quando inviate dati a una [!DNL FTP] directory Audience Manager, impostate i nomi e le dimensioni dei file in base alle seguenti specifiche.

>[!WARNING]
>
>Il trasferimento FTP per i file di dati in entrata non è più supportato. Utilizzate Amazon S 3 per unire i dati offline. Per [informazioni dettagliate, consultate i requisiti di Amazon S 3 Nome e Dimensione file per i file](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) di dati in entrata.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi quadre `[ ]` `( )`, ecc.) in questo documento indica gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta [Convenzioni di stile per Codice e Elementi di testo](../../../reference/code-style-elements.md).

## Sintassi nome file {#file-name-syntax}

[!DNL FTP] I nomi dei file contengono i seguenti elementi obbligatori e facoltativi:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Per altri formati di nomi file accettati, consultate [Integrazioni partner personalizzate](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {importance = &quot;high&quot;}
>
>[!DNL Audience Manager] solo processi [!DNL ASCII] e [!DNL UTF-8] file codificati.

### Nome elementi

La tabella definisce gli elementi nel nome di un [!DNL FTP] file.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento nome file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_ dpm_</code> </p> </td> 
   <td colname="col2"> <p>Percorso e nome della directory FTP <span class="keyword"> di Audience Manager</span> . Contatta l'Account Manager per la directory e le credenziali FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Un LD che informa <span class="keyword"> Audience Manager</span> se un file di dati contiene i propri ID utente o Android o ID iOS. Accetta le seguenti opzioni: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID partner dati:</b> Questo è un ID univoco di Audience Manager assegnato alla tua società o organizzazione. Usa questo ID assegnato in un nome di file quando invii dati che contengono i tuoi ID utente. Ad esempio, <code>… ftp_ dpm_ 21_ 123456789. sync</code> informa <span class="keyword"> Audience Manager</span> che un partner con ID 21 ha inviato il file e contiene gli ID utente assegnati da tale partner. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID Android (GAID):</b> Utilizzate ID 20914 in un nome di file dati se contiene ID Android. Ad esempio, <code>… ftp_ dpm_ 20914_ 123456789. sync</code> informa <span class="keyword"> Audience Manager</span> che il file di dati contiene solo gli ID Android. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA):</b> Utilizzate ID 20915 in un nome di file dati se contiene ID iOS. Ad esempio, <code>… ftp_ dpm_ 20915_ 123456789. sync</code> informa <span class="keyword"> Audience Manager</span> che il file di dati contiene solo gli ID iOS. </li> 
    </ul> <p> <p>Nota: Non usare i tipi ID nei file di dati. Ad esempio, se il nome del file include l'identificatore Android, non inserire gli ID iOS o i tuoi ID nel file di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> </p> </td> 
   <td colname="col2"> <p>Un segnaposto per un ID. Ad esempio, puoi impostarlo sull'ID <span class="keyword"> Audience Manager</span> se imposti il DPID su un ID di origine dati o su un ID Android o iOS. In questo modo <span class="keyword"> Audience Manager</span> rimandi nuovamente i dati del file all'organizzazione. </p> <p>Ad esempio: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_ 33_ 21_ 1234567890. sync</code> mostra un partner con ID 21 inviato nei dati da un'origine dati che utilizza ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_ 20914_ 21_ 1234567890. sync</code> mostra un partner con ID 21 inviato in dati che contengono ID Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_ 20915_ 21_ 1234567890. sync</code> mostra un partner con ID 21 inviato in dati che contengono ID iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opzioni di sincronizzazione che includono: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normal scenario when third-party data providers send traits on a per-user basis to be added or removed in the Audience Manager system. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Consente ai clienti e ai fornitori di dati di inviare un elenco di caratteristiche in base a ogni utente, sovrascrivendo tutte le caratteristiche esistenti di questo utente per una determinata origine dati in Audience Manager. Non è necessario includere tutti gli utenti in un file sovrascritto. Includete solo gli utenti che desiderate modificare. Le caratteristiche non assegnate all'origine dati di destinazione non verranno cancellate. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si dividono file di grandi dimensioni in più parti per migliorare i tempi di elaborazione. Il numero indica quale parte del file originale si sta inviando. </p> <p>Per un'elaborazione efficiente dei file, suddividere i file di dati come indicato: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compresso: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compresso: 200-300 MB </li> 
    </ul> <p>Consultate i primi <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> esempi</a> del nome file 2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Una marca temporale UTC a 10 cifre, in secondi. La marca temporale contribuisce a rendere univoco ogni nome file. </p> 
    <draft-comment> 
     <p> <p>Nota: Audience Manager non utilizza il timestamp durante l'elaborazione dei file in entrata. La marca temporale nel nome del file è stata rimossa da Audience Manager ma rimane necessaria per compatibilità con versioni precedenti. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip è il formato di compressione consentito per il nome di un file FTP. Se utilizzate la compressione file, accertatevi che il nome del file sia dotato dell'estensione appropriata. </p> <p>I file compressi devono essere di almeno 3 GB. Se i file dei file sono più grandi, contatta l'Assistenza clienti. Audience Manager può gestire file di grandi dimensioni, possiamo aiutarti a ridurre le dimensioni dei file e a rendere più efficiente il trasferimento di dati. Consultate <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Compressione file per trasferimento di dati in entrata</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi nome file {#file-name-examples}

Gli esempi seguenti mostrano nomi di file formattati correttamente. I nomi dei file possono essere simili.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

[Se necessario, scaricate](assets/ftp_dpm_1234_1445374061.overwrite) il file di esempio. Il file viene salvato con l&#39;estensione `.overwrite` del file. Apritela con un semplice editor di testo.

## Dimensioni file accettate {#accepted-file-sizes}

Considerate le cifre riportate di seguito per l&#39;elaborazione più rapida/rapida dei file, nonché per le limitazioni di dimensione file quando inviate dati a una [!DNL Audience Manager] / [!DNL FTP] directory.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo file </th> 
   <th colname="col2" class="entry"> Dimensioni ottimali </th> 
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

>[!MORE_ LIKE_ THIS]
>
>* [Requisiti di nome di Amazon S3 per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

