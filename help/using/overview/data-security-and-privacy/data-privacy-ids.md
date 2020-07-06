---
description: Questo documento descrive i tipi di ID di Audience Manager che puoi utilizzare nelle richieste relative alla privacy dei dati.
seo-description: Questo documento descrive i tipi di ID di Audience Manager che puoi utilizzare nelle richieste relative alla privacy dei dati.
seo-title: Identificatori di Audience Manager (ID)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Identificatori di Audience Manager (ID)
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
