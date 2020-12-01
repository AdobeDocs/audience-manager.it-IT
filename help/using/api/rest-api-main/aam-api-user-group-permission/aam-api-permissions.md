---
description: Rest Metodi API per gestire le autorizzazioni per oggetti e gruppi.
seo-description: Rest Metodi API per gestire le autorizzazioni per oggetti e gruppi.
seo-title: Metodi API per la gestione delle autorizzazioni
solution: Audience Manager
title: Metodi API per la gestione delle autorizzazioni
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---


# Metodi API per la gestione delle autorizzazioni {#permissions-management-api-methods}

Utilizzare i metodi [!DNL API] per gestire le autorizzazioni per oggetti e gruppi.

<!-- c_rest_api_perm_man.xml -->

## Elenca i tipi di oggetto disponibili {#list-object-types}

Un metodo `GET` per elencare i tipi di oggetti disponibili per i quali è possibile impostare controlli di accesso basati sui ruoli.

<!-- r_rest_api_perm_list.xml -->

### Richiesta

`GET /api/v1/permissionable-object-types/`

### Risposta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Elenca le autorizzazioni disponibili per un tipo di oggetto {#list-permissions-object-type}

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
>I tipi di oggetto TAGS e DERIVED SIGNALS non dispongono di autorizzazioni regolari da utilizzare. I controlli su questi tipi di oggetto vengono modificati solo dalle Autorizzazioni wild card All o Nothing.