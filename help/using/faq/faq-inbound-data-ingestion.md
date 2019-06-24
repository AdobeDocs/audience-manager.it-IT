---
description: Domande frequenti su come portare dati offline in Audience Manager.
keywords: ftp o s 3; s 3 o ftp
seo-description: Domande frequenti su come portare dati offline in Audience Manager.
seo-title: Domande frequenti sull'assimilazione dei dati cliente
solution: Audience Manager
title: Domande frequenti sull'assimilazione dei dati cliente
uuid: 491 e 9 ec 1-4731-46 a 8-86 e 7-d 8 c 613 e 6 cedc
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

Domande frequenti su come portare dati offline in Audience Manager.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**È possibile riepilogare il processo di onboarding?**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). che richiedono:

* Sincronizzazione ID
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Di seguito è riportato un elenco di domande e risposte utili dopo la revisione della documentazione.

>[!NOTE]
>
>Gli esempi di questa sezione sono semplificati o abbreviati a scopo di brevità e dimostrativa. Per informazioni dettagliate sui formati di file e la sintassi, consultate la documentazione di Inserimento dei dati in ingresso.

<br> 

**È possibile riepilogare il processo di distribuzione?**

Consigliamo di:

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider&#39;s visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* Distribuisci la sincronizzazione DIL/ID in produzione. La sincronizzazione ID sarà già configurata come modulo all&#39;interno del codice DIL dal consulente Adobe.
* Transfer production data files to [!DNL Audience Manager]. Considerate le dipendenze delle mappature di sincronizzazione ID, potrebbe essere sensato iniziare a trasferire dati fino a una settimana dopo la distribuzione del codice di produzione, anche se potete iniziare a trasferire i file di dati non appena il codice entra nella produzione.

<br> 

**Quale modalità FTP posso usare per trasferire file compressi o codificati?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Posso caricare un file di dati in entrata ([!DNL .sync]o il file[!DNL .overwrite]) prima di distribuire il codice[!DNL Audience Manager]in produzione?**

* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Caso 1</b> </p> </td> 
   <td colname="col2"> <p>Lunedì, un visitatore identificato nel database CRM come loga ABC visitatore, che attiva una sincronizzazione ID lato client. <span class="keyword"> Audience Manager</span> memorizza la mappatura del visitatore ABC nel <span class="keyword"> visitatore di Audience Manager</span> 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender" = "uomo", "lusso_ shopper" = "yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Riconosce il visitatore ABC dalla mappatura di sincronizzazione ID memorizzata. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "women", "wine_ enthusiast" = "yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> non dispone di un record di questo visitatore (o di un ID visitatore associato) in modo che il record non venga elaborato. </p> <p>Martedì, il visitatore DEF accede. Questa azione avvia la prima sincronizzazione ID lato client per quel visitatore. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. Tuttavia, il visitatore non dispone di dati CRM associati al relativo profilo. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "women", "wine_ enthusiast" = "yes", "dma" = "paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Riconosce il visitatore DEF dalla mappatura di sincronizzazione ID salvata. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> . sync</code> file contenente: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> . overwrite</code> file contenente: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender" = "uomo" "wine_ enthusiast" = "no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender" = "women" "wine_ enthusiast" = "yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> contiene un record mappato del visitatore JKL su ID 789, da una precedente sincronizzazione ID. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Riconosce JKL visitatore dalla mappatura di sincronizzazione ID salvata. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignora l'associazione delle caratteristiche per il visitatore GHI, poiché il relativo ID è stato sincronizzato solo nel batch corrente. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Che ora devo trasferire il file?**

[!DNL Audience Manager] controlla ed elabora i file più volte durante il giorno. Caricate i dati ogni volta che siete pronti.

<br> 

**Quanto tempo impiega prima che i dati di un file caricato siano disponibili per il targeting?**

I dati sono disponibili per il targeting dopo 48 ore. Inoltre, non interpretate l&#39;e-mail &quot;caricamento riuscito&quot; come istruzione che informa che i dati sono disponibili. This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br> 

**Con quale frequenza è necessario inviare file e devono trattarsi di file completi o incrementali?**

Si consiglia di inviare un file incrementale una volta al giorno per i nuovi visitatori e per i visitatori i cui dati sono cambiati. Many [!DNL Audience Manager] customers send a full file once per month. Tuttavia, questi intervalli e incrementi di file sono flessibili. È consigliabile inviare dati con incrementi e a volte più rilevanti.

<br> 

**Per quanto tempo Audience Manager tiene i miei file sul server?**

I file FTP vengono rimossi dopo l&#39;elaborazione. [!DNL S3] vengono rimossi dopo 30 giorni. I file che non possono essere elaborati a causa di formato, sintassi o altri errori vengono rimossi. See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**Qual è la differenza tra file completi e incrementali?**

* **Completo:** Un file completo sovrascrive tutti i profili visitatore esistenti e li sostituisce con quelli del file. Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

   >[!NOTE]
   >
   >The [!DNL .overwrite] files only overwrite [!DNL Audience Manager] profile data associated to this data provider. In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **Incremento:** Un file incrementale aggiunge nuovi dati ai profili visitatore esistenti. Incremental files are identified by the `.sync` tag appended to the file name. L&#39;invio in un file incrementale non cancella o sovrascrive i profili esistenti.

I seguenti casi d&#39;uso mostrano come questi tipi di file influiscono sui profili dei visitatori memorizzati.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Incremento e completo</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Solo incremento</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Day 2 <code> .sync</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori informazioni sui tipi di file completi e incrementali, vedi:

* [Requisiti di Amazon S 3 Nome e Dimensione file per i dati in entrata…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**Cosa succede se viene inviato un file con ID per i visitatori che non hanno mai eseguito la sincronizzazione ID su pagina?**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. Se un DPID (ID provider dati) è impostato come DPID su più dispositivi, i dati che vengono assimilati prima di una sincronizzazione ID vengono salvati ed è disponibile per l&#39;uso poco dopo la sincronizzazione ID.

<br> 

**Qual è l&#39;indicatore di data e ora per e può fornire un esempio?**

I timestamp vengono utilizzati per effettuare operazioni di registrazione e registrazione. Sono richiesti dalla sintassi utilizzata per un nome di file in ingresso adeguatamente formattato. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**Cos&#39;è un ID fornitore dati (DPID) e come lo capisco?**

Il tuo consulente Adobe assegna un DPID di tre cifre o quattro cifre a una particolare origine dati. Questo ID è univoco e non cambia.

<br> 

**Quanto sono grandi i file di dati giornalieri?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**La compressione del file di Audience Manager è supportata?**

Sì, vedi:

* [Compressione file per file di trasferimento dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**La chiave primaria nel database di origine dati è un indirizzo e-mail. Is that considered personally identifiable information?**

Sì. [!DNL Audience Manager] non memorizza gli indirizzi e-mail nel database. Ai visitatori deve essere assegnato un ID casuale o una versione con hash dell&#39;indirizzo e-mail prima di avviare le sincronizzazioni ID.

<br> 

**Il contenuto del file di dati è sensibile alla distinzione tra maiuscole e minuscole? How about the ID sync?**

Esistono due componenti di base di un file di dati: Un ID utente univoco (UUID) e dati di profilo, solitamente sotto forma di coppie chiave-valore o codici. L&#39;UUID distingue tra maiuscole e minuscole. In genere, il profilo o i dati chiave-valore non sono sensibili alle maiuscole/minuscole.

<br> 

**È necessario utilizzare l&#39;FTP o[!DNL Amazon S3]per trasferire i file?**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] trasferisce i file FTP a [!DNL S3] prescindere, pertanto il processo risulta più semplice se rilasci i file [!DNL Amazon S3] su voi stessi. Inoltre, i clienti che caricano contemporaneamente in FTP condividono la larghezza di banda dell&#39;FTP, quindi dovrebbero aspettarsi velocità di caricamento lente. [!DNL Amazon S3] vengono anche replicati e distribuiti, pertanto è generalmente più sicuro e affidabile rispetto a un server FTP. For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br> 

**In che modo Audience Manager elabora i file in entrata?**

[!DNL Audience Manager] utilizzati [!DNL Amazon Simple Queue Service (SQS)] per l&#39;elaborazione dei dati in entrata. Ecco come funziona:

1. [!DNL Audience Manager] i clienti caricano i dati in entrata su [!DNL Amazon S3] un bucket.

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager] legge fino a 119000 voci dalla [!DNL Amazon SQS] coda e le suddivide fino a 3 batch. I file in ciascun batch vengono elaborati contemporaneamente.

<br> 

**Devo caricare più file contemporaneamente. Will the files be processed simultaneously?**

Dipende da [!DNL Audience Manager] legge fino a 119000 voci dalla [!DNL Amazon SQS] coda e le suddivide fino a 3 batch. I file saranno elaborati contemporaneamente solo se finiscono nello stesso batch. However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_ LIKE_ THIS]
>
>* [Processo di trasferimento dati batch descritta](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

