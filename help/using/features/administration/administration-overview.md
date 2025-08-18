---
description: Le opzioni del menu Amministrazione consentono di creare utenti Audience Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
keywords: rbac;RBAC;basato su ruoli;basato su ruoli;controlli di accesso basati su ruoli
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Amministrazione
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] (controlli RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> È in corso lo spostamento della gestione degli account utente a [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti Audience Manager adottino immediatamente le misure necessarie descritte in questo articolo: [Migrazione degli utenti Audience Manager ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, le sezioni di gestione utenti di questo documento spariranno.

>[!IMPORTANT]
>
> Prima di poter utilizzare [!DNL RBAC], questa funzione deve essere abilitata da Adobe per la tua organizzazione. Rivolgiti al team del tuo account per richiedere l&#39;attivazione di [!DNL RBAC] o contatta l&#39;Assistenza clienti.


Le opzioni del menu [!UICONTROL Administration] consentono di creare utenti Audience Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).

I clienti aziendali che utilizzano [!DNL Audience Manager] hanno bisogno di una piattaforma di gestione dati per tutti i loro dati, ma devono essere in grado di controllare la visibilità dei diversi elementi dati per specifiche unità aziendali. Puoi eseguire questa operazione utilizzando le autorizzazioni del gruppo, dette anche [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilizza i gruppi per assegnare le autorizzazioni. Le autorizzazioni non vengono assegnate a livello di utente. Le autorizzazioni del gruppo sono legate agli oggetti ([!UICONTROL traits], segmenti e così via) e alle azioni che è possibile eseguire su tali oggetti (modifica, visualizzazione e così via). Questi controlli sono disponibili anche tramite le API REST di Audience Manager. Consulta i metodi API [Gestione utente](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gestione gruppi](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) e [Gestione autorizzazioni](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md).

## Crea utenti {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> È in corso lo spostamento della gestione degli account utente a [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti Audience Manager adottino immediatamente le misure necessarie descritte in questo articolo: [Migrazione degli utenti Audience Manager ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, la sezione sulla gestione degli utenti di questo documento sparirà.
> 
>Creare gli utenti in [!DNL Audience Manager] e specificare i dettagli utente, lo stato di accesso e assegnare gli utenti ai gruppi.

1. Fare clic su **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Fare clic su ![](assets/icon_add.png) per visualizzare la pagina [!UICONTROL Create New User].
1. In **[!UICONTROL User Details]**, compila i campi:
   * **[!UICONTROL Username]:** Specificare un nome utente univoco per Audience Manager.
   * **[!UICONTROL First Name]:** Specificare il nome dell&#39;utente.
   * **[!UICONTROL Last Name]:** Specificare il cognome dell&#39;utente.
   * **[!UICONTROL Email Address]:** Specifica l&#39;indirizzo e-mail dell&#39;utente. [!DNL Audience Manager] non invia notifiche regolari agli utenti. Gli amministratori di [!DNL Audience Manager] hanno accesso agli indirizzi e-mail degli utenti e possono inviare manualmente e-mail agli utenti in base alle esigenze. Ad esempio, se un utente dimentica la propria password, l’indirizzo e-mail specificato in questo campo viene utilizzato per inviare una password temporanea e istruzioni per reimpostare la password.
   * **[!UICONTROL Phone Number]:** Specificare il numero di telefono dell&#39;utente.
   * **[!UICONTROL Is Admin]:** Specificare se l&#39;utente è un amministratore [!DNL Audience Manager]. Gli utenti amministratori possono gestire utenti (creare, modificare, ecc.) e gruppi (creare, assegnare autorizzazioni, ecc.). Gli utenti non amministratori possono controllare solo i propri profili utente, inclusa la modifica degli indirizzi e-mail e la reimpostazione delle password. Per ulteriori informazioni, vedere [Modifica impostazioni account](../../features/administration/edit-account-settings.md).
1. In **[!UICONTROL Login]**, selezionare lo stato desiderato:
   * **[!UICONTROL Active]:** Gli utenti attivi possono accedere a [!DNL Audience Manager] e disporre delle autorizzazioni concesse dall&#39;appartenenza al gruppo.
   * **[!UICONTROL Deactivated]:** Gli utenti disattivati non possono accedere a [!DNL Audience Manager] e non dispongono di autorizzazioni. Se si disattivano gli utenti, le relative informazioni utente rimangono in [!DNL Audience Manager] e, se necessario, è possibile riattivarle semplicemente. Se rimuovi gli utenti, devi ricrearli se in futuro dovranno utilizzare di nuovo [!DNL Audience Manager].
   * **[!UICONTROL Expired]:** La password di un utente è più vecchia di 90 giorni.
   * **[!UICONTROL Pending]:** L&#39;utente dispone di una password temporanea, come dopo una reimpostazione della password o come nuovo account, e non ha ancora impostato una password permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativi di accesso non corretti bloccheranno un utente.
1. In **[!UICONTROL Assigned Groups]**, dall&#39;elenco a discesa, selezionare i gruppi desiderati a cui si desidera assegnare l&#39;utente.
Per ulteriori informazioni sui gruppi e sulle autorizzazioni, vedere [Creare un gruppo](../../features/administration/administration-overview.md#create-group).
1. Fare clic su **[!UICONTROL Save]**.

## Crea un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> È in corso lo spostamento della gestione degli account utente a [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti i clienti Audience Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [Migrazione degli utenti Audience Manager ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione sparirà.

Un *gruppo* è un insieme di utenti che condividono diritti di accesso a [!UICONTROL destination], [!UICONTROL segment] e [!UICONTROL trait] oggetti. È possibile limitare i gruppi solo a singoli oggetti o concedere loro un accesso ampio a combinazioni di oggetti diversi.

<!-- t_create_groups.xml -->

Per creare un gruppo:

1. Fare clic su **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Fare clic su ![](assets/icon_add.png) per aprire la pagina [!UICONTROL Group Settings].
3. In [!UICONTROL Group Details]:
   * Denomina il gruppo.
   * Fornisci una breve descrizione del gruppo.
4. In [!UICONTROL Group Members], fare clic su un utente delle opzioni **[!UICONTROL Add Users]** per aggiungerlo al gruppo.
5. In [!UICONTROL Group Permissions], selezionare una [caratteristica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md) o [destinazione](../../features/destinations/destinations.md) da **[!UICONTROL Add Object]**.
Viene visualizzata una finestra di autorizzazioni per l&#39;oggetto selezionato.
6. Selezionare la casella di controllo relativa alle autorizzazioni che si desidera assegnare ai membri del gruppo.
7. *(Facoltativo)* Assegna [Autorizzazioni wild card](../../features/administration/administration-overview.md#wild-card-permissions) al gruppo.
8. Fare clic su **[!UICONTROL Save Group]**.

## Informazioni su [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> È in corso lo spostamento della gestione degli account utente a [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti i clienti Audience Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [Migrazione degli utenti Audience Manager ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione sparirà.

Semplificare la gestione dei diritti dei gruppi con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] concedono ai membri del gruppo l&#39;accesso automatico a ogni origine dati associata a [!UICONTROL segment], [!UICONTROL destination] o [!UICONTROL trait]. Per confronto, le autorizzazioni regolari ti consentono di assegnare solo [!UICONTROL data sources] specifici a uno di questi oggetti. E quando si aggiunge un nuovo [!UICONTROL data sources], i membri del gruppo non hanno accesso a queste nuove origini.

Devi aprire le autorizzazioni del gruppo e assegnare i nuovi [!UICONTROL data sources] al gruppo. [!UICONTROL Wild Card Permissions] ti consente di evitare questo processo di aggiornamento manuale di [!UICONTROL data source]. I gruppi con [!UICONTROL Wild Card Permissions] possono accedere al nuovo [!UICONTROL data sources] senza autorizzazione esplicita.

![](assets/wild-card.png)

Per una descrizione del significato di ogni [!UICONTROL wildcard permission], leggere quanto segue:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Gli utenti possono selezionare [!UICONTROL traits] come previsione per [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Gli utenti possono modificare tutti i [!UICONTROL traits] configurati nel loro account aziendale.
* `VIEW_ALL_TRAITS` - Gli utenti possono visualizzare tutti i [!UICONTROL traits] configurati nel loro account aziendale.
* `DELETE_ALL_TRAITS` - Gli utenti possono eliminare tutti i [!UICONTROL traits] configurati nel loro account aziendale.
* `CREATE_ALL_ALGO_TRAITS` - Gli utenti possono creare [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Gli utenti possono aggiungere a [!UICONTROL traits] uno qualsiasi dei [!UICONTROL segments] appartenenti alla propria società.
* `CREATE_ALL_TRAITS` - Gli utenti possono creare [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Gli utenti dispongono dell&#39;autorizzazione per visualizzare [!UICONTROL models] appartenente alla propria società.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Gli utenti possono visualizzare tutti i [!UICONTROL derived signals] appartenenti alla loro azienda.
* `CREATE_DERIVED_SIGNALS` - Gli utenti possono creare [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Gli utenti possono modificare tutti i [!UICONTROL derived signals] appartenenti alla loro azienda.
* `DELETE_DERIVED_SIGNALS` - Gli utenti possono eliminare qualsiasi [!UICONTROL derived signals] appartenente alla propria società.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Gli utenti possono modificare tutti i [!UICONTROL destinations] configurati nel loro account aziendale.
* `CREATE_DESTINATIONS` - Gli utenti possono creare [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Gli utenti possono visualizzare tutti i [!UICONTROL destinations] configurati nel loro account aziendale.
* `DELETE_ALL_DESTINATIONS` - Gli utenti possono eliminare tutti i [!UICONTROL destinations] configurati nel loro account aziendale.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sul proprio [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gli utenti possono eseguire tutte le operazioni (visualizzare, creare, modificare, eliminare) sui gruppi di test [!UICONTROL Audience Lab].

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Gli utenti possono creare segmenti.
* `DELETE_ALL_SEGMENTS` - Gli utenti possono eliminare tutti i segmenti impostati nel loro account aziendale.
* `MAP_ALL_TO_DESTINATIONS` - Gli utenti possono mappare qualsiasi segmento appartenente alla propria azienda sulle destinazioni.
* `EDIT_ALL_SEGMENTS` - Gli utenti possono modificare tutti i segmenti impostati nel loro account aziendale.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gli utenti possono selezionare i segmenti come baseline per i modelli.
* `VIEW_ALL_SEGMENTS` - Gli utenti possono visualizzare tutti i segmenti impostati nel loro account aziendale.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Gli utenti possono visualizzare tutti i segnali acquisiti in [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casi d&#39;uso {#use-cases}

### Monitoraggio dell’accesso degli utenti {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] può aiutarti a monitorare lo stato di accesso degli utenti, fornendo un&#39;immagine chiara di chi può accedere alla tua istanza di Audience Manager.

A seconda dei requisiti aziendali, puoi abilitare e disabilitare gli account utente in base alle esigenze.

![monitor-user-access](assets/monitor-user-access.png)

### Garantire la protezione dell&#39;accesso per [!UICONTROL Data Sources] sensibili {#protect-sensitive-data-sources}

Puoi configurare [!UICONTROL Role-Based Access Control] a livello di [!UICONTROL trait], segmento e [!UICONTROL destination], per ogni gruppo di utenti.

Questa funzionalità consente di gestire il modo in cui gli utenti visualizzano, creano, leggono, scrivono e modificano set di dati specifici, nonché di impedire agli utenti di accedere ai set di dati che non dovrebbero essere disponibili.

![protezione accesso](assets/access-protection.png)
