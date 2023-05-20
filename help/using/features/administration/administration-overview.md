---
description: Le opzioni del menu Amministrazione consentono di creare utenti Audienci Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
keywords: rbac;RBAC;basato su ruoli;basato su ruoli;controlli di accesso basati su ruoli
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Amministrazione
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: 8ef6e8eb4351c24b55703b1788c68c580f199fc8
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 2%

---

# [!UICONTROL Administration] (Controlli RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La gestione degli account utente è in corso di spostamento al [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti Audience Manager adottino immediatamente le misure necessarie descritte in questo : [Migrazione degli utenti Audience Manager ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, le sezioni di gestione utenti di questo documento spariranno.


Le opzioni sotto [!UICONTROL Administration] consente di creare utenti Audience Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).

Clienti aziendali che utilizzano [!DNL Audience Manager] necessitano di una piattaforma di gestione dati per tutti i loro dati, ma devono essere in grado di controllare la visibilità dei diversi elementi dati per specifiche unità aziendali. Puoi eseguire questa operazione utilizzando le autorizzazioni del gruppo, denominate anche [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilizza i gruppi per assegnare le autorizzazioni. Le autorizzazioni non vengono assegnate a livello di utente. Le autorizzazioni del gruppo sono associate a oggetti ([!UICONTROL traits], segmenti, ecc.) e alle azioni che è possibile eseguire su tali oggetti (modifica, visualizzazione, ecc.). Questi controlli sono disponibili anche tramite le API REST di Audience Manager. Consulta [Gestione utente](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gestione dei gruppi](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), e [Gestione autorizzazioni](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) Metodi API.

## Crea utenti {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La gestione degli account utente è in corso di spostamento al [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti Audience Manager adottino immediatamente le misure necessarie descritte in questo : [Migrazione degli utenti Audience Manager ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, la sezione sulla gestione degli utenti di questo documento sparirà.
Creare utenti in [!DNL Audience Manager] e specificare i dettagli utente, lo stato di accesso e assegnare gli utenti ai gruppi.

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Clic ![](assets/icon_add.png) per visualizzare [!UICONTROL Create New User] pagina.
1. Sotto **[!UICONTROL User Details]**, compila i campi:
   * **[!UICONTROL Username]:** Specifica un nome utente univoco, ad Audience Manager.
   * **[!UICONTROL First Name]:** Specifica il nome dell’utente.
   * **[!UICONTROL Last Name]:** Specificare il cognome dell&#39;utente.
   * **[!UICONTROL Email Address]:** Specifica l’indirizzo e-mail dell’utente. [!DNL Audience Manager] non invia notifiche regolari agli utenti. [!DNL Audience Manager] gli amministratori hanno accesso agli indirizzi e-mail degli utenti e possono inviare manualmente i messaggi di posta elettronica agli utenti in base alle esigenze. Ad esempio, se un utente dimentica la propria password, l’indirizzo e-mail specificato in questo campo viene utilizzato per inviare una password temporanea e istruzioni per reimpostare la password.
   * **[!UICONTROL Phone Number]:** Specifica il numero di telefono dell&#39;utente.
   * **[!UICONTROL Is Admin]:** Specifica se l&#39;utente è un [!DNL Audience Manager] amministratore. Gli utenti amministratori possono gestire gli utenti (creare, modificare, ecc.) e gruppi (creazione, assegnazione di autorizzazioni, ecc.). Gli utenti non amministratori possono controllare solo i propri profili utente, inclusa la modifica degli indirizzi e-mail e la reimpostazione delle password. Per ulteriori informazioni, consulta [Modifica le impostazioni dell&#39;account](../../features/administration/edit-account-settings.md).
1. Sotto **[!UICONTROL Login]**, seleziona lo stato desiderato:
   * **[!UICONTROL Active]:**  Gli utenti attivi possono accedere [!DNL Audience Manager] e dispongono delle autorizzazioni concesse dall&#39;iscrizione al gruppo.
   * **[!UICONTROL Deactivated]:**  Gli utenti disattivati non possono accedere [!DNL Audience Manager] e non dispongono di autorizzazioni. Se disattivi gli utenti, le loro informazioni utente rimangono in [!DNL Audience Manager] e puoi semplicemente riattivarli, se necessario. Se rimuovi gli utenti, devi ricrearli se devono utilizzare [!DNL Audience Manager] anche in futuro.
   * **[!UICONTROL Expired]:** La password di un utente è più vecchia di 90 giorni.
   * **[!UICONTROL Pending]:** L’utente dispone di una password temporanea, come dopo una reimpostazione della password o come nuovo account, e non ha ancora impostato una password permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativi di accesso non corretti bloccheranno un utente.
1. Sotto **[!UICONTROL Assigned Groups]**, dall’elenco a discesa, seleziona i gruppi desiderati a cui desideri assegnare l’utente.
Per ulteriori informazioni su gruppi e autorizzazioni, consulta [Creare un gruppo](../../features/administration/administration-overview.md#create-group).
1. Clic **[!UICONTROL Save]**.

## Creare un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La gestione degli account utente è in corso di spostamento al [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti gli Audienci Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [Migrazione degli utenti Audience Manager ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione sparirà.

A *gruppo* è una raccolta di utenti che condividono i diritti di accesso a [!UICONTROL destination], [!UICONTROL segment], e [!UICONTROL trait] oggetti. È possibile limitare i gruppi solo a singoli oggetti o concedere loro un accesso ampio a combinazioni di oggetti diversi.

<!-- t_create_groups.xml -->

Per creare un gruppo:

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Clic  ![](assets/icon_add.png) per aprire [!UICONTROL Group Settings] pagina.
3. In [!UICONTROL Group Details]:
   * Denomina il gruppo.
   * Fornisci una breve descrizione del gruppo.
4. In entrata [!UICONTROL Group Members], fare clic su un utente da **[!UICONTROL Add Users]** opzioni per aggiungerle al gruppo.
5. In entrata [!UICONTROL Group Permissions], seleziona un [caratteristica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md), o [destinazione](../../features/destinations/destinations.md) da **[!UICONTROL Add Object]**.
Viene visualizzata una finestra di autorizzazioni per l&#39;oggetto selezionato.
6. Selezionare la casella di controllo relativa alle autorizzazioni che si desidera assegnare ai membri del gruppo.
7. *(Facoltativo)* Assegna [Autorizzazioni wild card](../../features/administration/administration-overview.md#wild-card-permissions) al gruppo.
8. Clic **[!UICONTROL Save Group]**.

## Informazioni [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La gestione degli account utente è in corso di spostamento al [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti gli Audienci Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [Migrazione degli utenti Audience Manager ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione sparirà.

Semplificare la gestione dei diritti dei gruppi con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] concedere ai membri del gruppo l&#39;accesso automatico a ogni origine dati associata a un [!UICONTROL segment], [!UICONTROL destination], o [!UICONTROL trait]. Per confronto, le autorizzazioni regolari ti consentono solo di assegnare specifiche [!UICONTROL data sources] all&#39;oggetto. E, quando aggiungi nuovo [!UICONTROL data sources], i membri del gruppo non hanno accesso a queste nuove origini.

Devi aprire le autorizzazioni del gruppo e assegnare le nuove [!UICONTROL data sources] al gruppo. [!UICONTROL Wild Card Permissions] ti consente di evitare questo manuale [!UICONTROL data source] processo di aggiornamento. Gruppi con [!UICONTROL Wild Card Permissions] accesso a nuovi [!UICONTROL data sources] senza autorizzazione esplicita.

![](assets/wild-card.png)

Leggi di seguito per una descrizione di ciò che ogni [!UICONTROL wildcard permission] significa:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Gli utenti possono selezionare [!UICONTROL traits] come linea di base per [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Gli utenti possono modificare tutte [!UICONTROL traits] all’interno del loro account aziendale.
* `VIEW_ALL_TRAITS` - Gli utenti possono visualizzare tutto [!UICONTROL traits] all’interno del loro account aziendale.
* `DELETE_ALL_TRAITS` - Gli utenti possono eliminare tutto [!UICONTROL traits] all’interno del loro account aziendale.
* `CREATE_ALL_ALGO_TRAITS` - Gli utenti possono creare [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Gli utenti possono aggiungere [!UICONTROL traits] appartenere alla loro azienda a [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Gli utenti possono creare [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Gli utenti dispongono dell’autorizzazione per visualizzare [!UICONTROL models] appartenenti alla loro società.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Gli utenti possono visualizzare tutte le [!UICONTROL derived signals] appartenenti alla loro società.
* `CREATE_DERIVED_SIGNALS` - Gli utenti possono creare [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Gli utenti possono modificare tutte le [!UICONTROL derived signals] appartenenti alla loro società.
* `DELETE_DERIVED_SIGNALS` - Gli utenti possono eliminare [!UICONTROL derived signals] appartenenti alla loro società.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Gli utenti possono modificare tutte le [!UICONTROL destinations] all’interno del loro account aziendale.
* `CREATE_DESTINATIONS` - Gli utenti possono creare [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Gli utenti possono visualizzare tutte le [!UICONTROL destinations] all’interno del loro account aziendale.
* `DELETE_ALL_DESTINATIONS` - Gli utenti possono eliminare tutte le [!UICONTROL destinations] all’interno del loro account aziendale.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sul proprio [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sul proprio [!UICONTROL Audience Lab] gruppi di test.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Gli utenti possono creare segmenti.
* `DELETE_ALL_SEGMENTS` - Gli utenti possono eliminare tutti i segmenti impostati all’interno dell’account aziendale.
* `MAP_ALL_TO_DESTINATIONS` - Gli utenti possono mappare qualsiasi segmento appartenente alla loro azienda sulle destinazioni.
* `EDIT_ALL_SEGMENTS` - Gli utenti possono modificare tutti i segmenti impostati all’interno dell’account aziendale.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gli utenti possono selezionare i segmenti come linea di base per i modelli.
* `VIEW_ALL_SEGMENTS` - Gli utenti possono visualizzare tutti i segmenti impostati all’interno dell’account aziendale.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Possibilità di visualizzare tutti i segnali acquisiti in [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casi d&#39;uso {#use-cases}

### Monitoraggio dell’accesso degli utenti {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] può aiutarti a monitorare lo stato di accesso dell’utente, fornendoti un’immagine chiara di chi può accedere alla tua istanza di Audience Manager.

A seconda dei requisiti aziendali, puoi abilitare e disabilitare gli account utente in base alle esigenze.

![monitor-user-access](assets/monitor-user-access.png)

### Garantire la protezione dell&#39;accesso per i dati sensibili [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Puoi configurare [!UICONTROL Role-Based Access Control] a [!UICONTROL trait], segmento e [!UICONTROL destination] livello, per ciascun gruppo di utenti.

Questa funzionalità consente di gestire il modo in cui gli utenti visualizzano, creano, leggono, scrivono e modificano set di dati specifici, nonché di impedire agli utenti di accedere ai set di dati che non dovrebbero essere disponibili.

![protezione dell&#39;accesso](assets/access-protection.png)
