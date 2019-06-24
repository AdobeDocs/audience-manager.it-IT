---
description: Panoramica dei clienti tecnici e non tecnici che desiderano trasferire dati da altri sistemi (offline) in Audience Manager.
keywords: in ingresso
seo-description: Panoramica dei clienti tecnici e non tecnici che desiderano trasferire dati da altri sistemi (offline) in Audience Manager.
seo-title: Invia dati batch alla panoramica di Audience Manager
solution: Audience Manager
title: Invia dati batch alla panoramica di Audience Manager
uuid: 472583 b 1-5057-4 add -8 e 3 c -5 e 50762 c 88 e 0
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Send Batch Data to Audience Manager Overview{#send-batch-data-to-audience-manager-overview}

Panoramica dei clienti tecnici e non tecnici che desiderano trasferire dati da altri sistemi (offline) in Audience Manager.

## Vantaggi

<!-- c_offline_to_online.xml -->

Puoi rendere disponibili i dati di altri sistemi in Audience Manager. Il nostro sistema può aiutarti a sbloccare i valori e sfruttare i dati degli utenti raccolti in precedenza. This includes information about purchases, customer surveys, registration data, [!DNL CRM] databases, etc. Anche se ogni integrazione presenta le proprie problematiche, condividono tutti questi passaggi comuni. Rivedete questo materiale per ridurre il sforzo necessario per rendere online i dati offline.

## Passaggio 1: Sincronizzazione degli ID utente

Durante la sincronizzazione, Audience Manager assegna ID univoci ai client e ai relativi utenti. These IDs are known as the [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) and [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectively. Audience Manager uses the [!UICONTROL DPID] and [!UICONTROL UUID] to identify users and qualify them for traits, segments, audience groups, and for reporting. Additionally, our data collection code ([!UICONTROL DIL]) looks for these IDs to capture visitor data from your website. Quando questo passaggio è completo, Audience Manager e l&#39;archivio offline devono contenere ID corrispondenti per ogni record utente.

Considerazioni importanti su questo passaggio:

* **Posizione ID client:** Audience Manager deve sapere dove si trova l&#39;ID cliente sul tuo sito Web (ad es., archiviato in un cookie, una variabile Analytics, nel codice della pagina, ecc.).
* **Escludi:[!DNL PII]Gli ID utente non devono contenere informazioni personali identificabili (**).[!DNL PII]
* **Distinzione tra maiuscole e minuscole:** Durante una sincronizzazione dati in tempo reale, gli ID utente acquisiti dal sito da Audience Manager devono corrispondere agli ID passati dall&#39;archivio offline. For example, if offline records hold information about [!DNL User123], but your site renders that ID as [!DNL USER123], Audience Manager sees these as different visitors. Di conseguenza, le informazioni online per questo visitatore non possono essere associate ai record corrispondenti nel database offline. Gli ID devono corrispondere esattamente.

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

## Passaggio 2: Formato file dati

I nomi e i contenuti dei file seguono linee guida rigorose. You *must* name and organize data files according to these specifications in this guide. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenuto del file di dati in ingresso: Sintassi, Variabili ed Esempi](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Dati online disponibili per iniziative di marketing offline

Quando trasferite online dati offline, potete comunque utilizzare queste informazioni per campagne offline. To do this, Audience Manager exports trait and segment information to an [!DNL FTP] or [!DNL Amazon S3] location of your choice. Contatta il tuo responsabile Soluzioni Partner per ulteriori informazioni o assistenza.

## Ambienti

Audience Manager offre i seguenti ambienti per il rilascio dei file:

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
   <td colname="col2"> <p> <code> demdex-s 2 s-client-sandbox-us-east -1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ulteriore lettura tecnica

Systems engineers, developers, or technical/implementation teams should review [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process) and the other articles in this section. Questi articoli forniscono dettagli sui protocolli di trasferimento, sui contenuti dei file e sui requisiti del nome file.