---
description: Panoramica generale delle prestazioni di uno scambio di dati batch asincrono con un fornitore di terze parti in Audience Manager.
seo-description: Panoramica generale delle prestazioni di uno scambio di dati batch asincrono con un fornitore di terze parti in Audience Manager.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Descrizione del processo di trasferimento dei dati in batch
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Trasferimenti di dati in entrata
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 7%

---

# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

Panoramica generale sulle prestazioni di [!DNL Audience Manager] uno scambio asincrono di dati batch con un fornitore di terze parti.

## Integrazione di dati in batch

<!-- c_async.xml -->

Il processo di integrazione dei dati in batch salva le informazioni dei visitatori sui nostri server e sincronizza tale materiale con i dati inviati da un provider a intervalli regolari. Il processo di trasferimento dati asincrono è utile quando:

* Non sono necessari trasferimenti immediati di dati.
* Raccolta di dati per creare un ampio pool di utenti segmentati.
* Vuoi ridurre le discrepanze di dati e le chiamate `HTTP` dal browser.

![](assets/s2s_70.png)

## Passaggi per l’integrazione dei dati

1. Un utente visita un sito del cliente.
1. [!DNL Audience Manager] e il provider di dati di terze parti assegna al visitatore un ID univoco (in genere con un cookie).
1. [!DNL Audience Manager] chiama il provider di dati di terze parti per far corrispondere gli ID visitatore.
1. Una richiesta pianificata, solitamente a intervalli giornalieri, scambia i dati dei segmenti di visitatori tra [!DNL Audience Manager] e il provider di dati di terze parti.
1. Ogni volta che viene elaborato un file in entrata [!UICONTROL Server-to-Server], una ricevuta viene inviata tramite e-mail alle soluzioni partner e, se configurata, al partner. Per ulteriori informazioni, consulta [Messaggio di esempio ai partner dopo l’elaborazione in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
