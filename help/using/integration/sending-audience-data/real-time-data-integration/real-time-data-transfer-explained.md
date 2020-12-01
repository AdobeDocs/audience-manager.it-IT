---
description: Panoramica generale delle modalità  Audience Manager di trasferimento dati in tempo reale con un fornitore di contenuti di terze parti.
seo-description: Panoramica generale delle modalità  Audience Manager di trasferimento dati in tempo reale con un fornitore di contenuti di terze parti.
seo-title: Descrizione del processo di trasferimento dati in tempo reale
solution: Audience Manager
title: Descrizione del processo di trasferimento dati in tempo reale
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Processo di trasferimento dati in tempo reale descritto{#real-time-data-transfer-process-described}

Panoramica generale delle modalità  Audience Manager di trasferimento dati in tempo reale con un fornitore di contenuti di terze parti.

<!-- real-time-data-transfer-explained.xml -->

## Trasferimenti di dati in tempo reale

Trasferimenti di dati in tempo reale inviano e ricevono gli ID del segmento come visita dell’utente o azione sul sito. In genere, i trasferimenti di dati sincroni sono utili quando è necessario qualificare o segmentare immediatamente gli utenti, mentre navigano all&#39;interno del proprio inventario.

## Passaggi di integrazione dei dati

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito del cliente che contiene  codice Audience Manager.
1.  Audience Manager carica un iframe ed effettua una chiamata al nostro [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. Il [!DNL DCS] chiama il server di terze parti (in tempo reale) per verificare se il fornitore dispone di informazioni di segmento sull&#39;utente.
1. Il provider di contenuti restituisce le informazioni sul segmento relative a tale utente al Audience Manager .
1.  Audience Manager riceve queste informazioni sul segmento e le rende disponibili per il targeting e la creazione di nuovi tratti e segmenti.

![](assets/rt_reduce70.png)