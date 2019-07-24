---
description: Panoramica generale su come Audience Manager esegue trasferimenti di dati in tempo reale con un fornitore di contenuti terze parti.
seo-description: Panoramica generale su come Audience Manager esegue trasferimenti di dati in tempo reale con un fornitore di contenuti terze parti.
seo-title: Processo di trasferimento dati in tempo reale Descrizione
solution: Audience Manager
title: Processo di trasferimento dati in tempo reale Descrizione
uuid: b 68781 b 3-0 b 7 a -442 d -8 e 34-2 db 2474849 a 4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

Panoramica generale su come Audience Manager esegue trasferimenti di dati in tempo reale con un fornitore di contenuti terze parti.

<!-- real-time-data-transfer-explained.xml -->

## Trasferimenti di dati in tempo reale

I trasferimenti di dati in tempo reale inviano e ricevono ID segmento quando un utente visita o utilizza il tuo sito. In genere, i trasferimenti di dati sincroni sono utili per qualificare o segmentare gli utenti immediatamente, man mano che navigano nell'inventario.

## Passaggi per l'integrazione dei dati

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito di un cliente che contiene il codice Audience Manager.
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. Il fornitore di contenuti restituisce informazioni sui segmenti su quell'utente ad Audience Manager.
1. Audience Manager riceve queste informazioni sul segmento e lo rende disponibile per il targeting e la creazione di nuove caratteristiche e segmenti.

![](assets/rt_reduce70.png)