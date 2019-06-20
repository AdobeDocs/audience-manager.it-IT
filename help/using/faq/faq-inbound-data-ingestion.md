---
description: Domande frequenti su come portare dati offline in Audience Manager.
keywords: ftp o s 3; s 3 o ftp
seo-description: Domande frequenti su come portare dati offline in Audience Manager.
seo-title: Domande frequenti sull'assimilazione dei dati cliente
solution: Audience Manager
title: Domande frequenti sull'assimilazione dei dati cliente
uuid: 491 e 9 ec 1-4731-46 a 8-86 e 7-d 8 c 613 e 6 cedc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domande frequenti sull&#39;assimilazione dei dati cliente{#inbound-customer-data-ingestion-faq}

Domande frequenti su come portare dati offline in Audience Manager.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**È possibile riepilogare il processo di onboarding?**

Il processo di registrazione è costituito da 2 componenti core descritti in [Procedura di trasferimento di dati batch descritta](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). che richiedono:

* Sincronizzazione ID
* File di dati in entrata ( [!DNL .sync] file o [!DNL .overwrite] file)

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

* Consultate il provider di dati per formattare il file di dati in entrata giornalieri in base [!DNL Adobe] alle specifiche.
* Trasferimento di un file di dati di prova per [!DNL Adobe] la verifica del formato.
* Rivolgersi al [!DNL Adobe] consulente per produrre una tassonomia adatta all&#39;interpretazione dei contenuti del file di dati.
* Nell&#39;ambiente di verifica/di sviluppo, conferma che la sincronizzazione ID è configurata per recuperare correttamente l&#39;ID visitatore del fornitore di dati e trasferirlo ai [!DNL Audience Manager] server in tempo reale.
* Distribuisci la sincronizzazione DIL/ID in produzione. La sincronizzazione ID sarà già configurata come modulo all&#39;interno del codice DIL dal consulente Adobe.
* Transfer production data files to [!DNL Audience Manager]. Considerate le dipendenze delle mappature di sincronizzazione ID, potrebbe essere sensato iniziare a trasferire dati fino a una settimana dopo la distribuzione del codice di produzione, anche se potete iniziare a trasferire i file di dati non appena il codice entra nella produzione.

<br> 

**Quale modalità FTP posso usare per trasferire file compressi o codificati?**

Consultate [Compressione file per trasferimento di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Posso caricare un file di dati in entrata ([!DNL .sync]o il file[!DNL .overwrite]) prima di distribuire il codice[!DNL Audience Manager]in produzione?**

* Se il provider di dati è configurato per utilizzare [Collegamento](../features/profile-merge-rules/merge-rules-overview.md) profilo per il targeting su più dispositivi, i dati disponibili per il targeting poco dopo la sincronizzazione ID identificano l&#39;ID [!DNL Audience Manager] visitatore corrispondente.

* Se il provider di dati non è configurato per utilizzare la [!UICONTROL Profile Link] funzionalità [!DNL Audience Manager] , elabora solo i dati per gli ID visitatore nel file di dati in entrata che sono stati precedentemente sincronizzati/associati a un [!DNL Audience Manager] ID visitatore.

Considerate i seguenti casi d&#39;uso in cui il provider di dati non è configurato per l&#39;utilizzo [!UICONTROL Profile Merge]:

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
   <td colname="col2"> <p>Lunedì, un visitatore identificato nel database CRM come loga ABC visitatore, che attiva una sincronizzazione ID lato client. <span class="keyword"> Audience Manager</span> memorizza la mappatura del visitatore ABC nel <span class="keyword"> visitatore di Audience Manager</span> 123. </p> <p>Martedì, il database CRM trasferisce un file di dati (<span class="filepath"> . sync</span>) al server <span class="keyword"> Audience Manager </span>con il record seguente: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender" = "uomo", "lusso_ shopper" = "yes"</code> </li> 
     </ul> </p> <p>In questo caso <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Riconosce il visitatore ABC dalla mappatura di sincronizzazione ID memorizzata. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associa le caratteristiche <code> maschio</code> e <code> di lusso_ shopper</code> al profilo visitatore 123. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 2</b> </p> </td> 
   <td colname="col2"> <p>Lunedì, il database CRM invia un file di dati (<span class="filepath"> . sync</span>) al server <span class="keyword"> Audience Manager</span> con il record seguente: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "women", "wine_ enthusiast" = "yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> non dispone di un record di questo visitatore (o di un ID visitatore associato) in modo che il record non venga elaborato. </p> <p>Martedì, il visitatore DEF accede. Questa azione avvia la prima sincronizzazione ID lato client per quel visitatore. Questa azione mappa il visitatore DEF su <span class="keyword"> Audience Manager</span> ID 456. Tuttavia, il visitatore non dispone di dati CRM associati al relativo profilo. Di conseguenza <span class="keyword"> , Audience Manager</span> non torna indietro e rielabora i vecchi file. </p> <p>Mercoledì, il database CRM invia un altro file di dati al <span class="keyword"> server Audience Manager</span> con il seguente record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender" = "women", "wine_ enthusiast" = "yes", "dma" = "paris"</code> </li> 
     </ul> </p> <p>In questo caso <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Riconosce il visitatore DEF dalla mappatura di sincronizzazione ID salvata. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associa le caratteristiche <code> femminili</code>, <code> parigi</code>e <code> vincenti</code> al profilo visitor 456. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 3</b> </p> </td> 
   <td colname="col2"> <p>Lunedì, <span class="keyword"> il server Audience Manager</span> riceve due file con i record seguenti: </p> <p> <code> . sync</code> file contenente: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> . overwrite</code> file contenente: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender" = "uomo" "wine_ enthusiast" = "no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender" = "women" "wine_ enthusiast" = "yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> contiene un record mappato del visitatore JKL su ID 789, da una precedente sincronizzazione ID. </p> <p>In questo caso <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Riconosce JKL visitatore dalla mappatura di sincronizzazione ID salvata. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associa le caratteristiche <code> femminili</code> e <code> vino_ appassionast</code> con il profilo ID visitatore 789. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignora l'associazione delle caratteristiche per il visitatore GHI, poiché il relativo ID è stato sincronizzato solo nel batch corrente. Per associare caratteristiche al visitatore PAT, è necessario includerle in futuro <code> . Sovrascrivi</code> file. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Che ora devo trasferire il file?**

[!DNL Audience Manager] controlla ed elabora i file più volte durante il giorno. Caricate i dati ogni volta che siete pronti.

<br> 

**Quanto tempo impiega prima che i dati di un file caricato siano disponibili per il targeting?**

I dati sono disponibili per il targeting dopo 48 ore. Inoltre, non interpretate l&#39;e-mail &quot;caricamento riuscito&quot; come istruzione che informa che i dati sono disponibili. Questo significa che [!DNL Audience Manager] ha selezionato il file e completato il primo passaggio dell&#39;elaborazione.

<br> 

**Con quale frequenza è necessario inviare file e devono trattarsi di file completi o incrementali?**

Si consiglia di inviare un file incrementale una volta al giorno per i nuovi visitatori e per i visitatori i cui dati sono cambiati. Molti [!DNL Audience Manager] clienti inviano un file completo una volta al mese. Tuttavia, questi intervalli e incrementi di file sono flessibili. È consigliabile inviare dati con incrementi e a volte più rilevanti.

<br> 

**Per quanto tempo Audience Manager tiene i miei file sul server?**

I file FTP vengono rimossi dopo l&#39;elaborazione. [!DNL S3] vengono rimossi dopo 30 giorni. I file che non possono essere elaborati a causa di formato, sintassi o altri errori vengono rimossi. Vedi anche Domande frequenti [sulla privacy e sulla conservazione dei dati](../faq/faq-privacy.md).

<br> 

**Qual è la differenza tra file completi e incrementali?**

* **Completo:** Un file completo sovrascrive tutti i profili visitatore esistenti e li sostituisce con quelli del file. I file completi sono identificati dal `.overwrite` tag aggiunto al nome del file. Puoi usare un `.overwrite` file per reimpostare le caratteristiche dei visitatori o rimuovere tratti stanti e obsoleti.

   >[!NOTE]
   >
   >I [!DNL .overwrite] file sovrascrivono solo i dati [!DNL Audience Manager] di profilo associati a questo provider di dati. In altre parole, tutti [!DNL Adobe Analytics] i dati associati al visitatore rimangono intatti dopo l&#39;elaborazione di un [!DNL .overwrite] file.

* **Incremento:** Un file incrementale aggiunge nuovi dati ai profili visitatore esistenti. I file incrementali sono identificati dal `.sync` tag aggiunto al nome del file. L&#39;invio in un file incrementale non cancella o sovrascrive i profili esistenti.

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
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> . sync</code> file contents: <code> visitor 123 = a, b, c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Giorno 2 <code> . sovrascrivi</code> il contenuto del file: <code> visitor 123 = c, d, e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c, d, e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Solo incremento</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> . sync</code> file contents: <code> visitor 123 = a, b, c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Day 2 <code> . sync</code> file contents: <code> visitor 123 = c, d, e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Il profilo visitor del giorno 3 contiene <code> a, b, c, d, e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori informazioni sui tipi di file completi e incrementali, vedi:

* [Requisiti di Amazon S 3 Nome e Dimensione file per i dati in entrata…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Requisiti di nome FTP e dimensione file per file di dati in entrata…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**Cosa succede se viene inviato un file con ID per i visitatori che non hanno mai eseguito la sincronizzazione ID su pagina?**

Durante l&#39;elaborazione, salta [!DNL Audience Manager] semplicemente tale record e passa a quello successivo. Se un DPID (ID provider dati) è impostato come DPID su più dispositivi, i dati che vengono assimilati prima di una sincronizzazione ID vengono salvati ed è disponibile per l&#39;uso poco dopo la sincronizzazione ID.

<br> 

**Qual è l&#39;indicatore di data e ora per e può fornire un esempio?**

I timestamp vengono utilizzati per effettuare operazioni di registrazione e registrazione. Sono richiesti dalla sintassi utilizzata per un nome di file in ingresso adeguatamente formattato. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Requisiti di nome FTP e dimensione file per file di dati in entrata…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**Cos&#39;è un ID fornitore dati (DPID) e come lo capisco?**

Il tuo consulente Adobe assegna un DPID di tre cifre o quattro cifre a una particolare origine dati. Questo ID è univoco e non cambia.

<br> 

**Quanto sono grandi i file di dati giornalieri?**

Consultate [Compressione file per trasferimento di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**La compressione del file di Audience Manager è supportata?**

Sì, vedi:

* [Compressione file per file di trasferimento dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Requisiti di nome FTP per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

<br> 

**La chiave primaria nel database di origine dati è un indirizzo e-mail. È considerato informazioni personali identificabili?**

Sì. [!DNL Audience Manager] non memorizza gli indirizzi e-mail nel database. Ai visitatori deve essere assegnato un ID casuale o una versione con hash dell&#39;indirizzo e-mail prima di avviare le sincronizzazioni ID.

<br> 

**Il contenuto del file di dati è sensibile alla distinzione tra maiuscole e minuscole? Informazioni sulla sincronizzazione ID**

Esistono due componenti di base di un file di dati: Un ID utente univoco (UUID) e dati di profilo, solitamente sotto forma di coppie chiave-valore o codici. L&#39;UUID distingue tra maiuscole e minuscole. In genere, il profilo o i dati chiave-valore non sono sensibili alle maiuscole/minuscole.

<br> 

**È necessario utilizzare l&#39;FTP o[!DNL Amazon S3]per trasferire i file?**

Come procedura ottimale, si consiglia [!DNL Amazon S3] di semplificare il processo. [!DNL Audience Manager] trasferisce i file FTP a [!DNL S3] prescindere, pertanto il processo risulta più semplice se rilasci i file [!DNL Amazon S3] su voi stessi. Inoltre, i clienti che caricano contemporaneamente in FTP condividono la larghezza di banda dell&#39;FTP, quindi dovrebbero aspettarsi velocità di caricamento lente. [!DNL Amazon S3] vengono anche replicati e distribuiti, pertanto è generalmente più sicuro e affidabile rispetto a un server FTP. Per ulteriori informazioni, consultate [Informazioni su Amazon S 3](../reference/amazon-s3.md).

<br> 

**In che modo Audience Manager elabora i file in entrata?**

[!DNL Audience Manager] utilizzati [!DNL Amazon Simple Queue Service (SQS)] per l&#39;elaborazione dei dati in entrata. Ecco come funziona:

1. [!DNL Audience Manager] i clienti caricano i dati in entrata su [!DNL Amazon S3] un bucket.

2. I dati entrano nella [!DNL Amazon SQS] coda in attesa [!DNL Audience Manager]dell&#39;elaborazione.

3. [!DNL Audience Manager] legge fino a 119000 voci dalla [!DNL Amazon SQS] coda e le suddivide fino a 3 batch. I file in ciascun batch vengono elaborati contemporaneamente.

<br> 

**Devo caricare più file contemporaneamente. I file saranno elaborati contemporaneamente?**

Dipende da [!DNL Audience Manager] legge fino a 119000 voci dalla [!DNL Amazon SQS] coda e le suddivide fino a 3 batch. I file saranno elaborati contemporaneamente solo se finiscono nello stesso batch. Tuttavia, a causa dell&#39;elevata quantità di dati assimilati [!DNL Audience Manager] su base giornaliera, non possiamo garantire l&#39;ordine di elaborazione dei file.

>[!MORE_ LIKE_ THIS]
>
>* [Processo di trasferimento dati batch descritta](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

