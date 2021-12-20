---
description: Le opzioni del menu Amministrazione consentono di creare utenti di Audience Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).
keywords: rback;RBAC;basato su ruolo;basato su ruolo;controlli di accesso basati su ruolo
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

# [!UICONTROL Administration] (controlli RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La gestione degli account utente viene spostata in [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti di Audience Manager adottino immediatamente le misure necessarie descritte in questo articolo: [Audience Manager di migrazione degli utenti ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, le sezioni di gestione utenti di questo documento spariranno.


Le opzioni sotto [!UICONTROL Administration] consente di creare utenti di Audience Manager e assegnarli a gruppi. Puoi anche visualizzare i limiti (caratteristiche, segmenti, destinazioni e modelli).

Clienti aziendali che utilizzano [!DNL Audience Manager] hanno bisogno di una piattaforma di gestione dati unica per tutti i loro dati, ma devono essere in grado di controllare la visibilità dei diversi elementi dati a specifiche unità operative. Puoi eseguire questa operazione utilizzando le autorizzazioni del gruppo, denominate anche [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilizza i gruppi per assegnare le autorizzazioni. Le autorizzazioni non vengono assegnate a livello di utente. Le autorizzazioni del gruppo sono associate agli oggetti ([!UICONTROL traits], segmenti, ecc.) e alle azioni eseguibili su tali oggetti (modifica, visualizzazione, ecc.). Questi controlli sono disponibili anche tramite le API REST di Audience Manager. Vedi [Gestione utente](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gestione dei gruppi](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)e [Gestione delle autorizzazioni](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) Metodi API.

## Creare utenti {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La gestione degli account utente viene spostata in [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, è necessario che tutti i clienti di Audience Manager adottino immediatamente le misure necessarie descritte in questo articolo: [Audience Manager di migrazione degli utenti ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, la sezione gestione utenti di questo documento verrà rimossa.
Crea utenti in [!DNL Audience Manager] e specifica i dettagli utente, lo stato di accesso e assegna gli utenti ai gruppi.

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Fai clic su ![](assets/icon_add.png) per visualizzare [!UICONTROL Create New User] pagina.
1. Sotto **[!UICONTROL User Details]**, compila i campi:
   * **[!UICONTROL Username]:** Specifica un nome utente univoco, ad Audience Manager.
   * **[!UICONTROL First Name]:** Specifica il nome dell’utente.
   * **[!UICONTROL Last Name]:** Specifica il cognome dell’utente.
   * **[!UICONTROL Email Address]:** Specifica l’indirizzo e-mail dell’utente. [!DNL Audience Manager] non invia notifiche regolari agli utenti. [!DNL Audience Manager] gli amministratori hanno accesso agli indirizzi e-mail degli utenti e possono inviare manualmente gli utenti tramite e-mail in base alle esigenze. Ad esempio, se un utente dimentica la password, l’indirizzo e-mail specificato in questo campo viene utilizzato per inviare una password temporanea e istruzioni per reimpostare la password.
   * **[!UICONTROL Phone Number]:** Specifica il numero di telefono dell&#39;utente.
   * **[!UICONTROL Is Admin]:** Specifica se l&#39;utente è un [!DNL Audience Manager] amministratore. Gli utenti amministratori possono gestire gli utenti (creare, modificare, ecc.) e gruppi (creazione, assegnazione di autorizzazioni, ecc.). Gli utenti non amministratori possono controllare solo i propri profili utente, inclusi la modifica dei propri indirizzi e-mail e la reimpostazione delle proprie password. Per ulteriori informazioni, consulta [Modifica le impostazioni account](../../features/administration/edit-account-settings.md).
1. Sotto **[!UICONTROL Login]**, seleziona lo stato desiderato:
   * **[!UICONTROL Active]:**  Gli utenti attivi possono accedere [!DNL Audience Manager] e dispongono delle autorizzazioni concesse dall&#39;appartenenza al gruppo.
   * **[!UICONTROL Deactivated]:**  Gli utenti disattivati non possono accedere [!DNL Audience Manager] e non dispongono di autorizzazioni. Se disattivi gli utenti, le relative informazioni utente rimangono in [!DNL Audience Manager] e puoi semplicemente riattivarli, se necessario. Se rimuovi gli utenti, devi ricrearli se devono utilizzare [!DNL Audience Manager] di nuovo in futuro.
   * **[!UICONTROL Expired]:** La password di un utente è più vecchia di 90 giorni.
   * **[!UICONTROL Pending]:** L’utente dispone di una password temporanea, come dopo il ripristino della password o come nuovo account, e non ha ancora impostato una password permanente.
   * **[!UICONTROL Locked Out]:** 5 tentativi di accesso errati bloccheranno un utente.
1. Sotto **[!UICONTROL Assigned Groups]**, dall’elenco a discesa , seleziona i gruppi desiderati a cui assegnare l’utente.
Per ulteriori informazioni su gruppi e autorizzazioni, consulta [Creare un gruppo](../../features/administration/administration-overview.md#create-group).
1. Clic **[!UICONTROL Save]**.

## Crea un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La gestione degli account utente viene spostata in [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti i clienti di Audience Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [Audience Manager di migrazione degli utenti ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione sparirà.

A *gruppo* è una raccolta di utenti che condividono i diritti di accesso a [!UICONTROL destination], [!UICONTROL segment]e [!UICONTROL trait] oggetti. È possibile limitare i gruppi a singoli oggetti o consentire loro un ampio accesso a combinazioni di oggetti diversi.

<!-- t_create_groups.xml -->

Per creare un gruppo:

1. Clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Fai clic su  ![](assets/icon_add.png) per aprire [!UICONTROL Group Settings] pagina.
3. In [!UICONTROL Group Details]:
   * Denomina il gruppo.
   * Fornisci una breve descrizione del gruppo.
4. In [!UICONTROL Group Members], fai clic su un utente da **[!UICONTROL Add Users]** opzioni per aggiungerli al gruppo.
5. In [!UICONTROL Group Permissions], seleziona un [caratteristica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md)oppure [destinazione](../../features/destinations/destinations.md) da **[!UICONTROL Add Object]**.
Viene visualizzata una finestra di autorizzazione per l’oggetto selezionato.
6. Selezionare la casella di controllo relativa alle autorizzazioni che si desidera assegnare ai membri del gruppo.
7. *(Facoltativo)* Assegna [Autorizzazioni wild card](../../features/administration/administration-overview.md#wild-card-permissions) al gruppo.
8. Clic **[!UICONTROL Save Group]**.

## Comprensione [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La gestione degli account utente viene spostata in [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Per avviare la migrazione degli utenti, consigliamo a tutti i clienti di Audience Manager di adottare immediatamente le misure necessarie descritte in questo articolo: [Audience Manager di migrazione degli utenti ad Admin Console](admin-console-migration.md).
> 
> Dopo la migrazione di tutti i clienti, questa sezione sparirà.

Semplificare la gestione dei diritti di gruppo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] consentire ai membri del gruppo l&#39;accesso automatico a ogni origine dati associata a un [!UICONTROL segment], [!UICONTROL destination]oppure [!UICONTROL trait]. A titolo di confronto, le autorizzazioni regolari consentono solo di assegnare specifiche [!UICONTROL data sources] a uno di questi oggetti. E quando si aggiungono nuovi [!UICONTROL data sources], i membri del gruppo non hanno accesso a queste nuove sorgenti.

È necessario aprire le autorizzazioni del gruppo e assegnare le nuove [!UICONTROL data sources] al gruppo. [!UICONTROL Wild Card Permissions] consente di evitare questo manuale [!UICONTROL data source] processo di aggiornamento. Gruppi con [!UICONTROL Wild Card Permissions] accedere alle nuove [!UICONTROL data sources] senza autorizzazione esplicita.

![](assets/wild-card.png)

Leggi qui sotto per una descrizione di ogni [!UICONTROL wildcard permission] mezzi:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Gli utenti possono selezionare [!UICONTROL traits] come linea di base per [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Gli utenti possono modificare tutte le [!UICONTROL traits] istituito nel loro account aziendale.
* `VIEW_ALL_TRAITS` - Gli utenti possono visualizzare tutti [!UICONTROL traits] istituito nel loro account aziendale.
* `DELETE_ALL_TRAITS` - Gli utenti possono eliminare tutti [!UICONTROL traits] istituito nel loro account aziendale.
* `CREATE_ALL_ALGO_TRAITS` - Gli utenti possono creare [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Gli utenti possono aggiungere uno qualsiasi dei [!UICONTROL traits] appartenenti alla loro società [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Gli utenti possono creare [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Gli utenti dispongono dell&#39;autorizzazione per visualizzare [!UICONTROL models] di proprietà della loro azienda.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Gli utenti possono visualizzare tutti i [!UICONTROL derived signals] di proprietà della loro azienda.
* `CREATE_DERIVED_SIGNALS` - Gli utenti possono creare [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Gli utenti possono modificare tutte le [!UICONTROL derived signals] di proprietà della loro azienda.
* `DELETE_DERIVED_SIGNALS` - Gli utenti possono eliminare [!UICONTROL derived signals] di proprietà della loro azienda.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Gli utenti possono modificare tutte le [!UICONTROL destinations] istituito nel loro account aziendale.
* `CREATE_DESTINATIONS` - Gli utenti possono creare [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Gli utenti possono visualizzare tutti i [!UICONTROL destinations] istituito nel loro account aziendale.
* `DELETE_ALL_DESTINATIONS` - Gli utenti possono eliminare tutti i [!UICONTROL destinations] istituito nel loro account aziendale.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Gli utenti possono eseguire tutte le operazioni (visualizzare, creare, modificare, eliminare) [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Gli utenti possono eseguire tutte le operazioni (visualizzare, creare, modificare, eliminare) [!UICONTROL Audience Lab] gruppi di test.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Gli utenti possono creare segmenti.
* `DELETE_ALL_SEGMENTS` - Gli utenti possono eliminare tutti i segmenti configurati all’interno del loro account aziendale.
* `MAP_ALL_TO_DESTINATIONS` - Gli utenti possono mappare alle destinazioni uno qualsiasi dei segmenti appartenenti alla propria azienda.
* `EDIT_ALL_SEGMENTS` - Gli utenti possono modificare tutti i segmenti configurati all’interno del loro account aziendale.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Gli utenti possono selezionare i segmenti come linea di base per i modelli.
* `VIEW_ALL_SEGMENTS` - Gli utenti possono visualizzare tutti i segmenti configurati all’interno del loro account aziendale.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Gli utenti possono visualizzare tutti i segnali acquisiti in [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casi d&#39;uso {#use-cases}

### Monitoraggio dell’accesso utente {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] può aiutarti a monitorare lo stato di accesso degli utenti, fornendo un&#39;immagine chiara di chi può accedere alla tua istanza di Audience Manager.

A seconda delle esigenze aziendali, puoi abilitare e disabilitare gli account utente in base alle tue esigenze.

![monitoraggio-accesso utente](assets/monitor-user-access.png)

### Protezione dell&#39;accesso sensibile [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Puoi configurare [!UICONTROL Role-Based Access Control] a [!UICONTROL trait], segmenti e [!UICONTROL destination] per ogni gruppo di utenti.

Questa funzionalità consente di gestire le modalità di visualizzazione, creazione, lettura, scrittura e modifica degli utenti di set di dati specifici e persino di impedire agli utenti di accedere a set di dati che non dovrebbero essere disponibili.

![protezione dell&#39;accesso](assets/access-protection.png)
