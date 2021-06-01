---
description: Metodi API per la gestione delle autorizzazioni per oggetti e gruppi.
seo-description: Metodi API per la gestione delle autorizzazioni per oggetti e gruppi.
seo-title: Metodi API per la gestione delle autorizzazioni
solution: Audience Manager
title: Metodi API per la gestione delle autorizzazioni
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 15%

---

# Metodi API per la gestione delle autorizzazioni {#permissions-management-api-methods}

Metodi [!DNL API] per gestire le autorizzazioni per oggetti e gruppi.

<!-- c_rest_api_perm_man.xml -->

## Elenco tipi di oggetti disponibili {#list-object-types}

Un metodo `GET` per elencare i tipi di oggetti disponibili per i quali è possibile impostare controlli di accesso basati su ruoli.

<!-- r_rest_api_perm_list.xml -->

### Richiesta

`GET /api/v1/permissionable-object-types/`

### Risposta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Elencare le autorizzazioni disponibili per un tipo di oggetto {#list-permissions-object-type}

Un metodo `GET` per elencare le autorizzazioni disponibili per un tipo di oggetto.

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
>I tipi di oggetto TAG e SEGNALI DERIVATI non dispongono di autorizzazioni regolari da utilizzare. I controlli su questi tipi di oggetti vengono modificati solo dalle autorizzazioni con caratteri jolly All o Nothing .
