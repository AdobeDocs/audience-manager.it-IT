---
description: Panoramica per i clienti tecnici e non tecnici che desiderano inserire in Audience Manager i dati provenienti da altri sistemi (offline).
keywords: in entrata, batch, caricamento batch, dati batch
seo-description: Panoramica per i clienti tecnici e non tecnici che desiderano inserire in Audience Manager i dati provenienti da altri sistemi (offline). A questo scopo, utilizza l’opzione di caricamento batch nell’Audience Manager.
seo-title: Panoramica dell’invio di dati in batch ad Audience Manager
solution: Audience Manager
title: Panoramica dell’invio di dati in batch ad Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 8%

---

# Invia dati in batch a [!DNL Audience Manager] Panoramica {#send-batch-data-to-audience-manager-overview}

Panoramica per i clienti tecnici e non tecnici che desiderano inserire dati da altri sistemi (offline) in [!DNL Audience Manager].

## Vantaggi

Puoi rendere disponibili i dati di altri sistemi in [!DNL Audience Manager]. Il nostro sistema può aiutarti a sbloccare il valore e a sfruttare i dati utente raccolti in precedenza. Questo include informazioni su acquisti, indagini sui clienti, dati di registrazione, [!DNL CRM] database, ecc. Sebbene ogni integrazione presenti le proprie sfide, tutti condividono questi passaggi comuni. Rivedi questo materiale per ridurre lo sforzo necessario per portare online i tuoi dati offline.

## Passaggio 1: Sincronizza ID utente

Durante la sincronizzazione, [!DNL Audience Manager] assegna ID univoci ai client e ai loro utenti. Questi ID sono noti rispettivamente come [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) e [!UICONTROL Unique User ID] ([!UICONTROL UUID]). [!DNL Audience Manager] utilizza  [!UICONTROL DPID] e  [!UICONTROL UUID] per identificare gli utenti e qualificarli per  [!UICONTROL traits],  [!UICONTROL segments], gruppi di pubblico e per il reporting. Inoltre, il nostro codice di raccolta dati ([!UICONTROL DIL]) cerca questi ID per acquisire i dati dei visitatori dal tuo sito web. Al termine di questo passaggio, [!DNL Audience Manager] e l’archivio offline devono contenere gli ID corrispondenti per ogni record utente.

Considerazioni importanti su questo passaggio:

* **Posizionamento ID client:** [!DNL Audience Manager]  deve sapere dove viene visualizzato l’ID client sul sito web (ad esempio, se è memorizzato in un cookie, una variabile Analytics, nel codice della pagina, ecc.).
* **Escludi  [!DNL PII]:** gli ID utente non devono contenere informazioni personali identificabili ([!DNL PII]).
* **Sensibilità a maiuscole e minuscole e contenuti:** durante una sincronizzazione dati in tempo reale, gli ID utente acquisiti dal sito da  [!DNL Audience Manager] devono corrispondere agli ID trasmessi dall’archivio offline. Ad esempio, se i record offline contengono informazioni su [!DNL User123], ma il sito esegue il rendering di tale ID come [!DNL USER123], [!DNL Audience Manager] li vede come visitatori diversi. Di conseguenza, le informazioni online per questo visitatore non possono essere associate ai record corrispondenti nel database offline. Gli ID devono corrispondere esattamente.

Consulta [Sincronizzazione ID per trasferimenti di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Passaggio 2: Formato del file di dati

I nomi e i contenuti dei file seguono linee guida rigorose. Devi *assegnare un nome a* e organizzare i file di dati in base a queste specifiche nella presente guida. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inbound Data File Contents: Syntax, Variables, and Examples](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## I dati online sono disponibili per gli sforzi di marketing offline

Quando porti dati offline online, puoi comunque utilizzare queste informazioni per le campagne offline. A questo scopo, [!DNL Audience Manager] esporta le informazioni su caratteristiche e segmenti in una posizione [!DNL FTP] o [!DNL Amazon S3] scelta. Contatta il tuo Partner Solutions Manager per ulteriori informazioni o assistenza.

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

## Lettura tecnica aggiuntiva

Gli ingegneri di sistema, gli sviluppatori o i team tecnici/di implementazione devono consultare [Processo di trasferimento dei dati in batch descritto](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) e gli altri articoli di questa sezione. Questi articoli forniscono dettagli sui protocolli di trasferimento, il contenuto del file e i requisiti del nome del file.
