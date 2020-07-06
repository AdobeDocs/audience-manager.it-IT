---
description: Domande frequenti su come importare dati offline in Audience Manager.
keywords: ftp or s3;s3 or ftp
seo-description: Domande frequenti su come importare dati offline in Audience Manager.
seo-title: Domande frequenti sull’acquisizione dei dati dei clienti in entrata
solution: Audience Manager
title: Domande frequenti sull’acquisizione dei dati dei clienti in entrata
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 91%

---


# Domande frequenti sull’acquisizione dei dati dei clienti in entrata {#inbound-customer-data-ingestion-faq}

Domande frequenti su come importare dati offline in Audience Manager.

 

**È possibile riepilogare il processo di onboarding?**

Il processo di onboarding consiste di due passaggi descritti in [Send Batch Data to Audience Manager Overview](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* Passaggio 1: sincronizza gli ID utente;
* Passaggio 2: crea e trasferisci il file di dati in entrata rispettando i requisiti di formato del file.

 

**È possibile riepilogare il processo di distribuzione?**

Consigliamo quanto segue:

* Rivolgiti al provider di dati per formattare il file di dati in entrata giornaliero in base alle specifiche Adobe. Per i requisiti di denominazione e sintassi dei file, consulta la seguente documentazione:
   * [Name and Content Requirements for ID Synchronization Files](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Amazon S3 Name and File Size Requirements for Inbound Data Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Rivolgiti al tuo consulente [!DNL Adobe] per trasferire un file di dati di prova in [!DNL Adobe] per verificarne il formato.
* Rivolgiti al tuo consulente [!DNL Adobe] per creare una tassonomia adatta all’interpretazione del contenuto del file di dati.
* Nell’ambiente di pre-produzione/sviluppo, verifica che la sincronizzazione ID sia configurata in modo da raccogliere correttamente l’ID visitatore del provider di dati e trasferirlo ai server [!DNL Audience Manager] in tempo reale.
* Implementa la sincronizzazione DIL/ID in produzione. La sincronizzazione ID sarà già configurata come un modulo all’interno del codice DIL dal tuo consulente Adobe.
* Trasferisci i file di dati di produzione in [!DNL Audience Manager]. Considerate le dipendenze dalle mappature di sincronizzazione ID, potrebbe essere utile iniziare a trasferire i dati fino a una settimana dopo la distribuzione del codice di produzione, anche se puoi iniziare a trasferire i file di dati non appena il codice entra in produzione.

 

**Quale modalità FTP devo utilizzare per trasferire i file compressi o crittografati?**

Consulta [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>Stiamo gradualmente eliminando il supporto per le configurazioni FTP. Anche se l’assimilazione dei file di dati in entrata è ancora supportata nelle integrazioni FTP esistenti, consigliamo vivamente di utilizzare Amazon S3 per l’onboarding dei dati offline per nuove integrazioni. Per informazioni dettagliate, consulta [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

 

**Posso caricare un file di dati in entrata (file [!DNL .sync] o [!DNL .overwrite]) prima di distribuire il codice [!DNL Audience Manager] in produzione?**

Sì. As long as you use a [!UICONTROL cross-device data source] to store the CRM data that you upload, Audience Manager always stores the data. In fact, following the [!UICONTROL Profile Merge Rules] enhancements that Audience Manager launched in October 2019 that allow for offline-only use cases, you can upload and action on data without deploying Audience Manager code into production at all. Consulta:

* [Overview of Profile Merge Rules Enhancements](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [Personalizzazione basata su dati solo offline](https://docs.adobe.com/content/help/it-IT/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**A che ora devo trasferire il file?**

[!DNL Audience Manager] verifica ed elabora i file più volte nel corso della giornata. Carica i dati quando sei pronto.

 

**Quanto tempo ci vuole prima che i dati di un file caricato siano disponibili per il targeting?**

I dati sono disponibili per il targeting dopo 48 ore. Inoltre, non interpretare l’e-mail di “caricamento riuscito” come un’indicazione che i dati sono disponibili. Ciò significa solo che [!DNL Audience Manager] ha acquisito il file e completato il primo passaggio di elaborazione.

 

**Con quale frequenza devo inviare i file? Devono essere file completi o incrementali?**

Come procedura ottimale, invia un file incrementale una volta al giorno per i nuovi visitatori e per i visitatori i cui dati sono cambiati. Molti clienti [!DNL Audience Manager] inviano un file completo una volta al mese. Tuttavia, questi intervalli e incrementi di file sono flessibili. Devi inviare i dati in maniera incrementale e quando ha senso per te.

 

**Per quanto tempo Audience Manager conserva i miei file sul server?**

I file FTP vengono rimossi dopo l’elaborazione. I file [!DNL S3] vengono rimossi dopo 30 giorni. I file che non possono essere elaborati a causa di formato, sintassi o altri errori, vengono rimossi. Consulta anche [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

 

**Qual è la differenza tra file completi e incrementali?**

* **Completo:** un file completo sovrascrive tutti i profili visitatore esistenti e li sostituisce con i dati presenti nel file. I file completi sono identificati dal tag `.overwrite` aggiunto al nome del file. Puoi usare un file `.overwrite` per ripristinare le caratteristiche dei visitatori o rimuovere caratteristiche obsolete e non aggiornate.

   >[!NOTE]
   >
   >I file [!DNL .overwrite] sovrascrivono solo i dati profilo di [!DNL Audience Manager] associati a questo provider di dati. In altre parole, tutti i dati [!DNL Audience Manager] associati al visitatore rimangono intatti dopo l’elaborazione di un file [!DNL .overwrite].

* **Incrementale:** un file incrementale aggiunge nuovi dati ai profili visitatore esistenti. I file incrementali sono identificati dal tag `.sync` aggiunto al nome del file. L’invio di un file incrementale non cancella o sovrascrive i profili esistenti.

I seguenti casi d’uso dimostrano come questi tipi di file influiscono sui profili dei visitatori memorizzati.

| Caso d&#39;uso | Descrizione |
|---|---|
| Incrementale e completo | <ul><li>Contenuto del file `.sync` del giorno 1: `visitor123 = a,b,c`</li><li>Contenuto del file `.overwrite` del giorno 2: `visitor123 = c,d,e`</li><li>Contenuto dell’ID profilo visitatore 123 del giorno 3: `c,d,e`</li></ul> |
| Solo incrementale | <ul><li>Contenuto del file `.sync` del giorno 1: `visitor123 = a,b,c`</li><li>Contenuto del file `.sync` del giorno 2: `visitor123 = c,d,e`</li><li>Contenuto dell’ID profilo visitatore 123 del giorno 3: `a,b,c,d,e`</li></ul> |

Per ulteriori informazioni sui tipi di file completi e incrementali, consulta:

* [Amazon S3 Name and File Size Requirements for Inbound Data...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Cosa succede se invio un file con ID per visitatori che non hanno mai eseguito la sincronizzazione ID su pagina?**

Durante l’elaborazione, [!DNL Audience Manager] ignora quel record e passa al successivo. Se un [DPID (Data Provider ID)](../reference/ids-in-aam.md) è configurato come DPID per più dispositivi, i dati che vengono acquisiti prima della sincronizzazione ID vengono salvati e sono disponibili per l’uso poco dopo che la sincronizzazione ID è avvenuta.

 

**Che cos’è la marca temporale e a cosa serve? Potete fornire un esempio?**

Le marche temporali vengono utilizzate per la registrazione e per la conservazione di record. Sono richieste dalla sintassi utilizzata per formattare correttamente il nome di un file in entrata. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Cos&#39;è un[!DNL Data Provider ID (DPID)]e come lo ottengo?**

Il tuo consulente Adobe assegnerà un [DPID (Data Provider ID)](../reference/ids-in-aam.md) di tre o quattro cifre alla tua specifica sorgente di dati. Questo ID è univoco e non viene modificato.

 

**Quanto possono essere grandi i file di dati giornalieri?**

Consulta [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**Audience Manager supporta la compressione dei file?**

Sì, consulta:

* [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Amazon S3 Name Requirements for Inbound Data Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**La chiave primaria nel mio database delle sorgenti di dati è un indirizzo e-mail. È considerata un’informazione personale?**

Sì. [!DNL Audience Manager] non memorizza gli indirizzi e-mail nel proprio database. Prima di avviare la sincronizzazione degli ID, ai visitatori deve essere assegnato un ID generato in modo casuale o una versione con hash unidirezionale dell’indirizzo e-mail.

 

**Il contenuto dei file di dati è sensibile a maiuscole e minuscole? E la sincronizzazione ID?**

Esistono due componenti di base di un file di dati: un [!UICONTROL User ID] (consulta [!UICONTROL User ID] in [File Variables Defined](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) e dati di profilo, in genere sotto forma di coppie o codici chiave-valore. Lo [!UICONTROL User ID] è sensibile a maiuscole e minuscole. In genere, i dati relativi al profilo o al valore chiave non sono sensibili a maiuscole e minuscole.

 

**Devo utilizzare l’FTP o [!DNL Amazon S3] per trasferire i file?**

Come best practice, consigliamo [!DNL Amazon S3] perché il processo è più semplice. [!DNL Audience Manager] trasferisce i file FTP in [!DNL S3] a prescindere, in modo che il processo sia più semplice se rilasci tu stesso i file in [!DNL Amazon S3]. Inoltre, i clienti che caricano simultaneamente su FTP condividono la larghezza di banda dell’FTP, quindi dovrebbero aspettarsi velocità di caricamento minori. [!DNL Amazon S3] viene anche replicato e distribuito, quindi in genere è più sicuro e affidabile di un server FTP. Per ulteriori informazioni, consulta [About Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Stiamo gradualmente eliminando il supporto per le configurazioni FTP. While inbound data file ingestion is still supported in existing FTP integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. Per informazioni dettagliate, consulta [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

 

**In che modo Audience Manager elabora i file in entrata?**

[!DNL Audience Manager] utilizza [!DNL Amazon Simple Queue Service (SQS)] per l’elaborazione di dati in entrata. Ecco come funziona:

1. I clienti [!DNL Audience Manager] caricano i dati in entrata in un bucket [!DNL Amazon S3].
1. I dati vengono aggiunti alla coda di [!DNL Amazon SQS], in attesa di essere elaborati da [!DNL Audience Manager].
1. [!DNL Audience Manager] legge fino a 119.000 voci dalla coda di [!DNL Amazon SQS] e le divide in massimo 3 batch. I file in ciascun batch vengono elaborati simultaneamente.

 

**Ho bisogno di caricare più file contemporaneamente. I file verranno elaborati simultaneamente?**

Dipende. [!DNL Audience Manager] legge fino a 119.000 voci dalla coda di [!DNL Amazon SQS] e le divide in massimo 3 batch. I file verranno elaborati simultaneamente solo se sono inclusi nello stesso batch. Tuttavia, a causa dell’elevata quantità di dati acquisiti da [!DNL Audience Manager] su base giornaliera, non possiamo garantire alcun ordine di elaborazione dei file.

>[!MORELIKETHIS]
>
>* [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

