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


# Inserimento dati in tempo reale {#real-time-inbound-data-ingestion}

Il processo di assimilazione in tempo reale in tempo reale utilizza una serie di `HTTP` richieste dal browser di un utente per trasmettere dati ad Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

I dati in entrata devono essere formattati come coppie chiave-valore denominate segnali. In genere, ogni segnale viene mappato su un segmento creato o gestito tramite l&#39;interfaccia utente o [!DNL API].

## Parametri stringa URL e sintassi {#url-string-syntax}

Il [!DNL URL] trasferimento di dati in entrata deve contenere le variabili descritte di seguito. Ricorda di [creare caratteristiche](../../../features/traits/create-onboarded-rule-based-traits.md) e una struttura [di cartelle](../../../features/traits/trait-storage.md#create-trait-storage-folder) nell&#39; [!DNL Audience Manager] interfaccia utente prima di impostare trasferimenti di dati in tempo reale.

>[!NOTE]
>
>Sostituisce il contenuto in corsivo con i valori effettivi dei parametri.

| Parametro | Descrizione |
|---|---|
| `<KEY>` | Un identificatore univoco in coppia chiave-valore (ad es. genere, colore, prezzo). |
| `<VAL>` | Una variabile che appartiene al set di dati definito dalla chiave (ad es., genere = maschio, colore = verde, prezzo = 100) |

### Sintassi URL

Durante un processo di assimilazione in tempo reale in tempo reale, una stringa formattata [!DNL URL] correttamente utilizza la sintassi seguente:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
