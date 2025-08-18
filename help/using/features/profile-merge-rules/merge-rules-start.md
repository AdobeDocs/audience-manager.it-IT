---
description: Per creare regole di unione profili, esaminare e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Guida introduttiva alle regole di unione profili
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 1%

---

# Guida introduttiva alle regole di unione profili {#getting-started-with-profile-merge-rules}

Per creare [!UICONTROL Profile Merge Rules], rivedere e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.

<!-- merge-rules-start.xml -->

## Creazione di un Source dati multi-dispositivo {#create-data-source}

Per creare un&#39;origine dati multi-dispositivo, passare a **[!UICONTROL Audience Data > Data Sources > Add New]** e completare i passaggi per ogni sezione qui descritta. Le autorizzazioni di amministratore sono necessarie per creare o modificare un’origine dati per più dispositivi.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Per le descrizioni dei diversi controlli, vedere [Impostazioni e opzioni di menu di Data Source](../datasources-list-and-settings.md#settings-menu-options).

## Dettagli di Data Source {#details}

Per completare la sezione [!UICONTROL Data Source Details]:

1. Denomina l’origine dati.
2. *(Facoltativo)* Descrivere l&#39;origine dati. Una descrizione concisa consente di definire il ruolo o lo scopo dell&#39;origine dati.
3. Fornisci un codice di integrazione. Un codice di integrazione è il tuo ID univoco per questa origine dati.
4. Nell&#39;elenco **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
5. Nell&#39;elenco **[!UICONTROL ID Definition]** selezionare un&#39;opzione che definisce il tipo di origine dati. Le opzioni includono:
   * **[!UICONTROL Person]**: ID che definisce una singola persona. Questo ID può essere mappato a più ID [!DNL Audience Manager].
   * **[!UICONTROL Household]**: un ID che definisce un gruppo di persone. Questo ID può essere mappato a più ID [!DNL Audience Manager].

## Controlli sull&#39;esportazione dei dati {#export-controls}

[I controlli sull&#39;esportazione dei dati](../data-export-controls.md) sono regole di classificazione facoltative che è possibile applicare a un&#39;origine dati e a una destinazione. Ti impediscono di inviare dati a una destinazione quando tale azione viola un accordo sulla privacy dei dati o sull’uso. Ignorare questa sezione se non si utilizza [!UICONTROL Data Export Controls].

## Impostazioni Source dati {#settings}

La sezione [!UICONTROL Data Source Settings] fornisce più opzioni, ma queste 2 sono importanti per la creazione di un&#39;origine dati cross-device:

* **[!UICONTROL Use as Authenticated Profile]**: selezionata per impostazione predefinita, questa impostazione consente di creare [!UICONTROL Profile Merge Rule] con i propri dati autenticati.

* **[!UICONTROL Use as a Device Graph]**: controllo disponibile solo per gli account elencati come provider di dati. Se si seleziona questa casella di controllo, l&#39;origine dati verrà creata come grafico dei dispositivi e sarà possibile condividerla con altri clienti [!DNL Audience Manager]. Rivolgiti al tuo consulente [!DNL Audience Manager] per configurarti come provider di dati e specificare con quali clienti condividere [!UICONTROL Data Source]. Il tuo consulente fornirà la condivisione del tuo account e del grafico dei dispositivi tramite un processo di provisioning interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: questo controllo consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo Audience Manager conserva gli ID cliente nel nostro database dopo che sono stati visti l’ultima volta sulla piattaforma Audience Manager. Il valore predefinito è 24 mesi (720 giorni). Il valore minimo è 1 mese e il valore massimo è 5 anni. Tieni presente che tutti i mesi vengono conteggiati come 30 giorni. Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità alla conservazione dei dati impostata per gli ID cliente inattivi.

I campi di testo associati a queste impostazioni consentono di rinominare [!UICONTROL Data Source] con un alias visualizzato nelle [opzioni della regola di unione profili](merge-rule-definitions.md). Se ad esempio si aggiunge un alias a **[!UICONTROL Use as Authenticated Profile]**, il nome verrà visualizzato nell&#39;elenco [!UICONTROL Authenticated Profile Options]. Se si aggiunge un alias a **[!UICONTROL Use as a Device Graph]**, il nome verrà visualizzato nell&#39;elenco [!UICONTROL Device Options].

## Creare una regola di unione profili {#create-profile-merge-rule}

Per creare un [!UICONTROL Profile Merge Rule], vai a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e completa i passaggi per ogni sezione qui descritta.

Puoi creare fino a 3 regole di unione dopo aver impostato un’origine dati cross-device. Puoi accedere a una quarta regola di unione profili ([!UICONTROL All Cross-Device Profiles]) se ti iscrivi a [Destinazioni basate su persone](../destinations/people-based-destinations-overview.md).

Le autorizzazioni di amministratore sono necessarie per creare, modificare o eliminare una regola. Tutti gli utenti possono visualizzare e utilizzare [!UICONTROL Profile Merge Rules] esistente.

<!-- create-profile-merge-rule.xml -->

**Prerequisiti:** Per generare [!UICONTROL Profile Merge Rule] è necessaria un&#39;origine dati multi-dispositivo. Vedere [Creare un Data Source](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Per le descrizioni dei diversi controlli, vedere [Opzioni regole di unione profili definite](merge-rule-definitions.md).

## Informazioni di base {#basic-info}

Per completare la sezione [!UICONTROL Basic Information]:

1. Denomina [!UICONTROL Profile Merge Rule].
2. *(Facoltativo)* Descrivere [!UICONTROL Profile Merge Rule]. Una descrizione concisa consente di definire il ruolo o lo scopo della regola.
3. *(Facoltativo)* Seleziona **[!UICONTROL Set as default]** se vuoi impostarlo come predefinito [!UICONTROL Profile Merge Rule]. I nuovi segmenti vengono associati automaticamente alla regola predefinita.

## Controlli sull&#39;esportazione dei dati {#data-export-controls}

[Controlli sull&#39;esportazione dei dati](../data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a [!UICONTROL Profile Merge Rule]. Ti impediscono di inviare dati a una destinazione quando tale azione viola un accordo sulla privacy dei dati o sull’uso. Ignorare questa sezione se non si utilizza [!UICONTROL Data Export Controls].

## Impostazione regola di unione profili {#profile-merge-rule-setup}

Per completare la sezione [!UICONTROL Proflie Merge Rule Setup]:

1. Selezionare un **[!UICONTROL Authenticated Option]**. Le opzioni includono:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Seleziona un **[!UICONTROL Authenticated Profile Option]** (fino a 3, massimo). Queste sono le [origini dati multi-dispositivo](merge-rules-start.md) create in precedenza.
3. Seleziona **[!UICONTROL Device Option]**. Le opzioni includono:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Fare clic su **[!UICONTROL Save]**.

### Considerazioni per le destinazioni Adobe Campaign che utilizzano ID multi-dispositivo come chiavi ID utente {#considerations}

Alla fine del 2019 sono stati rilasciati una serie di miglioramenti alle Profile Merge Rules per migliorare la precisione dei file batch generati utilizzando ID multi-dispositivo. Questi miglioramenti saranno rigorosamente rispettati nella tua istanza di Audience Manager a partire da lunedì 16 marzo 2020. Di conseguenza, i segmenti mappati su una destinazione utilizzando ID multi-dispositivo cesseranno di produrre esportazioni in alcune configurazioni delle regole di unione profili.

Per garantire la corretta integrazione tra l’istanza di Audience Manager e le destinazioni utilizzando ID multi-dispositivo, come Adobe Campaign, assicurati di soddisfare i seguenti requisiti:

1. Esamina la regola di unione profili utilizzata dai segmenti mappati sulla destinazione dell’ID dichiarato di Adobe Campaign. La regola di unione profili deve utilizzare l&#39;opzione [!UICONTROL Last Authenticated Profile], in modo che tutti i profili autenticati possano essere inclusi nelle esportazioni. Se la regola di unione profili utilizza un&#39;opzione diversa, passala a [!UICONTROL Last Authenticated Profile].
2. Seleziona l’origine dati Adobe Campaign Declared ID (ID dichiarato) nelle impostazioni della regola di unione profili.

>[!NOTE]
>
> Se hai raggiunto il numero massimo di [!UICONTROL Profile Merge Rules] e hai bisogno di assistenza per configurarli in base alle istruzioni precedenti, contatta l&#39;Assistenza clienti.

## Configura codice regola di unione {#configure-merge-rule-code}

Segui queste istruzioni per configurare il codice [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] e mobile [!DNL SDK] per l&#39;utilizzo delle regole di unione.

<!-- merge-rules-configure-code.xml -->

### Prerequisiti

Prima di [ completare queste procedure, è necessario impostare ](#create-data-source)un&#39;origine dati multi-dispositivo[ e ](#create-profile-merge-rule)regole di unione profili **.

## Per i clienti del servizio Adobe Experience Platform Identity {#id-service-customers}

[!UICONTROL Adobe Experience Platform Identity Service] e la versione più recente di [DIL](../../dil/dil-overview.md) sono consigliati quando si lavora con [!UICONTROL Profile Merge Rules]. Tuttavia, non è necessario utilizzare [!UICONTROL Adobe Experience Platform Identity Service] per utilizzare questa funzionalità. Se utilizzi solo [!UICONTROL DIL], consulta la [sezione legacy di DIL](#legacy-dil) di seguito.

### Configurare la funzione Set Customer ID

Quando si lavora con [!UICONTROL Adobe Experience Platform Identity Service], la funzione `setCustomerIDs` passa gli ID dichiarati a [!DNL Audience Manager]. Per utilizzare una regola di unione profili, è necessario modificare `setCustomerIDs` per utilizzare il codice di integrazione specificato al momento della creazione di un&#39;origine dati per più dispositivi. Si supponga, ad esempio, di aver creato un&#39;origine dati cross-device con il codice di integrazione `my_datasource_ic`. Per trasmettere un ID dichiarato, devi aggiungere il codice di integrazione alla funzione ID visitatore, come mostrato nell’esempio di codice modificato di seguito.

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

Per ulteriori informazioni, vedere [Creare un Source dati multi-dispositivo](#create-data-source) e [ID cliente e stati di autenticazione](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### Configura funzione `DIL.create`

Le versioni più recenti di [!UICONTROL DIL] ora raccolgono automaticamente [!UICONTROL declared ID] dalla funzione `visitorService` in `DIL.create` (vedi [Variabili ID dichiarate](../declared-ids.md#declared-id-variables)). Controlla la funzione `DIL.create` per assicurarti che sia configurata correttamente come mostrato nell&#39;esempio di codice seguente.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Nella coppia chiave-valore dello spazio dei nomi, la variabile `*`MCORG`*` è l&#39;ID organizzazione [!DNL Experience Cloud]. Se non disponi di questo ID, puoi trovarlo nella sezione [!UICONTROL Administration] del dashboard [!DNL Experience Cloud]. Per visualizzare questo dashboard sono necessarie le autorizzazioni di amministratore. Vedere [Amministrazione: servizi principali](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configurare gli SDK

Consulta la sezione [Configurare gli SDK](#configure-sdks-legacy-dil) di seguito.

## DIL legacy {#legacy-dil}

Se non utilizzi ancora [!DNL Adobe Experience Platform Identity Service], è necessario farlo. Ma, capiamo che passare a un nuovo codice richiede un&#39;attenta riflessione e test. In questi casi, controllare la funzione `DIL.create` per verificare che sia configurata correttamente, come illustrato nell&#39;esempio di codice seguente.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Per ulteriori informazioni, vedere la sezione legacy [!UICONTROL DIL] in [Variabili ID dichiarate](../declared-ids.md#declared-id-variables).

### Configurare gli SDK {#configure-sdks-legacy-dil}

Controlla i metodi nel codice [!DNL SDK] che ti consentono di passare [!UICONTROL declared IDs] da [!DNL Android] e [!DNL iOS] dispositivi mobili. I nomi delle variabili per le librerie di codice [!DNL Android] e [!DNL iOS] sono gli stessi:

* `dpid`: ID dell&#39;origine dati multi-dispositivo.
* `dpuuid`: [!UICONTROL declared ID] (ovvero l&#39;ID utente).

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Sintassi:</b> </p> <p> <pre> void statico pubblico setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Esempio:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
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
      &lbrack;ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"&rbrack;;
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Vedi anche [Metodi Audience Manager per Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) e [Metodi Audience Manager per iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Creare una sorgente di dati](../manage-datasources.md#create-data-source)
