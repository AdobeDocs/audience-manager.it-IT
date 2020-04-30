---
description: Per creare le regole di unione dei profili esaminare e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.
seo-description: Per creare le regole di unione dei profili esaminare e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.
seo-title: Guida introduttiva alle regole di unione dei profili
solution: Audience Manager
title: Guida introduttiva alle regole di unione dei profili
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Guida introduttiva alle regole di unione dei profili {#getting-started-with-profile-merge-rules}

Per creare [!UICONTROL Profile Merge Rules], esaminare e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.

<!-- merge-rules-start.xml -->

## Creare un&#39;origine dati multi-dispositivo {#create-data-source}

Per creare un&#39;origine dati multi-dispositivo, passare a **[!UICONTROL Audience Data > Data Sources > Add New]** e completare i passaggi per ciascuna sezione descritta qui. Per creare o modificare un&#39;origine dati multi-dispositivo sono necessarie autorizzazioni di amministratore.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Per una descrizione di questi diversi controlli, vedere Impostazioni origine [dati e Opzioni](../datasources-list-and-settings.md#settings-menu-options) menu.

## Dettagli origine dati {#details}

Per completare la [!UICONTROL Data Source Details] sezione:

1. Denominare l&#39;origine dati.
2. *(Facoltativo)* Descrivere l&#39;origine dati. Una breve descrizione consente di definire il ruolo o lo scopo dell&#39;origine dati.
3. Fornite un codice di integrazione. Un codice di integrazione è il tuo ID univoco per questa origine dati.
4. Nell&#39; **[!UICONTROL ID Type]** elenco, selezionare **[!UICONTROL Cross Device]**.
5. Nell&#39; **[!UICONTROL ID Definition]** elenco, selezionare un&#39;opzione che definisce il tipo di origine dati. Le opzioni includono:
   * **[!UICONTROL Person]**: Un ID che definisce una singola persona. Questo ID può essere mappato su più [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: Un ID che definisce un gruppo di persone. Questo ID può essere mappato su più [!DNL Audience Manager] ID.

## Controlli sull&#39;esportazione dei dati {#export-controls}

[I Controlli](../data-export-controls.md) sull&#39;esportazione dei dati sono regole di classificazione facoltative applicabili a un&#39;origine dati e a una destinazione. Impediscono l&#39;invio di dati a una destinazione in caso di violazione della privacy dei dati o dell&#39;accordo di utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] Questa sezione offre diverse opzioni, ma queste due sono importanti per la creazione di un&#39;origine dati cross-device:

* **[!UICONTROL Use as Authenticated Profile]**: Selezionata per impostazione predefinita, questa impostazione consente di creare un [!UICONTROL Profile Merge Rule] file con i propri dati autenticati.

* **[!UICONTROL Use as a Device Graph]**: Questo controllo è disponibile solo per gli account elencati come provider di dati. Selezionando questa casella di controllo, l&#39;origine dati viene creata come grafico del dispositivo e puoi condividerla con altri [!DNL Audience Manager] clienti. Consultate il vostro [!DNL Audience Manager] consulente per ottenere la configurazione come fornitore di dati e per specificare con quali clienti [!UICONTROL Data Source] condividere questo servizio. Il consulente fornirà il vostro account e la condivisione del grafico del dispositivo attraverso un processo di provisioning interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Questo controllo consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo Audience Manager mantiene gli ID cliente nel nostro database dopo che sono stati visti per l’ultima volta sulla piattaforma Audience Manager. Il valore predefinito è 24 mesi (720 giorni). Il valore minimo che potete impostare è 1 mese e il valore massimo è 5 anni. Teniamo presente che contiamo tutti i mesi come 30 giorni. Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.

I campi di testo associati a queste impostazioni consentono di rinominare l&#39;oggetto [!UICONTROL Data Source] con un alias visualizzato nelle opzioni [Regola unione](merge-rule-definitions.md)profilo. Ad esempio, se aggiungete un alias a **[!UICONTROL Use as Authenticated Profile]**, il nome verrà visualizzato nell&#39; [!UICONTROL Authenticated Profile Options] elenco. Se aggiungete un alias a **[!UICONTROL Use as a Device Graph]**, il nome verrà visualizzato nell&#39; [!UICONTROL Device Options] elenco.

## Creare una regola di unione dei profili {#create-profile-merge-rule}

Per creare un [!UICONTROL Profile Merge Rule], andate a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e completate i passaggi per ciascuna sezione descritta qui.

È possibile creare fino a 3 regole di unione dopo la configurazione di un&#39;origine dati multi-dispositivo. Se ti iscrivi a Destinazioni[!UICONTROL All Cross-Device Profiles]basate sulle [persone, puoi accedere a una regola di unione dei 4° profilo (](../destinations/people-based-destinations-overview.md)).

Per creare, modificare o eliminare una regola è necessario disporre delle autorizzazioni di amministratore. Tutti gli utenti possono visualizzare e utilizzare gli [!UICONTROL Profile Merge Rules]elementi esistenti.

<!-- create-profile-merge-rule.xml -->

**Prerequisiti:** Per creare un&#39;origine dati multi-dispositivo è necessaria un&#39;origine dati [!UICONTROL Profile Merge Rule]. Consulta [Creare un&#39;origine](../manage-datasources.md#create-data-source)dati.

>[!TIP]
>
>Per le descrizioni di questi diversi controlli, consultate Opzioni regole di unione [profilo](merge-rule-definitions.md) .

## Informazioni di base {#basic-info}

Per completare la [!UICONTROL Basic Information] sezione:

1. Denominate il [!UICONTROL Profile Merge Rule].
2. *(Facoltativo)* Descrivete il [!UICONTROL Profile Merge Rule]. Una breve descrizione consente di definire il ruolo o lo scopo della regola.
3. *(Facoltativo)* Selezionate **[!UICONTROL Set as default]** se desiderate che questo sia il valore predefinito [!UICONTROL Profile Merge Rule]. I nuovi segmenti vengono associati automaticamente alla regola predefinita.

## Controlli sull&#39;esportazione dei dati {#data-export-controls}

[I controlli](../data-export-controls.md) di esportazione dei dati sono regole di classificazione facoltative che puoi applicare al tuo [!UICONTROL Profile Merge Rule]. Impediscono l&#39;invio di dati a una destinazione in caso di violazione della privacy dei dati o dell&#39;accordo di utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Impostazione regola di unione dei profili {#profile-merge-rule-setup}

Per completare la [!UICONTROL Proflie Merge Rule Setup] sezione:

1. Selezionate un **[!UICONTROL Authenticated Option]**. Le opzioni includono:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selezionate un **[!UICONTROL Authenticated Profile Option]** (fino a 3, massimo). Si tratta delle origini [dati](merge-rules-start.md) cross-device create in precedenza.
3. Seleziona una **[!UICONTROL Device Option]**. Le opzioni includono:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Clic **[!UICONTROL Save]**.

## Configurare il codice della regola di unione {#configure-merge-rule-code}

Seguire queste istruzioni per impostare il [!UICONTROL Adobe Experience Platform Identity Service]codice mobile [!UICONTROL DIL]e il [!DNL SDK] codice mobile in modo che funzioni con le regole di unione.

<!-- merge-rules-configure-code.xml -->

### Prerequisiti

È necessario impostare un&#39;origine [dati](#create-data-source) cross-device e regole [di unione](#create-profile-merge-rule) profilo *prima* di completare queste procedure.

## Per i clienti di Adobe Experience Platform Identity {#id-service-customers}

Quando si lavora con [!UICONTROL Adobe Experience Platform Identity Service] DIL [, si consiglia di utilizzare la versione più recente di](../../dil/dil-overview.md) DIL [!UICONTROL Profile Merge Rules]. Tuttavia, non è necessario utilizzare la funzione [!UICONTROL Adobe Experience Platform Identity Service] per utilizzarla. Se utilizzi solo [!UICONTROL DIL]questa opzione, consulta la sezione [DIL](#legacy-dil) precedente riportata di seguito.

### Configurare la funzione Imposta ID cliente

Quando si lavora con [!UICONTROL Adobe Experience Platform Identity Service], la `setCustomerIDs` funzione trasmette gli ID dichiarati a [!DNL Audience Manager]. Per utilizzare una regola di unione dei profili, è necessario modificare `setCustomerIDs` per utilizzare il codice di integrazione specificato al momento della creazione di un&#39;origine dati multi-dispositivo. Ad esempio, supponiamo che sia stata creata un&#39;origine dati cross-device con il codice di integrazione `my_datasource_ic`. Per trasmettere un ID dichiarato, aggiungi il codice di integrazione alla funzione ID visitatore come mostrato nell’esempio di codice modificato riportato di seguito.

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

Per ulteriori informazioni, vedi [Creare un&#39;origine](#create-data-source) dati e ID [cliente tra dispositivi e stati](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)di autenticazione.

### Configura `DIL.create` funzione

Le versioni più recenti di [!UICONTROL DIL] ora recuperano automaticamente la [!UICONTROL declared ID] funzione dalla `visitorService` funzione in `DIL.create` (vedere Variabili [ID](../declared-ids.md#declared-id-variables)dichiarate). Controllare la `DIL.create` funzione per assicurarsi che sia impostata correttamente, come mostrato nell&#39;esempio di codice seguente.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Nella coppia chiave-valore dello spazio dei nomi, la variabile `*`MCORG`*` è l’ID [!DNL Experience Cloud] organizzazione. Se non disponete di questo ID, potete trovarlo nella [!UICONTROL Administration] sezione del [!DNL Experience Cloud] dashboard. Per visualizzare questo dashboard è necessario disporre delle autorizzazioni di amministratore. See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configurare gli SDK

Consulta la sezione [Configura SDK](#configure-sdks-legacy-dil) di seguito.

## DIL legacy {#legacy-dil}

Se non usi [!DNL Adobe Experience Platform Identity Service] ancora, dovresti davvero farlo. Ma sappiamo che per passare a un nuovo codice è necessario un attento esame e riflessione. In questi casi, controllare la `DIL.create` funzione per assicurarsi che sia impostata correttamente come mostrato nel codice di esempio riportato di seguito.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Per ulteriori informazioni, consulta la [!UICONTROL DIL] sezione precedente in Variabili [ID](../declared-ids.md#declared-id-variables)dichiarate.

### Configurare gli SDK {#configure-sdks-legacy-dil}

Controllate i metodi nel [!DNL SDK] codice che consentono di passare [!UICONTROL declared IDs] da dispositivi [!DNL Android] e [!DNL iOS] dispositivi mobili. I nomi delle variabili per le librerie di [!DNL Android] codici e le librerie di [!DNL iOS] codici sono gli stessi:

* `dpid`: L&#39;ID origine dati cross-device.
* `dpuuid`: L’ID [!UICONTROL declared ID] (ad es. l’ID utente).

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Sintassi:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Esempio:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Sintassi:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Esempio:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Vedi anche Metodi [Audience Manager per Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) e Metodi [Audience Manager per iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Creazione di un&#39;origine dati](../manage-datasources.md#create-data-source)

