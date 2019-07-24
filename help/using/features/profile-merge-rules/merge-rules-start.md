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


# Getting Started with Profile Merge Rules {#getting-started-with-profile-merge-rules}

To create [!UICONTROL Profile Merge Rules], review and complete the steps in each of the procedures described in this section.

<!-- merge-rules-start.xml -->

## Create a Cross-Device Data Source {#create-data-source}

To create a cross-device data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Le autorizzazioni di amministratore sono necessarie per creare o modificare un'origine dati multi-dispositivo.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Denominate l'origine dati.
1. *(Facoltativo)* Descrivete l'origine dati. Una descrizione concisa consente di definire il ruolo o lo scopo dell'origine dati.
1. Fornite un codice di integrazione. Un codice di integrazione è il tuo ID univoco per questa origine dati.
1. In the **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**.
1. In the **[!UICONTROL ID Definition]** list, select an option that defines the data source type. Le opzioni includono:
   * **[!UICONTROL Person]**: Un ID che definisce una sola persona. This ID can be mapped to multiple [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: Un ID che definisce un gruppo di persone. This ID can be mapped to multiple [!DNL Audience Manager] IDs.

## Controlli sull'esportazione dei dati {#export-controls}

[I controlli sull'esportazione dei dati](../../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a un'origine dati e a una destinazione. Essi non potranno inviare dati a una destinazione quando questa azione viola una privacy dei dati o utilizzano l'accordo. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] sono disponibili diverse opzioni, ma questi 2 sono importanti per la creazione di un'origine dati tra dispositivi:

* **[!UICONTROL Use as Authenticated Profile]**: Selezionata per impostazione predefinita, questa impostazione consente di creare un insieme [!UICONTROL Profile Merge Rule] con dati autenticati.

* **[!UICONTROL Use as a Device Graph]**: Questo controllo è disponibile solo per gli account elencati come provider di dati. Selecting this check box creates your data source as a device graph and lets you share it with other [!DNL Audience Manager] customers. Work with your [!DNL Audience Manager] consultant to get set up as a data provider and to specify which customers this [!UICONTROL Data Source] should be shared with. Il tuo consulente effettua il provisioning della condivisione di account e dispositivi tramite un processo di provisioning interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Questo controllo consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina quanto tempo Audience Manager mantiene nel nostro database gli ID cliente dopo che sono stati visti sulla piattaforma Audience Manager. Il valore predefinito è 24 mesi (720 giorni). Il valore minimo è 1 mesi e il valore massimo è 5 anni. Tieni presente che contiamo tutti i mesi come 30 giorni. Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per ID cliente inattivi.

The text fields associated with these settings let you rename the [!UICONTROL Data Source] with an alias that appears in the [Profile Merge Rule options](../../features/profile-merge-rules/merge-rule-definitions.md). For example, if you add an alias to **[!UICONTROL Use as Authenticated Profile]**, that name appears in the [!UICONTROL Authenticated Profile Options] list. If you add an alias to **[!UICONTROL Use as a Device Graph]**, that name appears in the [!UICONTROL Device Options] list.

>[!MORE_ LIKE_ THIS]
>
>* [Creare un'origine dati](../../features/manage-datasources.md#create-data-source)


## Create a Profile Merge Rule {#create-profile-merge-rule}

To create a [!UICONTROL Profile Merge Rule], go to **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** and complete the steps for each section described here. Dopo aver configurato un'origine dati cross-device potete creare fino a 3 regole di unione. Le autorizzazioni di amministratore sono necessarie per creare, modificare o eliminare una regola. All users can view and use existing [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Prerequisiti:** Per creare un [!UICONTROL Profile Merge Rule]'immagine, è necessaria un'origine dati cross-device. See [Create a Data Source](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>See [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md) for descriptions of these different controls.

## Informazioni di base {#basic-info}

To complete the [!UICONTROL Basic Information] section:

1. Name the [!UICONTROL Profile Merge Rule].
2. *(Facoltativo)* Descrivete l ' [!UICONTROL Profile Merge Rule]. Una descrizione concisa consente di definire il ruolo o lo scopo della regola.
3. *(Facoltativo)* Selezionate **[!UICONTROL Set as default]** questa opzione per rendere questa impostazione [!UICONTROL Profile Merge Rule]predefinita. I nuovi segmenti vengono associati automaticamente alla regola predefinita.

## Controlli sull'esportazione dei dati {#data-export-controls}

[I controlli sull'esportazione dei dati](../../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare al [!UICONTROL Profile Merge Rule]tuo. Essi non potranno inviare dati a una destinazione quando questa azione viola una privacy dei dati o utilizzano l'accordo. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Profile Merge Rule Setup {#profile-merge-rule-setup}

To complete the [!UICONTROL Proflie Merge Rule Setup] section:

1. Select an **[!UICONTROL Authenticated Option]**. Le opzioni includono:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Select an **[!UICONTROL Authenticated Profile Option]** (up to 3, maximum). These are the [cross-device data sources](../../features/profile-merge-rules/merge-rules-start.md) you have created previously.
3. Seleziona una **[!UICONTROL Device Option]**. Le opzioni includono:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Fai clic su **[!UICONTROL Save]**.

## Configure Merge Rule Code {#configure-merge-rule-code}

Follow these instructions to set up the [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL], and mobile [!DNL SDK] code to work with your merge rules.

<!-- merge-rules-configure-code.xml -->

### Prerequisiti

You must set up a [cross-device data source](#create-data-source) and [profile merge rules](#create-profile-merge-rule) *before* completing these procedures.

## For Experience Cloud ID Service Customers {#id-service-customers}

The [!UICONTROL Experience Cloud ID Service] and the latest version of [DIL](../../dil/dil-overview.md) are recommended when working with [!UICONTROL Profile Merge Rules]. However, you don't have to use the [!UICONTROL Experience Cloud ID Service] to work with this feature. If you're just using [!UICONTROL DIL], see the [legacy DIL section](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) below.

### Configurare la funzione Imposta ID cliente

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. To use a profile merge rule, you must modify `setCustomerIDs` to use the integration code specified when you created a cross-device data source. For example, say you've created a cross-device data source with the integration code `my_datasource_ic`. Per trasmettere un ID dichiarato, aggiungete il codice di integrazione alla funzione ID visitatore come mostrato nel codice modificato di seguito.

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

For more information, see [Create a Cross-Device Data Source](#create-data-source) and [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### `DIL.create` Configura, funzione

The latest versions of [!UICONTROL DIL] now automatically pick up the [!UICONTROL declared ID] from the `visitorService` function in `DIL.create` (see [Declared ID Variables](../../features/declared-ids.md#declared-id-variables)). Check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>var vdil = DIL. create ({partner: " partner name ",
 visitorservice: {namespace: "<i>INSERT-MCORG-ID-HERE</i>"}});</code>
</pre>

In the namespace key-value pair, the `*`MCORG`*` variable is your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. Per visualizzare il dashboard, dovete disporre delle autorizzazioni di amministratore. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### Configurare gli SDK

See the [Configure SDKs](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks) section below.

## Legacy DIL {#legacy-dil}

If you're not using [!DNL Experience Cloud ID Service] yet, you really ought to. Tuttavia, sappiamo che passare a un nuovo codice richiede un'attenta idea e un'attenta verifica. In these cases, check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>DIL. create ({partner: " partner name ",
 declaredid: {dpuuid:<i>dpuuid</i>,
 dpid:<i>dpid</i>}});</code>
</pre>

For more information, see the legacy [!UICONTROL DIL] section in [Declared ID Variables](../../features/declared-ids.md#declared-id-variables).

### Configure SDKs {#configure-sdks-legacy-dil}

Check the methods in your [!DNL SDK] code that let you pass [!UICONTROL declared IDs] from [!DNL Android] and [!DNL iOS] mobile devices. The variable names for the [!DNL Android] and [!DNL iOS] code libraries are the same:

* `dpid`: L'ID di origine dati su più dispositivi.
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

See also, [Audience Manager Methods for Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) and [Audience Manager Methods for iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
