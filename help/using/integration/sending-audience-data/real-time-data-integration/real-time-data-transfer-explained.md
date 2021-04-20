---
description: Panoramica generale delle prestazioni dei trasferimenti di dati in tempo reale da parte di Audience Manager con un provider di contenuti di terze parti.
seo-description: Panoramica generale delle prestazioni dei trasferimenti di dati in tempo reale da parte di Audience Manager con un provider di contenuti di terze parti.
seo-title: Descrizione del processo di trasferimento dei dati in tempo reale
solution: Audience Manager
title: Descrizione del processo di trasferimento dei dati in tempo reale
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---


# Descrizione del processo di trasferimento dati in tempo reale{#real-time-data-transfer-process-described}

Panoramica generale delle prestazioni dei trasferimenti di dati in tempo reale da parte di Audience Manager con un provider di contenuti di terze parti.

<!-- real-time-data-transfer-explained.xml -->

## Trasferimenti di dati in tempo reale

I trasferimenti di dati in tempo reale inviano e ricevono gli ID del segmento quando un utente visita o agisce sul tuo sito. In genere, i trasferimenti di dati sincroni sono utili quando devi qualificare o segmentare immediatamente gli utenti mentre navigano nel tuo inventario.

## Passaggi per l’integrazione dei dati

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito di un cliente che contiene codice Audience Manager.
1. Audience Manager carica un iframe ed effettua una chiamata al nostro [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. Il [!DNL DCS] chiama il server di terze parti (in tempo reale) per verificare se il fornitore dispone di informazioni di segmento sull&#39;utente.
1. Il provider di contenuti restituisce ad Audience Manager le informazioni sui segmenti relative a tale utente.
1. Audience Manager riceve queste informazioni sui segmenti e le rende disponibili per il targeting e la creazione di nuove caratteristiche e segmenti.

![](assets/rt_reduce70.png)