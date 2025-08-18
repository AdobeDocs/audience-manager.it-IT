---
description: Panoramica per clienti tecnici e non tecnici che desiderano inserire in Audience Manager dati provenienti da altri sistemi (offline).
keywords: in entrata, batch, caricamento batch, dati batch
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Panoramica dell’invio di dati in batch ad Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 3%

---

# Invia dati batch alla panoramica di [!DNL Audience Manager] {#send-batch-data-to-audience-manager-overview}

Panoramica per i clienti tecnici e non tecnici che desiderano inserire in [!DNL Audience Manager] dati provenienti da altri sistemi (offline).

## Vantaggi

È possibile rendere disponibili i dati di altri sistemi in [!DNL Audience Manager]. Il nostro sistema può aiutarti a sbloccare valore e a sfruttare i dati utente che hai raccolto in precedenza. Ciò include informazioni su acquisti, sondaggi sui clienti, dati di registrazione, database [!DNL CRM], ecc. Sebbene ogni integrazione presenti le proprie sfide, condividono tutti questi passaggi comuni. Consulta questo materiale per semplificare il lavoro necessario per portare online i dati offline.

## Passaggio 1: sincronizzare gli ID utente

Durante la sincronizzazione, [!DNL Audience Manager] assegna ID univoci ai client e ai relativi utenti. Questi ID sono noti rispettivamente come [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) e [!UICONTROL Unique User ID] ([!UICONTROL UUID]). [!DNL Audience Manager] utilizza [!UICONTROL DPID] e [!UICONTROL UUID] per identificare gli utenti e qualificarli per [!UICONTROL traits], [!UICONTROL segments], gruppi di pubblico e per il reporting. Inoltre, il nostro codice di raccolta dati ([!UICONTROL DIL]) cerca questi ID per acquisire i dati dei visitatori dal tuo sito Web. Al termine di questo passaggio, [!DNL Audience Manager] e l&#39;archivio offline devono contenere gli ID corrispondenti per ogni record utente.

Considerazioni importanti su questo passaggio:

* **Posizionamento ID client:** [!DNL Audience Manager] deve sapere dove viene visualizzato l&#39;ID client nel sito Web (ad esempio, se è memorizzato in un cookie, in una variabile Analytics, nel codice della pagina e così via).
* **Escludi [!DNL PII]:** gli ID utente non devono contenere informazioni personali ([!DNL PII]).
* **Distinzione maiuscole/minuscole e contenuto:** Durante una sincronizzazione dati in tempo reale, gli ID utente acquisiti dal sito da [!DNL Audience Manager] devono corrispondere agli ID passati dal repository offline. Ad esempio, se i record offline contengono informazioni su [!DNL User123], ma il tuo sito esegue il rendering di tale ID come [!DNL USER123], [!DNL Audience Manager] li vede come visitatori diversi. Di conseguenza, le informazioni online per questo visitatore non possono essere associate ai record corrispondenti nel database offline. Gli ID devono corrispondere esattamente.

Vedi [Sincronizzazione ID per trasferimenti dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Passaggio 2: formato dei file di dati

I nomi dei file e il contenuto seguono linee guida rigorose. *è necessario* denominare e organizzare i file di dati in base a queste specifiche in questa guida. Consulta:

* [Requisiti di nome di Amazon S3 per file di dati in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Contenuti dei file di dati in entrata: sintassi, variabili ed esempi](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## I dati online sono disponibili per attività di marketing offline

Quando si mettono online dati offline, è comunque possibile utilizzare queste informazioni per le campagne offline. A questo scopo, [!DNL Audience Manager] esporta le informazioni sulle caratteristiche e sui segmenti in una posizione [!DNL FTP] o [!DNL Amazon S3] a tua scelta. Contattare il Partner Solutions Manager per ulteriori informazioni o assistenza.

## Ambienti

[!DNL Audience Manager] fornisce i seguenti ambienti per l&#39;eliminazione dei file:

| Ambiente | Servizio | Posizione |
|---------|----------|---------|
| Produzione | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-client</li><li>ftp-in.demdex.com</li></ul> |
| Ambiente Beta | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-client-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## Ulteriori informazioni tecniche

Ingegneri di sistema, sviluppatori o team tecnici/di implementazione devono esaminare [Processo di trasferimento dei dati in batch descritto](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) e gli altri articoli in questa sezione. Questi articoli forniscono dettagli sui protocolli di trasferimento, sul contenuto dei file e sui requisiti dei nomi dei file.
