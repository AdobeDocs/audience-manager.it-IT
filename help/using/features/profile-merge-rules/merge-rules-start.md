---
description: Per creare le regole di unione profili, consulta e completa i passaggi descritti in ciascuna procedura descritta in questa sezione.
seo-description: Per creare le regole di unione profili, consulta e completa i passaggi descritti in ciascuna procedura descritta in questa sezione.
seo-title: Guida introduttiva alle regole di unione profilo
solution: Audience Manager
title: Guida introduttiva alle regole di unione profilo
uuid: 7 d 32 c 60 f -467 c -42 dd-afa 9-437 fd 7 c 473 c 5
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Guida introduttiva alle regole di unione profilo {#getting-started-with-profile-merge-rules}

Per creare [!UICONTROL Profile Merge Rules], rivedere e completare i passaggi descritti in questa sezione.

<!-- merge-rules-start.xml -->

## Creare un&#39;origine dati multi-dispositivo {#create-data-source}

Per creare un&#39;origine dati cross-device, vai a **[!UICONTROL Audience Data > Data Sources > Add New]** e completa i passaggi per ogni sezione descritta qui. Le autorizzazioni di amministratore sono necessarie per creare o modificare un&#39;origine dati multi-dispositivo.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consultate [Impostazioni origine dati e Opzioni](../../features/datasources-list-and-settings.md#settings-menu-options) menu per le descrizioni di questi diversi controlli.

## Dettagli origine dati {#details}

Per completare la [!UICONTROL Data Source Details] sezione:

1. Denominate l&#39;origine dati.
1. *(Facoltativo)* Descrivete l&#39;origine dati. Una descrizione concisa consente di definire il ruolo o lo scopo dell&#39;origine dati.
1. Fornite un codice di integrazione. Un codice di integrazione è il tuo ID univoco per questa origine dati.
1. Nell **[!UICONTROL ID Type]** &#39;elenco, selezionate **[!UICONTROL Cross Device]**.
1. Nell **[!UICONTROL ID Definition]** &#39;elenco, selezionare un&#39;opzione che definisca il tipo di origine dati. Le opzioni includono:
   * **[!UICONTROL Person]**: Un ID che definisce una sola persona. Questo ID può essere mappato su più [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: Un ID che definisce un gruppo di persone. Questo ID può essere mappato su più [!DNL Audience Manager] ID.

## Controlli sull&#39;esportazione dei dati {#export-controls}

[I controlli sull&#39;esportazione dei dati](../../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a un&#39;origine dati e a una destinazione. Essi non potranno inviare dati a una destinazione quando questa azione viola una privacy dei dati o utilizzano l&#39;accordo. Ignorate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Impostazioni origine dati {#settings}

[!UICONTROL Data Source Settings] sono disponibili diverse opzioni, ma questi 2 sono importanti per la creazione di un&#39;origine dati tra dispositivi:

* **[!UICONTROL Use as Authenticated Profile]**: Selezionata per impostazione predefinita, questa impostazione consente di creare un insieme [!UICONTROL Profile Merge Rule] con dati autenticati.

* **[!UICONTROL Use as a Device Graph]**: Questo controllo è disponibile solo per gli account elencati come provider di dati. Selezionando questa casella di controllo, la tua origine dati viene creata come grafico del dispositivo e puoi condividerla con altri [!DNL Audience Manager] clienti. Consultate [!DNL Audience Manager] il vostro consulente per essere impostato come fornitore di dati e per specificare con quali clienti [!UICONTROL Data Source] deve essere condiviso. Il tuo consulente effettua il provisioning della condivisione di account e dispositivi tramite un processo di provisioning interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Questo controllo consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina quanto tempo Audience Manager mantiene nel nostro database gli ID cliente dopo che sono stati visti sulla piattaforma Audience Manager. Il valore predefinito è 24 mesi (720 giorni). Il valore minimo è 1 mesi e il valore massimo è 5 anni. Tieni presente che contiamo tutti i mesi come 30 giorni. Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per ID cliente inattivi.

I campi di testo associati a queste impostazioni consentono di rinominare l&#39; [!UICONTROL Data Source] alias visualizzato nelle opzioni Regola unione [profilo](../../features/profile-merge-rules/merge-rule-definitions.md). Ad esempio, se aggiungete un alias a **[!UICONTROL Use as Authenticated Profile]**, tale nome viene visualizzato nell [!UICONTROL Authenticated Profile Options] &#39;elenco. Se aggiungete un alias a **[!UICONTROL Use as a Device Graph]**, questo nome viene visualizzato nell [!UICONTROL Device Options] &#39;elenco.

>[!MORE_ LIKE_ THIS]
>
>* [Creare un&#39;origine dati](../../features/manage-datasources.md#create-data-source)


## Creare una regola di unione profilo {#create-profile-merge-rule}

Per creare un [!UICONTROL Profile Merge Rule], vai a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e completa i passaggi per ogni sezione descritta qui. Dopo aver configurato un&#39;origine dati cross-device potete creare fino a 3 regole di unione. Le autorizzazioni di amministratore sono necessarie per creare, modificare o eliminare una regola. Tutti gli utenti possono visualizzare e utilizzare già [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Prerequisiti:** Per creare un [!UICONTROL Profile Merge Rule]&#39;immagine, è necessaria un&#39;origine dati cross-device. Consultate [Creare un&#39;origine dati](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>Consultate [Opzioni regola unione profilo definite](../../features/profile-merge-rules/merge-rule-definitions.md) per le descrizioni di questi diversi controlli.

## Informazioni di base {#basic-info}

Per completare la [!UICONTROL Basic Information] sezione:

1. Denominate il [!UICONTROL Profile Merge Rule]nome.
2. *(Facoltativo)* Descrivete l &#39; [!UICONTROL Profile Merge Rule]. Una descrizione concisa consente di definire il ruolo o lo scopo della regola.
3. *(Facoltativo)* Selezionate **[!UICONTROL Set as default]** questa opzione per rendere questa impostazione [!UICONTROL Profile Merge Rule]predefinita. I nuovi segmenti vengono associati automaticamente alla regola predefinita.

## Controlli sull&#39;esportazione dei dati {#data-export-controls}

[I controlli sull&#39;esportazione dei dati](../../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare al [!UICONTROL Profile Merge Rule]tuo. Essi non potranno inviare dati a una destinazione quando questa azione viola una privacy dei dati o utilizzano l&#39;accordo. Ignorate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Configurazione regola unione profilo {#profile-merge-rule-setup}

Per completare la [!UICONTROL Proflie Merge Rule Setup] sezione:

1. Selezionate un **[!UICONTROL Authenticated Option]**. Le opzioni includono:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selezionate un ( **[!UICONTROL Authenticated Profile Option]** fino a 3, massimo). Queste sono le [origini](../../features/profile-merge-rules/merge-rules-start.md) dati cross-device che hai creato in precedenza.
3. Seleziona una **[!UICONTROL Device Option]**. Le opzioni includono:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Fai clic su **[!UICONTROL Save]**.

## Configurare il codice regola Unisci {#configure-merge-rule-code}

Per impostare le [!UICONTROL Experience Cloud ID Service]regole di unione, [!UICONTROL DIL]seguite [!DNL SDK] le istruzioni riportate di seguito.

<!-- merge-rules-configure-code.xml -->

### Prerequisiti

Prima di procedere con le procedure, devi configurare un&#39;origine dati [cross-device](#create-data-source) e [regole](#create-profile-merge-rule) *di unione* dei profili.

## Per i clienti del servizio Experience Cloud ID {#id-service-customers}

La [!UICONTROL Experience Cloud ID Service] versione più recente di [DIL](../../dil/dil-overview.md) [!UICONTROL Profile Merge Rules]è consigliata. Tuttavia, non è necessario utilizzare questa [!UICONTROL Experience Cloud ID Service] funzione. Se stai semplicemente utilizzando [!UICONTROL DIL], vedi la [sezione DIL precedente](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) di seguito.

### Configurare la funzione Imposta ID cliente

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. Per utilizzare una regola di unione dei profili, è necessario modificare `setCustomerIDs` per utilizzare il codice di integrazione specificato quando si crea un&#39;origine dati su più dispositivi. Ad esempio, supponiamo che sia stata creata un&#39;origine dati multi-dispositivo con il codice `my_datasource_ic`di integrazione. Per trasmettere un ID dichiarato, aggiungete il codice di integrazione alla funzione ID visitatore come mostrato nel codice modificato di seguito.

#### Esempio di codice generico

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Esempio di codice modificato

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Per ulteriori informazioni, vedi [Creare un&#39;origine dati multi-dispositivo](#create-data-source) e [ID cliente e stati di autenticazione](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### `DIL.create` Configura, funzione

Le versioni più recenti di [!UICONTROL DIL] ora raccolgono automaticamente la [!UICONTROL declared ID]`visitorService` funzione in `DIL.create` (vedi [Variabili ID dichiarate](../../features/declared-ids.md#declared-id-variables)). Controllate `DIL.create` la funzione per essere certi che sia configurata correttamente, come mostrato nel codice seguente.

<pre class="js"><code>var vdil = DIL. create ({partner: " partner name ",
 visitorservice: {namespace: "<i>INSERT-MCORG-ID-HERE</i>"}});</code>
</pre>

Nella coppia chiave-valore dello spazio nomi, la `*`variabile MCORG`*` è l&#39;ID [!DNL Experience Cloud] organizzazione. Se non disponete di questo ID, potete trovarlo nella [!UICONTROL Administration] sezione del [!DNL Experience Cloud] dashboard. Per visualizzare il dashboard, dovete disporre delle autorizzazioni di amministratore. Consulta [Amministrazione: Servizi di base](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### Configurare gli SDK

Consulta la [sezione Configura SDK](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks) di seguito.

## DIL legacy {#legacy-dil}

Se non usi [!DNL Experience Cloud ID Service] ancora, dovresti farlo. Tuttavia, sappiamo che passare a un nuovo codice richiede un&#39;attenta idea e un&#39;attenta verifica. In questi casi, controllate la `DIL.create` funzione per essere certi che sia configurata correttamente, come mostrato nel codice seguente.

<pre class="js"><code>DIL. create ({partner: " partner name ",
 declaredid: {dpuuid:<i>dpuuid</i>,
 dpid:<i>dpid</i>}});</code>
</pre>

Per ulteriori informazioni, vedi la [!UICONTROL DIL] sezione precedente nelle [variabili ID dichiarati](../../features/declared-ids.md#declared-id-variables).

### Configurare gli SDK {#configure-sdks-legacy-dil}

Controllate i metodi nel [!DNL SDK] codice che vi permettono di passare [!UICONTROL declared IDs] da [!DNL Android] e dispositivi [!DNL iOS] mobili. I nomi delle variabili per [!DNL Android] le [!DNL iOS] librerie e i codici sono identici:

* `dpid`: L&#39;ID di origine dati su più dispositivi.
* `dpuuid`: The [!UICONTROL declared ID] (es., the user ID).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di dispositivo </th> 
   <th colname="col2" class="entry"> Metodo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Sintassi:</b> </p> <p> <pre> public static void setdpidanddpuuid (String dpid, String dpuuid); </pre> </p> <p> <b>Esempio:</b> </p> <p> <pre> Audiencemanager. setdpidanddpuuid ("mydpid", "mydpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> Audiencesetdpid: dpuuid </code> </p> <p> <b>Sintassi:</b> </p><p>
    <code class="javascript">+ (void) audiencesetdpid: (Nsstring *) dpid 
 dpuuid: (Nsstring *) dpuuid; </code>
 </p>
    <p> <b>Esempio:</b> </p><p>
    <code class="javascript">[Adbmobile audiencesetdpid: @ "290" dpuuid: @ "99301393923940"]; </code>
 </p>
    </td>
  </tr>
 </tbody>
</table>

Vedi anche Metodi [di Audience Manager per i metodi di Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) e [Audience Manager per iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
