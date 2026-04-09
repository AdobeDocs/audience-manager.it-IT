---
description: Questo documento descrive i tipi di ID di Audience Manager che puoi utilizzare nelle richieste relative alla privacy dei dati.
seo-description: This document covers the types of Audience Manager IDs that you can use in data privacy requests.
seo-title: Audience Manager Identifiers (IDs)
solution: Audience Manager
keywords: Interfaccia utente RGPD, API RGPD, CCPA, privacy, AAM ID
title: Identificatori di Audience Manager (ID)
feature: Data Governance & Privacy
exl-id: 5f18ed0a-c875-4596-a4d1-f9a7fe871d1b
TQID: https://experienceleague.adobe.com/YZn8tjI28VWvXTsV-VF8IJoj9Pr7YI2ZgbA7ynvyPuo
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 96%

---

# Identificatori di Audience Manager (ID) {#aam-ids}

Quando invii ad Adobe Audience Manager le [richieste relative alla privacy dei dati](data-privacy-requests.md), devi includere uno degli identificatori (ID) elencati di seguito. Puoi trovare ulteriori informazioni sui formati ID nel nostro [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

## ID utente univoco di Adobe Audience Manager

* **ID utente**: `aam_uuid`
* **Definizione**: ID utente univoco di Adobe Audience Manager
* **ID dello spazio dei nomi**: 0

**Esempio JSON**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>Puoi inoltre possibile utilizzare lo spazio dei nomi [!DNL CORE].

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **ID utente**: `mid`
* **Definizione**: [!DNL Adobe Experience Cloud ID], precedentemente noto come [!DNL Visitor ID] o [!DNL Marketing Cloud ID]
* **ID dello spazio dei nomi**: 4

>[!NOTE]
>
>Puoi inoltre possibile utilizzare lo spazio dei nomi [!DNL ECID]. Vedi il secondo esempio [!DNL JSON].

**Esempio JSON**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## ID cliente

**ID utente**: `cid`

**Definizione**: ID cliente, ad esempio un cookie impostato per i visitatori anonimi del sito o un ID [!DNL CRM] proveniente da un sistema offline o un nome utente con hash.

**ID dello spazio dei nomi**: specifico per il cliente. Puoi trovarlo nella tua istanza Audience Manager.

**Esempio JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## ID mobile advertising

**ID utente**: `d_cid`

**Definizione**: ID mobile advertising.

**ID dello spazio dei nomi**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Per ulteriori informazioni, consulta [Global Data Sources](../../features/global-data-sources.md).

>[!IMPORTANT]
>
> Se utilizzi l’[!DNL SDK] Mobile, devi anche inviare l’Experience Cloud ID (`MID`) insieme agli ID mobile advertising per ricevere risposte complete su accesso ed eliminazione.

**Esempio JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## Codice di integrazione

**ID utente**: `d_cid_ic`

**Definizione**: un codice di integrazione per la sorgente di dati. Questo può essere utilizzato al posto dell’ID sorgente dei dati/ID dello spazio dei nomi nella richiesta [!DNL API] ad [!DNL Adobe Experience Cloud Privacy Core Service].

**ID dello spazio dei nomi**: non applicabile

**Esempio JSON**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
