---
description: Il processo di acquisizione dei dati in entrata in tempo reale utilizza una serie di richieste HTTP dal browser di un utente per passare i dati ad Audience Manager.
seo-description: Il processo di acquisizione dei dati in entrata in tempo reale utilizza una serie di richieste HTTP dal browser di un utente per passare i dati ad Audience Manager.
seo-title: Acquisizione di dati in entrata in tempo reale
solution: Audience Manager
title: Acquisizione di dati in entrata in tempo reale
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 7%

---

# Acquisizione di dati in entrata in tempo reale {#real-time-inbound-data-ingestion}

Il processo di acquisizione dei dati in entrata in tempo reale utilizza una serie di richieste `HTTP` provenienti dal browser di un utente per passare i dati ad Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

I dati in entrata devono essere formattati come coppie chiave-valore denominate segnali. In genere, ogni segnale viene mappato su un segmento creato o gestito tramite l&#39;interfaccia utente o [!DNL API].

## Parametri stringa URL e sintassi {#url-string-syntax}

La sezione [!DNL URL] per un trasferimento di dati in entrata deve contenere le variabili descritte di seguito. Ricorda di [creare caratteristiche](../../../features/traits/create-onboarded-rule-based-traits.md) e una [struttura di cartelle](../../../features/traits/trait-storage.md#create-trait-storage-folder) nell&#39;interfaccia utente [!DNL Audience Manager] prima di configurare trasferimenti di dati in tempo reale.

>[!NOTE]
>
>Sostituisci il contenuto in corsivo con i valori effettivi dei parametri.

| Parametro | Descrizione |
|---|---|
| `<KEY>` | Identificatore univoco in una coppia chiave-valore (ad esempio genere, colore, prezzo). |
| `<VAL>` | Variabile che appartiene al set di dati definito dalla chiave (ad esempio, gender=male, color=verde, price=100) |

### Sintassi URL

Durante un processo di acquisizione dei dati in entrata in tempo reale, una stringa [!DNL URL] formattata correttamente utilizza la sintassi seguente:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
