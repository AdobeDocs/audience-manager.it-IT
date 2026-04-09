---
description: Panoramica generale delle prestazioni di Audience Manager per lo scambio asincrono di dati in batch con fornitori terzi.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Descrizione del processo di trasferimento di dati in batch
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
TQID: https://experienceleague.adobe.com/HXA9Ql-ulLQ8itnnGnwMuk82nFRZnrFYaOGniGNDgn8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 0%

---

# Descrizione del processo di trasferimento di dati in batch {#batch-data-transfer-process-described}

Panoramica generale sul modo in cui [!DNL Audience Manager] esegue uno scambio di dati batch asincrono con un fornitore di terze parti.

## Integrazione dei dati in batch

<!-- c_async.xml -->

Il processo di integrazione dei dati in batch salva le informazioni sui visitatori sui nostri server e sincronizza tale materiale con i dati inviati da un provider a intervalli regolari. Il processo di trasferimento dati asincrono è utile quando:

* Non sono necessari trasferimenti immediati di dati.
* Raccolta di dati per creare un ampio pool di utenti segmentati.
* Vuoi ridurre le discrepanze di dati e `HTTP` chiamate dal browser.

![](assets/s2s_70.png)

## Passaggi dell’integrazione dei dati

1. Un utente visita una sede del cliente.
1. [!DNL Audience Manager] e il provider di dati di terze parti assegnano al visitatore un ID univoco (in genere con un cookie).
1. [!DNL Audience Manager] chiama il provider di dati di terze parti per far corrispondere gli ID visitatore.
1. Una richiesta pianificata, in genere su base giornaliera, scambia i dati del segmento visitatore tra [!DNL Audience Manager] e il provider di dati di terze parti.
1. Ogni volta che viene elaborato un file [!UICONTROL Server-to-Server] in entrata, viene inviata una conferma tramite e-mail alle soluzioni partner e, se configurate, al partner. Per ulteriori informazioni, vedere [Messaggio di esempio ai partner dopo l&#39;elaborazione in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
