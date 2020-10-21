---
description: Le API DIL a livello di istanza consentono di creare e utilizzare in modo programmatico  oggetti Audience Manager. I metodi a livello di istanza migliorano la funzionalità API stabilita dai metodi a livello di classe.
keywords: create traits;create trait
seo-description: Le API DIL a livello di istanza consentono di creare e utilizzare in modo programmatico  oggetti Audience Manager. I metodi a livello di istanza migliorano la funzionalità API stabilita dai metodi a livello di classe.
seo-title: Metodi DIL a livello di istanza
solution: Audience Manager
title: Metodi DIL a livello di istanza
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 15%

---


# Metodi DIL a livello di istanza{#instance-level-dil-methods}

Le [!UICONTROL DIL] API a livello di istanza consentono di creare e utilizzare in modo programmatico  oggetti Audience Manager. I metodi a livello di istanza migliorano la funzionalità API stabilita dai metodi a livello di classe.

## Guida introduttiva ai metodi DIL a livello di istanza {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Quando si utilizzano le [!UICONTROL DIL] API a livello di istanza:

* L&#39;accesso richiede un nome partner e un ID spazio nomi contenitore (NSID). Contattate il vostro responsabile commerciale  Audience Manager per ottenere queste informazioni.
* Sostituite eventuale testo *in corsivo* di esempio nella documentazione API con valore, ID o altra variabile, come richiesto dal metodo con cui state lavorando.

<!-- 

c_instance_start.xml

 -->

## signal {#signals}

Aggiunge mappature a livello di cliente e piattaforma alla stringa di query di una richiesta in sospeso.

<!-- 

r_dil_signals.xml

 -->

**Firma funzione:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Potete catena altre chiamate API a questo metodo.
>* Se la libreria Adobe Experience Cloud JavaScript si trova sulla pagina, `submit()` attende che il Cloud imposti un cookie prima di inviare una richiesta.


**Chiavi richieste riservate**

Le seguenti chiavi di richiesta sono riservate e non possono essere sovrascritte con questo metodo:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `obj` | Oggetto | Un oggetto che rappresenta le coppie chiave-valore per le mappature a livello di piattaforma. Il parametro accetta stringhe e array come valori di proprietà nell&#39;oggetto. |
| `prefix` | Stringa | Facoltativo. Il valore della stringa con il prefisso di ogni chiave di oggetto (sostituisce la chiave originale). |
| `return` | DIL.api | Restituisce l&#39;oggetto API dell&#39;istanza DIL corrente. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

Aggiunge i SID alla stringa di query di una richiesta in sospeso.

<!-- 

r_dil_traits.xml

 -->

**Firma funzione:** `traits:function (sids){}`

>[!NOTE]
>
>Potete catena altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `sids` | Array | ID segmento caratteristica in un array. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Aggiungere dati ai file di registro nella richiesta in sospeso.

<!-- 

r_dil_logs.xml

 -->

**Firma funzione:** `logs: function {key1:value1, key2:value2}`

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## submit {#submit}

Invia tutti i dati in sospeso a  Audience Manager per l&#39; [!UICONTROL DIL] istanza.

<!-- 

r_dil_submit.xml

 -->

**Firma funzione:** `submit: function () {}`

>[!NOTE]
>
>Potete catena altre chiamate API a questo metodo. Inoltre, [!UICONTROL DIL] scrive dati codificati in un cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20` e punto e virgola come `%3B`.

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

Funzione che viene eseguita dopo il callback di pubblicazione di destinazione predefinito.

<!-- 

r_dil_after_result.xml

 -->

**Firma funzione:** `afterResult: function (fn) {}`

>[!NOTE]
>
>Potete catena altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `fn` | Funzione | La funzione che si desidera eseguire dopo JSON viene elaborata dal callback predefinito che gestisce la pubblicazione delle destinazioni. |

**Risposta**

Restituisce un oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

Cancella tutti i dati in una richiesta in sospeso.

<!-- 

r_dil_clear_data.xml

 -->

**Firma funzione:** `clearData: function () {}`

>[!NOTE]
>
>Potete catena altre chiamate API a questo metodo.

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Aggiunge a una richiesta in sospeso parametri di query personalizzati non definiti in modo esplicito dal server di raccolta dati.

<!-- 

r_dil_custom_query_params.xml

 -->

**Firma funzione:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Potete catena altre chiamate API a questo metodo.

**Chiavi richieste riservate**

Le seguenti chiavi di richiesta sono riservate e non possono essere sovrascritte con questo metodo:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Risposta**

Restituisce l&#39;oggetto API dell&#39;istanza DIL corrente.

**Codice di esempio**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Restituisce il valore del NSID contenitore per l&#39; [!UICONTROL DIL] istanza. Utile per il debug e la risoluzione dei problemi.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Firma funzione:** `dil.api.getContainerNSID: function () {}`

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Restituisce i dati del registro eventi ordinati cronologicamente come un array di stringhe. Utile per il debug e la risoluzione dei problemi.

<!-- 

r_dil_get_event_log.xml

 -->

**Firma funzione:** `dil.api.getEventLog: function () {}`

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

Restituisce il nome del partner per un&#39; [!UICONTROL DIL] istanza. Utile per il debug e la risoluzione dei problemi.

<!-- 

r_dil_get_partner.xml

 -->

**Firma funzione:** `dil.api.getPartner: function () {}`

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Restituisce lo stato dell&#39; [!UICONTROL DIL] istanza corrente. Utile per il debug e la risoluzione dei problemi.

<!-- 

r_dil_get_state.xml

 -->

**Firma funzione:** `dil.api.getState: function () {}`

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

È composta da due funzioni che consentono ai partner di dati di scambiare e sincronizzare gli ID utente tra loro e  Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Firma funzione:**

Funziona con [!UICONTROL DIL] versioni 2.10 e 3.1 o successive.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codice </th> 
   <th colname="col2" class="entry"> Sincronizza gli ID utente </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Tra partner di dati diversi e Audience Manager . Ad esempio, il partner x lo utilizza per sincronizzare un ID utente con il partner y e inviarlo al Audience Manager . </p> <p> <p><b>Importante:</b>  Questo metodo è obsoleto. Utilizzare il <code> idSyncByURL </code> metodo dell'istanza di Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Quando si conosce già l'ID utente e si desidera inviarlo  Audience Manager. </p> <p> <p><b>Importante:</b>  Questo metodo è obsoleto. Utilizzare il <code> idSyncByDataSource </code> metodo dell'istanza di Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync Elements**

`idSync` può essere costituito dai seguenti elementi:

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Stringa </td> 
   <td colname="col3"> <p>ID del fornitore dei dati assegnato da Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Stringa </td> 
   <td colname="col3"> <p>ID univoco del fornitore di dati per l'utente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Numero </td> 
   <td colname="col3"> <p><i>(Facoltativo)</i> Imposta la data di scadenza del cookie. Deve essere un numero intero. Impostazione predefinita: 20160 minuti (14 giorni). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> Stringa </td> 
   <td colname="col3"> <p>URL di destinazione. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Macro**

`idSync` accetta le macro seguenti:

* **`%TIMESTAMP%`:** genera una marca temporale (in millisecondi). Utilizzato per svuotare la cache.
* **`%DID%`:** inserisce l&#39;ID di Audience Manager per l&#39;utente.
* **`%HTTP_PROTO%`:** Imposta il protocollo di pagina ( `http` o `https`).

**Risposta**

In `Successfully queued` caso di esito positivo, entrambe le funzioni restituiscono. In caso di esito negativo, restituiscono la stringa di un messaggio di errore.

**Codice di esempio**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## result {#result}

Aggiunge un callback (che riceve JSON) alla richiesta in sospeso.

<!-- 

r_dil_result.xml

 -->

**Firma funzione:** `result: function (callback) {}`

Questo callback sostituisce il callback predefinito che gestisce la pubblicazione delle destinazioni.

>[!NOTE]
>
>Potete catena altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `callback` | Funzione | Funzione JavaScript eseguita dal callback JSONP. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` è un parametro booleano che controlla il modo in cui [!UICONTROL DIL] effettua le chiamate a [!UICONTROL Data Collection Servers (DCS)] e Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Quando `secureDataCollection= true` (impostazione predefinita), effettua [!UICONTROL DIL] sempre chiamate HTTPS sicure.

* Quando `secureDataCollection= false`, [!UICONTROL DIL] effettua chiamate HTTP o HTTPS seguendo il protocollo di sicurezza impostato dalla pagina.

>[!IMPORTANT]
>
>Impostato `secureDataCollection= false` se utilizzi visitorAPI.js e [!UICONTROL DIL] sulla stessa pagina. Vedi l’esempio di codice riportato di seguito.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` è un parametro booleano true/false che controlla come il browser richiede risorse da altri domini.

<!-- 

dil-use-cors-only.xml

 -->

**Panoramica**

`useCORSOnly` è false per impostazione predefinita. False indica che il browser può eseguire controlli delle risorse con CORS o JSONP. Tuttavia, [!UICONTROL DIL] cerca sempre di richiedere risorse prima con CORS. Se necessario, utilizza JSONP per i browser più datati che non supportano CORS. Se dovete obbligare il browser a utilizzare solo CORS, ad esempio con siti che hanno requisiti di sicurezza elevati, impostate `useCORSOnly:true`.

**Esempio di codice**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* È consigliabile impostare `useCORSOnly: true` solo quando si è certi che i visitatori del sito dispongono di browser che supportano questa funzione.
>* Quando `useCORSOnly: true`, [!UICONTROL DIL] non effettua chiamate ID da Internet Explorer versione 9 o versioni precedenti.

>



## useImageRequest {#useimagerequest}

Cambia il tipo di richiesta in immagine `<img>` da script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Firma funzione:** `useImageRequest: function () {}`

>[!NOTE]
>
>Potete catena altre chiamate API a questo metodo.

**Risposta**

Restituisce un oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Requisiti di denominazione delle variabili chiave](../features/traits/trait-key-name-requirements.md)
>* [Requisiti di prefisso delle variabili chiave](../features/traits/trait-variable-prefixes.md)
>* [Funzioni di sincronizzazione in Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/idsync.html)
>* [DIL create](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Servizio identità Adobe Experience Platform: UseCORSOnly](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Supporto CORS in Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/reference/cors.html)

