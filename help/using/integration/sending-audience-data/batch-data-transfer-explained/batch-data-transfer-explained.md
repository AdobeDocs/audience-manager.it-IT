---
description: Panoramica generale delle modalità in cui  Audience Manager esegue uno scambio di dati batch asincrono con un fornitore di terze parti.
seo-description: Panoramica generale delle modalità in cui  Audience Manager esegue uno scambio di dati batch asincrono con un fornitore di terze parti.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Processo di trasferimento dati batch descritto
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

Panoramica generale delle modalità in cui [!DNL Audience Manager] esegue uno scambio di dati batch asincrono con un fornitore di terze parti.

## Integrazione dei dati batch

<!-- c_async.xml -->

Il processo di integrazione dei dati batch salva le informazioni dei visitatori sui nostri server e sincronizza il materiale con i dati inviati da un fornitore a intervalli regolari. Il processo di trasferimento dati asincrono è utile quando:

* Non sono necessari trasferimenti di dati immediati.
* Raccolta di dati per creare un ampio pool di utenti segmentati.
* Ridurre le discrepanze di dati e le chiamate `HTTP` dal browser.

![](assets/s2s_70.png)

## Passaggi di integrazione dei dati

1. Un utente visita un sito cliente.
1. [!DNL Audience Manager] e il fornitore di dati di terze parti assegna al visitatore un ID univoco (in genere con un cookie).
1. [!DNL Audience Manager] chiama il provider di dati di terze parti per far corrispondere gli ID visitatore.
1. Una richiesta pianificata, in genere a intervalli giornalieri, scambia i dati del segmento dei visitatori tra [!DNL Audience Manager] e il provider di dati di terze parti.
1. Ogni volta che viene elaborato un file in entrata [!UICONTROL Server-to-Server], una ricevuta viene inviata via e-mail alle soluzioni partner e, se configurato, al partner. Per ulteriori informazioni, vedere [Messaggio di esempio ai partner dopo l&#39;elaborazione in ingresso](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
