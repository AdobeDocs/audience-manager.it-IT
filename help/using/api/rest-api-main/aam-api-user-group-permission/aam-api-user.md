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


# Metodi API di gestione utenti {#user-management-api-methods}

Metodi rest [!DNL API] per gestire gli utenti, compresa la creazione, l&#39;aggiornamento, l&#39;elenco, l&#39;eliminazione e il ritorno degli oggetti utente.

<!-- c_rest_api_user_man_user.xml -->

## Creare un utente {#create-user}

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

Se `isAdmin` è impostato su true, l&#39;utente viene creato come amministratore di partner. Questa proprietà consente anche di sapere se un utente è un amministratore di partner.

Restituisce `409 Conflict` se il nome utente è già in uso.

## Aggiornare un utente {#update-user}

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

Restituisce `409 Conflict` se il nome utente è già in uso.

## Aggiornamento dell&#39;utente connesso {#update-logged-in-user}

`PUT` Un metodo per aggiornare l&#39;utente attualmente connesso.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>La maggior parte [!DNL API] dei metodi è chiamabile solo dagli amministratori partner, questo metodo è chiamabile dagli utenti non amministratori.

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

Restituisce `409 Conflict` se il nome utente è già in uso.

## Aggiornare la password utente connesso {#update-logged-in-user-pw}

`PUT` Un metodo per aggiornare l&#39;utente attualmente connesso.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>La maggior parte [!DNL API] dei metodi è chiamabile solo dagli amministratori partner, questo metodo è chiamabile dagli utenti non amministratori.

### Richiesta

`POST /users/self/update-password`

### Corpo richiesta di esempio

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Restituisce `200 OK` in caso di esito positivo. Restituisce `400 Bad Request` se un valore è errato con una delle due password.

## Reimposta password utente con accesso {#reset-logged-in-user-pw}

`PUT` Un metodo per reimpostare l&#39;utente attualmente connesso. [!UICONTROL Audience Management] invia all&#39;utente una password generata dal sistema.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>La maggior parte [!DNL API] dei metodi è chiamabile solo dagli amministratori partner, questo metodo è chiamabile dagli utenti non amministratori.

### Richiesta

`POST /self/reset-password`

Restituisce `200 OK` in caso di esito positivo.

## Restituzione dell&#39;oggetto utente per un ID utente {#return-user-object-for-id}

`Get` Un metodo per restituire l&#39;oggetto utente a un ID utente.

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

## Restituzione dell&#39;oggetto utente per l&#39;utente connesso {#return-user-object-for-logged-in-user}

`Get` Un metodo per restituire l&#39;oggetto utente per l&#39;utente attualmente connesso.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>La maggior parte [!DNL API] dei metodi è chiamabile solo dagli amministratori partner, questo metodo è chiamabile dagli utenti non amministratori.

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

## Elenco utenti {#list-users}

`GET` Un metodo per l&#39;elenco degli utenti.

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

## Eliminare un utente {#delete-users}

`DELETE` Un metodo per eliminare un utente.

<!-- r_rest_api_user_delete.xml -->

### Richiesta

`DELETE /api/v1/users/`*`<user_id>`*

Restituisce `204 No Content` in caso di esito positivo. In caso di ritorni `409 Conflict`a capo.

## Elimina utenti in gruppo {#delete-users-bulk}

`POST` Un metodo per eliminare più utenti in gruppo.

<!-- r_rest_api_user_delete_bulk.xml -->

### Richiesta

`POST /api/v1/users/bulk-delete`

### Corpo richiesta di esempio

```
{[<user_id_1>, <user_id_2>, ...]}
```
