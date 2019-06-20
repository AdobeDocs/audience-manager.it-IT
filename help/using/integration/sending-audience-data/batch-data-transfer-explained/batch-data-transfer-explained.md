---
description: Panoramica generale su come Audience Manager esegue lo scambio di dati in batch asincroni con un fornitore di terze parti.
seo-description: Panoramica generale su come Audience Manager esegue lo scambio di dati in batch asincroni con un fornitore di terze parti.
seo-title: Processo di trasferimento dati batch descritta
solution: Audience Manager
title: Processo di trasferimento dati batch descritta
uuid: a 9 eee 940-151 c -44 f 8-9 fe 9-8 ab 47 d 8 fa 45 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Processo di trasferimento dati batch descritta {#batch-data-transfer-process-described}

Panoramica generale su come Audience Manager esegue lo scambio di dati in batch asincroni con un fornitore di terze parti.

## Integrazione dei dati in batch

<!-- c_async.xml -->

Il processo di integrazione dei dati batch salva le informazioni sui visitatori sui nostri server e li sincronizza con i dati inviati da un fornitore a intervalli regolari. Il processo di trasferimento dati asincrono è utile quando:

* I trasferimenti di dati immediati non sono obbligatori.
* Raccogliere dati per creare un pool elevato di utenti segmentati.
* Vuoi ridurre le discrepanze dei dati e `HTTP` le chiamate dal browser.

![](assets/s2s_70.png)

## Passaggi per l&#39;integrazione dei dati

1. Un utente visita un sito cliente.
1. Audience Manager e il provider di dati di terze parti assegnano al visitatore un ID univoco (in genere con un cookie).
1. Audience Manager chiama il provider di dati di terze parti per far corrispondere gli ID visitatore.
1. Una richiesta pianificata, solitamente su un intervallo giornaliero, scambia i dati dei segmenti dei visitatori tra Audience Manager e il fornitore di dati di terze parti.
1. Ogni volta che un [!UICONTROL Server-to-Server] file in entrata viene elaborato, una ricevuta viene inviata via e-mail alle soluzioni partner e, se configurato, al partner. Per ulteriori informazioni, vedi [Messaggio di esempio ai partner dopo l&#39;elaborazione in entrata](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).