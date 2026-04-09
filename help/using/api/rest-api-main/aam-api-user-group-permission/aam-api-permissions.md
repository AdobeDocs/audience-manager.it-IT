---
description: Metodi API REST per gestire le autorizzazioni per oggetti e gruppi.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: Metodi API per la gestione delle autorizzazioni
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
TQID: https://experienceleague.adobe.com/E9JWh1JKhHOSd7MzeOR8csVXChyh4Q0RiCj3Y5yb2vM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 96
ht-degree: 2%

---

# Metodi API per la gestione delle autorizzazioni {#permissions-management-api-methods}

Rest di [!DNL API] metodi per gestire le autorizzazioni per oggetti e gruppi.

<!-- c_rest_api_perm_man.xml -->

## Elenca tipi di oggetto disponibili {#list-object-types}

Un metodo `GET` per elencare i tipi di oggetto disponibili su cui è possibile impostare i controlli di accesso basati sul ruolo.

<!-- r_rest_api_perm_list.xml -->

### Richiesta

`GET /api/v1/permissionable-object-types/`

### Risposta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Elenco delle autorizzazioni disponibili per un tipo di oggetto {#list-permissions-object-type}

Metodo `GET` per elencare le autorizzazioni disponibili per un tipo di oggetto.

<!-- r_rest_api_perm_list_perms.xml -->

### Richiesta

`GET /api/v1/permissionable-object-types/SEGMENT/`

### Risposta

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>I tipi di oggetto TAGS e DERIVED SIGNALS non dispongono di autorizzazioni regolari da utilizzare. I controlli di questi tipi di oggetto vengono modificati solo dalle autorizzazioni per i caratteri jolly Tutto o Niente.
