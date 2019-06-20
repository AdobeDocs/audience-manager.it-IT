---
description: Metodi REST API per gestire gruppi, compresa la creazione, l'aggiornamento, l'elenco, l'eliminazione di gruppi.
seo-description: Metodi REST API per gestire gruppi, compresa la creazione, l'aggiornamento, l'elenco, l'eliminazione di gruppi.
seo-title: Metodi API di gestione dei gruppi
solution: Audience Manager
title: Metodi API di gestione dei gruppi
uuid: fe 042 eb 5-ea 12-42 fe-be 98-d 721 f 987 a 914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Metodi API di gestione dei gruppi {#group-management-api-methods}

Metodi rest [!DNL API] per gestire gruppi, compresa la creazione, l&#39;aggiornamento, l&#39;elenco, l&#39;eliminazione di gruppi.

<!-- c_rest_api_user_man_group.xml -->

## Creare un gruppo {#create-group}

`POST` Un metodo per creare un nuovo gruppo utenti.

<!-- r_rest_api_group_create.xml -->

### Richiesta

`POST /api/v1/groups/`

### Corpo richiesta di esempio

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Risposta

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Aggiornare un gruppo {#update-group}

`PUT` Un metodo per aggiornare un gruppo utenti.

<!--
r_rest_api_group_update.xml
-->

### Richiesta

`PUT /api/v1/groups/`*`<groupId>`*

### Corpo richiesta di esempio

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Risposta

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Gruppi di elenco {#list-groups}

`GET` Metodo per l&#39;elenco dei gruppi di utenti.

<!--
r_rest_api_group_list.xml
-->

### Richiesta

`GET /api/v1/groups/`

### Risposta

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## Eliminare un gruppo {#delete-groups}

`DELETE` Un metodo per eliminare un gruppo di utenti e rimuovere tutti i membri da tale gruppo.

<!-- r_rest_api_group_delete.xml -->

### Richiesta

`DELETE /api/v1/groups/`*`<groupId>`*

Restituisce `204 No Content` in caso di esito positivo. In caso di ritorni `409 Conflict`a capo.

## Elimina gruppi in gruppo {#delete-groups-bulk}

`DELETE` Metodo per eliminare più gruppi in gruppo e rimuovere tutti i membri da tale gruppo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Richiesta

`DELETE /api/v1/groups/bulk-delete`

Restituisce `204 No Content` in caso di esito positivo. In caso di ritorni `409 Conflict`a capo.

## Elenca tutte le autorizzazioni per un gruppo {#list-permissions-group}

`GET` Un metodo per elencare gli oggetti delle autorizzazioni in un gruppo.

<!-- r_rest_api_perm_list_group.xml -->

### Richiesta

`GET /api/v1/groups/{groupId}/permissions`

### Risposta

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

Restituisce `400 Bad Request` se il gruppo è inaccessibile.

## Impostazione delle autorizzazioni per un gruppo {#set-permissions-group}

`PUT` Un metodo per aggiornare le autorizzazioni del gruppo. Questo metodo sovrascrive le precedenti autorizzazioni con le nuove autorizzazioni.

<!-- r_rest_api_perm_set.xml -->

### Richiesta

`PUT /api/v1/groups/{groupId}/permissions/`

### Risposta

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

La risposta di esempio rappresenta l&#39;elenco aggiornato degli oggetti delle autorizzazioni.

Restituisce `200 OK` in caso di esito positivo. Restituisce `400` se una determinata autorizzazione non è valida. Può essere restituito `403` anche se l&#39;oggetto non è accessibile dall&#39;utente connesso.