---
title: Aggiorna la libreria di raccolta dati, ad Audience Manager dalla libreria JavaScript di AppMeasurement alla libreria JavaScript dell’SDK per web.
description: Scopri i passaggi per aggiornare la libreria di raccolta dati, ad Audience Manager dalla libreria JavaScript di AppMeasurement alla libreria JavaScript dell’SDK Web.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# Aggiorna la libreria di raccolta dati, ad Audience Manager dalla libreria JavaScript di AppMeasurement alla libreria JavaScript dell’SDK per web

## Pubblico previsto {#intended-audience}

Questa pagina è destinata agli Audienci Manager di clienti che utilizzano AppMeasurement per inserire in Audience Manager i dati di raccolta web. Per i clienti che utilizzano l&#39;[estensione tag di Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), leggere la guida su come aggiornare la raccolta dati per l&#39;Audience Manager [dall&#39;estensione tag di Audience Manager all&#39;estensione tag di Web SDK](dil-extension-to-web-sdk.md).

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Utilizza l&#39;implementazione esistente**: anche se questo approccio richiede alcune modifiche di implementazione, non richiede un&#39;implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti con modifiche minime alla logica di implementazione.</li><li>**Non richiede uno schema**: per questa fase della migrazione all&#39;SDK Web, non è necessario uno schema XDM. È invece possibile popolare l&#39;oggetto `data`, che invia i dati direttamente ad Audience Manager. Una volta completata la migrazione all’SDK per web, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Audience Manager. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Debito tecnico per l&#39;implementazione**: poiché questo approccio utilizza una forma modificata dell&#39;implementazione esistente, può essere più difficile tenere traccia della logica di implementazione ed eseguire modifiche in futuro quando necessario.</li><li>**È necessaria la mappatura per inviare dati a Platform**: quando l&#39;organizzazione è pronta per utilizzare Real-Time CDP, è necessario inviare dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell&#39;oggetto `data` sia una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita una sola volta per questo flusso di lavoro e non richiede l’apporto di modifiche all’implementazione. Si tratta tuttavia di un passaggio aggiuntivo non richiesto per l’invio di dati in un oggetto XDM.</li></ul> |

L’Adobe consiglia di seguire questo percorso di implementazione nei seguenti scenari:

* È disponibile un’implementazione esistente utilizzando la libreria JavaScript di Adobe Analytics AppMeasurement. Se disponi di un&#39;implementazione che utilizza l&#39;estensione tag Audience Manager, segui [Esegui migrazione dall&#39;estensione tag Audience Manager all&#39;estensione tag Web SDK](dil-extension-to-web-sdk.md).
* Intendi utilizzare Real-Time CDP in futuro, ma non desideri sostituire l’implementazione Audience Manager con un’implementazione Web SDK da zero. La sostituzione dell’implementazione da zero su Web SDK richiede il massimo impegno, ma offre anche l’architettura di implementazione a lungo termine più efficiente. Se la tua organizzazione è disposta a eseguire un&#39;implementazione pulita di Web SDK, consulta la [documentazione di Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) per ulteriori dettagli.

## Passaggi necessari per migrare a Web SDK

Le seguenti fasi contengono obiettivi concreti da perseguire. Fai clic su ogni passaggio per istruzioni dettagliate su come eseguirlo.

+++**1. Crea e configura un flusso di dati**

Creare uno stream di dati in Raccolta dati di Adobe Experience Platform. Quando invii dati a questo stream di dati, questi vengono inoltrati ad Audience Manager. In futuro, lo stesso flusso di dati inoltra i dati a Real-Time CDP.

1. Passa a [experience.adobe.com](https://experience.adobe.com) e accedi con le tue credenziali.
1. Utilizzare la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, selezionare **[!UICONTROL Datastreams]**.
1. Selezionare **[!UICONTROL New Datastream]**.
1. Immettere il nome desiderato, quindi selezionare **[!UICONTROL Save]**.
1. Una volta creato lo stream di dati, selezionare **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, selezionare **[!UICONTROL Audience Manager]**.

   ![Aggiungi servizio Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Il flusso di dati è ora pronto per ricevere e trasmettere i dati ad Audience Manager. Prendi nota dell’ID dello stream di dati, in quanto questo ID è richiesto durante la configurazione dell’SDK web nel codice.

+++

+++**2. Installa la libreria Web SDK JavaScript**

Per informazioni dettagliate e blocchi di codice da utilizzare, consulta [Installare Web SDK utilizzando la libreria JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library). Fare riferimento alla versione più recente di `alloy.js` in modo che sia possibile utilizzare le relative chiamate al metodo.

+++

+++**3. Configura Web SDK**

Configurare l&#39;implementazione in modo che punti allo stream di dati creato nel passaggio 1 utilizzando il comando Web SDK [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview). Il comando `configure` deve essere impostato su ogni pagina, in modo da poterlo includere insieme al codice di installazione della libreria.

Utilizzare le proprietà [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) e [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) all&#39;interno del comando `configure` dell&#39;SDK Web:

* Imposta `edgeConfigId` sull&#39;ID dello stream di dati recuperato dal passaggio precedente.
* Imposta `orgId` sull&#39;ID organizzazione IMS della tua organizzazione.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Facoltativamente, è possibile impostare altre proprietà nel comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) in base ai requisiti di implementazione della propria organizzazione.

+++

+++**4. Aggiorna la logica del codice per utilizzare un payload JSON**

Modificare l&#39;implementazione di Audience Manager in modo che non si basi su `AppMeasurement.js` o sull&#39;oggetto `s`. Imposta invece le variabili in un oggetto JavaScript formattato correttamente, che viene convertito in un oggetto JSON quando viene inviato a Adobe. Disporre di un [livello dati](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) sul sito è molto utile quando si impostano i valori, in quanto è possibile continuare a fare riferimento agli stessi valori.

Per inviare i dati ad Audience Manager, il payload dell&#39;SDK Web deve utilizzare `data.__adobe.audiencemanager` con tutte le variabili di analisi impostate all&#39;interno di questo oggetto. Le variabili all&#39;interno di questo oggetto condividono nomi e formati identici come controparti AppMeasurement di variabili. Ad esempio, se imposti la variabile `products`, non suddividerla in singoli oggetti come si farebbe con XDM. Invece, includila come stringa esattamente se imposti la variabile `s.products`:

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

Questo payload contiene tutti i valori desiderati e tutti i riferimenti all&#39;oggetto `s` nell&#39;implementazione vengono rimossi. Puoi utilizzare una qualsiasi delle risorse fornite da JavaScript per impostare questo oggetto payload, inclusa la notazione del punto per impostare i singoli valori.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. Aggiorna le chiamate del metodo per utilizzare Web SDK**

Aggiorna tutte le istanze in cui chiami [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) e [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), sostituendole con il comando [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview). Ci sono tre scenari da considerare:

* **Tracciamento visualizzazione pagina**: sostituisci la chiamata di tracciamento visualizzazione pagina con il comando `sendEvent` dell&#39;SDK Web:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Tracciamento automatico dei collegamenti**: la proprietà di configurazione [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) è attivata per impostazione predefinita. Imposta automaticamente le variabili di tracciamento dei collegamenti corrette per inviare i dati a Audience Manager. Se si desidera disabilitare il rilevamento automatico dei collegamenti, impostare questa proprietà su `false` nel comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview).

* **Tracciamento manuale dei collegamenti**: l&#39;SDK Web non dispone di comandi separati tra le chiamate pageview e non pageview. Specifica la distinzione all&#39;interno dell&#39;oggetto payload.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Convalida e pubblicazione delle modifiche**

Dopo aver rimosso tutti i riferimenti a AppMeasurement e all&#39;oggetto `s`, pubblica le modifiche nell&#39;ambiente di sviluppo per verificare che la nuova implementazione funzioni. Dopo aver verificato il corretto funzionamento di tutto, puoi pubblicare gli aggiornamenti in produzione.

Se migrato correttamente, `AppMeasurement.js` non è più necessario nel sito e tutti i riferimenti a questo script possono essere rimossi.

+++

A questo punto, l’implementazione Audience Manager viene completamente migrata all’SDK per web ed è pronta per il passaggio a Real-Time CDP in futuro.
