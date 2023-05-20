---
description: Panoramica generale sulle prestazioni di Audience Manager nei trasferimenti di dati in tempo reale con un provider di contenuti di terze parti.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Descrizione del processo di trasferimento dei dati in tempo reale
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---


# Descrizione del processo di trasferimento dei dati in tempo reale{#real-time-data-transfer-process-described}

Panoramica generale sulle prestazioni di Audience Manager nei trasferimenti di dati in tempo reale con un provider di contenuti di terze parti.

<!-- real-time-data-transfer-explained.xml -->

## Trasferimenti di dati in tempo reale

I trasferimenti di dati in tempo reale inviano e ricevono ID di segmenti quando un utente visita o interviene sul sito. In genere, i trasferimenti di dati sincroni sono utili quando è necessario qualificare o segmentare immediatamente gli utenti che navigano nel tuo inventario.

## Passaggi dell’integrazione dei dati

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito di un cliente che contiene codice di Audience Manager.
1. Audience Manager carica un iframe e effettua una chiamata al nostro [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. Il [!DNL DCS] chiama il server di terze parti (in tempo reale) per verificare se il fornitore dispone di informazioni di segmento sull’utente.
1. Il provider di contenuti restituisce come Audience Manager informazioni sui segmenti relativi a tale utente.
1. Audience Manager riceve le informazioni sul segmento e le rende disponibili per il targeting e la creazione di nuove caratteristiche e segmenti.

![](assets/rt_reduce70.png)