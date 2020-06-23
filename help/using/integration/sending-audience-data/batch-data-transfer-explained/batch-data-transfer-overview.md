---
description: Panoramica per i clienti tecnici e non tecnici che desiderano portare i dati di altri sistemi (offline) in  Audience Manager.
keywords: inbound, batch, batch upload, batch data
seo-description: Panoramica per i clienti tecnici e non tecnici che desiderano portare i dati di altri sistemi (offline) in  Audience Manager. A questo scopo, usate l’opzione di caricamento batch in  Audience Manager.
seo-title: Invia dati batch a  Panoramica Audience Manager
solution: Audience Manager
title: Invia dati batch a  Panoramica Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 3%

---


# Invia dati batch a [!DNL Audience Manager] panoramica {#send-batch-data-to-audience-manager-overview}

Una panoramica per i clienti tecnici e non tecnici che desiderano trasferire dati da altri sistemi (offline) in [!DNL Audience Manager].

## Vantaggi

È possibile rendere disponibili i dati provenienti da altri sistemi in [!DNL Audience Manager]. Il nostro sistema può aiutarti a sbloccare i valori e a sfruttare i dati utente raccolti in precedenza. Questo include informazioni su acquisti, sondaggi sui clienti, dati di registrazione, [!DNL CRM] database ecc. Sebbene ogni integrazione presenti le proprie sfide, tutti condividono questi passi comuni. Rivedete questo materiale per ridurre gli sforzi necessari per portare online i dati offline.

## Passaggio 1: Sincronizza ID utente

Durante la sincronizzazione, [!DNL Audience Manager] assegna ID univoci ai client e ai loro utenti. Tali ID sono noti rispettivamente come [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) e [!UICONTROL Unique User ID] ([!UICONTROL UUID]). [!DNL Audience Manager] utilizza il [!UICONTROL DPID] e [!UICONTROL UUID] per identificare gli utenti e qualificarli per [!UICONTROL traits], [!UICONTROL segments]i gruppi di pubblico e per il reporting. Inoltre, il nostro codice di raccolta dati ([!UICONTROL DIL]) cerca questi ID per acquisire i dati dei visitatori dal tuo sito Web. Una volta completato questo passaggio, [!DNL Audience Manager] l&#39;archivio offline deve contenere gli ID corrispondenti per ciascun record utente.

Considerazioni importanti su questo passaggio:

* **Posizione ID client:** [!DNL Audience Manager] deve sapere dove viene visualizzato l’ID client sul sito Web (ad es. se è memorizzato in un cookie, una variabile Analytics , nel codice della pagina e così via).
* **Escludi[!DNL PII]:** Gli ID utente non devono contenere informazioni personali ([!DNL PII]).
* **Sensibilità di maiuscole e minuscole:** Durante una sincronizzazione dei dati in tempo reale, gli ID utente acquisiti dal sito [!DNL Audience Manager] devono corrispondere agli ID trasmessi dal repository offline. Ad esempio, se i record offline contengono informazioni su [!DNL User123], ma il sito esegue il rendering dell&#39;ID come [!DNL USER123], [!DNL Audience Manager] li vede come visitatori diversi. Di conseguenza, le informazioni online per questo visitatore non possono essere associate ai record corrispondenti nel database offline. Gli ID devono corrispondere esattamente.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Passaggio 2: Formato file dati

I nomi e il contenuto dei file seguono linee guida rigorose. In questa guida *è necessario* assegnare un nome e organizzare i file di dati in base alle seguenti specifiche. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenuto file dati in entrata: Sintassi, variabili ed esempi](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## I dati online sono disponibili per gli sforzi di marketing offline

Quando portate online i dati offline, potete comunque utilizzare tali informazioni per le campagne offline. A tal fine, [!DNL Audience Manager] esporta le informazioni sulle caratteristiche e sui segmenti in una posizione [!DNL FTP] o [!DNL Amazon S3] nella posizione desiderata. Contatta il tuo Partner Solutions Manager per ulteriori informazioni o assistenza.

## Ambienti

[!DNL Audience Manager] fornisce i seguenti ambienti per il rilascio dei file:

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
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ulteriore lettura tecnica

Gli ingegneri di sistemi, gli sviluppatori o i team tecnici/di implementazione devono consultare il processo di trasferimento dei dati [batch descritto](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) e gli altri articoli di questa sezione. Questi articoli forniscono dettagli sui protocolli di trasferimento, il contenuto del file e i requisiti relativi al nome del file.
