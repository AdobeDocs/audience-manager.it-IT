---
description: Per creare le regole di unione dei profili esaminare e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.
seo-description: Per creare le regole di unione dei profili esaminare e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.
seo-title: Guida introduttiva alle regole di unione profili
solution: Audience Manager
title: Guida introduttiva alle regole di unione profili
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: dc22ed98b51b5633532bab45a79a14ee14dba5f5
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 3%

---


# Guida introduttiva alle regole di unione profili {#getting-started-with-profile-merge-rules}

Per creare [!UICONTROL Profile Merge Rules], controlla e completa i passaggi descritti in ciascuna delle procedure descritte in questa sezione.

<!-- merge-rules-start.xml -->

## Creare un&#39;origine dati multi-dispositivo {#create-data-source}

Per creare un&#39;origine dati multi-dispositivo, andate a **[!UICONTROL Audience Data > Data Sources > Add New]** e completate i passaggi per ciascuna sezione descritta qui. Per creare o modificare un&#39;origine dati multi-dispositivo sono necessarie autorizzazioni di amministratore.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Per le descrizioni di questi diversi controlli, vedere [Impostazioni origine dati e Opzioni menu](../datasources-list-and-settings.md#settings-menu-options).

## Dettagli origine dati {#details}

Per completare la sezione [!UICONTROL Data Source Details]:

1. Denominare l&#39;origine dati.
2. *(Facoltativo)* Descrivere l&#39;origine dati. Una breve descrizione consente di definire il ruolo o lo scopo dell&#39;origine dati.
3. Fornite un codice di integrazione. Un codice di integrazione è il tuo ID univoco per questa origine dati.
4. Nell&#39;elenco **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
5. Nell&#39;elenco **[!UICONTROL ID Definition]**, selezionare un&#39;opzione che definisce il tipo di origine dati. Le opzioni includono:
   * **[!UICONTROL Person]**: Un ID che definisce una singola persona. Questo ID può essere mappato su più [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: Un ID che definisce un gruppo di persone. Questo ID può essere mappato su più [!DNL Audience Manager] ID.

## Controlli sull’esportazione dei dati {#export-controls}

[I ](../data-export-controls.md) controlli di esportazione dei dati sono regole di classificazione facoltative applicabili a un&#39;origine dati e a una destinazione. Impediscono l&#39;invio di dati a una destinazione in caso di violazione della privacy dei dati o dell&#39;accordo di utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Impostazioni origine dati {#settings}

[!UICONTROL Data Source Settings] Questa sezione offre diverse opzioni, ma queste due sono importanti per la creazione di un&#39;origine dati cross-device:

* **[!UICONTROL Use as Authenticated Profile]**: Selezionata per impostazione predefinita, questa impostazione consente di creare un  [!UICONTROL Profile Merge Rule] con i propri dati autenticati.

* **[!UICONTROL Use as a Device Graph]**: Questo controllo è disponibile solo per gli account elencati come provider di dati. Selezionando questa casella di controllo, l&#39;origine dati viene creata come grafico del dispositivo e puoi condividerla con altri clienti [!DNL Audience Manager]. Consultate il vostro [!DNL Audience Manager] consulente per ottenere la configurazione come provider di dati e per specificare con quali clienti condividere questo [!UICONTROL Data Source]. Il consulente fornirà il vostro account e la condivisione del grafico del dispositivo attraverso un processo di provisioning interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Questo controllo consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo  Audience Manager mantiene gli ID cliente nel nostro database dopo che sono stati visti per l&#39;ultima volta sulla piattaforma del Audience Manager . Il valore predefinito è 24 mesi (720 giorni). Il valore minimo che potete impostare è 1 mese e il valore massimo è 5 anni. Teniamo presente che contiamo tutti i mesi come 30 giorni.  Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.

I campi di testo associati a queste impostazioni consentono di rinominare il [!UICONTROL Data Source] con un alias che viene visualizzato nelle opzioni [Regola unione profilo](merge-rule-definitions.md). Ad esempio, se aggiungete un alias a **[!UICONTROL Use as Authenticated Profile]**, tale nome viene visualizzato nell&#39;elenco [!UICONTROL Authenticated Profile Options]. Se si aggiunge un alias a **[!UICONTROL Use as a Device Graph]**, tale nome viene visualizzato nell&#39;elenco [!UICONTROL Device Options].

## Creare una regola di unione dei profili {#create-profile-merge-rule}

Per creare un [!UICONTROL Profile Merge Rule], andate a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e completate i passaggi per ciascuna sezione descritta qui.

È possibile creare fino a 3 regole di unione dopo la configurazione di un&#39;origine dati multi-dispositivo. Se ti iscrivi a [Destinazioni basate sulle persone](../destinations/people-based-destinations-overview.md), puoi accedere a una regola di unione dei 4 profili ([!UICONTROL All Cross-Device Profiles]).

Per creare, modificare o eliminare una regola è necessario disporre delle autorizzazioni di amministratore. Tutti gli utenti possono visualizzare e utilizzare [!UICONTROL Profile Merge Rules] esistenti.

<!-- create-profile-merge-rule.xml -->

**Prerequisiti:** Per creare un&#39;origine dati multi-dispositivo è necessaria un&#39;origine dati  [!UICONTROL Profile Merge Rule]. Vedere [Creare un&#39;origine dati](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Per le descrizioni di questi diversi controlli, vedere [Opzioni regole di unione profilo definite](merge-rule-definitions.md).

## Informazioni di base {#basic-info}

Per completare la sezione [!UICONTROL Basic Information]:

1. Denominate il simbolo [!UICONTROL Profile Merge Rule].
2. *(Facoltativo)* Descrivete il  [!UICONTROL Profile Merge Rule]pulsante. Una breve descrizione consente di definire il ruolo o lo scopo della regola.
3. *(Facoltativo)* Selezionate  **[!UICONTROL Set as default]** se desiderate che questo sia il valore predefinito  [!UICONTROL Profile Merge Rule]. I nuovi segmenti vengono associati automaticamente alla regola predefinita.

## Controlli sull’esportazione dei dati {#data-export-controls}

[I ](../data-export-controls.md) controlli di esportazione dei dati sono regole di classificazione facoltative che puoi applicare al tuo  [!UICONTROL Profile Merge Rule]. Impediscono l&#39;invio di dati a una destinazione in caso di violazione della privacy dei dati o dell&#39;accordo di utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Impostazione regola di unione profilo {#profile-merge-rule-setup}

Per completare la sezione [!UICONTROL Proflie Merge Rule Setup]:

1. Selezionare un elemento **[!UICONTROL Authenticated Option]**. Le opzioni includono:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selezionare un elemento **[!UICONTROL Authenticated Profile Option]** (fino a 3, massimo). Sono le [origini dati cross-device](merge-rules-start.md) create in precedenza.
3. Seleziona una **[!UICONTROL Device Option]**. Le opzioni includono:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Clic **[!UICONTROL Save]**.

### Considerazioni per  destinazioni Adobe Campaign utilizzando ID multi-dispositivo come chiavi ID utente {#considerations}

Alla fine del 2019, è disponibile una serie di miglioramenti delle regole di unione dei profili per migliorare la precisione dei file batch generati utilizzando ID cross-device. Questi miglioramenti saranno rigorosamente rispettati nell&#39;istanza di  Audience Manager a partire da lunedì 16 marzo 2020. Di conseguenza, i segmenti mappati a una destinazione utilizzando ID cross-device cesseranno di produrre esportazioni in alcune configurazioni di regole di unione profilo.

Per garantire la corretta integrazione tra l’istanza del Audience Manager  e le destinazioni utilizzando ID cross-device, come  Adobe Campaign, accertatevi di soddisfare i seguenti requisiti:

1. Rivedete la regola di unione dei profili utilizzata dai segmenti mappati alla destinazione ID dichiarata  Adobe Campaign. La regola di unione dei profili deve utilizzare l&#39;opzione [!UICONTROL Last Authenticated Profile], in modo che tutti i profili autenticati possano essere inclusi nelle esportazioni. Se la regola di unione dei profili utilizza un&#39;altra opzione, è necessario passare a [!UICONTROL Last Authenticated Profile].
2. Seleziona l&#39;origine dati ID dichiarato di Adobe Campaign  nelle impostazioni Regola unione profilo.

>[!NOTE]
>
> Se hai raggiunto il numero massimo di [!UICONTROL Profile Merge Rules] e hai bisogno di assistenza per configurarli in base alle istruzioni sopra riportate, contatta l&#39;Assistenza clienti.

## Configurare il codice della regola di unione {#configure-merge-rule-code}

Seguire queste istruzioni per impostare il codice [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] e mobile [!DNL SDK] in modo che funzioni con le regole di unione.

<!-- merge-rules-configure-code.xml -->

### Prerequisiti

È necessario impostare un&#39;origine dati [cross-device](#create-data-source) e [regole di unione dei profili](#create-profile-merge-rule) *prima di* completare queste procedure.

## Per i clienti di Adobe Experience Platform Identity Service {#id-service-customers}

Quando si utilizza [!UICONTROL Adobe Experience Platform Identity Service] si consiglia di utilizzare la versione [DIL](../../dil/dil-overview.md) e la versione più recente di [!UICONTROL Profile Merge Rules]. Tuttavia, non è necessario utilizzare [!UICONTROL Adobe Experience Platform Identity Service] per utilizzare questa funzione. Se utilizzi solo [!UICONTROL DIL], consulta la sezione [DIL legacy](#legacy-dil) di seguito.

### Configurare la funzione Imposta ID cliente

Quando si utilizza [!UICONTROL Adobe Experience Platform Identity Service], la funzione `setCustomerIDs` trasmette gli ID dichiarati a [!DNL Audience Manager]. Per utilizzare una regola di unione dei profili, è necessario modificare `setCustomerIDs` per utilizzare il codice di integrazione specificato al momento della creazione di un&#39;origine dati multi-dispositivo. Ad esempio, supponiamo che sia stata creata un&#39;origine dati cross-device con il codice di integrazione `my_datasource_ic`. Per trasmettere un ID dichiarato, aggiungi il codice di integrazione alla funzione ID visitatore come mostrato nell’esempio di codice modificato riportato di seguito.

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

Per ulteriori informazioni, vedere [Creare un&#39;origine dati multi-dispositivo](#create-data-source) e [ID cliente e stati di autenticazione](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Configurare la funzione `DIL.create`

Le versioni più recenti di [!UICONTROL DIL] ora recuperano automaticamente la [!UICONTROL declared ID] dalla funzione `visitorService` in `DIL.create` (vedere [Variabili ID dichiarate](../declared-ids.md#declared-id-variables)). Controllare la funzione `DIL.create` per verificare che sia impostata correttamente come illustrato nell&#39;esempio di codice riportato di seguito.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Nella coppia chiave-valore dello spazio dei nomi, la variabile `*`MCORG`*` è il tuo [!DNL Experience Cloud] ID organizzazione. Se non disponi di questo ID, puoi trovarlo nella sezione [!UICONTROL Administration] del dashboard [!DNL Experience Cloud]. Per visualizzare questo dashboard è necessario disporre delle autorizzazioni di amministratore. Vedere [Amministrazione: Servizi di base](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configurare gli SDK

Consulta la sezione [Configura SDK](#configure-sdks-legacy-dil) di seguito.

## DIL precedente {#legacy-dil}

Se non si utilizza ancora [!DNL Adobe Experience Platform Identity Service], è davvero necessario. Ma sappiamo che per passare a un nuovo codice è necessario un attento esame e riflessione. In questi casi, controllare la funzione `DIL.create` per assicurarsi che sia impostata correttamente come mostrato nel codice di esempio riportato di seguito.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Per ulteriori informazioni, consultare la sezione precedente [!UICONTROL DIL] in [Variabili ID dichiarate](../declared-ids.md#declared-id-variables).

### Configurare gli SDK {#configure-sdks-legacy-dil}

Controllare i metodi nel codice [!DNL SDK] che consentono di passare [!UICONTROL declared IDs] da [!DNL Android] e [!DNL iOS] dispositivi mobili. I nomi delle variabili per le librerie di codici [!DNL Android] e [!DNL iOS] sono gli stessi:

* `dpid`: L&#39;ID origine dati cross-device.
* `dpuuid`: L’ID  [!UICONTROL declared ID] (ad es. l’ID utente).

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

Vedere anche [ metodi di Audience Manager per Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) e [ metodi di Audience Manager per iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Creare una sorgente di dati](../manage-datasources.md#create-data-source)

