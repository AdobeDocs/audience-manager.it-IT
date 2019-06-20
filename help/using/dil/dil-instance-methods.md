---
description: Le API DIL a livello di istanza consentono di creare e lavorare a livello di codice con gli oggetti Audience Manager. I metodi a livello di istanza migliorano la funzionalità API stabilita dai metodi a livello di classe.
keywords: creare caratteristiche; creare caratteristiche
seo-description: Le API DIL a livello di istanza consentono di creare e lavorare a livello di codice con gli oggetti Audience Manager. I metodi a livello di istanza migliorano la funzionalità API stabilita dai metodi a livello di classe.
seo-title: Metodi DIL a livello di istanza
solution: Audience Manager
title: Metodi DIL a livello di istanza
uuid: aa 5147 bb -51 d 5-41 d 4-a 78 a-e 550 f 7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Metodi DIL a livello di istanza{#instance-level-dil-methods}

Le API a livello di istanza [!UICONTROL DIL] consentono di creare e lavorare a livello di codice con gli oggetti Audience Manager. I metodi a livello di istanza migliorano la funzionalità API stabilita dai metodi a livello di classe.

## Guida introduttiva ai metodi DIL a livello di istanza {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Quando si utilizzano [!UICONTROL DIL] le API a livello di istanza:

* L&#39;accesso richiede un nome partner e un ID di namespace del contenitore (NSID). Contatta il tuo account manager Audience Manager per ottenere queste informazioni.
* Sostituite qualsiasi testo *con corsivo* di esempio nella documentazione API con valore, ID o altra variabile come richiesto dal metodo in uso.

<!-- 

c_instance_start.xml

 -->

## segnali {#signals}

Aggiunge mappature a livello di piattaforma e piattaforma alla stringa query di una richiesta in sospeso.

<!-- 

r_dil_signals.xml

 -->

**Firma funzione:**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Potete catena di altre chiamate API a questo metodo.
>* Se la libreria javascript di Adobe Experience Cloud si trova nella pagina, `submit()` attende che Cloud imposti un cookie prima di inviare una richiesta.


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
| `obj` | Oggetto | Un oggetto che rappresenta le coppie chiave-valore per le mappature a livello di piattaforma. Il parametro accetta stringhe e array come valori delle proprietà nell&#39;oggetto. |
| `prefix` | Stringa | Facoltativo. Il valore della stringa prefissato a ogni chiave oggetto (sostituisce la chiave originale). |
| `return` | DIL. api | Restituisce l&#39;oggetto API dell&#39;istanza DIL corrente. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>' 
 Containernsid: <i>Containernsid</i> }); 
 
// Metodo 1 
var obj = {key 1: 1, key 2: 2}; 
Datalib. api. signals (obj,'c_'). submit (); 
 
// Method 2 
datalib. api. signals ({c_ zdid: 54321}). submit (); 
 
// Method 3 
// will send'c_ key = a &amp; c_ key = 2 &amp; c_ key = 3 'to Audience Manager 
var obj = {key: ['a ','b ','c ']}; 
Datalib. api. signals (obj,'c_'). submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Requisiti del nome per le variabili chiave](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

Aggiunge sids alla stringa query di una richiesta in sospeso.

<!-- 

r_dil_traits.xml

 -->

**Firma della funzione:**`traits:function (sids){}`

>[!NOTE]
>
>Potete catena di altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `sids` | Array | ID segmento caratteristiche in un array. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>var partnerobject = DIL. create ({ 
 partner: '<i>partner name</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. traits (<i>[123, 456, 789]</i>);</code>
</pre>

## registri {#logs}

Aggiungere dati ai file di registro nella richiesta in sospeso.

<!-- 

r_dil_logs.xml

 -->

**Firma della funzione:**`logs: function {key1:value1, key2:value2}`

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>var partnerobject = DIL. create ({ 
 partner:<i>' partner</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. log ({ 
 file: ' dil. js ', 
 message: ' This is the first request '});</code>
</pre>

## submit {#submit}

Invia tutti i dati in sospeso ad Audience Manager per l&#39; [!UICONTROL DIL] istanza.

<!-- 

r_dil_submit.xml

 -->

**Firma funzione:**`submit: function () {}`

>[!NOTE]
>
>Potete catena di altre chiamate API a questo metodo. [!UICONTROL DIL] Inoltre, scrive dati codificati in un cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20``%3B`e punto e virgola.

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123,456, 
789</i>]). log ({ 
 file: ' dil. js ', 
 message: ' This is the first request '}). 
signals ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}). 
submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Requisiti di prefisso per variabili chiave](../features/traits/trait-variable-prefixes.md)


## Afterresult {#afterresult}

Funzione che viene eseguita dopo il callback di pubblicazione di destinazione predefinito.

<!-- 

r_dil_after_result.xml

 -->

**Firma funzione:**`afterResult: function (fn) {}`

>[!NOTE]
>
>Potete catena di altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `fn` | Funzione | La funzione da eseguire dopo che JSON è stato elaborato dal callback predefinito che gestisce la pubblicazione della destinazione. |

**Risposta**

Restituisce un oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. sign({ 
 c_ zdid: <i>54321</i> 
 d_ dma: '<i>default</i>'}). 
afterresult (function (json) { 
 //Do something with the JSON data returned from the server. 
}). submit ();</code>
</pre>

## Cleardata {#cleardata}

Cancella tutti i dati in una richiesta in sospeso.

<!-- 

r_dil_clear_data.xml

 -->

**Firma funzione:**`clearData: function () {}`

>[!NOTE]
>
>Potete catena di altre chiamate API a questo metodo.

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123,456, 789</i>]). log ({ 
 file: ' dil. js ' 
 message: ' This is the first request '}). 
signals ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); 
 
//Reset the pending data 
datalib. cleardata ();</code>
</pre>

## Customqueryparams {#customqueryparams}

Aggiunge parametri di query personalizzati che non vengono definiti in modo esplicito dal server di raccolta dati a una richiesta in sospeso.

<!-- 

r_dil_custom_query_params.xml

 -->

**Firma funzione:**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>Potete catena di altre chiamate API a questo metodo.

**Chiavi di richiesta riservate**

Le seguenti chiavi di richiesta sono riservate e non possono essere sovrascritte da questo metodo:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Risposta**

Restituisce l&#39;oggetto API dell&#39;istanza DIL corrente.

**Codice di esempio**

<pre><code>var partnerobject = DIL. create ({ 
 partner:<i>' partner</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. customqueryparams ({ 
 nid: 54231, 
 ntype: ' default '});</code>
</pre>

## Getcontainernsid {#getcontainernsid}

Restituisce il valore del NSID contenitore per l&#39; [!UICONTROL DIL] istanza. Utile per debug e risoluzione di problemi.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Firma funzione:**`dil.api.getContainerNSID: function () {}`

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
//Verify il contenitore NSID 
var nsid = datalib. api. getcontainernsid ();</code>
</pre>

## Geteventlog {#geteventlog}

Restituisce dati di registro evento ordinati cronologicamente come array di stringhe. Utile per debug e risoluzione di problemi.

<!-- 

r_dil_get_event_log.xml

 -->

**Firma funzione:**`dil.api.getEventLog: function () {}`

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). log ({ 
 file: ' dil. js ', 
 message: ' This is the first request '}); . signals ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); . submit (); 
 
//Check registro per i messaggi 
var log = datalib. api. geteventlog (); 
if (log &amp; &amp; log. length) { 
 alert (log. join ('\ n ')); 
} else { 
 alert ('No log messages '); 
}</code>
</pre>

## Getpartner {#getpartner}

Restituisce il nome del partner per un [!UICONTROL DIL] &#39;istanza. Utile per debug e risoluzione di problemi.

<!-- 

r_dil_get_partner.xml

 -->

**Firma funzione:**`dil.api.getPartner: function () {}`

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>' 
 Containernsid: <i>Containernsid</i> }); 
 
//Verify il nome 
del partner var partner = datalib. api. getpartner ();</code>
</pre>

## Getstate {#getstate}

Restituisce lo stato dell&#39; [!UICONTROL DIL] istanza corrente. Utile per debug e risoluzione di problemi.

<!-- 

r_dil_get_state.xml

 -->

**Firma funzione:**`dil.api.getState: function () {}`

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). log ({ 
 file: ' dil. js ', 
 message: ' This is the first request '}); . signals ({ 
 c. zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); . submit (); 
 
var state = datalib. api. getstate (); 
 
/* Struttura oggetto dello stato stato 
= { 
 Pendingrequest: {<i>pending data for call to server</i>}, 
 Otherrequestinfo: {{ 
 Firingqueue: [], 
 fired: [], 
 attivazione: false, 
 errati: [], 
 Riservedkeys: {{ 
 sids: true, 
 pdata: true, 
 logdata: true, 
 callback: true, 
 Postcallbackfn: true, 
 Useimagerequest: true, 
 }, 
 Firstrequesthasshed: false, 
 num_ of_ jsonp_ responses: 0, 
 num_ of_ jsonp_ errors: 0, 
 num_ of_ img_ responses: 0, 
 num_ of_ img_ errors: 0 
 }, 
 Purchionpublishinginfo: {{ 
 THROTTLE_ START: 3000, 
 Throttletimerset: false, 
 id: " destination_ publishing_ iframe_'+ partner +'_'+ containernsid, 
 url: (costanti. ishttps? ' https://': ' https://fast.') + partner +'.demdex.net/dest3.html?d_nsid=' 
 + Containernsid +'#'+ encodeuricomponent (document. location. href), 
 iframe: null, 
 Iframehasloaded: false, 
 Sendingmessages: false, 
 messaggi: [], 
 Messagesendinginterval: concostanti. POST_ MESSAGE_ ENABLED? 15: 100, 
 //Recommend 100 ms for IE 6 &amp; 7, 15 ms for other browsers 
 Jsonprocessed: [] 
 }} 
*/</code>
</pre>

## Idsync {#idsync}

Consiste di due funzioni che consentono ai partner di dati di scambiare e sincronizzare gli ID utente tra se stessi e Audience Manager.

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
   <td colname="col1"> <code> dil. Instance. api. idsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Tra partner dati diversi e Audience Manager. Ad esempio, il partner x utilizzerà questo per sincronizzare un ID utente con il partner y e inviarlo ad Audience Manager. </p> <p> <p><b>Importante:</b> Questo metodo è obsoleto. Usa il metodo <code> idsyncbyurl </code> dell'istanza Experience Cloud ID Service. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. aamidsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Quando conosci già l'ID utente e vuoi inviarlo ad Audience Manager. </p> <p> <p><b>Importante:</b> Questo metodo è obsoleto. Usa il metodo <code> idsyncbydatasource </code> dell'istanza Experience Cloud ID Service. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Idsync Elements**

`idSync` può comprendere quanto segue:

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
* **`%HTTP_PROTO%`:** Imposta il protocollo della pagina ( `http` o `https`).

**Risposta**

Entrambe le funzioni restituiscono in `Successfully queued` caso di esito positivo. In caso di esito negativo, restituiscono la stringa di un messaggio di errore.

**Codice di esempio**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">// Triggurl with macros replaced 
flowinstance. api. idsync ({ 
 dpid: ' 23 ', // deve essere una stringa 
 url: '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
% 2 Fibs % 3 Adpid % 3 D 420% 26 dpuuid % 3 D % 7 B % 7 Buid % 7 D % 7 D ', 
 Minutestolive: 20160 // facoltativo, impostazione predefinita: 20160 minuti (14 giorni)});</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">// Firèhttps:/https:' +'//dpm.demdex.net/ibs:dpid= &lt; dpid &gt; &amp; dpuuid = &lt; dpuuid &gt;'dilinstance. api. aamidsync ({ 
 dpid: ' 23 ', // deve essere una stringa 
 dpuuid: ' 98765 ', // deve essere una stringa 
 Minutestolive: 20160 // facoltativo, impostazione predefinita: 20160 minuti (14 giorni)});</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Funzioni sincronizzazione nel servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

Aggiunge una callback (che riceve JSON) alla richiesta in sospeso.

<!-- 

r_dil_result.xml

 -->

**Firma funzione:**`result: function (callback) {}`

Questa callback sostituisce il callback predefinito che gestisce la pubblicazione della destinazione.

>[!NOTE]
>
>Potete catena di altre chiamate API a questo metodo.

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `callback` | Funzione | Funzione javascript eseguita dal callback JSONP. |

**Risposta**

Restituisce l&#39;oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). result (function (json) { 
 //Do qualcosa, eventualmente con i dati JSON restituiti dal server. 
}); . submit ();</code>
</pre>

## Securedatacollection {#securedatacollection}

`secureDataCollection` è un parametro booleano che controlla come [!UICONTROL DIL] effettuare chiamate a [!UICONTROL Data Collection Servers (DCS)] e Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Quando `secureDataCollection= true` (predefinito), [!UICONTROL DIL] effettua sempre chiamate sicure HTTPS.

* Quando `secureDataCollection= false`effettua [!UICONTROL DIL] chiamate HTTP o HTTPS seguendo il protocollo di protezione impostato dalla pagina.

>[!IMPORTANT]
>
>Imposta `secureDataCollection= false` se utilizzi visitorapi. js e [!UICONTROL DIL] sulla stessa pagina. Vedi il codice di esempio di seguito.

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Securedatacollection: false});</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Creazione DIL](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` è un parametro booleano vero/falso che controlla in che modo il browser richiede risorse da altri domini.

<!-- 

dil-use-cors-only.xml

 -->

**Panoramica**

`useCORSOnly` è false per impostazione predefinita. False significa che il browser può eseguire verifiche di risorse con CORS o JSONP. Tuttavia, tenta [!UICONTROL DIL] sempre di richiedere prima le risorse con CORS. Se necessario, utilizza JSONP per i browser più datati che non supportano CORS. Se dovete obbligare il browser a utilizzare solo CORS, ad esempio con i siti con requisiti di protezione elevati, impostate `useCORSOnly:true`.

**Esempio di codice**

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Usecorsonly: true});</code>
</pre>

>[!IMPORTANT]
>
>* È consigliabile impostare `useCORSOnly: true` solo quando siete certi che i visitatori del sito dispongono di browser che supportano questa funzione.
>* Quando `useCORSOnly: true`, [!UICONTROL DIL] non effettuerà chiamate ID da Internet Explorer versione 9 o precedente.
>



>[!MORE_ LIKE_ THIS]
>
>* [Creazione DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Servizio Experience Cloud ID: Usecorsonly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Supporto per CORS nel servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## Useimagerequest {#useimagerequest}

Modifica il tipo di richiesta all&#39;immagine `<img>` dallo script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Firma funzione:**`useImageRequest: function () {}`

>[!NOTE]
>
>Potete catena di altre chiamate API a questo metodo.

**Risposta**

Restituisce un oggetto API dell&#39; [!UICONTROL DIL] istanza corrente.

**Codice di esempio**

<pre><code>var datalib = DIL. create ({ 
 partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. traits ([<i>123, 456, 789</i>]). useimagerequest (). submit ();</code>
</pre>

