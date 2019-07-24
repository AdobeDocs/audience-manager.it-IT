---
description: Il processo di assimilazione in tempo reale in tempo reale utilizza una serie di richieste HTTP dal browser di un utente per trasmettere dati ad Audience Manager.
seo-description: Il processo di assimilazione in tempo reale in tempo reale utilizza una serie di richieste HTTP dal browser di un utente per trasmettere dati ad Audience Manager.
seo-title: Inserimento dati in tempo reale
solution: Audience Manager
title: Inserimento dati in tempo reale
uuid: 43 cb 0 ebc -6 c 36-4391-bbfb -6 b 203 d 63 c 69 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

I dati in entrata devono essere formattati come coppie chiave-valore denominate segnali. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>Sostituisce il contenuto in corsivo con i valori effettivi dei parametri.

| Parametro | Descrizione |
|---|---|
| `<KEY>` | Un identificatore univoco in coppia chiave-valore (ad es. genere, colore, prezzo). |
| `<VAL>` | Una variabile che appartiene al set di dati definito dalla chiave (ad es., genere = maschio, colore = verde, prezzo = 100) |

### Sintassi URL

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
