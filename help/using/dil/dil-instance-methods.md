---
description: Le API DIL a livello di istanza consentono di creare e lavorare in modo programmatico con oggetti Audienci Manager. I metodi a livello di istanza migliorano le funzionalità API stabilite dai metodi a livello di classe.
keywords: creare caratteristiche;creare caratteristiche
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: Metodi DIL a livello di istanza
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 12%

---

# Metodi DIL a livello di istanza{#instance-level-dil-methods}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo di [!DNL Data Integration Library (DIL)] e dell&#39;estensione [!DNL DIL].
>
>I clienti esistenti possono continuare a utilizzare l&#39;implementazione [!DNL DIL]. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

Le API [!UICONTROL DIL] a livello di istanza consentono la creazione e l&#39;utilizzo di oggetti Audience Manager a livello di programmazione. I metodi a livello di istanza migliorano le funzionalità API stabilite dai metodi a livello di classe.

## Guida introduttiva ai metodi DIL a livello di istanza {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Quando si utilizzano le API [!UICONTROL DIL] a livello di istanza:

* L&#39;accesso richiede un nome partner e un ID spazio dei nomi contenitore (NSID). Per ottenere queste informazioni, contatta il tuo account manager di Audience Manager.
* Sostituisci il testo *in corsivo* di esempio nella documentazione dell&#39;API con valore, ID o altra variabile come richiesto dal metodo con cui stai lavorando.

<!-- 

c_instance_start.xml

 -->

## Segnali {#signals}

Aggiunge mappature a livello di cliente e piattaforma alla stringa query di una richiesta in sospeso.

<!-- 

r_dil_signals.xml

 -->

**Firma funzione:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Puoi concatenare altre chiamate API a questo metodo.
>* Se la libreria JavaScript di Adobe Experience Cloud si trova nella pagina, `submit()` attende che il cloud imposti un cookie prima di inviare una richiesta.

**Chiavi di richiesta riservate**

Le seguenti chiavi di richiesta sono riservate e non possono essere sovrascritte da questo metodo:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `obj` | Oggetto | Oggetto che rappresenta le coppie chiave-valore per le mappature a livello di piattaforma. Il parametro accetta stringhe e matrici come valori di proprietà nell&#39;oggetto. |
| `prefix` | Stringa | Facoltativo. Il valore stringa con il prefisso di ogni chiave oggetto (sostituisce la chiave originale). |
| `return` | DIL.api | Restituisce l’oggetto API dell’istanza DIL corrente. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39;istanza [!UICONTROL DIL] corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
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

Aggiunge SID alla stringa query di una richiesta in sospeso.

<!-- 

r_dil_traits.xml

 -->

**Firma funzione:** `traits:function (sids){}`

>[!NOTE]
>
>Puoi concatenare altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `sids` | Array | ID dei segmenti di caratteristiche in un array. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39;istanza [!UICONTROL DIL] corrente.

**Codice di esempio**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## registri {#logs}

Aggiungi dati ai file di registro nella richiesta in sospeso.

<!-- 

r_dil_logs.xml

 -->

**Firma funzione:** `logs: function {key1:value1, key2:value2}`

**Risposta**

Restituisce l&#39;oggetto API dell&#39;istanza [!UICONTROL DIL] corrente.

**Codice di esempio**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);
</code></pre>

## invia {#submit}

Invia tutti i dati in sospeso all&#39;Audience Manager per l&#39;istanza [!UICONTROL DIL].

<!-- 

r_dil_submit.xml

 -->

**Firma funzione:** `submit: function () {}`

>[!NOTE]
>
>Puoi concatenare altre chiamate API a questo metodo. Inoltre, [!UICONTROL DIL] scrive i dati codificati in un cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20` e i punti e virgola come `%3B`.

**Risposta**

Restituisce l&#39;oggetto API dell&#39;istanza [!UICONTROL DIL] corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits(&lbrack; 
<i>123,456, 789</i>&rbrack;).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;).submit();
</code></pre>

## afterResult {#afterresult}

Funzione che viene eseguita dopo il callback di pubblicazione della destinazione predefinita.

<!-- 

r_dil_after_result.xml

 -->

**Firma funzione:** `afterResult: function (fn) {}`

>[!NOTE]
>
>Puoi concatenare altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `fn` | Funzione | La funzione che desideri eseguire dopo che JSON è stato elaborato dal callback predefinito che gestisce la pubblicazione della destinazione. |

**Risposta**

Restituisce un oggetto API dell&#39;istanza [!UICONTROL DIL] corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.signals(&lbrace; 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
&rbrace;).afterResult(function(json)&lbrace; 
     //Do something with the JSON data returned from the server. 
&rbrace;).submit();
</code></pre>

## clearData {#cleardata}

Cancella tutti i dati in una richiesta in sospeso.

<!-- 

r_dil_clear_data.xml

 -->

**Firma funzione:** `clearData: function () {}`

>[!NOTE]
>
>Puoi concatenare altre chiamate API a questo metodo.

**Risposta**

Restituisce l&#39;oggetto API dell&#39;istanza [!UICONTROL DIL] corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs(&lbrace; 
     file: 'dil.js' 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Aggiunge parametri di query personalizzati non definiti in modo esplicito dal server di raccolta dati a una richiesta in sospeso.

<!-- 

r_dil_custom_query_params.xml

 -->

**Firma funzione:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Puoi concatenare altre chiamate API a questo metodo.

**Chiavi di richiesta riservate**

Le seguenti chiavi di richiesta sono riservate e non possono essere sovrascritte da questo metodo:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Risposta**

Restituisce l’oggetto API dell’istanza DIL corrente.

**Codice di esempio**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.customQueryParams(&lbrace; 
     nid: 54231, 
     ntype: 'default' 
&rbrace;); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Restituisce il valore del NSID contenitore per l&#39;istanza [!UICONTROL DIL]. Utile per il debug e la risoluzione dei problemi.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Firma funzione:** `dil.api.getContainerNSID: function () {}`

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Restituisce i dati del registro eventi ordinati cronologicamente come matrice di stringhe. Utile per il debug e la risoluzione dei problemi.

<!-- 

r_dil_get_event_log.xml

 -->

**Firma funzione:** `dil.api.getEventLog: function () {}`

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) &lbrace; 
     alert(log.join('\n')); 
&rbrace;else&lbrace; 
     alert('No log messages'); 
&rbrace;
</code></pre>

## getPartner {#getpartner}

Restituisce il nome del partner per un&#39;istanza [!UICONTROL DIL]. Utile per il debug e la risoluzione dei problemi.

<!-- 

r_dil_get_partner.xml

 -->

**Firma funzione:** `dil.api.getPartner: function () {}`

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Restituisce lo stato dell&#39;istanza [!UICONTROL DIL] corrente. Utile per il debug e la risoluzione dei problemi.

<!-- 

r_dil_get_state.xml

 -->

**Firma funzione:** `dil.api.getState: function () {}`

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message:'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = &lbrace; 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:&lbrace; 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: &lbrace; 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          &rbrace;, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     &rbrace;, 
     destinationPublishingInfo: &lbrace; 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          &#x200B;+ containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     &rbrace; 
&rbrace; 
*/
</code></pre>

## idSync {#idsync}

È costituito da due funzioni che consentono ai partner dati di scambiare e sincronizzare gli ID utente tra loro e con Audience Manager.

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
   <td colname="col2"> <p>Tra partner di dati e Audienci Manager diversi. Ad esempio, il partner x lo utilizzerebbe per sincronizzare un ID utente con il partner y e inviarlo all’Audience Manager. </p> <p> <p><b>Importante:</b> Questo metodo è obsoleto. Utilizzare il metodo <code> idSyncByURL </code> dell'istanza del servizio Adobe Experience Platform Identity. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Quando conosci già l’ID utente e vuoi inviarlo ad Audience Manager. </p> <p> <p><b>Importante:</b> Questo metodo è obsoleto. Utilizzare il metodo <code> idSyncByDataSource </code> dell'istanza del servizio Adobe Experience Platform Identity. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**elementi idSync**

`idSync` può essere costituito da:

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

`idSync` accetta le seguenti macro:

* **`%TIMESTAMP%`:** genera una marca temporale (in millisecondi). Utilizzato per svuotare la cache.
* **`%DID%`:** inserisce l&#39;ID Audience Manager per l&#39;utente.
* **`%HTTP_PROTO%`:** Imposta il protocollo della pagina ( `http` o `https`).

**Risposta**

Entrambe le funzioni restituiscono `Successfully queued` in caso di esito positivo. In caso di esito negativo, restituiscono la stringa di un messaggio di errore.

**Codice di esempio**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync(&lbrace; 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync(&lbrace; 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

## risultato {#result}

Aggiunge un callback (che riceve JSON) alla richiesta in sospeso.

<!-- 

r_dil_result.xml

 -->

**Firma funzione:** `result: function (callback) {}`

Questo callback sostituisce il callback predefinito che gestisce la pubblicazione della destinazione.

>[!NOTE]
>
>Puoi concatenare altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `callback` | Funzione | Funzione JavaScript eseguita dal callback JSONP. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39;istanza [!UICONTROL DIL] corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json)&lbrace; 
     //Do something, possibly with the JSON data returned from the server. 
&rbrace;);.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` è un parametro booleano che controlla come [!UICONTROL DIL] effettua chiamate a [!UICONTROL Data Collection Servers (DCS)] e Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Quando `secureDataCollection= true` (impostazione predefinita), [!UICONTROL DIL] effettua sempre chiamate HTTPS sicure.

* Quando `secureDataCollection= false`, [!UICONTROL DIL] effettua chiamate HTTP o HTTPS seguendo il protocollo di sicurezza impostato dalla pagina.

>[!IMPORTANT]
>
>Imposta `secureDataCollection= false` se usi visitorAPI.js e [!UICONTROL DIL] sulla stessa pagina. Vedi l’esempio di codice seguente.

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     secureDataCollection: false 
&rbrace;);
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` è un parametro booleano true/false che controlla il modo in cui il browser richiede risorse da altri domini.

<!-- 

dil-use-cors-only.xml

 -->

**Panoramica**

`useCORSOnly` è false per impostazione predefinita. False indica che il browser può eseguire controlli delle risorse con CORS o JSONP. Tuttavia, [!UICONTROL DIL] tenta sempre di richiedere risorse prima con CORS. Se necessario, utilizza JSONP per i browser più datati che non supportano CORS. Se devi forzare il solo utilizzo di CORS, ad esempio con siti con requisiti di sicurezza elevati, imposta `useCORSOnly:true`.

**Esempio di codice**

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     useCORSOnly: true 
&rbrace;);
</code></pre>

>[!IMPORTANT]
>
>* È consigliabile impostare `useCORSOnly: true` solo quando si è certi che i visitatori del sito dispongono di browser che supportano questa funzionalità.
>* Quando `useCORSOnly: true`, [!UICONTROL DIL] non effettuerà chiamate ID da Internet Explorer versione 9 o precedenti.
>

## useImageRequest {#useimagerequest}

Modifica il tipo di richiesta in immagine `<img>` dallo script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Firma funzione:** `useImageRequest: function () {}`

>[!NOTE]
>
>Puoi concatenare altre chiamate API a questo metodo.

**Risposta**

Restituisce un oggetto API dell&#39;istanza [!UICONTROL DIL] corrente.

**Codice di esempio**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Requisiti di denominazione delle variabili chiave](../features/traits/trait-key-name-requirements.md)
>* [Requisiti di prefisso delle variabili chiave](../features/traits/trait-variable-prefixes.md)
>* [Funzioni di sincronizzazione nel servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [DIL create](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Servizio Adobe Experience Platform Identity: UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Supporto per CORS nel servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
