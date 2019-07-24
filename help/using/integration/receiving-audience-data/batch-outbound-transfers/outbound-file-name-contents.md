---
description: Descrive i campi, la sintassi e le convenzioni richiesti per il nome di un file di dati in uscita.
seo-description: Descrive i campi, la sintassi e le convenzioni richiesti per il nome di un file di dati in uscita.
seo-title: Sintassi nome file dati in uscita ed Esempi
solution: Audience Manager
title: Sintassi nome file dati in uscita ed Esempi
uuid: effdcaf 6-c 37 c -45 f 3-9 d 2 f-a 938 a 9 da 47 a 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Outbound Data File Name: Syntax and Examples{#outbound-data-file-name-syntax-and-examples}

Descrive i campi, la sintassi e le convenzioni richiesti per il nome di un file di dati in uscita.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) in questo documento indica gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

## Syntax and File Name Elements {#syntax-file-name}

I nomi dei file in uscita contengono i seguenti elementi obbligatori e facoltativi:

```
SYNC-TYPE_ DID_ MASTER-DPID_ [PID-ALIAS]_ SYNC-MODE_ TIMESTAMP[- SPLIT_NUMBER].sync[.gz]
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
   <td colname="col1"> <p> <code><i>SYNC-TYPE </i></code> </p> </td> 
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
   <td colname="col1"> <p> <code><i>MASTER-DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Provider dati o ID di origine dati. Questo ID identifica il tipo di ID utente presente nel contenuto del file. Le chiavi ID utente più comuni sono: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID </span> (raw, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID for Advertisers </span> (raw, unhashed) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">ID fornitore - ID utente 3 rd party (web/cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID-ALIAS </i></code> </p> </td> 
   <td colname="col2"> L'identificatore cliente della piattaforma 3 rd party. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC-MODE </i></code> </p> </td> 
   <td colname="col2"> <p>La modalità Sinc. è un segnaposto di macro che aggiunge un'etichetta al nome del file in base al tipo di sincronizzazione. I tipi di sincronizzazione sono completi e incrementali. They'll appear in the file name as <code> iter </code> or <code> full </code>. </p> 
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
   <td colname="col1"> <p> [<code><i>-SPLIT_NUMBER </i></code>] </p> </td> 
   <td colname="col2"> <p>Un numero intero. Identifica parte di un file suddiviso in più parti per migliorare i tempi di elaborazione. Il numero indica quale parte del file originale appartiene ai dati. </p> <p>Il file originale non conterrà alcun numero. Il primo file suddiviso con 1. Vedi esempi di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (facoltativo) </i></code> </p> </td> 
   <td colname="col2"> <p>Compressione GZIP. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

### Scenario 1

Files sent over to an [!DNL Amazon S3] location, with *`PID-ALIAS="XYZCustomer"`* and with [!DNL Google Advertiser IDs] in the file content.

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000-1.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000-10.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000-1.sync.gz </code> </li> 
</ul>

### Scenario 2

Files sent over to [!DNL FTP] location, without *`PID-ALIAS`* and with [!DNL Apple Advertiser IDs] in the file content:

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000-1.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000-1.sync.gz </code> </li> 
</ul>

**Scenario 3**: File inviati in [!DNL FTP] posizione, con *`PID-ALIAS="XYZCustomer"`* e con ID utente 3 rd party nel contenuto del file ( *`Vendor ID=45454`*):

Ad esempio, file incrementali:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000-1.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000-10.sync.gz </code> </li> 
</ul>

Ad esempio, file completi:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200-1.sync.gz </code> </li> 
</ul>

## Outbound Data File Contents: Syntax and Parameters {#outbound-contents-syntax}

Descrive i campi, la sintassi e le convenzioni richiesti per organizzare le informazioni in un file di dati in uscita. Formattare i dati in base alle seguenti specifiche.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) in questo documento indica gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../../reference/code-style-elements.md).

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
   <td colname="col2"> <p>A unique user ID assigned by <span class="keyword"> Audience Manager </span>. </p> </td> 
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
   <td colname="col2"> <p>L'ID del segmento da cui è stato disabilitato l'utente. Separate più segmenti con una virgola. Con una sincronizzazione completa, puoi ignorare i segmenti rimossi perché il file di dati conterrà l'elenco completo dei segmenti correnti per l'utente. In genere, vuoi conoscere i segmenti a cui appartiene un utente anziché quelli che sono stati rimossi. See also <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Outbound Data File Name: Syntax and Examples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempio: Formato file di base

Un file di dati formattato correttamente potrebbe assomigliare al seguente esempio. Questa voce di file indica che l'utente è idoneo per i segmenti 24, 26 e 27. As required, a space separates the `UUID` and segment IDs. Un altro spazio separa i set di ID segmento. In questo esempio, un utente appartiene ai segmenti 24, 26 e 27. Sono stati rimossi dai segmenti 25 e 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
