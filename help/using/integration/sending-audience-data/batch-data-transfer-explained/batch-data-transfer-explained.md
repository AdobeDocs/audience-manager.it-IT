---
description: Panoramica generale sulle prestazioni di Audience Manager in uno scambio di dati batch asincrono con un fornitore di terze parti.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Batch Data Transfer Process Described
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 5%

---

# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

Panoramica generale di come [!DNL Audience Manager] esegue uno scambio di dati in batch asincrono con un fornitore di terze parti.

## Integrazione dei dati in batch

<!-- c_async.xml -->

Il processo di integrazione dei dati in batch salva le informazioni sui visitatori sui nostri server e sincronizza tale materiale con i dati inviati da un provider a intervalli regolari. Il processo di trasferimento dati asincrono è utile quando:

* Non sono necessari trasferimenti immediati di dati.
* Raccolta di dati per creare un ampio pool di utenti segmentati.
* Desideri ridurre le discrepanze di dati e `HTTP` chiamate dal browser.

![](assets/s2s_70.png)

## Passaggi dell’integrazione dei dati

1. Un utente visita una sede del cliente.
1. [!DNL Audience Manager] e il provider di dati di terze parti assegnano al visitatore un ID univoco (di solito con un cookie).
1. [!DNL Audience Manager] chiama il provider di dati di terze parti per far corrispondere gli ID visitatore.
1. Una richiesta pianificata, in genere a intervalli giornalieri, scambia i dati del segmento del visitatore tra [!DNL Audience Manager] e il provider di dati di terze parti.
1. Ogni volta che un oggetto [!UICONTROL Server-to-Server] file elaborato, viene inviata una conferma via e-mail alle soluzioni partner e, se configurate, al partner. Per ulteriori informazioni, consulta [Messaggio di esempio ai partner dopo l’elaborazione in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
