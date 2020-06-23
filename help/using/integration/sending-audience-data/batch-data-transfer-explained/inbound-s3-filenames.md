---
description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l'invio di dati a  Audience Manager. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una directory Audience Manager / Amazon S3 .
seo-description: Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l'invio di dati a  Audience Manager. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una directory Audience Manager / Amazon S3 .
seo-title: Requisiti di nome e dimensione file Amazon S3 per i file di dati in entrata
solution: Audience Manager
title: Requisiti di nome e dimensione file Amazon S3 per i file di dati in entrata
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '1154'
ht-degree: 2%

---


# [!DNL Amazon S3] Requisiti di nome e dimensione file per i file di dati in entrata {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Descrive i campi, la sintassi, le convenzioni di denominazione e le dimensioni di file richiesti per l&#39;invio dei dati a [!DNL Audience Manager]. Impostate i nomi e le dimensioni dei file in base alle seguenti specifiche quando inviate i dati a una [!DNL Audience Manager] / [!DNL Amazon S3] directory.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicano gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Sintassi nome file {#file-name-syntax}

[!DNL S3] i nomi dei file contengono i seguenti elementi obbligatori e facoltativi:

* **[!DNL S3]Prefisso:**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Elementi nome file:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Per altri formati di file accettati, consulta Integrazioni [partner](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personalizzate.

>[!NOTE] {important=&quot;high&quot;}
>
>[!DNL Audience Manager] elabora solo file [!DNL ASCII] e file [!DNL UTF-8] codificati.

### Elementi nome

La tabella definisce gli elementi in un nome di [!DNL S3] file.

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
   <td colname="col2"> <p>Percorso e nome del bucket Amazon S3. Contatta il tuo Account Manager per conoscere il nome della directory S3, il percorso e le credenziali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Una marca temporale (in base all'ora UTC) del momento in cui si inviano i file al bucket S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>L'ID <span class="term"> del provider di</span> dati (DPID, Data Provider ID <span class="keyword"> ) è un identificatore che informa</span> Audience Managerse un file di dati contiene ID utente o ID Android o iOS personali. Accetta le seguenti opzioni: </p> <p> <b>ID partner dati</b> </p> <p>Si tratta di un ID univoco assegnato  Audience Manager alla tua azienda o organizzazione. Utilizzate questo ID assegnato in un nome file per l'invio di dati che contengono i vostri ID utente. Ad esempio, <code>...ftp_dpm_21_123456789.sync</code> indica <span class="keyword"> Audience Manager</span> che un partner con ID 21 ha inviato il file e contiene gli ID utente assegnati da tale partner. </p> <p> <b>ID Android (GAID)</b> </p> <p> Utilizzate ID 20914 come DPID in un nome file di dati se il file contiene ID Android. Se utilizzi ID 20914 come DPID, devi comunque identificare la tua azienda per <span class="keyword"> Audience Manager</span>. Questo significa che il nome file deve usare il <code><i>_DPID_TARGET_DATA_OWNER</i></code> parametro per contenere l'ID società. Ad esempio, supponiamo che vengano inviati file con ID Android e che il tuo ID provider di dati sia 21. In questo caso, il nome del file sarà simile a quello <code>...ftp_dpm_20914_21_123456789.sync</code>. Questo indica <span class="keyword"> Audience Manager</span> che il file contiene ID Android ed è di un partner identificato dall'ID 21. </p> <p> <b>ID iOS (IDFA)</b> </p> <p> Utilizzate ID 20915 come DPID in un nome file di dati se il file contiene ID iOS. Se utilizzi ID 20915 come DPID, devi comunque identificare la tua società per <span class="keyword"> Audience Manager</span>. Questo significa che il nome file deve usare il <code><i>_DPID_TARGET_DATA_OWNER</i></code> parametro per contenere l'ID società. Ad esempio, supponiamo che vengano inviati file con ID Android e che il tuo ID provider di dati sia 21. In questo caso, il nome del file sarà simile a quello <code>...ftp_dpm_20915_21_123456789.sync</code>. Questo indica <span class="keyword"> Audience Manager</span> che il file contiene ID iOS ed è di un partner identificato dall'ID 21. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID partner dati:</b> Si tratta di un ID univoco assegnato  Audience Manager alla tua azienda o organizzazione. Utilizzate questo ID assegnato in un nome file per l'invio di dati che contengono i vostri ID utente. Ad esempio, <code>...ftp_dpm_21_123456789.sync</code> indica <span class="keyword"> Audience Manager</span> che un partner con ID 21 ha inviato il file e contiene gli ID utente assegnati da tale partner. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>ID Android (GAID):</b> Utilizzate l'ID 20914 in un nome file di dati se contiene un ID Android. Ad esempio, <code>...ftp_dpm_20914_21_123456789.sync</code> indica <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID Android. Nota: ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA):</b> Usa l'ID 20915 in un nome file di dati se contiene ID iOS. Ad esempio, <code>...ftp_dpm_20915_123456789.sync</code> indica <span class="keyword"> Audience Manager</span> che il file di dati contiene solo ID iOS. </li> 
     </ul> 
    </draft-comment> <p> <p>Nota:  Non utilizzare tipi di ID misti nei file di dati. Ad esempio, se il nome file include l'identificatore Android, non inserire gli ID iOS o i tuoi ID nel file di dati. </p> </p><p>Per ulteriori informazioni, consulta <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">Origini</a> dati globali.</p> <p>Vedere anche la <code><i>_DPID_TARGET_DATA_OWNER</i></code> voce seguente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Un segnaposto per un ID. Ad esempio, puoi impostarlo sul tuo <span class="keyword"> ID Audience Manager</span> se imposti il DPID a un ID origine dati o a un ID Android o iOS. Questo consente <span class="keyword"> Audience Manager</span> di ricollegare i dati del file alla propria organizzazione. </p> <p>Ad esempio: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> mostra che un partner con ID 21 ha inviato dati da un'origine dati che utilizza ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> mostra che un partner con ID 21 ha inviato dati che contengono ID Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> mostra che un partner con ID 21 ha inviato dati che contengono ID iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Il nome della società o dell’organizzazione utilizzato in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Marca temporale UTC di 10 cifre in secondi. La marca temporale consente di rendere univoco ciascun nome file. </p> 
    <draft-comment> 
     <p> <p>Nota:   Audience Manager non utilizza la marca temporale durante l'elaborazione dei file in ingresso. Il timestamp nel nome del file è stato dichiarato obsoleto in  Audience Manager, ma è comunque richiesto per la compatibilità con le versioni precedenti. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Opzioni di sincronizzazione che includono: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scenario normale in cui i fornitori di dati di terze parti inviano caratteristiche in base all'utente da aggiungere o rimuovere nel sistema Audience Manager . </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Consente ai provider di dati di inviare un elenco di caratteristiche in base all'utente che dovrebbero sovrascrivere tutte le caratteristiche di terze parti esistenti per questo provider di dati nell'Audience Manager . Non è necessario includere tutti gli utenti in un file di sovrascrittura. Includete solo gli utenti che desiderate modificare. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Un numero intero. Utilizzato quando si suddividono file di grandi dimensioni in più parti per migliorare i tempi di elaborazione. Il numero indica quale parte del file originale viene inviata. </p> <p>Per un'elaborazione efficiente dei file, suddividere i file di dati come indicato: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compresso: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compresso: 200-300 MB </li> 
    </ul> <p>Vedere i primi due esempi <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"></a> di nome file riportati di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Quando inviate i file ad Amazon S3, utilizzate solo la compressione gzip. Se compressi, questi file ottengono l' <code> .gz</code> estensione. Non utilizzate la compressione .zip. </p> <p>I file compressi devono essere di almeno 3 GB. Se i file sono più grandi, rivolgiti all'Assistenza clienti. Anche se  Audience Manager può gestire file di grandi dimensioni, possiamo aiutarti a ridurre le dimensioni dei file e rendere più efficiente il trasferimento dei dati. Consulta <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Compressione file per i file</a>di trasferimento dati in entrata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di nomi file {#file-name-examples}

Gli esempi seguenti mostrano nomi di file formattati correttamente. I nomi dei file potrebbero essere simili.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

Potete [scaricare](assets/ftp_dpm_1234_1445374061.overwrite) il file di esempio se desiderate ulteriori esempi. Il file è stato salvato con l&#39;estensione del `.overwrite` file. Aprite l’immagine con un semplice editor di testo.

## Dimensioni file accettate {#accepted-file-sizes}

Considerare le figure riportate di seguito per l&#39;elaborazione più rapida/rapida dei file e per i limiti di dimensione dei file quando si inviano dati a una [!DNL Audience Manager] / [!DNL Amazon S3] directory.

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
>Il processo di convalida dei dati in entrata contrassegnerà i file vuoti come non validi e non li elaborerà.

>[!MORELIKETHIS]
>
>* [Requisiti di nome FTP per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

