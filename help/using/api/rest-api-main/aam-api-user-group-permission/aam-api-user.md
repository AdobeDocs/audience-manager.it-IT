---
description: Metodi REST API per gestire gli utenti, compresa la creazione, l'aggiornamento, l'elenco, l'eliminazione e il ritorno degli oggetti utente.
seo-description: Metodi REST API per gestire gli utenti, compresa la creazione, l'aggiornamento, l'elenco, l'eliminazione e il ritorno degli oggetti utente.
seo-title: Metodi API di gestione utenti
solution: Audience Manager
title: Metodi API di gestione utenti
uuid: 6 e 1 f 2 c 35-bb 9 d -4166-b 7 d 4-d 9 c 5518 a 61 ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# User Management API Methods {#user-management-api-methods}

Rest [!DNL API] methods to manage users, including creating, updating, listing, deleting, and returning user objects.

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

`POST` Un metodo per creare un nuovo utente.

<!-- r_rest_api_user_create.xml -->

### Richiesta

`POST /api/v1/users/`

### Corpo richiesta di esempio

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

If `isAdmin` is set to true, the user is created as a partner admin. Questa proprietà consente anche di sapere se un utente è un amministratore di partner.

Returns `409 Conflict` if the username is already taken.

## Update a User {#update-user}

`PUT` Un metodo per aggiornare un utente.

<!-- r_rest_api_user_update.xml -->

### Richiesta

`PUT /api/v1/users/`*`<userId>`*

### Corpo richiesta di esempio

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User {#update-logged-in-user}

`PUT` Un metodo per aggiornare l'utente attualmente connesso.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Richiesta

`PUT /self/update`

### Corpo richiesta di esempio

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User Password {#update-logged-in-user-pw}

`PUT` Un metodo per aggiornare l'utente attualmente connesso.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Richiesta

`POST /users/self/update-password`

### Corpo richiesta di esempio

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Returns `200 OK` if successful. Returns `400 Bad Request` if something is wrong with either password.

## Reset Logged-In User Password {#reset-logged-in-user-pw}

`PUT` Un metodo per reimpostare l'utente attualmente connesso. [!UICONTROL Audience Management] invia all'utente una password generata dal sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Richiesta

`POST /self/reset-password`

Returns `200 OK` if successful.

## Return User Object for a User ID {#return-user-object-for-id}

`Get` Un metodo per restituire l'oggetto utente a un ID utente.

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

## Return User Object for Logged-In User {#return-user-object-for-logged-in-user}

`Get` Un metodo per restituire l'oggetto utente per l'utente attualmente connesso.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

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

## List Users {#list-users}

`GET` Un metodo per l'elenco degli utenti.

<!-- r_rest_api_user_list.xml -->

### Richiesta

`GET /api/v1/users/`

Nei parametri query potete specificare più ID gruppo:

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

## Delete a User {#delete-users}

`DELETE` Un metodo per eliminare un utente.

<!-- r_rest_api_user_delete.xml -->

### Richiesta

`DELETE /api/v1/users/`*`<user_id>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Users in Bulk {#delete-users-bulk}

`POST` Un metodo per eliminare più utenti in gruppo.

<!-- r_rest_api_user_delete_bulk.xml -->

### Richiesta

`POST /api/v1/users/bulk-delete`

### Corpo richiesta di esempio

```
{[<user_id_1>, <user_id_2>, ...]}
```
