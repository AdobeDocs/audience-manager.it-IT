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
source-git-commit: 9801bf6a1a4c2c2e7cc2aa8ab32cb81094368554

---


# Amministrazione (Controlli RBAC) {#administration}

![](assets/rbac-controls.png)

Le opzioni presenti nel [!UICONTROL Administration] menu consentono di creare utenti Audience Manager e assegnarli ai gruppi. Puoi inoltre visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).

I clienti Enterprise che utilizzano [!DNL Audience Manager] una piattaforma di gestione dati per tutti i loro dati, ma devono essere in grado di controllare la visibilità dei diversi elementi di dati a unità aziendali specifiche. Potete eseguire questa operazione utilizzando le autorizzazioni del gruppo, dette anche [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilizza i gruppi per assegnare le autorizzazioni. Le autorizzazioni non vengono assegnate a livello di utente. Le autorizzazioni del gruppo sono associate a oggetti (caratteristiche, segmenti, ecc.) e alle azioni che puoi eseguire su tali oggetti (modifica, visualizzazione, ecc.). Questi controlli sono disponibili anche tramite le API REST di Audience Manager. Consultate [Metodi di gestione utenti](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [gestione](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)dei gruppi e [gestione](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) delle autorizzazioni.

## Crea utenti {#create-users}

<!-- t_create_users.xml -->

Create utenti in [!DNL Audience Manager] e specificate i dettagli utente, lo stato di accesso e assegnate gli utenti ai gruppi.

1. Fate clic **[!UICONTROL Administration]** su &gt; **[!UICONTROL Users]**.
1. Fare clic per ![](assets/icon_add.png) visualizzare [!UICONTROL Create New User] la pagina.
1. Sotto **[!UICONTROL User Details]**, compila i campi:
   * **Nome utente:** Specifica un nome utente univoco per Audience Manager.
   * **Nome:** Specificate il nome dell&#39;utente.
   * **Cognome:** Specificate il cognome dell&#39;utente.
   * **Indirizzo e-mail:** Specificate l&#39;indirizzo e-mail dell&#39;utente. [!DNL Audience Manager] non invia una notifica regolare agli utenti. [!DNL Audience Manager] gli amministratori possono accedere agli indirizzi e-mail degli utenti e possono inviare manualmente gli utenti e-mail in base alle esigenze. Ad esempio, se un utente dimentica la password, l&#39;indirizzo e-mail specificato in questo campo viene usato per inviare una password temporanea e le istruzioni per reimpostare la password.
   * **Numero di telefono:** Specificate il numero di telefono dell&#39;utente.
   * **È Amministratore:** Specificate se l&#39;utente è [!DNL Audience Manager] un amministratore. Gli utenti Admin possono gestire gli utenti (creazione, modifica ecc.) e gruppi (create, assegnate autorizzazioni, ecc.). Gli utenti non amministratori possono controllare solo i propri profili utente, inclusa la modifica dei loro indirizzi e-mail e la reimpostazione delle password. Per ulteriori informazioni, vedi [Modifica impostazioni account](../../features/administration/edit-account-settings.md).
1. Sotto **[!UICONTROL Login]**, selezionate lo stato desiderato:
   * **Attivo:** Gli utenti attivi possono accedere [!DNL Audience Manager] e disporre delle autorizzazioni concesse per appartenenza al gruppo.
   * **Disattivato:** Gli utenti disattivati non possono accedere [!DNL Audience Manager] e non dispongono di autorizzazioni. Se disattivate gli utenti, le informazioni relative agli utenti rimangono in [!DNL Audience Manager] e potete facilmente riattivarle, se necessario. Se rimuovete gli utenti, dovete ricrearli se dovranno riutilizzarli [!DNL Audience Manager] in futuro.
   * **Scaduto:** La password di un utente è precedente a 90 giorni.
   * **In sospeso:** L&#39;utente dispone di una password temporanea, come dopo una reimpostazione della password o come nuovo account, e non ha ancora impostato una password permanente.
   * **Bloccato:** 5 tentativi di accesso errati bloccheranno un utente.
1. Sotto **[!UICONTROL Assigned Groups]**, dall&#39;elenco a discesa, selezionate i gruppi desiderati a cui assegnare l&#39;utente.
Per ulteriori informazioni sui gruppi e le autorizzazioni, consultate [Creare un gruppo](../../features/administration/administration-overview.md#create-group).
1. Fai clic su **[!UICONTROL Save]**.

## Creare un gruppo {#create-group}

*Un gruppo* è una raccolta di utenti che condividono diritti di accesso a oggetti di destinazione, segmento e caratteristiche. È possibile limitare i gruppi solo a singoli oggetti o consentire loro un accesso ampio a combinazioni di oggetti diversi.

<!-- t_create_groups.xml -->

Per creare un gruppo:

1. Fate clic **[!UICONTROL Administration]** su &gt; **[!UICONTROL Groups]**.
1. Fare clic per ![](assets/icon_add.png) aprire la [!UICONTROL Group Settings] pagina.
1. In [!UICONTROL Group Details]:
   * Denominate il gruppo.
   * Fornite una breve descrizione del gruppo.
1. In [!UICONTROL Group Members], fate clic su un utente per **[!UICONTROL Add Users]** aggiungerle al gruppo.
1. In [!UICONTROL Group Permissions], seleziona una [caratteristica](../../features/traits/trait-details-page.md), [un segmento](../../features/segments/segments-purpose.md)o [una destinazione](../../features/destinations/destinations.md) da **[!UICONTROL Add Object]**.
Viene aperta una finestra delle autorizzazioni per l&#39;oggetto selezionato.
1. Selezionate la casella di controllo per le autorizzazioni che desiderate assegnare ai membri del gruppo.
1. *(Facoltativo)* Assegna [le autorizzazioni](../../features/administration/administration-overview.md#wild-card-permissions) wild card al gruppo.
1. Fai clic su **[!UICONTROL Save Group]**.

## Autorizzazioni wild card {#wild-card-permissions}

Semplificate la gestione dei diritti dei gruppi [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] assegna ai membri del gruppo l&#39;accesso automatico a ogni origine dati associata a un segmento, a una destinazione o a una caratteristica. Per confronto, le autorizzazioni regolari consentono solo di assegnare origini dati specifiche a uno di questi oggetti. Inoltre, quando aggiungi nuove sorgenti dati, i membri del gruppo non possono accedere a tali fonti.

Devi aprire le autorizzazioni del gruppo e assegnare tali nuove origini dati al gruppo. [!UICONTROL Wild Card Permissions] consente di evitare questo processo di aggiornamento manuale dell&#39;origine dati. I gruppi con [!UICONTROL Wild Card Permissions] accesso a nuove sorgenti dati senza autorizzazione esplicita.

![](assets/wild-card.png)

Leggi di seguito per una descrizione di ogni autorizzazione di caratteri jolly:

**Caratteristica**

* `MAP_ALL_TRAITS_TO_MODELS` - need to clarify?
* `EDIT_ALL_TRAITS` - Gli utenti possono modificare tutte le caratteristiche appartenenti alla propria società (PID)
* `VIEW_ALL_TRAITS` - Gli utenti possono visualizzare tutte le caratteristiche appartenenti alla propria società (PID)
* `DELETE_ALL_TRAITS` - Gli utenti possono eliminare tutte le caratteristiche appartenenti alla propria società (PID).
* `CREATE_ALL_ALGO_TRAITS` - è necessario chiarire
* `MAP_ALL_TO_SEGMENTS` - Gli utenti possono aggiungere qualsiasi caratteristica appartenente alla propria società ai segmenti.
* `CREATE_ALL_TRAITS` - Gli utenti possono creare caratteristiche.

**Rapporti**

* `PTRREPORTS` - Questa autorizzazione jolly fa riferimento a funzionalità obsolete e verrà rimossa dall&#39;interfaccia utente di Audience Manager a breve.

**Modelli**

* `VIEW_MODELS` - Gli utenti dispongono dell&#39;autorizzazione per visualizzare i modelli appartenenti alla propria azienda.

**Segnali derivati**

* `VIEW_DERIVED_SIGNALS` - Gli utenti possono visualizzare tutti i segnali derivati appartenenti alla loro società.
* `CREATE_DERIVED_SIGNALS` - Gli utenti possono creare segnali derivati.
* `EDIT_DERIVED_SIGNALS` - Gli utenti possono modificare tutti i segnali derivati appartenenti alla propria azienda.
* `DELETE_DERIVED_SIGNALS` - Gli utenti possono eliminare qualsiasi segnale derivato appartenente alla propria società.

**Destinazione**

* `EDIT_ALL_DESTINATIONS` - Gli utenti possono modificare tutta la destinazione impostata all&#39;interno del proprio account della società.
* `CREATE_DESTINATIONS` - Gli utenti possono creare delle destinazioni.
* `VIEW_ALL_DESTINATIONS` - Gli utenti possono visualizzare tutte le destinazioni configurate all&#39;interno del proprio account della società.
* `DELETE_ALL_DESTINATIONS` - Gli utenti possono eliminare tutte le destinazioni configurate all&#39;interno del proprio account della società.

**Tag**

* `VIEW_TAGS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sui propri contenitori Tag.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sui gruppi di test Audience Lab.

**Segmento**

* `CREATE_ALL_SEGMENTS` - Gli utenti possono creare segmenti.
* `DELETE_ALL_SEGMENTS` - Gli utenti possono eliminare tutti i segmenti configurati all&#39;interno del relativo account della società.
* `MAP_ALL_TO_DESTINATIONS` - Gli utenti possono mappare qualsiasi segmento appartenente alla propria società a destinazioni.
* `EDIT_ALL_SEGMENTS` - Gli utenti possono modificare tutti i segmenti configurati all&#39;interno del relativo account aziendale.
* `MAP_ALL_SEGMENTS_TO_MODELS` - need to clarify?
* `VIEW_ALL_SEGMENTS` - Gli utenti possono visualizzare tutti i segmenti configurati all&#39;interno del relativo account della società.

**Segnali**

* `VIEW_ALL_SIGNALS` - Gli utenti possono visualizzare tutti i segnali acquisiti in [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).