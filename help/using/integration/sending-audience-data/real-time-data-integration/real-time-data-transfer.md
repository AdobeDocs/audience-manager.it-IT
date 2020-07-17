---
description: Il processo di assimilazione dei dati in entrata in tempo reale utilizza una serie di richieste HTTP dal browser di un utente per trasmettere i dati a  Audience Manager.
seo-description: Il processo di assimilazione dei dati in entrata in tempo reale utilizza una serie di richieste HTTP dal browser di un utente per trasmettere i dati a  Audience Manager.
seo-title: Acquisizione di dati in entrata in tempo reale
solution: Audience Manager
title: Acquisizione di dati in entrata in tempo reale
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---


# Acquisizione di dati in entrata in tempo reale {#real-time-inbound-data-ingestion}

Il processo di assimilazione dei dati in entrata in tempo reale utilizza una serie di `HTTP` richieste dal browser di un utente per trasmettere i dati a  Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

I dati in entrata devono essere formattati come coppie chiave-valore denominate segnali. In genere, ogni segnale viene mappato su un segmento creato o gestito tramite l&#39;interfaccia utente o [!DNL API].

## Parametri stringa URL e sintassi {#url-string-syntax}

Le variabili [!DNL URL] per il trasferimento di dati in entrata devono contenere le variabili descritte di seguito. Ricordare di [creare caratteristiche](../../../features/traits/create-onboarded-rule-based-traits.md) e una struttura [di](../../../features/traits/trait-storage.md#create-trait-storage-folder) [!DNL Audience Manager] cartelle nell’interfaccia utente prima di configurare i trasferimenti di dati in tempo reale.

>[!NOTE]
>
>Sostituire il contenuto in corsivo con valori di parametro effettivi.

| Parametro | Descrizione |
|---|---|
| `<KEY>` | Identificatore univoco in una coppia chiave-valore (ad esempio, genere, colore, prezzo). |
| `<VAL>` | Variabile che appartiene al set di dati definito dalla chiave (ad esempio, gender=maschio, color=green, price=100) |

### Sintassi URL

Durante un processo di assimilazione dei dati in entrata in tempo reale, una [!DNL URL] stringa formattata correttamente utilizza la sintassi seguente:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
