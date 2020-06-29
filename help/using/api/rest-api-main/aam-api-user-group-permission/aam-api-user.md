---
description: Resto di metodi API per gestire gli utenti, inclusi creazione, aggiornamento, elenco, eliminazione e restituzione di oggetti utente.
seo-description: Resto di metodi API per gestire gli utenti, inclusi creazione, aggiornamento, elenco, eliminazione e restituzione di oggetti utente.
seo-title: Metodi API di gestione utenti
solution: Audience Manager
title: Metodi API di gestione utenti
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 4%

---


# Metodi API di gestione utenti {#user-management-api-methods}

Metodi [!DNL API] di ripristino per gestire gli utenti, inclusi creazione, aggiornamento, elenco, eliminazione e restituzione di oggetti utente.

<!-- c_rest_api_user_man_user.xml -->

## Creazione di un utente {#create-user}

Un `POST` metodo per creare un nuovo utente.

<!-- r_rest_api_user_create.xml -->

### Richiesta

`POST /api/v1/users/`

### Corpo della richiesta di esempio

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### Risposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

Se `isAdmin` è impostato su true, l&#39;utente viene creato come amministratore partner. Questa proprietà consente inoltre di sapere se un utente è un amministratore di partner.

Restituisce `409 Conflict` se il nome utente è già stato usato.

## Aggiornare un utente {#update-user}

Un `PUT` metodo per aggiornare un utente.

<!-- r_rest_api_user_update.xml -->

### Richiesta

`PUT /api/v1/users/`*`<userId>`*

### Corpo della richiesta di esempio

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### Risposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

Restituisce `409 Conflict` se il nome utente è già stato usato.

## Aggiorna utente connesso {#update-logged-in-user}

Un `PUT` metodo per aggiornare l’utente attualmente connesso.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Mentre la maggior parte [!DNL API] dei metodi è richiamabile solo dagli amministratori dei partner, questo metodo è richiamabile dagli utenti non amministratori.

### Richiesta

`PUT /self/update`

### Corpo della richiesta di esempio

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### Risposta

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

Restituisce `409 Conflict` se il nome utente è già stato usato.

## Aggiorna password utente con accesso {#update-logged-in-user-pw}

Un `PUT` metodo per aggiornare l’utente attualmente connesso.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Mentre la maggior parte [!DNL API] dei metodi è richiamabile solo dagli amministratori dei partner, questo metodo è richiamabile dagli utenti non amministratori.

### Richiesta

`POST /users/self/update-password`

### Corpo della richiesta di esempio

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Restituisce `200 OK` se ha esito positivo. Restituisce `400 Bad Request` se si verifica un errore in una delle due password.

## Reimposta password utente di accesso {#reset-logged-in-user-pw}

Un `PUT` metodo per ripristinare l’utente attualmente connesso. [!UICONTROL Audience Management] invia all&#39;utente una password generata dal sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Mentre la maggior parte [!DNL API] dei metodi è richiamabile solo dagli amministratori dei partner, questo metodo è richiamabile dagli utenti non amministratori.

### Richiesta

`POST /self/reset-password`

Restituisce `200 OK` se ha esito positivo.

## Restituisci oggetto utente per un ID utente {#return-user-object-for-id}

Un `Get` metodo per restituire l’oggetto utente per un ID utente.

<!-- r_rest_api_user_get_user_obj.xml -->

### Richiesta

`GET /api/v1/users/`*`<userId>`*

### Risposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Restituisci oggetto utente per l’utente connesso {#return-user-object-for-logged-in-user}

Un `Get` metodo per restituire l’oggetto utente all’utente attualmente connesso.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Mentre la maggior parte [!DNL API] dei metodi è richiamabile solo dagli amministratori dei partner, questo metodo è richiamabile dagli utenti non amministratori.

### Richiesta

`GET /api/v1/users/self`

### Risposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Utenti elenco {#list-users}

Un `GET` metodo per elencare gli utenti.

<!-- r_rest_api_user_list.xml -->

### Richiesta

`GET /api/v1/users/`

Potete specificare più ID gruppo nei parametri di query:

`GET /api/v1/users/?groupId=343&groupdId=12`

Questa query restituisce un elenco di tutti gli utenti nei gruppi specificati.

### Risposta

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Eliminare un utente {#delete-users}

Un `DELETE` metodo per eliminare un utente.

<!-- r_rest_api_user_delete.xml -->

### Richiesta

`DELETE /api/v1/users/`*`<user_id>`*

Restituisce `204 No Content` se ha esito positivo. In caso di ritorno a un conflitto `409 Conflict`.

## Elimina utenti in blocco {#delete-users-bulk}

Un `POST` metodo per eliminare più utenti in massa.

<!-- r_rest_api_user_delete_bulk.xml -->

### Richiesta

`POST /api/v1/users/bulk-delete`

### Corpo della richiesta di esempio

```
{[<user_id_1>, <user_id_2>, ...]}
```
