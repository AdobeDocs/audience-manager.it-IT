---
description: Panoramica generale delle modalità in cui  Audience Manager esegue i trasferimenti di dati in tempo reale con un fornitore di contenuti di terze parti.
seo-description: Panoramica generale delle modalità in cui  Audience Manager esegue i trasferimenti di dati in tempo reale con un fornitore di contenuti di terze parti.
seo-title: Descrizione del processo di trasferimento dati in tempo reale
solution: Audience Manager
title: Descrizione del processo di trasferimento dati in tempo reale
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Descrizione del processo di trasferimento dati in tempo reale{#real-time-data-transfer-process-described}

Panoramica generale delle modalità in cui  Audience Manager esegue i trasferimenti di dati in tempo reale con un fornitore di contenuti di terze parti.

<!-- real-time-data-transfer-explained.xml -->

## Trasferimenti di dati in tempo reale

Trasferimenti di dati in tempo reale inviano e ricevono gli ID del segmento come visita dell’utente o azione sul sito. In genere, i trasferimenti di dati sincroni sono utili quando è necessario qualificare o segmentare immediatamente gli utenti, mentre navigano all&#39;interno del proprio inventario.

## Passaggi di integrazione dei dati

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito del cliente che contiene  codice Audience Manager.
1.  Audience Manager carica un iframe ed effettua una chiamata al nostro [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. Il sistema [!DNL DCS] chiama il server di terze parti (in tempo reale) per verificare se il fornitore dispone di informazioni di segmento sull&#39;utente.
1. Il fornitore di contenuti restituisce ad Audience Manager le informazioni sul segmento relative a tale utente.
1.  Audience Manager riceve queste informazioni sul segmento e le rende disponibili per il targeting e la creazione di nuove caratteristiche e segmenti.

![](assets/rt_reduce70.png)