---
description: Panoramica generale sulle prestazioni di Audience Manager nei trasferimenti di dati in tempo reale con un provider di contenuti di terze parti.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Descrizione del processo di trasferimento dei dati in tempo reale
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%
---

# Descrizione del processo di trasferimento dei dati in tempo reale{#real-time-data-transfer-process-described}

Panoramica generale sulle prestazioni di Audience Manager nei trasferimenti di dati in tempo reale con un provider di contenuti di terze parti.

<!-- real-time-data-transfer-explained.xml -->

## Trasferimenti di dati in tempo reale

I trasferimenti di dati in tempo reale inviano e ricevono ID di segmenti quando un utente visita o interviene sul sito. In genere, i trasferimenti di dati sincroni sono utili quando è necessario qualificare o segmentare immediatamente gli utenti che navigano nel tuo inventario.

## Passaggi dell’integrazione dei dati

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito di un cliente che contiene codice Audience Manager.
1. Audience Manager carica un iframe e effettua una chiamata a [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. [!DNL DCS] chiama il server di terze parti (in tempo reale) per verificare se il fornitore dispone di informazioni sui segmenti dell&#39;utente.
1. Il provider di contenuti restituisce ad Audience Manager le informazioni del segmento relative a tale utente.
1. Audience Manager riceve queste informazioni sui segmenti e le rende disponibili per il targeting e la creazione di nuove caratteristiche e segmenti.

![](assets/rt_reduce70.png)