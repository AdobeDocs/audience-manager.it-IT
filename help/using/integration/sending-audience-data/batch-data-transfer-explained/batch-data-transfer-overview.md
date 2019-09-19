---
description: Panoramica per i clienti tecnici e non tecnici che desiderano portare dati da altri sistemi (offline) in Audience Manager.
keywords: in entrata, batch, caricamento batch, dati batch
seo-description: Panoramica per i clienti tecnici e non tecnici che desiderano portare dati da altri sistemi (offline) in Audience Manager. A tal fine, utilizzate l'opzione di caricamento batch in Audience Manager.
seo-title: Invia dati batch ad Audience Manager Panoramica
solution: Audience Manager
title: Invia dati batch ad Audience Manager Panoramica
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# Invia dati batch ad Audience Manager Panoramica{#send-batch-data-to-audience-manager-overview}

Panoramica per i clienti tecnici e non tecnici che desiderano portare dati da altri sistemi (offline) in Audience Manager.

## Vantaggi

<!-- c_offline_to_online.xml -->

Puoi rendere disponibili i dati di altri sistemi in Audience Manager. Il nostro sistema può aiutarti a sbloccare i valori e a sfruttare i dati utente raccolti in precedenza. Questo include informazioni su acquisti, sondaggi sui clienti, dati di registrazione, [!DNL CRM] database ecc. Sebbene ogni integrazione presenti le proprie sfide, tutti condividono questi passi comuni. Rivedete questo materiale per ridurre gli sforzi necessari per portare online i dati offline.

## Passaggio 1: Sincronizza ID utente

Durante la sincronizzazione, Audience Manager assegna ID univoci ai client e ai loro utenti. Tali ID sono noti rispettivamente come [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) e [!UICONTROL Unique User ID] ([!UICONTROL UUID]). Audience Manager utilizza l' [!UICONTROL DPID] e [!UICONTROL UUID] per identificare gli utenti e qualificarli per caratteristiche, segmenti, gruppi di pubblico e per la creazione di report. Inoltre, il nostro codice di raccolta dati ([!UICONTROL DIL]) cerca questi ID per acquisire i dati dei visitatori dal tuo sito Web. Al termine di questo passaggio, Audience Manager e il repository offline devono contenere gli ID corrispondenti per ciascun record utente.

Considerazioni importanti su questo passaggio:

* **** Posizione ID client: Audience Manager deve sapere dove viene visualizzato l’ID cliente sul sito Web (ad esempio, se è memorizzato in un cookie, una variabile di Analytics, nel codice della pagina, ecc.).
* **[!DNL PII]Escludi**: Gli ID utente non devono contenere informazioni personali ([!DNL PII]).
* **** Sensibilità di maiuscole e minuscole: Durante una sincronizzazione dei dati in tempo reale, gli ID utente acquisiti dal sito da Audience Manager devono corrispondere agli ID trasmessi dal repository offline. Ad esempio, se i record offline contengono informazioni su [!DNL User123]ma il sito esegue il rendering dell'ID come [!DNL USER123], Audience Manager li vede come visitatori diversi. Di conseguenza, le informazioni online per questo visitatore non possono essere associate ai record corrispondenti nel database offline. Gli ID devono corrispondere esattamente.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## Passaggio 2:Formato file dati

I nomi e il contenuto dei file seguono linee guida rigorose. In questa guida *è necessario* assegnare un nome e organizzare i file di dati in base alle seguenti specifiche. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenuto file dati in entrata: Sintassi, variabili ed esempi](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## I dati online sono disponibili per gli sforzi di marketing offline

Quando portate online i dati offline, potete comunque utilizzare tali informazioni per le campagne offline. A tal fine, Audience Manager esporta le informazioni sulle caratteristiche e sui segmenti in una [!DNL FTP] posizione o [!DNL Amazon S3] posizione desiderata. Contatta il tuo Partner Solutions Manager per ulteriori informazioni o assistenza.

## Ambienti

Audience Manager fornisce i seguenti ambienti per il rilascio dei file:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ambiente </th> 
   <th colname="col02" class="entry"> Servizio </th> 
   <th colname="col2" class="entry"> Posizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Produzione</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Ambiente beta</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-client-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ulteriore lettura tecnica

Gli ingegneri di sistemi, gli sviluppatori o i team tecnici/di implementazione devono consultare il processo di trasferimento dei dati [batch descritto](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) e gli altri articoli di questa sezione. Questi articoli forniscono dettagli sui protocolli di trasferimento, il contenuto del file e i requisiti relativi al nome del file.