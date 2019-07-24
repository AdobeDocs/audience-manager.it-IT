---
description: Le opzioni nel menu Amministrazione consentono di creare utenti di Audience Manager e assegnarli ai gruppi. Puoi inoltre visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
keywords: rbac; RBAC; ruolo basato su; basate su ruolo; controlli di accesso basati su ruolo
seo-description: Le opzioni nel menu Amministrazione consentono di creare utenti di Audience Manager e assegnarli ai gruppi. Puoi inoltre visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
seo-title: Amministrazione
solution: Audience Manager
title: Amministrazione
topic: API DIL
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 5d66c44a9072129de9da69918e9eeda2e18ccb22

---


# Administration (RBAC Controls) {#administration}

![](assets/rbac-controls.png)

The options under the [!UICONTROL Administration] menu let you create Audience Manager users and assign them to groups. Puoi inoltre visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).

Enterprise customers using [!DNL Audience Manager] need one data management platform for all of their data, but must be able to control the visibility of the different data elements to specific business units. You can accomplish this using group permissions, also referred to as [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilizza i gruppi per assegnare le autorizzazioni. Le autorizzazioni non vengono assegnate a livello di utente. Le autorizzazioni del gruppo sono associate a oggetti (caratteristiche, segmenti, ecc.) e alle azioni che puoi eseguire su tali oggetti (modifica, visualizzazione, ecc.). Questi controlli sono disponibili anche tramite le API REST di Audience Manager. See [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), and [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API methods.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Create users in [!DNL Audience Manager] and specify user details, login status, and assign users to groups.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nome utente:** Specifica un nome utente univoco per Audience Manager.
   * **Nome:** Specificate il nome dell'utente.
   * **Cognome:** Specificate il cognome dell'utente.
   * **Indirizzo e-mail:** Specificate l'indirizzo e-mail dell'utente. [!DNL Audience Manager] non invia una notifica regolare agli utenti. [!DNL Audience Manager] gli amministratori possono accedere agli indirizzi e-mail degli utenti e possono inviare manualmente gli utenti e-mail in base alle esigenze. Ad esempio, se un utente dimentica la password, l'indirizzo e-mail specificato in questo campo viene usato per inviare una password temporanea e le istruzioni per reimpostare la password.
   * **Numero di telefono:** Specificate il numero di telefono dell'utente.
   * **È Amministratore:** Specificate se l'utente è [!DNL Audience Manager] un amministratore. Gli utenti Admin possono gestire gli utenti (creazione, modifica ecc.) e gruppi (create, assegnate autorizzazioni, ecc.). Gli utenti non amministratori possono controllare solo i propri profili utente, inclusa la modifica dei loro indirizzi e-mail e la reimpostazione delle password. For more information, see [Edit Your Account Settings](../../features/administration/edit-account-settings.md).
1. Under **[!UICONTROL Login]**, select the desired status:
   * **Attivo:** Gli utenti attivi possono accedere [!DNL Audience Manager] e disporre delle autorizzazioni concesse per appartenenza al gruppo.
   * **Disattivato:** Gli utenti disattivati non possono accedere [!DNL Audience Manager] e non dispongono di autorizzazioni. If you deactivate users, their user information remains in [!DNL Audience Manager] and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use [!DNL Audience Manager] again in the future.
   * **Scaduto:** La password di un utente è precedente a 90 giorni.
   * **In sospeso:** L'utente dispone di una password temporanea, come dopo una reimpostazione della password o come nuovo account, e non ha ancora impostato una password permanente.
   * **Bloccato:** 5 tentativi di accesso errati bloccheranno un utente.
1. Under **[!UICONTROL Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.
For more information about groups and permissions, see [Create a Group](../../features/administration/administration-overview.md#create-group).
1. Fai clic su **[!UICONTROL Save]**.

## Creare un gruppo {#create-group}

*Un gruppo* è una raccolta di utenti che condividono diritti di accesso a oggetti di destinazione, segmento e caratteristiche. È possibile limitare i gruppi solo a singoli oggetti o consentire loro un accesso ampio a combinazioni di oggetti diversi.

<!-- t_create_groups.xml -->

Per creare un gruppo:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1. In [!UICONTROL Group Details]:
   * Denominate il gruppo.
   * Fornite una breve descrizione del gruppo.
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), or [destination](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
Viene aperta una finestra delle autorizzazioni per l'oggetto selezionato.
1. Selezionate la casella di controllo per le autorizzazioni che desiderate assegnare ai membri del gruppo.
1. *(Facoltativo)* Assegna [le autorizzazioni](../../features/administration/administration-overview.md#wild-card-permissions) wild card al gruppo.
1. Fai clic su **[!UICONTROL Save Group]**.

## Understanding Wild Card Permissions {#wild-card-permissions}

Simplify group rights management with [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] assegna ai membri del gruppo l'accesso automatico a ogni origine dati associata a un segmento, a una destinazione o a una caratteristica. Per confronto, le autorizzazioni regolari consentono solo di assegnare origini dati specifiche a uno di questi oggetti. Inoltre, quando aggiungi nuove sorgenti dati, i membri del gruppo non possono accedere a tali fonti.

Devi aprire le autorizzazioni del gruppo e assegnare tali nuove origini dati al gruppo. [!UICONTROL Wild Card Permissions] consente di evitare questo processo di aggiornamento manuale dell'origine dati. Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.

![](assets/wild-card.png)

Leggi di seguito per una descrizione di ogni autorizzazione di caratteri jolly:

**Caratteristica**

* `MAP_ALL_TRAITS_TO_MODELS` - Gli utenti possono selezionare caratteristiche come linea di base per i modelli.
* `EDIT_ALL_TRAITS` - Gli utenti possono modificare tutte le caratteristiche appartenenti alla propria società (PID).
* `VIEW_ALL_TRAITS` - Gli utenti possono visualizzare tutte le caratteristiche appartenenti alla propria società (PID).
* `DELETE_ALL_TRAITS` - Gli utenti possono eliminare tutte le caratteristiche appartenenti alla propria società (PID).
* `CREATE_ALL_ALGO_TRAITS` - Gli utenti possono creare caratteristiche algoritmiche.
* `MAP_ALL_TO_SEGMENTS` - Gli utenti possono aggiungere qualsiasi caratteristica appartenente alla propria società ai segmenti.
* `CREATE_ALL_TRAITS` - Gli utenti possono creare caratteristiche.

**Rapporti**

* `PTRREPORTS` - Questa autorizzazione jolly fa riferimento a funzionalità obsolete e verrà rimossa dall'interfaccia utente di Audience Manager a breve.

**Modelli**

* `VIEW_MODELS` - Gli utenti dispongono dell'autorizzazione per visualizzare i modelli appartenenti alla propria azienda.

**Segnali derivati**

* `VIEW_DERIVED_SIGNALS` - Gli utenti possono visualizzare tutti i segnali derivati appartenenti alla loro società.
* `CREATE_DERIVED_SIGNALS` - Gli utenti possono creare segnali derivati.
* `EDIT_DERIVED_SIGNALS` - Gli utenti possono modificare tutti i segnali derivati appartenenti alla propria azienda.
* `DELETE_DERIVED_SIGNALS` - Gli utenti possono eliminare qualsiasi segnale derivato appartenente alla propria società.

**Destinazione**

* `EDIT_ALL_DESTINATIONS` - Gli utenti possono modificare tutta la destinazione impostata all'interno del proprio account della società.
* `CREATE_DESTINATIONS` - Gli utenti possono creare delle destinazioni.
* `VIEW_ALL_DESTINATIONS` - Gli utenti possono visualizzare tutte le destinazioni configurate all'interno del proprio account della società.
* `DELETE_ALL_DESTINATIONS` - Gli utenti possono eliminare tutte le destinazioni configurate all'interno del proprio account della società.

**Tag**

* `VIEW_TAGS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sui propri contenitori Tag.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sui gruppi di test Audience Lab.

**Segmento**

* `CREATE_ALL_SEGMENTS` - Gli utenti possono creare segmenti.
* `DELETE_ALL_SEGMENTS` - Gli utenti possono eliminare tutti i segmenti configurati all'interno del relativo account della società.
* `MAP_ALL_TO_DESTINATIONS` - Gli utenti possono mappare qualsiasi segmento appartenente alla propria società a destinazioni.
* `EDIT_ALL_SEGMENTS` - Gli utenti possono modificare tutti i segmenti configurati all'interno del relativo account aziendale.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gli utenti possono selezionare segmenti come linea di base per i modelli.
* `VIEW_ALL_SEGMENTS` - Gli utenti possono visualizzare tutti i segmenti configurati all'interno del relativo account della società.

**Segnali**

* `VIEW_ALL_SIGNALS` - Gli utenti possono visualizzare tutti i segnali acquisiti in [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).