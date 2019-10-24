---
description: Domande frequenti su come portare dati offline in Audience Manager.
keywords: ftp o s3;s3 o ftp
seo-description: Domande frequenti su come portare dati offline in Audience Manager.
seo-title: Domande frequenti sull'inserimento dei dati dei clienti in entrata
solution: Audience Manager
title: Domande frequenti sull'inserimento dei dati dei clienti in entrata
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: e081e31380d4600883f927b5ecef3b38be2a676e

---


# Domande frequenti sull'inserimento dei dati dei clienti in entrata{#inbound-customer-data-ingestion-faq}

Domande frequenti su come portare dati offline in Audience Manager.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**Potete riepilogare il processo di onboarding?**

Il processo di onboarding è costituito da 2 componenti core descritti nel processo di trasferimento dati [batch descritto](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md). Si tratta di:

* Sincronizzazione ID
* File di dati in entrata ( [!DNL .sync] file o [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Di seguito è riportato un elenco di domande e risposte che potreste trovare utili dopo aver rivisto la documentazione.

>[!NOTE]
>
>Gli esempi di questa sezione sono semplificati o abbreviati a scopo di brevità e dimostrazione. Per informazioni dettagliate sui formati dei file e sulla sintassi, consultare la documentazione relativa all'inserimento dei dati in entrata.

<br> 

**È possibile riepilogare il processo di distribuzione?**

Consigliamo quanto segue:

* Collabora con il provider di dati per formattare il file di dati in entrata giornaliero in base alle [!DNL Adobe] specifiche.
* Trasferire un file di dati di prova [!DNL Adobe] per la verifica del formato.
* Consultate il vostro [!DNL Adobe] consulente per produrre una tassonomia adatta all'interpretazione del contenuto del file di dati.
* Nell’ambiente di pre-produzione/sviluppo, verifica che la sincronizzazione ID sia configurata in modo da raccogliere correttamente l’ID visitatore del provider di dati e trasferirlo ai [!DNL Audience Manager] server in tempo reale.
* Distribuisci la sincronizzazione DIL/ID in produzione. La sincronizzazione ID sarà già configurata come modulo all’interno del codice DIL dal tuo consulente Adobe.
* Trasferisci i file di dati di produzione in [!DNL Audience Manager]. Considerate le dipendenze dalle mappature di sincronizzazione ID, potrebbe essere utile iniziare a trasferire i dati fino a una settimana dopo la distribuzione del codice di produzione, anche se è possibile iniziare a trasferire i file di dati non appena il codice va in produzione.

<br> 

**Quale modalità FTP devo utilizzare per trasferire i file compressi o crittografati?**

Consulta [Compressione file per i file](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)di trasferimento dati in entrata.

<br> 

**Posso caricare un file di dati in entrata (file[!DNL .sync]o[!DNL .overwrite]) prima di distribuire il codice[!DNL Audience Manager]in produzione?**

* Se il fornitore di dati è configurato per utilizzare Collegamento [](../features/profile-merge-rules/merge-rules-overview.md) profilo per il targeting tra dispositivi, i dati disponibili per il targeting poco dopo che una sincronizzazione ID si identifica con l’ID [!DNL Audience Manager] visitatore corrispondente.

* Se il provider di dati non è configurato per utilizzare la [!UICONTROL Profile Link] funzione, [!DNL Audience Manager] elabora solo i dati per gli ID visitatore presenti nel file di dati in entrata che sono stati precedentemente sincronizzati/associati a un ID [!DNL Audience Manager] visitatore.

Tenere in considerazione i seguenti casi di utilizzo in cui il provider di dati non è configurato per l'utilizzo [!UICONTROL Profile Merge]:

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
   <td colname="col2"> <p>Lunedì, un visitatore identificato nel database CRM come visitor ABC effettua l'accesso, che avvia una sincronizzazione ID lato client. <span class="keyword"> Audience Manager</span> memorizza la mappatura del visitatore ABC al visitatore <span class="keyword"> Audience Manager</span> 123. </p> <p>Martedì, il database CRM trasferisce un file di dati (<span class="filepath"> .sync</span>) al <span class="keyword"> server </span>Audience Manager con il seguente record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In questo caso, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Riconosce l’ABC del visitatore dalla mappatura della sincronizzazione ID memorizzata. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associa le caratteristiche <code> male</code> e <code> luxury_shopper</code> con il profilo visitatore 123. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 2</b> </p> </td> 
   <td colname="col2"> <p>Lunedì, il database CRM invia un file di dati (<span class="filepath"> .sync</span>) al server <span class="keyword"> Audience Manager</span> con il seguente record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> non dispone di un record di questo visitatore (o di un ID visitatore associato), pertanto questo record non viene elaborato. </p> <p>Martedì, il DEF visitatore accede. Questa azione avvia la prima sincronizzazione ID lato client per quel visitatore. Questa azione mappa DEF visitatore su ID <span class="keyword"> Audience Manager</span> 456. Tuttavia, a questo visitatore non sono associati dati CRM con il relativo profilo. Di conseguenza, <span class="keyword"> Audience Manager</span> non torna indietro e non rielabora i file precedenti. </p> <p>Mercoledì, il database CRM invia un altro file di dati al server <span class="keyword"> Audience Manager</span> con il seguente record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In questo caso, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Riconosce il DEF visitatore dalla mappatura della sincronizzazione ID memorizzata. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associa le caratteristiche <code> female</code>, <code> paris</code>, e <code> wine_enthusiast</code> con il profilo visitatore 456. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Caso 3</b> </p> </td> 
   <td colname="col2"> <p>Lunedì, il server <span class="keyword"> Audience Manager</span> riceve due file con i seguenti record: </p> <p> <code> .sync</code> file contenente: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file contenente: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> contiene un record mappato di JKL visitatore a ID 789, da una sincronizzazione ID precedente. </p> <p>In questo caso, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Riconosce il JKL del visitatore dalla mappatura della sincronizzazione ID memorizzata. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associa le caratteristiche <code> female</code> e <code> wine_enthusiast</code> il profilo dell’ID visitatore 789. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignora l’associazione di caratteristiche per il GHI visitatore, poiché il relativo ID è stato sincronizzato solo nel batch corrente. Per associare caratteristiche con GHI visitatore, è necessario includerle in <code> .overwrite</code> file futuri. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**A che ora devo trasferire il file?**

[!DNL Audience Manager] verifica ed elabora i file più volte nel corso della giornata. Carica i dati quando sei pronto.

<br> 

**Quanto tempo ci vuole prima che i dati da un file caricato siano disponibili per il targeting?**

I dati sono disponibili per il targeting dopo 48 ore. Inoltre, non interpretate l’e-mail di "caricamento riuscito" come un’istruzione che indica che i dati sono disponibili. Ciò significa solo che [!DNL Audience Manager] ha prelevato il file e completato il primo passaggio di elaborazione.

<br> 

**Con quale frequenza devo inviare i file e questi devono essere file completi o incrementali?**

Come procedura ottimale, inviate un file incrementale una volta al giorno per i nuovi visitatori e per i visitatori i cui dati sono cambiati. Molti [!DNL Audience Manager] clienti inviano un file completo una volta al mese. Tuttavia, questi intervalli e incrementi di file sono flessibili. I dati devono essere inviati in incrementi e a volte rilevanti.

<br> 

**Per quanto tempo Audience Manager conserva i miei file sul server?**

I file FTP vengono rimossi dopo l'elaborazione. [!DNL S3] i file vengono rimossi dopo 30 giorni. I file che non possono essere elaborati a causa di formato, sintassi o altri errori vengono rimossi. Vedi anche Domande frequenti sulla [privacy e sulla conservazione dei dati](../faq/faq-privacy.md).

<br> 

**Qual è la differenza tra file completi e incrementali?**

* **** Completa: Un file completo sovrascrive tutti i profili visitatore esistenti e li sostituisce con i dati presenti nel file. I file completi sono identificati dal `.overwrite` tag aggiunto al nome del file. Potete usare un `.overwrite` file per ripristinare le caratteristiche dei visitatori o rimuovere tratti obsoleti e non aggiornati.

   >[!NOTE]
   >
   >I [!DNL .overwrite] file sovrascrivono solo i dati [!DNL Audience Manager] del profilo associati a questo provider di dati. In altre parole, tutti [!DNL Adobe Analytics] i dati associati al visitatore rimangono intatti dopo l’elaborazione di un [!DNL .overwrite] file.

* **** Incrementale: Un file incrementale aggiunge nuovi dati ai profili visitatore esistenti. I file incrementali sono identificati dal `.sync` tag aggiunto al nome del file. L'invio in un file incrementale non cancella o sovrascrive i profili esistenti.

I seguenti casi di utilizzo dimostrano come questi tipi di file influiscono sui profili dei visitatori memorizzati.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Incrementale e completo</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Contenuto del <code> .sync</code> file Giorno 1: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Contenuto <code> .overwrite</code> del file Giorno 2: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Il giorno 3 il profilo visitatore ID 123 contiene <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Solo incrementale</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Contenuto del <code> .sync</code> file Giorno 1: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Contenuto <code> .sync</code> del file Giorno 2: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Il giorno 3 il profilo visitatore ID 123 contiene <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori informazioni sui tipi di file completi e incrementali, vedi:

* [Requisiti di nome e dimensione file Amazon S3 per i dati in entrata...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**Cosa succede se invio un file con ID per i visitatori che non hanno mai eseguito la sincronizzazione ID sulla pagina?**

Durante l'elaborazione, [!DNL Audience Manager] ignora semplicemente la registrazione e passa alla fase successiva. Se un DPID (ID provider dati) è configurato come DPID per più dispositivi, i dati acquisiti prima del salvataggio della sincronizzazione ID sono disponibili per l’uso poco dopo la sincronizzazione ID.

<br> 

**Qual è l'indicazione di data e ora, a cosa serve e potete fornire un esempio?**

I timestamp vengono utilizzati per la registrazione e la conservazione dei record. Sono richiesti dalla sintassi utilizzata per il nome di un file in entrata formattato correttamente. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**Che cos’è un ID provider di dati (DPID) e come si ottiene?**

Il consulente Adobe assegnerà un DPID di tre o quattro cifre alla vostra origine dati specifica. Questo ID è univoco e non viene modificato.

<br> 

**Quanto possono essere grandi i file di dati giornalieri?**

Consulta [Compressione file per i file](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)di trasferimento dati in entrata.

<br> 

**Audience Manager supporta la compressione dei file?**

Sì, vedi:

* [Compressione file per i file di trasferimento dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Requisiti di nome di Amazon S3 per file di dati in entrata](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**La chiave primaria nel database dell'origine dati è un indirizzo e-mail. Sono considerate informazioni personali?**

Sì. [!DNL Audience Manager] non memorizza gli indirizzi e-mail nel nostro database. Prima di avviare la sincronizzazione ID, è necessario assegnare ai visitatori un ID casuale o una versione con hash unidirezionale dell’indirizzo e-mail.

<br> 

**Il contenuto del file di dati è sensibile alle maiuscole/minuscole? E la sincronizzazione ID?**

Esistono due componenti di base di un file di dati: Un ID utente (vedere ID utente nelle variabili di [file definite](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) e i dati di profilo, in genere sotto forma di coppie o codici chiave-valore. L’ID utente fa distinzione tra maiuscole e minuscole. In genere, i dati relativi al profilo o al valore chiave non fanno distinzione tra maiuscole e minuscole.

<br> 

**Devo utilizzare l'FTP o[!DNL Amazon S3]per trasferire i file?**

Come procedura ottimale, consigliamo [!DNL Amazon S3] perché il processo è più semplice. [!DNL Audience Manager] trasferisce i file FTP a [!DNL S3] prescindere, in modo che il processo sia più semplice se rilasci i file da [!DNL Amazon S3] solo. Inoltre, i clienti che caricano simultaneamente su FTP condividono la larghezza di banda dell'FTP, quindi dovrebbero aspettarsi una velocità di caricamento più lenta. [!DNL Amazon S3] viene anche replicato e distribuito, quindi in genere è più sicuro e affidabile di un server FTP. Per ulteriori informazioni, consultate [Informazioni su Amazon S3](../reference/amazon-s3.md).

<br> 

**In che modo Audience Manager elabora i file in entrata?**

[!DNL Audience Manager] utilizza [!DNL Amazon Simple Queue Service (SQS)] per l'elaborazione dati in entrata. Come funziona:

1. [!DNL Audience Manager] i clienti caricano i dati in entrata in un [!DNL Amazon S3] bucket.

2. I dati entrano nella [!DNL Amazon SQS] coda, in attesa di essere elaborati da [!DNL Audience Manager].

3. [!DNL Audience Manager] legge fino a 119000 voci dalla [!DNL Amazon SQS] coda e le divide in fino a 3 batch. I file in ciascun batch vengono elaborati simultaneamente.

<br> 

**È necessario caricare più file contemporaneamente. I file verranno elaborati contemporaneamente?**

Dipende. [!DNL Audience Manager] legge fino a 119000 voci dalla [!DNL Amazon SQS] coda e le divide in fino a 3 batch. I file verranno elaborati simultaneamente solo se finiscono nello stesso batch. Tuttavia, a causa dell'elevata quantità di dati acquisiti [!DNL Audience Manager] su base giornaliera, non possiamo garantire alcun ordine di elaborazione dei file.

>[!MORE_LIKE_this]
>
>* [Processo di trasferimento dati batch descritto](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

