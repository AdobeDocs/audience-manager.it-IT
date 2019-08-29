---
description: Descrive i campi, la sintassi e le convenzioni richiesti per il nome di un file di dati in uscita.
seo-description: Descrive i campi, la sintassi e le convenzioni richiesti per il nome di un file di dati in uscita.
seo-title: Sintassi nome file dati in uscita ed Esempi
solution: Audience Manager
title: Sintassi nome file dati in uscita ed Esempi
uuid: effdcaf 6-c 37 c -45 f 3-9 d 2 f-a 938 a 9 da 47 a 6
translation-type: tm+mt
source-git-commit: e6f1a3b86658a882ebe927cefe55be6ddd40b906

---


# Nome file dati in uscita: Sintassi ed esempi{#outbound-data-file-name-syntax-and-examples}

Descrive i campi, la sintassi e le convenzioni richiesti per il nome di un file di dati in uscita.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Elementi di stile (`monospaced text`, *corsivo*, parentesi quadre `[ ]``( )`ecc.) in questo documento indica gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Elementi sintassi e nome file {#syntax-file-name}

I nomi dei file in uscita contengono i seguenti elementi. Tutti gli elementi sottostanti sono facoltativi.

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
   <td colname="col1"> <p> <code><i>SYNC_ TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Si riferisce ai metodi di trasferimento dati. I metodi di trasferimento includono: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Trasferimento tramite SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S 3 </span> - Trasferimento ad <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>ID destinazione. </p> <p><span class="keyword"> In Audience Manager </span>, una destinazione è l'istanza dell'integrazione in cui puoi mappare i segmenti targabili. I clienti possono disporre di più destinazioni, a seconda dei requisiti aziendali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_ DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Provider dati o ID di origine dati. Questo ID identifica il tipo di ID utente presente nel contenuto del file. Le chiavi ID utente più comuni sono: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID </span> (non elaborato, non con hash) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID per inserzionisti </span> (non elaborato, non con hash) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID fornitore - ID utente 3 rd party (web/cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ ALIAS </i></code> </p> </td> 
   <td colname="col2"> L'identificatore cliente della piattaforma 3 rd party. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_ MODE </i></code> </p> </td> 
   <td colname="col2"> <p>La modalità Sinc. è un segnaposto di macro che aggiunge un'etichetta al nome del file in base al tipo di sincronizzazione. I tipi di sincronizzazione sono completi e incrementali. Verranno visualizzati nel nome del file come <code> iter </code> o <code> pieno </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Indica una sincronizzazione "iterativa" o incrementale. Un file incrementale contiene solo i nuovi dati raccolti dall'ultima sincronizzazione. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Indica una sincronizzazione «completa». Un file completamente sincronizzato contiene dati obsoleti e nuovi dati raccolti dall'ultima sincronizzazione. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Un timestamp UNIX di 13 cifre in millisecondi, nel fuso orario UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Un numero intero. Identifica parte di un file suddiviso in più parti per migliorare i tempi di elaborazione. Il numero indica quale parte del file originale appartiene ai dati.</p>  <p>Il numero intero deve essere composto da almeno 3 cifre, preceduto da zero, se le dimensioni divise sono inferiori a 100 parti.</p>  <p>Il file originale non conterrà alcun numero. Il primo file suddiviso con 001. Vedi esempi di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (facoltativo) </i></code> </p> </td> 
   <td colname="col2"> <p>Compressione GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi nome file {#file-name-examples}

### Scenario 1

File inviati in [!DNL Amazon S3] una posizione, con *`PID_ALIAS="XYZCustomer"`* e con [!DNL Google Advertiser IDs] il contenuto del file.

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Scenario 2

File inviati in [!DNL FTP] posizione, senza *`PID_ALIAS`* e con [!DNL Apple Advertiser IDs] il contenuto del file:

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Scenario 3**: File inviati in [!DNL FTP] posizione, con *`PID_ALIAS="XYZCustomer"`* e con ID utente 3 rd party nel contenuto del file ( *`Vendor ID=45454`*):

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Contenuto file dati in uscita: Sintassi e parametri {#outbound-contents-syntax}

Descrive i campi, la sintassi e le convenzioni richiesti per organizzare le informazioni in un file di dati in uscita. Formattare i dati in base alle seguenti specifiche.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Elementi di stile (`monospaced text`, *corsivo*, parentesi quadre `[ ]``( )`ecc.) in questo documento indica gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

### Sintassi

I campi nel file di dati vengono visualizzati in questo ordine:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parametri

La tabella elenca le variabili che definiscono il contenuto di un file di dati.

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
   <td colname="col1"> <p> <code><i>&lt; SPAZIO &gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Separa l'UUID e i dati dei segmenti con uno spazio </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>L'ID del segmento a cui appartiene un visitatore. Separate più segmenti con una virgola. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_ SEGMENT_ N </i></code> </p> </td> 
   <td colname="col2"> <p>L'ID del segmento da cui è stato disabilitato l'utente. Separate più segmenti con una virgola. Con una sincronizzazione completa, puoi ignorare i segmenti rimossi perché il file di dati conterrà l'elenco completo dei segmenti correnti per l'utente. In genere, vuoi conoscere i segmenti a cui appartiene un utente anziché quelli che sono stati rimossi. Vedere anche <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Nome file dati in uscita: Sintassi ed esempi </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempio: Formato file di base

Un file di dati formattato correttamente potrebbe assomigliare al seguente esempio. Questa voce di file indica che l'utente è idoneo per i segmenti 24, 26 e 27. Se necessario, uno spazio separa gli `UUID` ID del segmento. Un altro spazio separa i set di ID segmento. In questo esempio, un utente appartiene ai segmenti 24, 26 e 27. Sono stati rimossi dai segmenti 25 e 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
