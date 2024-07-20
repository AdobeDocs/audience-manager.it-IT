---
description: Metodi API REST per gestire gli utenti, tra cui creazione, aggiornamento, elenco, eliminazione e restituzione di oggetti utente.
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: Metodi API per la gestione degli utenti
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 1%

---

# Metodi API per la gestione degli utenti {#user-management-api-methods}

Utilizzare i metodi [!DNL API] per gestire gli utenti, ad esempio la creazione, l&#39;aggiornamento, l&#39;elenco, l&#39;eliminazione e la restituzione di oggetti utente.

<!-- c_rest_api_user_man_user.xml -->

## Crea un utente {#create-user}

Un metodo `POST` per creare un nuovo utente.

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

Se `isAdmin` è impostato su true, l&#39;utente viene creato come amministratore partner. Questa proprietà consente inoltre di sapere se un utente è un amministratore partner.

Restituisce `409 Conflict` se il nome utente è già utilizzato.

## Aggiornare un utente {#update-user}

Un metodo `PUT` per aggiornare un utente.

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

Restituisce `409 Conflict` se il nome utente è già utilizzato.

## Aggiorna utente connesso {#update-logged-in-user}

Un metodo `PUT` per aggiornare l&#39;utente attualmente connesso.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Mentre la maggior parte dei metodi [!DNL API] può essere chiamata solo dagli amministratori partner, questo metodo può essere chiamato da utenti non amministratori.

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

Restituisce `409 Conflict` se il nome utente è già utilizzato.

## Aggiorna password utente connesso {#update-logged-in-user-pw}

Un metodo `PUT` per aggiornare l&#39;utente attualmente connesso.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Mentre la maggior parte dei metodi [!DNL API] può essere chiamata solo dagli amministratori partner, questo metodo può essere chiamato da utenti non amministratori.

### Richiesta

`POST /users/self/update-password`

### Corpo della richiesta di esempio

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

In caso di esito positivo, restituisce `200 OK`. Restituisce `400 Bad Request` se si è verificato un errore con una delle due password.

## Reimposta password utente connesso {#reset-logged-in-user-pw}

Un metodo `PUT` per reimpostare l&#39;utente attualmente connesso. [!UICONTROL Audience Management] invia all&#39;utente una password generata dal sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Mentre la maggior parte dei metodi [!DNL API] può essere chiamata solo dagli amministratori partner, questo metodo può essere chiamato da utenti non amministratori.

### Richiesta

`POST /self/reset-password`

In caso di esito positivo, restituisce `200 OK`.

## Restituire un oggetto utente per un ID utente {#return-user-object-for-id}

Un metodo `Get` per restituire l&#39;oggetto utente per un ID utente.

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

## Oggetto utente restituito per l&#39;utente connesso {#return-user-object-for-logged-in-user}

Un metodo `Get` per restituire l&#39;oggetto utente per l&#39;utente attualmente connesso.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Mentre la maggior parte dei metodi [!DNL API] può essere chiamata solo dagli amministratori partner, questo metodo può essere chiamato da utenti non amministratori.

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

## Elenca utenti {#list-users}

Un metodo `GET` per elencare gli utenti.

<!-- r_rest_api_user_list.xml -->

### Richiesta

`GET /api/v1/users/`

Puoi specificare più ID gruppo nei parametri della query:

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

Un metodo `DELETE` per eliminare un utente.

<!-- r_rest_api_user_delete.xml -->

### Richiesta

`DELETE /api/v1/users/`*`<user_id>`*

In caso di esito positivo, restituisce `204 No Content`. In caso di conflitto restituisce `409 Conflict`.

## Elimina utenti in blocco {#delete-users-bulk}

Un metodo `POST` per eliminare più utenti in blocco.

<!-- r_rest_api_user_delete_bulk.xml -->

### Richiesta

`POST /api/v1/users/bulk-delete`

### Corpo della richiesta di esempio

```
{[<user_id_1>, <user_id_2>, ...]}
```
