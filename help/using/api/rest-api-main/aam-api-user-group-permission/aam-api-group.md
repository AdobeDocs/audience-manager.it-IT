---
description: Rest Metodi API per gestire i gruppi, inclusi creazione, aggiornamento, elenco, eliminazione di gruppi.
seo-description: Rest Metodi API per gestire i gruppi, inclusi creazione, aggiornamento, elenco, eliminazione di gruppi.
seo-title: Metodi API per la gestione dei gruppi
solution: Audience Manager
title: Metodi API per la gestione dei gruppi
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 12%

---


# Metodi API per la gestione dei gruppi {#group-management-api-methods}

Utilizzare i metodi [!DNL API] rimanenti per gestire i gruppi, inclusi la creazione, l&#39;aggiornamento, l&#39;elenco, l&#39;eliminazione dei gruppi.

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

Metodo `DELETE` per eliminare un gruppo di utenti e rimuovere tutti i membri da tale gruppo.

<!-- r_rest_api_group_delete.xml -->

### Richiesta

`DELETE /api/v1/groups/`*`<groupId>`*

Restituisce `204 No Content` in caso di esito positivo. In caso di conflitto restituisce `409 Conflict`.

## Elimina gruppi in blocco {#delete-groups-bulk}

Un metodo `DELETE` per eliminare più gruppi in blocco e rimuovere tutti i membri da tale gruppo.

<!-- r_rest_api_group_delete_bulk.xml -->

### Richiesta

`DELETE /api/v1/groups/bulk-delete`

Restituisce `204 No Content` in caso di esito positivo. In caso di conflitto restituisce `409 Conflict`.

## Elenca tutte le autorizzazioni per un gruppo {#list-permissions-group}

Un metodo `GET` per elencare gli oggetti di autorizzazione di un gruppo.

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

## Impostare le autorizzazioni per un gruppo {#set-permissions-group}

Metodo `PUT` per aggiornare le autorizzazioni del gruppo. Questo metodo sovrascrive le autorizzazioni precedenti con le nuove autorizzazioni.

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

La risposta di esempio rappresenta l&#39;elenco aggiornato di oggetti autorizzazione.

Restituisce `200 OK` in caso di esito positivo. Restituisce `400` se un&#39;autorizzazione specificata non è valida. Può anche restituire `403` se l&#39;oggetto non è accessibile dall&#39;utente che ha eseguito l&#39;accesso.