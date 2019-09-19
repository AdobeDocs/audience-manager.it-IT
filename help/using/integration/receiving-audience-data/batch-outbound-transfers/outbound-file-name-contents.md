---
description: Descrive i campi, la sintassi e le convenzioni necessari per assegnare un nome a un file di dati in uscita.
seo-description: Descrive i campi, la sintassi e le convenzioni necessari per assegnare un nome a un file di dati in uscita.
seo-title: Sintassi ed esempi di file di dati in uscita
solution: Audience Manager
title: Sintassi ed esempi di file di dati in uscita
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
translation-type: tm+mt
source-git-commit: e6f1a3b86658a882ebe927cefe55be6ddd40b906

---


# Nome file dati in uscita: Sintassi ed esempi{#outbound-data-file-name-syntax-and-examples}

Descrive i campi, la sintassi e le convenzioni necessari per assegnare un nome a un file di dati in uscita.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Gli elementi di stile (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`ecc.) in questo documento indicano gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Elementi di sintassi e nome file {#syntax-file-name}

I nomi dei file in uscita contengono gli elementi seguenti. Tutti gli elementi seguenti sono facoltativi.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parametri

La tabella definisce gli elementi in un nome file di dati in uscita.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento nome file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Si riferisce ai metodi di trasferimento dei dati. I metodi di trasferimento includono: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Trasferimento tramite SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> - Trasferimento su <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID destinazione. </p> <p>In <span class="keyword"> Audience Manager </span>, una destinazione è l’istanza dell’integrazione in cui potete mappare i segmenti di destinazione. I clienti possono avere più destinazioni, a seconda dei requisiti aziendali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>ID provider dati o origine dati. Questo ID identifica il tipo di ID utente presente nel contenuto del file. Le chiavi ID utente più comuni sono: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">2014 - <span class="keyword"> Google Advertiser ID </span> (raw, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">2015 - <span class="keyword"> Apple ID per inserzionisti </span> (non elaborati, senza hash) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID fornitore - ID utente di terze parti (web/cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> Identificatore del cliente dalla piattaforma di terze parti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>La modalità di sincronizzazione è un segnaposto di macro che aggiunge un'etichetta al nome del file in base al tipo di sincronizzazione. I tipi di sincronizzazione includono full e incremental. Vengono visualizzati nel nome del file come <code> iter </code> o <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Indica una sincronizzazione "iterativa" o incrementale. Un file incrementale contiene solo nuovi dati raccolti dall'ultima sincronizzazione. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Indica una sincronizzazione "completa". Un file completamente sincronizzato contiene dati vecchi ed eventuali nuovi dati raccolti dall'ultima sincronizzazione. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Marca temporale UNIX di 13 cifre, in millisecondi, nel fuso orario UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Un numero intero. Identifica parte di un file suddiviso in più parti per migliorare i tempi di elaborazione. Il numero indica a quale parte del file originale appartengono i dati.</p>  <p>Il numero intero deve essere lungo almeno 3 cifre, preceduto da zero, se la dimensione della divisione è inferiore a 100 parti.</p>  <p>Il file originale non avrà alcun numero di divisione. Il primo file diviso termina con 001. Vedere gli esempi di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (facoltativo) </i></code> </p> </td> 
   <td colname="col2"> <p>Compressione GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di nomi file {#file-name-examples}

### Scenario 1

I file inviati a una [!DNL Amazon S3] posizione, con *`PID_ALIAS="XYZCustomer"`* e con [!DNL Google Advertiser IDs] il contenuto del file.

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_148614084400001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_148614084400002.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_148614084400001.sync.gz </code> </li> 
</ul>

### Scenario 2

I file inviati nella [!DNL FTP] posizione, senza *`PID_ALIAS`* e con [!DNL Apple Advertiser IDs] il contenuto del file:

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_148614084300001.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Scenario 3**: File inviati nella [!DNL FTP] posizione, con *`PID_ALIAS="XYZCustomer"`* e con ID utente di terze parti nel contenuto del file ( *`Vendor ID=45454`*):

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_148614084300001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_148614084300001.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_148614084320001.sync.gz </code> </li> 
</ul>

## Contenuto file dati in uscita: Sintassi e parametri {#outbound-contents-syntax}

Descrive i campi, la sintassi e le convenzioni necessari per organizzare le informazioni in un file di dati in uscita. Formattare i dati in base alle presenti specifiche.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Gli elementi di stile (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`ecc.) in questo documento indicano gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

### Sintassi

I campi nel file di dati vengono visualizzati nell'ordine seguente:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parametri

Nella tabella sono elencate le variabili che definiscono il contenuto di un file di dati.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>Un ID utente univoco assegnato da <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Separare i dati UUID e del segmento con uno spazio </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>L’ID del segmento a cui un visitatore appartiene. Separa più segmenti con una virgola. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>L’ID del segmento da cui l’utente è stato squalificato. Separa più segmenti con una virgola. Con una sincronizzazione completa, puoi ignorare i segmenti rimossi perché il file di dati conterrà l'elenco completo dei segmenti correnti per l'utente. In genere, è necessario conoscere i segmenti a cui appartiene un utente anziché quelli da cui è stato rimosso. Vedere anche Nome file dati <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> in uscita: Sintassi ed esempi </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempio: Formato file di base

Un file di dati formattato correttamente potrebbe essere simile al seguente esempio. Questa voce di file indica che l'utente è idoneo per i segmenti 24, 26 e 27. Se necessario, uno spazio separa gli ID `UUID` e del segmento. Un altro spazio separa i set di ID segmento. In questo esempio, un utente appartiene ai segmenti 24, 26 e 27. Sono stati rimossi dai segmenti 25 e 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
