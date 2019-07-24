---
description: Metodi REST API per gestire le autorizzazioni per oggetti e gruppi.
seo-description: Metodi REST API per gestire le autorizzazioni per oggetti e gruppi.
seo-title: Metodi API per gestione autorizzazioni
solution: Audience Manager
title: Metodi API per gestione autorizzazioni
uuid: 111 d 0 f 92-d 92 c -4 d 4 b-b 0 d 6-10 dd 3 fa 466 ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Permissions Management API Methods {#permissions-management-api-methods}

Rest [!DNL API] methods to manage permissions for objects and groups.

<!-- c_rest_api_perm_man.xml -->

## List Available Object Types {#list-object-types}

`GET` Un metodo per elencare i tipi di oggetti disponibili sui quali è possibile impostare i controlli di accesso basati sul ruolo.

<!-- r_rest_api_perm_list.xml -->

### Richiesta

`GET /api/v1/permissionable-object-types/`

### Risposta

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## List Available Permissions for an Object Type {#list-permissions-object-type}

`GET` Un metodo per elencare le autorizzazioni disponibili per un tipo di oggetto.

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
>I tipi di oggetto TAGS e DERIVED SIGNAL non dispongono di autorizzazioni regolari. I controlli di questi tipi di oggetto vengono modificati da Tutte o Nessuna autorizzazione Wild card.