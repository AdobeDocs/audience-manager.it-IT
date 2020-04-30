---
description: Questo documento descrive i tipi di ID Audience Manager che potete utilizzare nelle richieste di privacy dei dati.
seo-description: Questo documento descrive i tipi di ID Audience Manager che potete utilizzare nelle richieste di privacy dei dati.
seo-title: ID (Audience Manager Identifiers)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: ID (Audience Manager Identifiers)
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# ID (Audience Manager Identifiers) {#aam-ids}

Quando invii ad Adobe Audience Manager le richieste [di privacy dei](data-privacy-requests.md) dati, devi includere uno degli identificatori (ID) elencati di seguito. Puoi trovare ulteriori informazioni sui formati ID nel nostro [indice degli ID](../../reference/ids-in-aam.md)di Audience Manager.

## ID utente univoco di Adobe Audience Manager

* **ID utente**: `aam_uuid`
* **Definizione**: ID utente univoco di Adobe Audience Manager
* **ID** spazio nomi: 0

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
>È inoltre possibile utilizzare lo [!DNL CORE] spazio nomi.

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
* **ID** spazio nomi: 4

>[!NOTE]
>
>È inoltre possibile utilizzare lo [!DNL ECID] spazio nomi. Vedere il secondo [!DNL JSON] esempio.

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

**Definizione**: ID cliente, ad esempio un cookie impostato per i visitatori anonimi del sito o un [!DNL CRM] ID da un sistema offline o un nome utente con hash.

**ID** spazio nomi: Specifico per il cliente. Trovalo dalla tua istanza Audience Manager.

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

## ID pubblicità mobile

**ID utente**: `d_cid`

**Definizione**: ID pubblicitari per dispositivi mobili.

**ID dello spazio dei nomi**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Per ulteriori informazioni, consulta [Origini](../../features/global-data-sources.md) dati globali.

>[!IMPORTANT]
>
> Se utilizzi Mobile [!DNL SDK], devi anche inviare l’Experience Cloud ID (`MID`) insieme agli ID pubblicitari per dispositivi mobili per ricevere risposte complete su Accesso ed Elimina.

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

## Codice integrazione

**ID utente**: `d_cid_ic`

**Definizione**: Un codice di integrazione per l&#39;origine dati. Questo può essere utilizzato al posto dell&#39;ID origine dati/ID spazio nomi nella [!DNL API] richiesta di [!DNL Adobe Experience Cloud Privacy Core Service].

**ID** spazio nomi: Non applicabile

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
