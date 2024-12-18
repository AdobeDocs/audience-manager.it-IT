---
description: Il processo di acquisizione dei dati in entrata in tempo reale utilizza una serie di richieste HTTP provenienti dal browser di un utente per la trasmissione dei dati ad Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Acquisizione di dati in entrata in tempo reale
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 1%

---

# Acquisizione di dati in entrata in tempo reale {#real-time-inbound-data-ingestion}

Il processo di acquisizione dei dati in entrata in tempo reale utilizza una serie di `HTTP` richieste provenienti dal browser di un utente per la trasmissione dei dati ad Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

I dati in entrata devono essere formattati come coppie chiave-valore chiamate segnali. In genere, ogni segnale è mappato a un segmento creato o gestito tramite l&#39;interfaccia utente o [!DNL API].

## Parametri e sintassi della stringa URL {#url-string-syntax}

[!DNL URL] per un trasferimento di dati in entrata deve contenere le variabili descritte di seguito. Ricordati di [creare caratteristiche](../../../features/traits/create-onboarded-rule-based-traits.md) e una [struttura di cartelle](../../../features/traits/trait-storage.md#create-trait-storage-folder) nell&#39;interfaccia utente [!DNL Audience Manager] prima di impostare trasferimenti di dati in tempo reale.

>[!NOTE]
>
>Sostituisci il contenuto in corsivo con i valori effettivi dei parametri.

| Parametro | Descrizione |
|---|---|
| `<KEY>` | Un identificatore univoco in una coppia chiave-valore (ad esempio, genere, colore, prezzo). |
| `<VAL>` | Una variabile che appartiene al set di dati definito dalla chiave (ad esempio, genere=maschile, colore=verde, prezzo=100) |

### Sintassi URL

Durante un processo di acquisizione di dati in entrata in tempo reale, una stringa [!DNL URL] formattata correttamente utilizza la sintassi seguente:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
