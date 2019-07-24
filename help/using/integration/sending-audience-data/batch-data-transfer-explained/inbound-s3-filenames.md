---
description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file necessari per l'invio di dati ad Audience Manager. Quando inviate dati a una directory di Audience Manager/Amazon S 3, impostate i nomi e le dimensioni dei file in base alle seguenti specifiche.
seo-description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file necessari per l'invio di dati ad Audience Manager. Quando inviate dati a una directory di Audience Manager/Amazon S 3, impostate i nomi e le dimensioni dei file in base alle seguenti specifiche.
seo-title: Requisiti di nome e dimensione file Amazon S 3 per i file di dati in entrata
solution: Audience Manager
title: Requisiti di nome e dimensione file Amazon S 3 per i file di dati in entrata
uuid: 3692 a 122-6 ad 5-468 c -934 e -53067 bd 8 cf 71
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Amazon S3 Name and File Size Requirements for Inbound Data Files{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file necessari per l'invio di dati ad Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / [!DNL Amazon S3] directory.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indica gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## File Name Syntax {#file-name-syntax}

[!DNL S3] I nomi dei file contengono i seguenti elementi obbligatori e facoltativi:

* **[!DNL S3]prefisso:**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Elementi nome file:**`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {importance = "high"}
>
>[!DNL Audience Manager] solo processi [!DNL ASCII] e [!DNL UTF-8] file codificati.

### Nome elementi

The table defines the elements in an [!DNL S3] file name.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento nome </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>AWS_ directory</i></code> </p> </td> 
   <td colname="col2"> <p>Percorso e nome del bucket Amazon S 3. Contattate l'Account Manager per il nome, il percorso e le credenziali della directory S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date =<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Una marca temporale (basata sull'ora UTC) di quando si inviano i file al bucket S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>The <span class="term"> Data Provider ID</span> (DPID) is an identifier that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. Accetta le seguenti opzioni: </p> <p> <b>ID partner dati</b> </p> <p>Questo è un ID univoco di Audience Manager assegnato alla tua società o organizzazione. Usa questo ID assegnato in un nome di file quando invii dati che contengono i tuoi ID utente. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </p> <p> <b>ID Android (GAID)</b> </p> <p> Utilizzate ID 20914 come DPID nel nome di un file di dati se il file contiene ID Android. When you use ID 20914 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. Ad esempio, supponiamo che tu stia trasferendo file con gli ID Android e che l'ID del fornitore dati sia 21. In this case, the file name would look like <code>...ftp_dpm_20914_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains Android IDs and is from a partner identified by ID 21. </p> <p> <b>ID iOS (IDFA)</b> </p> <p> Utilizzate ID 20915 come DPID nel nome di un file di dati se il file contiene ID iOS. When you use ID 20915 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. Ad esempio, supponiamo che tu stia trasferendo file con gli ID Android e che l'ID del fornitore dati sia 21. In this case, the file name would look like <code>...ftp_dpm_20915_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains iOS IDs and is from a partner identified by ID 21. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID partner dati:</b> Questo è un ID univoco di Audience Manager assegnato alla tua società o organizzazione. Usa questo ID assegnato in un nome di file quando invii dati che contengono i tuoi ID utente. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID Android (GAID):</b> Utilizzate ID 20914 in un nome di file dati se contiene ID Android. For example, <code>...ftp_dpm_20914_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. Nota, ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA):</b> Utilizzate ID 20915 in un nome di file dati se contiene ID iOS. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
     </ul> 
    </draft-comment> <p> <p>Nota: Non usare i tipi ID nei file di dati. Ad esempio, se il nome del file include l'identificatore Android, non inserire gli ID iOS o i tuoi ID nel file di dati. </p> </p> <p>See also the <code><i>_DPID_TARGET_DATA_OWNER</i></code> entry below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> </p> </td> 
   <td colname="col2"> <p>Un segnaposto per un ID. For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>Ad esempio: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_ 33_ 21_ 1234567890. sync</code> mostra un partner con ID 21 inviato nei dati da un'origine dati che utilizza ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_ 20914_ 21_ 1234567890. sync</code> mostra un partner con ID 21 inviato in dati che contengono ID Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_ 20915_ 21_ 1234567890. sync</code> mostra un partner con ID 21 inviato in dati che contengono ID iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>partner_ name</i></code> </p> </td> 
   <td colname="col2"> <p>The company or organization name you use in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Una marca temporale UTC a 10 cifre, in secondi. La marca temporale contribuisce a rendere univoco ogni nome file. </p> 
    <draft-comment> 
     <p> <p>Nota: Audience Manager non utilizza il timestamp durante l'elaborazione dei file in entrata. La marca temporale nel nome del file è stata rimossa da Audience Manager ma rimane necessaria per compatibilità con versioni precedenti. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opzioni di sincronizzazione che includono: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sincronizzazione: Scenario normale quando i fornitori di dati di terze parti inviano tratti su base utente da aggiungere o rimuovere nel sistema Audience Manager.</code> </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Consente ai fornitori di dati di inviare un elenco di caratteristiche in base a ogni utente, che dovrebbe sovrascrivere tutte le caratteristiche di terze parti esistenti di questo utente in Audience Manager. Non è necessario includere tutti gli utenti in un file sovrascritto. Includete solo gli utenti che desiderate modificare. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si dividono file di grandi dimensioni in più parti per migliorare i tempi di elaborazione. Il numero indica quale parte del file originale si sta inviando. </p> <p>Per un'elaborazione efficiente dei file, suddividere i file di dati come indicato: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compresso: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compresso: 200-300 MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Quando inviate file ad Amazon S 3, utilizzate solo la compressione gzip. When compressed, these files get the <code> .gz</code> extension. Non utilizzate la compressione.zip. </p> <p>I file compressi devono essere di almeno 3 GB. Se i tuoi file sono più grandi, contatta l'Assistenza clienti. Audience Manager può gestire file di grandi dimensioni, possiamo aiutarti a ridurre le dimensioni dei file e a rendere più efficiente il trasferimento di dati. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

Gli esempi seguenti mostrano nomi di file formattati correttamente. I nomi dei file possono essere simili.

<ul class="simplelist"> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. sync</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; partner_ name &gt;/date = 2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; nome_ partner &gt;/data = 2016-05-09/ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

You can [download](assets/ftp_dpm_1234_1445374061.overwrite) the sample file if you want additional examples. This file has been saved with the `.overwrite` file extension. Apritela con un semplice editor di testo.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.

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

>[!NOTE]
>
>Il processo di convalida dei dati in entrata contrassegnerà i file vuoti come non validi e non li elabora.

>[!MORE_ LIKE_ THIS]
>
>* [Requisiti di nome FTP per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

