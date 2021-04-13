---
description: Le opzioni del menu Amministrazione consentono di creare utenti di Audience Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
keywords: rback;RBAC;basato su ruolo;basato su ruolo;controlli di accesso basati su ruolo
seo-description: Le opzioni del menu Amministrazione consentono di creare utenti di Audience Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
seo-title: Amministrazione
solution: Audience Manager
title: Amministrazione
topic-edit: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Amministrazione
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 2%

---

# [!UICONTROL Administration] (controlli RBAC)  {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La gestione dell&#39;account utente sta passando all&#39; [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti di Audience Manager adottino immediatamente le misure necessarie descritte in questo articolo: [Audience Manager di migrazione degli utenti ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, le sezioni di gestione utenti di questo documento spariranno.


Le opzioni del menu [!UICONTROL Administration] consentono di creare utenti di Audience Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).

I clienti aziendali che utilizzano [!DNL Audience Manager] hanno bisogno di una piattaforma di gestione dati per tutti i loro dati, ma devono essere in grado di controllare la visibilità dei diversi elementi dati su specifiche unità aziendali. Puoi eseguire questa operazione utilizzando le autorizzazioni del gruppo, denominate anche [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilizza i gruppi per assegnare le autorizzazioni. Le autorizzazioni non vengono assegnate a livello di utente. Le autorizzazioni del gruppo sono legate a oggetti ([!UICONTROL traits], segmenti, ecc.) e alle azioni eseguibili su tali oggetti (modifica, visualizzazione, ecc.). Questi controlli sono disponibili anche tramite le API REST di Audience Manager. Consulta [Gestione utente](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gestione dei gruppi](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) e [Gestione delle autorizzazioni](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) metodi API.

## Creare utenti {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La gestione dell&#39;account utente sta passando all&#39; [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti di Audience Manager adottino immediatamente le misure necessarie descritte in questo articolo: [Audience Manager di migrazione degli utenti ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, la sezione gestione utenti di questo documento verrà rimossa.

Crea gli utenti in [!DNL Audience Manager] e specifica i dettagli utente, lo stato di accesso e assegna gli utenti ai gruppi.

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Fare clic su ![](assets/icon_add.png) per visualizzare la pagina [!UICONTROL Create New User].
1. Sotto **[!UICONTROL User Details]**, compila i campi:
   * **[!UICONTROL Username]:** Specifica un nome utente univoco, ad Audience Manager.
   * **[!UICONTROL First Name]:** specifica il nome dell’utente.
   * **[!UICONTROL Last Name]:** specifica il cognome dell’utente.
   * **[!UICONTROL Email Address]:** specifica l’indirizzo e-mail dell’utente. [!DNL Audience Manager] non invia notifiche regolari agli utenti. [!DNL Audience Manager] gli amministratori hanno accesso agli indirizzi e-mail degli utenti e possono inviare manualmente gli utenti tramite e-mail in base alle esigenze. Ad esempio, se un utente dimentica la password, l’indirizzo e-mail specificato in questo campo viene utilizzato per inviare una password temporanea e istruzioni per reimpostare la password.
   * **[!UICONTROL Phone Number]:** specifica il numero di telefono dell’utente.
   * **[!UICONTROL Is Admin]:** specifica se l’utente è un  [!DNL Audience Manager] amministratore. Gli utenti amministratori possono gestire gli utenti (creare, modificare, ecc.) e gruppi (creazione, assegnazione di autorizzazioni, ecc.). Gli utenti non amministratori possono controllare solo i propri profili utente, inclusi la modifica dei propri indirizzi e-mail e la reimpostazione delle proprie password. Per ulteriori informazioni, consulta [Modifica impostazioni account](../../features/administration/edit-account-settings.md).
1. In **[!UICONTROL Login]**, seleziona lo stato desiderato:
   * **[!UICONTROL Active]:**  Gli utenti attivi possono accedere  [!DNL Audience Manager] e disporre delle autorizzazioni concesse dall’appartenenza al gruppo.
   * **[!UICONTROL Deactivated]:**  Gli utenti disattivati non possono accedere  [!DNL Audience Manager] e non dispongono di autorizzazioni. Se disattivi gli utenti, le relative informazioni utente rimangono in [!DNL Audience Manager] e puoi semplicemente riattivarle, se necessario. Se rimuovi gli utenti, devi ricrearli se in futuro dovranno utilizzare nuovamente [!DNL Audience Manager].
   * **[!UICONTROL Expired]:** la password di un utente è maggiore di 90 giorni.
   * **[!UICONTROL Pending]:** l’utente dispone di una password temporanea, come dopo il reset della password o come account nuovo, e non ha ancora impostato una password permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativi di accesso errati bloccheranno un utente.
1. Nell’elenco a discesa **[!UICONTROL Assigned Groups]**, seleziona i gruppi desiderati a cui assegnare l’utente.
Per ulteriori informazioni sui gruppi e le autorizzazioni, consulta [Creare un gruppo](../../features/administration/administration-overview.md#create-group).
1. Clic **[!UICONTROL Save]**.

## Crea un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La gestione dell&#39;account utente sta passando all&#39; [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti i clienti di Audience Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [Audience Manager di migrazione degli utenti ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione sparirà.

Un *gruppo* è un insieme di utenti che condividono i diritti di accesso agli oggetti [!UICONTROL destination], [!UICONTROL segment] e [!UICONTROL trait]. È possibile limitare i gruppi a singoli oggetti o consentire loro un ampio accesso a combinazioni di oggetti diversi.

<!-- t_create_groups.xml -->

Per creare un gruppo:

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Fai clic su ![](assets/icon_add.png) per aprire la pagina [!UICONTROL Group Settings].
3. In [!UICONTROL Group Details]:
   * Denomina il gruppo.
   * Fornisci una breve descrizione del gruppo.
4. In [!UICONTROL Group Members], fai clic su un utente tra le opzioni **[!UICONTROL Add Users]** per aggiungerlo al gruppo.
5. In [!UICONTROL Group Permissions], seleziona un [tratto](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md) o [destinazione](../../features/destinations/destinations.md) da **[!UICONTROL Add Object]**.
Viene visualizzata una finestra di autorizzazione per l’oggetto selezionato.
6. Selezionare la casella di controllo relativa alle autorizzazioni che si desidera assegnare ai membri del gruppo.
7. *(Facoltativo)* Assegna  [permessi con caratteri jolly ](../../features/administration/administration-overview.md#wild-card-permissions) al gruppo.
8. Clic **[!UICONTROL Save Group]**.

## Informazioni [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La gestione dell&#39;account utente sta passando all&#39; [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti i clienti di Audience Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [Audience Manager di migrazione degli utenti ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione sparirà.

Semplifica la gestione dei diritti di gruppo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] consente ai membri del gruppo di accedere automaticamente a ogni origine dati associata a un  [!UICONTROL segment],  [!UICONTROL destination], o  [!UICONTROL trait]. A titolo di confronto, le autorizzazioni regolari consentono solo di assegnare [!UICONTROL data sources] specifici a uno di questi oggetti. Inoltre, quando si aggiunge un nuovo [!UICONTROL data sources], i membri del gruppo non hanno accesso a queste nuove sorgenti.

È necessario aprire le autorizzazioni del gruppo e assegnare al gruppo i nuovi [!UICONTROL data sources]. [!UICONTROL Wild Card Permissions] evita questo processo di  [!UICONTROL data source] aggiornamento manuale. I gruppi con [!UICONTROL Wild Card Permissions] possono accedere al nuovo [!UICONTROL data sources] senza autorizzazione esplicita.

![](assets/wild-card.png)

Leggi di seguito una descrizione del significato di ciascun [!UICONTROL wildcard permission]:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Gli utenti possono selezionare  [!UICONTROL traits] come linea di base per  [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Gli utenti possono modificare tutte le  [!UICONTROL traits] impostazioni all’interno del proprio account aziendale.
* `VIEW_ALL_TRAITS` - Gli utenti possono visualizzare tutte le  [!UICONTROL traits] impostazioni all’interno del proprio account aziendale.
* `DELETE_ALL_TRAITS` - Gli utenti possono eliminare tutte le  [!UICONTROL traits] configurazioni all’interno del proprio account aziendale.
* `CREATE_ALL_ALGO_TRAITS` - Gli utenti possono creare  [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Gli utenti possono aggiungere uno qualsiasi degli elementi  [!UICONTROL traits] appartenenti alla propria azienda a  [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Gli utenti possono creare  [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` - Si  [!UICONTROL wildcard permission] riferisce a funzionalità obsolete e verrà rimosso dall’interfaccia utente di Audience Manager a breve.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Gli utenti hanno il permesso di visualizzare  [!UICONTROL models] l&#39;appartenenza alla propria azienda.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Gli utenti possono visualizzare tutti gli  [!UICONTROL derived signals] appartenenti alla propria azienda.
* `CREATE_DERIVED_SIGNALS` - Gli utenti possono creare  [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Gli utenti possono modificare tutte le  [!UICONTROL derived signals] proprietà della propria azienda.
* `DELETE_DERIVED_SIGNALS` - Gli utenti possono eliminare uno qualsiasi dei  [!UICONTROL derived signals] membri della propria azienda.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Gli utenti possono modificare tutta la  [!UICONTROL destinations] configurazione all’interno del proprio account aziendale.
* `CREATE_DESTINATIONS` - Gli utenti possono creare  [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Gli utenti possono visualizzare tutte le  [!UICONTROL destinations] impostazioni all’interno del proprio account aziendale.
* `DELETE_ALL_DESTINATIONS` - Gli utenti possono eliminare tutte le  [!UICONTROL destinations] impostazioni all’interno del proprio account aziendale.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Gli utenti possono eseguire tutte le operazioni (visualizzare, creare, modificare, eliminare) sul proprio  [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gli utenti possono eseguire tutte le operazioni (visualizzare, creare, modificare, eliminare) sui propri gruppi di  [!UICONTROL Audience Lab] test.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Gli utenti possono creare segmenti.
* `DELETE_ALL_SEGMENTS` - Gli utenti possono eliminare tutti i segmenti configurati all’interno del loro account aziendale.
* `MAP_ALL_TO_DESTINATIONS` - Gli utenti possono mappare alle destinazioni uno qualsiasi dei segmenti appartenenti alla propria azienda.
* `EDIT_ALL_SEGMENTS` - Gli utenti possono modificare tutti i segmenti configurati all’interno del loro account aziendale.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gli utenti possono selezionare i segmenti come linea di base per i modelli.
* `VIEW_ALL_SEGMENTS` - Gli utenti possono visualizzare tutti i segmenti configurati all’interno del loro account aziendale.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Gli utenti possono visualizzare tutti i segnali acquisiti in  [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casi d&#39;uso {#use-cases}

### Monitoraggio dell’accesso degli utenti {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] può aiutarti a monitorare lo stato di accesso degli utenti, fornendo un&#39;immagine chiara di chi può accedere alla tua istanza di Audience Manager.

A seconda delle esigenze aziendali, puoi abilitare e disabilitare gli account utente in base alle tue esigenze.

![monitoraggio-accesso utente](assets/monitor-user-access.png)

### Protezione dell&#39;accesso per sensibile [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Puoi configurare [!UICONTROL Role-Based Access Control] a livello di [!UICONTROL trait], segmento e [!UICONTROL destination] per ciascun gruppo di utenti.

Questa funzionalità consente di gestire le modalità di visualizzazione, creazione, lettura, scrittura e modifica degli utenti di set di dati specifici e persino di impedire agli utenti di accedere a set di dati che non dovrebbero essere disponibili.

![protezione dell&#39;accesso](assets/access-protection.png)
