---
description: Le opzioni del menu Amministrazione consentono di creare  utenti Audience Manager e di assegnarli ai gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: Le opzioni del menu Amministrazione consentono di creare  utenti Audience Manager e di assegnarli ai gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
seo-title: Amministrazione
solution: Audience Manager
title: Amministrazione
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 1%

---


# Amministrazione (controlli RBAC) {#administration}

![](assets/rbac-controls.png)

Le opzioni del [!UICONTROL Administration] menu consentono di creare  utenti Audience Manager e di assegnarli ai gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).

I clienti Enterprise che utilizzano [!DNL Audience Manager] necessitano di una piattaforma di gestione dati per tutti i loro dati, ma devono essere in grado di controllare la visibilità dei diversi elementi di dati a specifiche unità aziendali. A tal fine potete utilizzare le autorizzazioni di gruppo, denominate anche [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilizza i gruppi per assegnare le autorizzazioni. Le autorizzazioni non vengono assegnate a livello di utente. Le autorizzazioni del gruppo sono associate a oggetti (caratteristiche, segmenti, ecc.) e alle azioni che è possibile eseguire su tali oggetti (modifica, visualizzazione, ecc.). Questi controlli sono disponibili anche tramite le  API REST di Audience Manager. Consultate [Gestione](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)utente, Gestione dei [gruppi](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)e Metodi API per la gestione delle [autorizzazioni](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) .

## Crea utenti {#create-users}

<!-- t_create_users.xml -->

Create gli utenti in [!DNL Audience Manager] e specificate i dettagli utente, lo stato di accesso e assegnate gli utenti ai gruppi.

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Fate clic ![](assets/icon_add.png) per visualizzare la [!UICONTROL Create New User] pagina.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nome utente:** Specificate un nome utente univoco per  Audience Manager.
   * **Nome:** Specificate il nome dell&#39;utente.
   * **Cognome:** Specificate il cognome dell’utente.
   * **Indirizzo e-mail:** Specificate l&#39;indirizzo e-mail dell&#39;utente. [!DNL Audience Manager] non invia notifiche regolari agli utenti. [!DNL Audience Manager] gli amministratori hanno accesso agli indirizzi e-mail degli utenti e possono inviare manualmente gli utenti come necessario. Ad esempio, se un utente dimentica la password, l&#39;indirizzo e-mail specificato in questo campo viene utilizzato per inviare una password temporanea e le istruzioni per reimpostare la password.
   * **Numero di telefono:** Specificate il numero di telefono dell&#39;utente.
   * **Amministratore Is:** Specificate se questo utente è un [!DNL Audience Manager] amministratore. Gli utenti amministratori possono gestire gli utenti (creare, modificare, ecc.) e i gruppi (creare, assegnare le autorizzazioni, ecc.). Gli utenti non amministratori possono controllare solo i propri profili utente, inclusi la modifica degli indirizzi e-mail e la reimpostazione delle proprie password. Per ulteriori informazioni, consultate [Modificare le impostazioni](../../features/administration/edit-account-settings.md)dell&#39;account.
1. In **[!UICONTROL Login]**, selezionate lo stato desiderato:
   * **Attivo:**  Gli utenti attivi possono accedere [!DNL Audience Manager] e disporre delle autorizzazioni concesse per appartenenza al gruppo.
   * **Disattivato:**  Gli utenti disattivati non possono accedere [!DNL Audience Manager] e non dispongono di alcuna autorizzazione. Se disattivate gli utenti, le relative informazioni restano invariate [!DNL Audience Manager] e potete semplicemente riattivarle, se necessario. Se rimuovete degli utenti, dovete ricrearli se dovranno riutilizzarli [!DNL Audience Manager] in futuro.
   * **Scaduto:** La password di un utente supera i 90 giorni.
   * **In sospeso:** L&#39;utente dispone di una password temporanea, come dopo il ripristino della password o come nuovo account, e non ha ancora impostato una password permanente.
   * **Bloccato:** 5 tentativi di accesso errati bloccheranno un utente.
1. Nell&#39;elenco **[!UICONTROL Assigned Groups]**a discesa, selezionate i gruppi a cui desiderate assegnare l&#39;utente.
Per ulteriori informazioni su gruppi e autorizzazioni, consultate [Creare un gruppo](../../features/administration/administration-overview.md#create-group).
1. Clic **[!UICONTROL Save]**.

## Creare un gruppo {#create-group}

Un *gruppo* è un insieme di utenti che condividono i diritti di accesso agli oggetti di destinazione, segmento e caratteristica. È possibile limitare i gruppi a un solo oggetto o consentire loro un ampio accesso a combinazioni di oggetti diversi.

<!-- t_create_groups.xml -->

Per creare un gruppo:

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. Fate clic ![](assets/icon_add.png) per aprire la [!UICONTROL Group Settings] pagina.
1. In [!UICONTROL Group Details]:
   * Denominate il gruppo.
   * Fornite una breve descrizione del gruppo.
1. In [!UICONTROL Group Members], fate clic su un utente tra **[!UICONTROL Add Users]** le opzioni per aggiungerlo al gruppo.
1. In [!UICONTROL Group Permissions], seleziona una [caratteristica](../../features/traits/trait-details-page.md), un [segmento](../../features/segments/segments-purpose.md)o una [destinazione](../../features/destinations/destinations.md) da **[!UICONTROL Add Object]**.
Viene visualizzata una finestra di autorizzazioni per l&#39;oggetto selezionato.
1. Selezionate la casella di controllo per le autorizzazioni che desiderate assegnare ai membri del gruppo.
1. *(Facoltativo)* Assegnate le autorizzazioni per schede [jolly](../../features/administration/administration-overview.md#wild-card-permissions) al gruppo.
1. Clic **[!UICONTROL Save Group]**.

## Informazioni sulle autorizzazioni per le schede wild {#wild-card-permissions}

Semplificate la gestione dei diritti di gruppo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] consente ai membri del gruppo di accedere automaticamente a ogni origine dati associata a un segmento, una destinazione o una caratteristica. A titolo di confronto, le autorizzazioni regolari consentono solo di assegnare origini dati specifiche a uno di questi oggetti. Inoltre, quando si aggiungono nuove origini dati, i membri del gruppo non hanno accesso a queste nuove origini.

È necessario aprire le autorizzazioni del gruppo e assegnare le nuove origini dati al gruppo. [!UICONTROL Wild Card Permissions] consente di evitare questo processo manuale di aggiornamento dell&#39;origine dati. Gruppi con [!UICONTROL Wild Card Permissions] accesso a nuove origini dati senza autorizzazione esplicita.

![](assets/wild-card.png)

Di seguito è riportata una descrizione del significato di ciascuna autorizzazione per caratteri jolly:

**Caratteristiche**

* `MAP_ALL_TRAITS_TO_MODELS` - Gli utenti possono selezionare le caratteristiche come linea di base per i modelli.
* `EDIT_ALL_TRAITS` - Gli utenti possono modificare tutte le caratteristiche configurate nel proprio account aziendale.
* `VIEW_ALL_TRAITS` - Gli utenti possono visualizzare tutte le caratteristiche configurate nel proprio account aziendale.
* `DELETE_ALL_TRAITS` - Gli utenti possono eliminare tutte le caratteristiche configurate nel proprio account aziendale.
* `CREATE_ALL_ALGO_TRAITS` - Gli utenti possono creare caratteristiche algoritmiche.
* `MAP_ALL_TO_SEGMENTS` - Gli utenti possono aggiungere ai segmenti qualsiasi caratteristica appartenente alla propria società.
* `CREATE_ALL_TRAITS` - Gli utenti possono creare caratteristiche.

**Rapporti**

* `PTRREPORTS` - Questa autorizzazione per i caratteri jolly si riferisce a funzionalità obsolete e verrà rimossa dall&#39;interfaccia utente  Audience Manager a breve.

**Modelli**

* `VIEW_MODELS` - Gli utenti dispongono dell&#39;autorizzazione per visualizzare i modelli appartenenti alla propria società.

**Segnali derivati**

* `VIEW_DERIVED_SIGNALS` - Gli utenti possono visualizzare tutti i segnali derivati appartenenti alla propria azienda.
* `CREATE_DERIVED_SIGNALS` - Gli utenti possono creare segnali derivati.
* `EDIT_DERIVED_SIGNALS` - Gli utenti possono modificare tutti i segnali derivati appartenenti alla propria azienda.
* `DELETE_DERIVED_SIGNALS` - Gli utenti possono eliminare qualsiasi segnale derivato appartenente alla propria società.

**Destinazione**

* `EDIT_ALL_DESTINATIONS` - Gli utenti possono modificare tutta la destinazione impostata nel loro account società.
* `CREATE_DESTINATIONS` - Gli utenti possono creare delle destinazioni.
* `VIEW_ALL_DESTINATIONS` - Gli utenti possono visualizzare tutte le destinazioni configurate nel loro account società.
* `DELETE_ALL_DESTINATIONS` - Gli utenti possono eliminare tutte le destinazioni configurate nel loro account società.

**Tag**

* `VIEW_TAGS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sui propri contenitori di tag.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sui gruppi di test di Audience Lab.

**Segmento**

* `CREATE_ALL_SEGMENTS` - Gli utenti possono creare segmenti.
* `DELETE_ALL_SEGMENTS` - Gli utenti possono eliminare tutti i segmenti configurati nel loro account società.
* `MAP_ALL_TO_DESTINATIONS` - Gli utenti possono mappare i segmenti appartenenti alla propria società alle destinazioni.
* `EDIT_ALL_SEGMENTS` - Gli utenti possono modificare tutti i segmenti configurati all&#39;interno del loro account società.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gli utenti possono selezionare i segmenti come linea di base per i modelli.
* `VIEW_ALL_SEGMENTS` - Gli utenti possono visualizzare tutti i segmenti configurati nel loro account società.

**Segnali**

* `VIEW_ALL_SIGNALS` - Gli utenti possono visualizzare tutti i segnali acquisiti in [Esplora](/help/using/features/data-explorer/data-explorer-overview.md)dati.

## Casi d&#39;uso {#use-cases}

### Monitoraggio dell&#39;accesso utente {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] può essere utile per monitorare lo stato di accesso degli utenti, fornendo un&#39;immagine chiara di chi può accedere all&#39;istanza di Audience Manager .

A seconda delle esigenze aziendali, potete attivare e disattivare gli account utente in base alle esigenze.

![monitor-accesso utente](assets/monitor-user-access.png)

### Protezione dell&#39;accesso per le origini dati sensibili {#protect-sensitive-data-sources}

Puoi configurare [!UICONTROL Role-Based Access Control] a livello di caratteristica, segmento e destinazione per ciascun gruppo di utenti.

Questa funzionalità consente di gestire il modo in cui gli utenti visualizzano, creano, leggono, scrivono e modificano specifici set di dati, e persino di impedire agli utenti di accedere ai set di dati che non dovrebbero essere disponibili per loro.

![protezione dell&#39;accesso](assets/access-protection.png)
