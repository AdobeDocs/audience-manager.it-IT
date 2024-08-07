---
description: Metodi API REST per la gestione dei gruppi, tra cui creazione, aggiornamento, elenco ed eliminazione dei gruppi.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: Metodi API per la gestione dei gruppi
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 3%

---

# Metodi API per la gestione dei gruppi {#group-management-api-methods}

Metodi [!DNL API] rimanenti per la gestione dei gruppi, inclusi creazione, aggiornamento, elenco ed eliminazione dei gruppi.

<!-- c_rest_api_user_man_group.xml -->

## Creare un gruppo {#create-group}

Un metodo `POST` per creare un nuovo gruppo di utenti.

<!-- r_rest_api_group_create.xml -->

### Richiesta

`POST /api/v1/groups/`

### Corpo della richiesta di esempio

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

Un metodo `PUT` per aggiornare un gruppo di utenti.

<!--
r_rest_api_group_update.xml
-->

### Richiesta

`PUT /api/v1/groups/`*`<groupId>`*

### Corpo della richiesta di esempio

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

## Gruppi di elenchi {#list-groups}

Un metodo `GET` per elencare i gruppi di utenti.

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

Un metodo `DELETE` per eliminare un gruppo di utenti e rimuovere tutti i membri da tale gruppo.

<!-- r_rest_api_group_delete.xml -->

### Richiesta

`DELETE /api/v1/groups/`*`<groupId>`*

In caso di esito positivo, restituisce `204 No Content`. In caso di conflitto restituisce `409 Conflict`.

## Elimina gruppi in blocco {#delete-groups-bulk}

Un metodo `DELETE` per eliminare più gruppi in blocco e rimuovere tutti i membri da tale gruppo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Richiesta

`DELETE /api/v1/groups/bulk-delete`

In caso di esito positivo, restituisce `204 No Content`. In caso di conflitto restituisce `409 Conflict`.

## Elenca tutte le autorizzazioni per un gruppo {#list-permissions-group}

Un metodo `GET` per elencare gli oggetti autorizzazione in un gruppo.

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

Restituisce `400 Bad Request` se il gruppo non è accessibile.

## Impostare le autorizzazioni per un gruppo {#set-permissions-group}

Un metodo `PUT` per aggiornare le autorizzazioni del gruppo. Questo metodo sovrascrive le vecchie autorizzazioni con le nuove autorizzazioni.

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

La risposta di esempio rappresenta l’elenco aggiornato degli oggetti autorizzazione.

In caso di esito positivo, restituisce `200 OK`. Restituisce `400` se una determinata autorizzazione non è valida. Può inoltre restituire `403` se l&#39;oggetto non è accessibile dall&#39;utente connesso.
