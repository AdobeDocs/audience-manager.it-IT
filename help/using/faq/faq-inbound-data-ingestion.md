---
description: Domande frequenti su come portare dati offline in  Audience Manager.
keywords: ftp or s3;s3 or ftp
seo-description: Domande frequenti su come portare dati offline in  Audience Manager.
seo-title: Domande frequenti sull'inserimento dei dati dei clienti in entrata
solution: Audience Manager
title: Domande frequenti sull'inserimento dei dati dei clienti in entrata
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 3%

---


# Domande frequenti sull&#39;inserimento dei dati dei clienti in entrata{#inbound-customer-data-ingestion-faq}

Domande frequenti su come portare dati offline in  Audience Manager.

 

**Potete riepilogare il processo di onboarding?**

Il processo di onboarding consiste di due passaggi descritti in [Invia dati batch a  Panoramica](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)di Audience Manager:

* Passaggio 1: sincronizzare gli ID utente;
* Passaggio 2: creare e trasferire il file di dati in entrata, rispettando i requisiti di formato del file.

 

**È possibile riepilogare il processo di distribuzione?**

Consigliamo quanto segue:

* Consulta il provider di dati per formattare il file di dati in entrata giornaliero in base alle specifiche Adobe. Per i requisiti di denominazione dei file e sintassi, consultate la seguente documentazione:
   * [Requisiti di nome e contenuto per i file di sincronizzazione ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Contenuto file dati in entrata: Sintassi, caratteri non validi, variabili ed esempi](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Requisiti di nome e dimensione file Amazon S3 per i file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Consultate il vostro [!DNL Adobe] consulente per trasferire un file di dati di prova a [!DNL Adobe] scopo di verifica del formato.
* Consultate il vostro [!DNL Adobe] consulente per produrre una tassonomia adatta all&#39;interpretazione del contenuto del file di dati.
* Nell’ambiente di pre-produzione/sviluppo, verifica che la sincronizzazione ID sia configurata in modo da raccogliere correttamente l’ID visitatore del provider di dati e trasferirlo ai [!DNL Audience Manager] server in tempo reale.
* Implementare la sincronizzazione DIL/ID in produzione. La sincronizzazione ID sarà già configurata come modulo all’interno del codice DIL dal tuo consulente Adobe.
* Trasferisci i file di dati di produzione in [!DNL Audience Manager]. Considerate le dipendenze dalle mappature di sincronizzazione ID, potrebbe essere utile iniziare a trasferire i dati fino a una settimana dopo la distribuzione del codice di produzione, anche se è possibile iniziare a trasferire i file di dati non appena il codice entra in produzione.

 

**Quale modalità FTP devo utilizzare per trasferire i file compressi o crittografati?**

Consulta [Compressione file per i file](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)di trasferimento dati in entrata.

>[!WARNING]
>
>Stiamo gradualmente eliminando il supporto per le configurazioni FTP. Anche se l&#39;assimilazione dei file di dati in entrata è ancora supportata nelle integrazioni FTP esistenti, si consiglia vivamente di utilizzare Amazon S3 per incorporare dati offline per nuove integrazioni. Per informazioni dettagliate, consultate [Amazon S3 Name and File Size Requirements for Inbound Data Files (Requisiti di nome e dimensione file Amazon S3 per i file](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) in entrata).

 

**Posso caricare un file di dati in entrata (file [!DNL .sync] o [!DNL .overwrite]) prima di distribuire il codice [!DNL Audience Manager] in produzione?**

Sì. Se utilizzi un [!UICONTROL cross-device data source] per memorizzare i dati CRM caricati,  Audience Manager memorizza sempre i dati. Infatti, in seguito ai [!UICONTROL Profile Merge Rules] miglioramenti che  Audience Manager ha avviato a ottobre 2019 e che consentono casi di utilizzo esclusivamente offline, potete caricare e intervenire sui dati senza distribuire  codice Audience Manager in produzione. Consulta:

* [Panoramica dei miglioramenti delle regole di unione dei profili](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [Personalizzazione basata su dati solo offline](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

 

**Quanto tempo ci vuole prima che i dati da un file caricato siano disponibili per il targeting?**

I dati sono disponibili per il targeting dopo 48 ore. Inoltre, non interpretate l’e-mail di &quot;caricamento riuscito&quot; come un’istruzione che indica che i dati sono disponibili. Ciò significa solo che [!DNL Audience Manager] ha prelevato il file e completato il primo passaggio di elaborazione.

 

**Con quale frequenza devo inviare i file e questi devono essere file completi o incrementali?**

Come procedura ottimale, inviate un file incrementale una volta al giorno per i nuovi visitatori e per i visitatori i cui dati sono cambiati. Molti [!DNL Audience Manager] clienti inviano un file completo una volta al mese. Tuttavia, questi intervalli e incrementi di file sono flessibili. I dati devono essere inviati in incrementi e a volte rilevanti.

 

**Per quanto tempo  Audience Manager mantiene i miei file sul server?**

I file FTP vengono rimossi dopo l&#39;elaborazione. [!DNL S3] i file vengono rimossi dopo 30 giorni. I file che non possono essere elaborati a causa di formato, sintassi o altri errori, vengono rimossi. Vedi anche Domande frequenti sulla [privacy e sulla conservazione dei dati](../faq/faq-privacy.md).

 

**Qual è la differenza tra file completi e incrementali?**

* **Completa:** Un file completo sovrascrive tutti i profili visitatore esistenti e li sostituisce con i dati presenti nel file. I file completi sono identificati dal `.overwrite` tag aggiunto al nome del file. Potete usare un `.overwrite` file per ripristinare le caratteristiche dei visitatori o rimuovere tratti obsoleti e non aggiornati.

   >[!NOTE]
   >
   >I [!DNL .overwrite] file sovrascrivono solo i dati [!DNL Audience Manager] del profilo associati a questo provider di dati. In altre parole, tutti [!DNL Audience Manager] i dati associati al visitatore rimangono intatti dopo l’elaborazione di un [!DNL .overwrite] file.

* **Incrementale:** Un file incrementale aggiunge nuovi dati ai profili visitatore esistenti. I file incrementali sono identificati dal `.sync` tag aggiunto al nome del file. L&#39;invio in un file incrementale non cancella o sovrascrive i profili esistenti.

I seguenti casi di utilizzo dimostrano come questi tipi di file influiscono sui profili dei visitatori memorizzati.

| Caso d&#39;uso | Descrizione |
|---|---|
| Incrementale e completo | <ul><li>Contenuto del `.sync` file Giorno 1: `visitor123 = a,b,c`</li><li>Contenuto `.overwrite` del file Giorno 2: `visitor123 = c,d,e`</li><li>Contenuto del profilo visitatore ID 123 del giorno 3: `c,d,e`</li></ul> |
| Solo incrementale | <ul><li>Contenuto del `.sync` file Giorno 1: `visitor123 = a,b,c`</li><li>Contenuto `.sync` del file Giorno 2: `visitor123 = c,d,e`</li><li>Contenuto del profilo visitatore ID 123 del giorno 3: `a,b,c,d,e`</li></ul> |

Per ulteriori informazioni sui tipi di file completi e incrementali, vedi:

* [Requisiti di nome e dimensione file Amazon S3 per i dati in entrata...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Cosa succede se si invia un file con ID per i visitatori che non hanno mai eseguito la sincronizzazione ID sulla pagina?**

Durante l&#39;elaborazione, [!DNL Audience Manager] ignora la registrazione e passa alla fase successiva. Se un [DPID (ID provider dati)](../reference/ids-in-aam.md) è configurato come DPID per più dispositivi, i dati che vengono acquisiti prima del salvataggio della sincronizzazione ID e sono disponibili per l’uso poco dopo che si è verificata la sincronizzazione ID.

 

**Qual è l&#39;indicazione di data e ora, a cosa serve e potete fornire un esempio?**

I timestamp vengono utilizzati per la registrazione e la conservazione dei record. Sono richiesti dalla sintassi utilizzata per il nome di un file in entrata formattato correttamente. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Cos&#39;è un[!DNL Data Provider ID (DPID)]e come lo ottengo?**

Il tuo consulente Adobe assegnerà un [DPID (ID provider dati)](../reference/ids-in-aam.md) di tre o quattro cifre alla tua particolare origine dati. Questo ID è univoco e non viene modificato.

 

**Quanto possono essere grandi i file di dati giornalieri?**

Consulta [Compressione file per i file](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)di trasferimento dati in entrata.

 

**Audience Manager supporta la compressione dei file?**

Sì, vedi:

* [Compressione file per i file di trasferimento dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**La chiave primaria nel database dell&#39;origine dati è un indirizzo e-mail. Sono considerate informazioni personali?**

Sì. [!DNL Audience Manager] non memorizza gli indirizzi e-mail nel database. Prima di avviare la sincronizzazione degli ID, ai visitatori deve essere assegnato un ID generato in modo casuale o una versione con hash unidirezionale dell’indirizzo e-mail.

 

**Il contenuto del file di dati è sensibile alle maiuscole/minuscole? E la sincronizzazione ID?**

Esistono due componenti di base di un file di dati: A [!UICONTROL User ID] (vedere [!UICONTROL User ID] in Variabili di [file definite](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) e dati di profilo, in genere sotto forma di coppie o codici chiave-valore. Il modulo [!UICONTROL User ID] fa distinzione tra maiuscole e minuscole. In genere, i dati relativi al profilo o al valore chiave non fanno distinzione tra maiuscole e minuscole.

 

**Devo utilizzare l&#39;FTP o[!DNL Amazon S3]per trasferire i file?**

Come procedura ottimale, consigliamo [!DNL Amazon S3] perché il processo è più semplice. [!DNL Audience Manager] trasferisce i file FTP a [!DNL S3] prescindere, in modo che il processo sia più semplice se rilasci i file da [!DNL Amazon S3] solo. Inoltre, i clienti che caricano simultaneamente su FTP condividono la larghezza di banda dell&#39;FTP, quindi dovrebbero aspettarsi una velocità di caricamento più lenta. [!DNL Amazon S3] viene anche replicato e distribuito, quindi in genere è più sicuro e affidabile di un server FTP. Per ulteriori informazioni, consultate [Informazioni su Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Stiamo gradualmente eliminando il supporto per le configurazioni FTP. Anche se l&#39;assimilazione dei file di dati in entrata è ancora supportata nelle integrazioni FTP esistenti, si consiglia vivamente di utilizzare [!DNL Amazon S3] per le nuove integrazioni dati offline. Per informazioni dettagliate, consultate [Amazon S3 Name and File Size Requirements for Inbound Data Files (Requisiti di nome e dimensione file Amazon S3 per i file](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) in entrata).

 

**In che modo Audience Manager elabora i file in entrata?**

[!DNL Audience Manager] utilizza [!DNL Amazon Simple Queue Service (SQS)] per l&#39;elaborazione dati in entrata. Come funziona:

1. [!DNL Audience Manager] i clienti caricano i dati in entrata in un [!DNL Amazon S3] bucket.
1. I dati entrano nella [!DNL Amazon SQS] coda, in attesa di essere elaborati da [!DNL Audience Manager].
1. [!DNL Audience Manager] legge fino a 119000 voci dalla [!DNL Amazon SQS] coda e le divide in fino a 3 batch. I file in ciascun batch vengono elaborati simultaneamente.

 

**È necessario caricare più file contemporaneamente. I file verranno elaborati contemporaneamente?**

Dipende. [!DNL Audience Manager] legge fino a 119000 voci dalla [!DNL Amazon SQS] coda e le divide in fino a 3 batch. I file verranno elaborati simultaneamente solo se finiscono nello stesso batch. Tuttavia, a causa dell&#39;elevata quantità di dati acquisiti [!DNL Audience Manager] su base giornaliera, non possiamo garantire alcun ordine di elaborazione dei file.

>[!MORELIKETHIS]
>
>* [Processo di trasferimento dati batch descritto](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

