---
description: Per creare la revisione delle regole di unione profili e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.
seo-description: Per creare la revisione delle regole di unione profili e completare i passaggi descritti in ciascuna delle procedure descritte in questa sezione.
seo-title: Guida introduttiva alle regole di unione profili
solution: Audience Manager
title: Guida introduttiva alle regole di unione profili
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 3%

---

# Guida introduttiva alle regole di unione profili {#getting-started-with-profile-merge-rules}

Per creare [!UICONTROL Profile Merge Rules], rivedi e completa i passaggi descritti in ciascuna delle procedure descritte in questa sezione.

<!-- merge-rules-start.xml -->

## Creare un&#39;origine dati multi-dispositivo {#create-data-source}

Per creare un’origine dati multi-dispositivo, passa a **[!UICONTROL Audience Data > Data Sources > Add New]** e completa i passaggi per ogni sezione descritta qui. Per creare o modificare un’origine dati multi-dispositivo sono necessarie le autorizzazioni di amministratore.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Per la descrizione di questi diversi controlli, consulta [Impostazioni origine dati e Opzioni menu](../datasources-list-and-settings.md#settings-menu-options) .

## Dettagli origine dati {#details}

Per completare la sezione [!UICONTROL Data Source Details]:

1. Denomina l&#39;origine dati.
2. *(Facoltativo)* Descrivere l’origine dati. Una descrizione concisa ti aiuta a definire il ruolo o lo scopo dell’origine dati.
3. Fornisci un codice di integrazione. Un codice di integrazione è il tuo ID univoco per questa origine dati.
4. Nell’elenco **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
5. Nell’elenco **[!UICONTROL ID Definition]**, seleziona un’opzione che definisce il tipo di origine dati. Le opzioni includono:
   * **[!UICONTROL Person]**: Un ID che definisce una singola persona. Questo ID può essere mappato su più [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: Un ID che definisce un gruppo di persone. Questo ID può essere mappato su più [!DNL Audience Manager] ID.

## Controlli sull’esportazione dei dati {#export-controls}

[I ](../data-export-controls.md) controlli sull’esportazione dei dati sono regole di classificazione facoltative applicabili a un’origine dati e a una destinazione dati. Ti impediscono di inviare dati a una destinazione quando tale azione viola la privacy dei dati o l’accordo di utilizzo. Ignora questa sezione se non utilizzi [!UICONTROL Data Export Controls].

## Impostazioni origine dati {#settings}

[!UICONTROL Data Source Settings] Questa sezione fornisce più opzioni, ma queste due sono importanti per la creazione di un’origine dati multi-dispositivo:

* **[!UICONTROL Use as Authenticated Profile]**: Selezionata per impostazione predefinita, questa impostazione ti consente di creare un  [!UICONTROL Profile Merge Rule] con i tuoi dati autenticati.

* **[!UICONTROL Use as a Device Graph]**: Questo controllo è disponibile solo per gli account elencati come provider di dati. Selezionando questa casella di controllo, l&#39;origine dati viene creata come grafico dei dispositivi e puoi condividerla con altri clienti [!DNL Audience Manager]. Collabora con il tuo consulente [!DNL Audience Manager] per essere configurato come provider di dati e per specificare con quali clienti deve essere condiviso questo [!UICONTROL Data Source]. Il tuo consulente fornirà il tuo account e la condivisione del grafico del dispositivo tramite processi di provisioning interni.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Questo controllo consente di impostare il periodo di conservazione dei dati per gli ID cliente inattivi. Questo determina per quanto tempo Audience Manager mantiene gli ID cliente nel nostro database dopo che sono stati visti per l’ultima volta sulla piattaforma Audience Manager. Il valore predefinito è 24 mesi (720 giorni). Il valore minimo impostabile è 1 mese e il valore massimo è 5 anni. Tieni presente che contiamo tutti i mesi come 30 giorni. Audience Manager esegue un processo che elimina gli ID cliente inattivi una volta alla settimana, in conformità con la conservazione dei dati impostata per gli ID cliente inattivi.

I campi di testo associati a queste impostazioni consentono di rinominare il [!UICONTROL Data Source] con un alias visualizzato nelle opzioni [Regola di unione profili](merge-rule-definitions.md). Ad esempio, se aggiungi un alias a **[!UICONTROL Use as Authenticated Profile]**, questo nome verrà visualizzato nell&#39;elenco [!UICONTROL Authenticated Profile Options]. Se si aggiunge un alias a **[!UICONTROL Use as a Device Graph]**, tale nome verrà visualizzato nell&#39;elenco [!UICONTROL Device Options].

## Creare una regola di unione profili {#create-profile-merge-rule}

Per creare un [!UICONTROL Profile Merge Rule], vai a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** e completa i passaggi per ogni sezione descritta qui.

È possibile creare fino a 3 regole di unione dopo aver impostato un’origine dati multi-dispositivo. Puoi accedere a una quarta regola di unione profili ([!UICONTROL All Cross-Device Profiles]) se ti registri a [Destinazioni basate su persone](../destinations/people-based-destinations-overview.md).

Per creare, modificare o eliminare una regola sono necessarie le autorizzazioni di amministratore. Tutti gli utenti possono visualizzare e utilizzare [!UICONTROL Profile Merge Rules] esistente.

<!-- create-profile-merge-rule.xml -->

**Prerequisiti:** per creare un’origine dati multi-dispositivo è necessaria un’origine dati  [!UICONTROL Profile Merge Rule]. Consulta [Creare un&#39;origine dati](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Per la descrizione di questi diversi controlli, consulta [Opzioni regola di unione profili definite](merge-rule-definitions.md) .

## Informazioni di base {#basic-info}

Per completare la sezione [!UICONTROL Basic Information]:

1. Denomina il simbolo [!UICONTROL Profile Merge Rule].
2. *(Facoltativo)* Descrivi il  [!UICONTROL Profile Merge Rule]. Una descrizione concisa ti aiuta a definire il ruolo o lo scopo della regola.
3. *(Facoltativo)* Seleziona  **[!UICONTROL Set as default]** se desideri che questo sia il valore predefinito  [!UICONTROL Profile Merge Rule]. I nuovi segmenti vengono associati automaticamente alla regola predefinita.

## Controlli sull’esportazione dei dati {#data-export-controls}

[I ](../data-export-controls.md) controlli di esportazione dei dati sono regole di classificazione facoltative applicabili al tuo  [!UICONTROL Profile Merge Rule]. Ti impediscono di inviare dati a una destinazione quando tale azione viola la privacy dei dati o l’accordo di utilizzo. Ignora questa sezione se non utilizzi [!UICONTROL Data Export Controls].

## Impostazione regola di unione profili {#profile-merge-rule-setup}

Per completare la sezione [!UICONTROL Proflie Merge Rule Setup]:

1. Seleziona un **[!UICONTROL Authenticated Option]**. Le opzioni includono:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Seleziona un **[!UICONTROL Authenticated Profile Option]** (fino a 3, massimo). Si tratta delle [origini dati multi-dispositivo](merge-rules-start.md) create in precedenza.
3. Seleziona una **[!UICONTROL Device Option]**. Le opzioni includono:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Clic **[!UICONTROL Save]**.

### Considerazioni sulle destinazioni Adobe Campaign che utilizzano ID multi-dispositivo come chiavi ID utente {#considerations}

Alla fine del 2019, è stata rilasciata una serie di miglioramenti delle regole di unione profili per migliorare la precisione dei file batch generati utilizzando ID multi-dispositivo. Questi miglioramenti saranno rigorosamente rispettati nell’Audience Manager a partire da lunedì 16 marzo 2020. Di conseguenza, i segmenti mappati a una destinazione utilizzando un ID multi-dispositivo cesseranno di produrre esportazioni in alcune configurazioni di Profile Merge Rules.

Per garantire la corretta integrazione tra l’istanza di Audience Manager e le destinazioni utilizzando ID multi-dispositivo, come Adobe Campaign, assicurati di soddisfare i seguenti requisiti:

1. Rivedi la regola di unione profili utilizzata dai segmenti mappati alla destinazione Adobe Campaign Declared ID. La regola di unione profili deve utilizzare l’opzione [!UICONTROL Last Authenticated Profile] in modo che tutti i profili autenticati possano essere inclusi nelle esportazioni. Se la regola di unione profili utilizza un’opzione diversa, impostala su [!UICONTROL Last Authenticated Profile].
2. Seleziona l’origine dati Adobe Campaign Declared ID nelle impostazioni Regola di unione profili .

>[!NOTE]
>
> Se hai raggiunto il numero massimo di [!UICONTROL Profile Merge Rules] e hai bisogno di assistenza per configurarli in base alle istruzioni di cui sopra, contatta l’Assistenza clienti.

## Configura il codice della regola di unione {#configure-merge-rule-code}

Segui queste istruzioni per impostare il codice [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] e mobile [!DNL SDK] in modo che funzioni con le regole di unione.

<!-- merge-rules-configure-code.xml -->

### Prerequisiti

È necessario impostare una [origine dati multi-dispositivo](#create-data-source) e [regole di unione profili](#create-profile-merge-rule) *prima di* di completare queste procedure.

## Clienti del servizio Adobe Experience Platform Identity {#id-service-customers}

Quando si lavora con [!UICONTROL Profile Merge Rules], è consigliabile utilizzare [!UICONTROL Adobe Experience Platform Identity Service] e l&#39;ultima versione di [DIL](../../dil/dil-overview.md). Tuttavia, non è necessario utilizzare [!UICONTROL Adobe Experience Platform Identity Service] per utilizzare questa funzione. Se utilizzi solo [!UICONTROL DIL], consulta la sezione [legacy DIL](#legacy-dil) di seguito.

### Configurare la funzione Imposta ID cliente

Quando lavori con [!UICONTROL Adobe Experience Platform Identity Service], la funzione `setCustomerIDs` passa gli ID dichiarati a [!DNL Audience Manager]. Per utilizzare una regola di unione profili, devi modificare `setCustomerIDs` per utilizzare il codice di integrazione specificato durante la creazione di un’origine dati multi-dispositivo. Ad esempio, supponiamo che tu abbia creato un’origine dati multi-dispositivo con il codice di integrazione `my_datasource_ic`. Per trasmettere un ID dichiarato, devi aggiungere il codice di integrazione alla funzione ID visitatore come mostrato nell&#39;esempio di codice modificato seguente.

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

Per ulteriori informazioni, consulta [Creare un’origine dati multi-dispositivo](#create-data-source) e [ID cliente e stati di autenticazione](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Configura la funzione `DIL.create`

Le versioni più recenti di [!UICONTROL DIL] ora selezionano automaticamente il [!UICONTROL declared ID] dalla funzione `visitorService` in `DIL.create` (vedi [Variabili di ID dichiarate](../declared-ids.md#declared-id-variables)). Controlla la tua funzione `DIL.create` per assicurarti che sia configurata correttamente come mostrato nel codice di esempio di seguito.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Nella coppia chiave-valore dello spazio dei nomi , la variabile `*`MCORG`*` è l&#39; [!DNL Experience Cloud] ID organizzazione. Se non disponi di questo ID, puoi trovarlo nella sezione [!UICONTROL Administration] del dashboard [!DNL Experience Cloud]. Per visualizzare questo dashboard è necessario disporre delle autorizzazioni di amministratore. Consulta [Amministrazione: Servizi di base](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configurare gli SDK

Consulta la sezione [Configura SDK](#configure-sdks-legacy-dil) di seguito.

## DIL legacy {#legacy-dil}

Se non utilizzi ancora [!DNL Adobe Experience Platform Identity Service], devi davvero farlo. Ma sappiamo che il passaggio al nuovo codice richiede un attento esame e riflessione. In questi casi, controlla la tua funzione `DIL.create` per assicurarti che sia impostata correttamente come mostrato nel codice di esempio di seguito.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Per ulteriori informazioni, consulta la sezione precedente [!UICONTROL DIL] in [Variabili di ID dichiarate](../declared-ids.md#declared-id-variables).

### Configurare gli SDK {#configure-sdks-legacy-dil}

Controlla i metodi nel codice [!DNL SDK] che ti permettono di passare [!UICONTROL declared IDs] da [!DNL Android] e [!DNL iOS] dispositivi mobili. I nomi delle variabili per le librerie di codice [!DNL Android] e [!DNL iOS] sono gli stessi:

* `dpid`: L&#39;ID sorgente dati multi-dispositivo.
* `dpuuid`: L’  [!UICONTROL declared ID] (ovvero, l’ID utente).

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

Vedi anche Metodi di Audience Manager per Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) e Metodi di Audience Manager per iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html) .[[

>[!MORELIKETHIS]
>
>* [Creare una sorgente di dati](../manage-datasources.md#create-data-source)

