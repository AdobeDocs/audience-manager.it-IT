---
description: Le opzioni del menu Amministrazione consentono di creare utenti  Audience Manager e assegnarli ai gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
keywords: rback;RBAC;basato su ruoli;basato su ruoli;controlli di accesso basati su ruoli
seo-description: Le opzioni del menu Amministrazione consentono di creare utenti  Audience Manager e assegnarli ai gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
seo-title: Amministrazione
solution: Audience Manager
title: Amministrazione
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
translation-type: tm+mt
source-git-commit: 55cb69bad1f369ed3b58bece54aebdca4b14f7a7
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 2%

---


# [!UICONTROL Administration] (controlli RBAC)  {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La gestione dell&#39;account utente sta passando al Admin Console [](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti  Audience Manager adottino immediatamente le misure necessarie descritte in questo articolo: [ migrazione degli utenti di Audience Manager a  Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, le sezioni relative alla gestione degli utenti di questo documento verranno eliminate.


Le opzioni del menu [!UICONTROL Administration] consentono di creare utenti  Audience Manager e di assegnarli ai gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).

I clienti Enterprise che utilizzano [!DNL Audience Manager] hanno bisogno di una piattaforma di gestione dati per tutti i loro dati, ma devono essere in grado di controllare la visibilità dei diversi elementi di dati su unità aziendali specifiche. A tal fine, potete utilizzare le autorizzazioni del gruppo, denominate anche [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilizza i gruppi per assegnare le autorizzazioni. Le autorizzazioni non vengono assegnate a livello di utente. Le autorizzazioni del gruppo sono associate a oggetti ([!UICONTROL traits], segmenti, ecc.) e alle azioni che è possibile eseguire su tali oggetti (modifica, visualizzazione, ecc.). Questi controlli sono disponibili anche tramite le API REST  Audience Manager. Vedere [Gestione utente](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gestione dei gruppi](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) e [Gestione delle autorizzazioni](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) Metodi API.

## Crea utenti {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La gestione dell&#39;account utente sta passando al Admin Console [](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti  Audience Manager adottino immediatamente le misure necessarie descritte in questo articolo: [ migrazione degli utenti di Audience Manager a  Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, la sezione Gestione utenti di questo documento verrà rimossa.

Create gli utenti in [!DNL Audience Manager] e specificate i dettagli utente, lo stato di accesso e assegnate gli utenti ai gruppi.

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Fare clic su ![](assets/icon_add.png) per visualizzare la pagina [!UICONTROL Create New User].
1. In **[!UICONTROL User Details]**, compilare i campi:
   * **[!UICONTROL Username]:** Specificate un nome utente univoco per  Audience Manager.
   * **[!UICONTROL First Name]:** Specificate il nome dell’utente.
   * **[!UICONTROL Last Name]:** Specificate il cognome dell’utente.
   * **[!UICONTROL Email Address]:** Specificate l&#39;indirizzo e-mail dell&#39;utente. [!DNL Audience Manager] non invia notifiche regolari agli utenti. [!DNL Audience Manager] gli amministratori hanno accesso agli indirizzi e-mail degli utenti e possono inviare manualmente gli utenti come necessario. Ad esempio, se un utente dimentica la password, l&#39;indirizzo e-mail specificato in questo campo viene utilizzato per inviare una password temporanea e le istruzioni per reimpostare la password.
   * **[!UICONTROL Phone Number]:** Specificate il numero di telefono dell&#39;utente.
   * **[!UICONTROL Is Admin]:** Specificate se l’utente è un  [!DNL Audience Manager] amministratore. Gli utenti amministratori possono gestire gli utenti (creare, modificare, ecc.) e i gruppi (creare, assegnare le autorizzazioni, ecc.). Gli utenti non amministratori possono controllare solo i propri profili utente, inclusi la modifica degli indirizzi e-mail e la reimpostazione delle proprie password. Per ulteriori informazioni, vedere [Modifica delle impostazioni dell&#39;account](../../features/administration/edit-account-settings.md).
1. In **[!UICONTROL Login]**, selezionare lo stato desiderato:
   * **[!UICONTROL Active]:Gli utenti**  attivi possono accedere  [!DNL Audience Manager] e ottenere le autorizzazioni per appartenenza al gruppo.
   * **[!UICONTROL Deactivated]:Gli utenti**  disattivati non possono accedere  [!DNL Audience Manager] e non dispongono di alcuna autorizzazione. Se disattivate gli utenti, le relative informazioni restano in [!DNL Audience Manager] e potete semplicemente riattivarle, se necessario. Se rimuovete degli utenti, dovete ricrearli se in futuro dovranno usare nuovamente [!DNL Audience Manager].
   * **[!UICONTROL Expired]:** Una password utente ha più di 90 giorni.
   * **[!UICONTROL Pending]:** L&#39;utente dispone di una password temporanea, come dopo il ripristino della password o come nuovo account, e non ha ancora impostato una password permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativi di accesso errati bloccheranno un utente.
1. In **[!UICONTROL Assigned Groups]**, dall&#39;elenco a discesa, selezionate i gruppi a cui desiderate assegnare l&#39;utente.
Per ulteriori informazioni su gruppi e autorizzazioni, vedere [Creare un gruppo](../../features/administration/administration-overview.md#create-group).
1. Clic **[!UICONTROL Save]**.

## Creare un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La gestione dell&#39;account utente sta passando al Admin Console [](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti i clienti  Audience Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [ migrazione degli utenti di Audience Manager a  Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione verrà rimossa.

Un *gruppo* è un insieme di utenti che condividono i diritti di accesso agli oggetti [!UICONTROL destination], [!UICONTROL segment] e [!UICONTROL trait]. È possibile limitare i gruppi a un solo oggetto o consentire loro un ampio accesso a combinazioni di oggetti diversi.

<!-- t_create_groups.xml -->

Per creare un gruppo:

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Fare clic su ![](assets/icon_add.png) per aprire la pagina [!UICONTROL Group Settings].
3. In [!UICONTROL Group Details]:
   * Denominate il gruppo.
   * Fornite una breve descrizione del gruppo.
4. In [!UICONTROL Group Members], fare clic su un utente tra le opzioni **[!UICONTROL Add Users]** per aggiungerlo al gruppo.
5. In [!UICONTROL Group Permissions], selezionare una [caratteristica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md) o [destinazione](../../features/destinations/destinations.md) da **[!UICONTROL Add Object]**.
Viene visualizzata una finestra di autorizzazioni per l&#39;oggetto selezionato.
6. Selezionate la casella di controllo per le autorizzazioni che desiderate assegnare ai membri del gruppo.
7. *(Facoltativo)* Assegnate  [le ](../../features/administration/administration-overview.md#wild-card-permissions) autorizzazioni per le schede wild al gruppo.
8. Clic **[!UICONTROL Save Group]**.

## Informazioni su [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La gestione dell&#39;account utente sta passando al Admin Console [](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti i clienti  Audience Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [ migrazione degli utenti di Audience Manager a  Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione verrà rimossa.

Semplificate la gestione dei diritti di gruppo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] consente ai membri del gruppo di accedere automaticamente a ogni origine dati associata a un  [!UICONTROL segment],  [!UICONTROL destination] o  [!UICONTROL trait]. A titolo di confronto, le autorizzazioni regolari consentono di assegnare solo [!UICONTROL data sources] specifici a uno di questi oggetti. Inoltre, quando aggiungete nuove [!UICONTROL data sources], i membri del gruppo non hanno accesso a queste nuove origini.

È necessario aprire le autorizzazioni del gruppo e assegnare i nuovi [!UICONTROL data sources] al gruppo. [!UICONTROL Wild Card Permissions] evitate questo processo di  [!UICONTROL data source] aggiornamento manuale. I gruppi con [!UICONTROL Wild Card Permissions] possono accedere al nuovo [!UICONTROL data sources] senza autorizzazione esplicita.

![](assets/wild-card.png)

Leggi di seguito per una descrizione del significato di ciascun [!UICONTROL wildcard permission]:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Gli utenti possono selezionare  [!UICONTROL traits] come linea di base per  [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Gli utenti possono modificare tutte le  [!UICONTROL traits] impostazioni all&#39;interno del proprio account aziendale.
* `VIEW_ALL_TRAITS` - Gli utenti possono visualizzare tutte le  [!UICONTROL traits] impostazioni all&#39;interno del proprio account società.
* `DELETE_ALL_TRAITS` - Gli utenti possono eliminare tutte le  [!UICONTROL traits] impostazioni all&#39;interno del proprio account società.
* `CREATE_ALL_ALGO_TRAITS` - Gli utenti possono creare  [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Gli utenti possono aggiungere uno qualsiasi degli  [!UICONTROL traits] appartenenti alla propria società a  [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Gli utenti possono creare  [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` - Si  [!UICONTROL wildcard permission] riferisce a funzionalità obsolete e verrà rimosso dall&#39;interfaccia utente del Audience Manager  a breve.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Gli utenti dispongono dell&#39;autorizzazione per visualizzare  [!UICONTROL models] l&#39;appartenenza alla propria società.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Gli utenti possono visualizzare tutti gli  [!UICONTROL derived signals] appartenenti alla propria società.
* `CREATE_DERIVED_SIGNALS` - Gli utenti possono creare  [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Gli utenti possono modificare tutti gli  [!UICONTROL derived signals] appartenenti alla propria società.
* `DELETE_DERIVED_SIGNALS` - Gli utenti possono eliminare qualsiasi  [!UICONTROL derived signals] membro della propria società.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Gli utenti possono modificare tutta la  [!UICONTROL destinations] configurazione all&#39;interno del proprio account aziendale.
* `CREATE_DESTINATIONS` - Gli utenti possono creare  [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Gli utenti possono visualizzare tutta la  [!UICONTROL destinations] configurazione all&#39;interno del proprio account aziendale.
* `DELETE_ALL_DESTINATIONS` - Gli utenti possono eliminare tutta la  [!UICONTROL destinations] configurazione all’interno del loro account società.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Gli utenti possono fare tutto (visualizzare, creare, modificare, eliminare) sul  [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gli utenti possono eseguire tutte le operazioni (visualizzare, creare, modificare, eliminare) sui propri gruppi di  [!UICONTROL Audience Lab] test.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Gli utenti possono creare segmenti.
* `DELETE_ALL_SEGMENTS` - Gli utenti possono eliminare tutti i segmenti configurati nel loro account società.
* `MAP_ALL_TO_DESTINATIONS` - Gli utenti possono mappare i segmenti appartenenti alla propria società alle destinazioni.
* `EDIT_ALL_SEGMENTS` - Gli utenti possono modificare tutti i segmenti configurati all&#39;interno del loro account società.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gli utenti possono selezionare i segmenti come linea di base per i modelli.
* `VIEW_ALL_SEGMENTS` - Gli utenti possono visualizzare tutti i segmenti configurati nel loro account società.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Gli utenti possono visualizzare tutti i segnali acquisiti in  [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casi d&#39;uso {#use-cases}

### Monitoraggio dell&#39;accesso degli utenti {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] può essere utile per monitorare lo stato di accesso degli utenti, fornendo un&#39;immagine chiara di chi può accedere all&#39;istanza del Audience Manager .

A seconda delle esigenze aziendali, potete attivare e disattivare gli account utente in base alle esigenze.

![monitor-accesso utente](assets/monitor-user-access.png)

### Protezione dell&#39;accesso per [!UICONTROL Data Sources] {#protect-sensitive-data-sources} sensibili

È possibile configurare [!UICONTROL Role-Based Access Control] a [!UICONTROL trait], segmento e [!UICONTROL destination] livello, per ciascun gruppo di utenti.

Questa funzionalità consente di gestire il modo in cui gli utenti visualizzano, creano, leggono, scrivono e modificano specifici set di dati, e persino di impedire agli utenti di accedere ai set di dati che non dovrebbero essere disponibili per loro.

![protezione dell&#39;accesso](assets/access-protection.png)
