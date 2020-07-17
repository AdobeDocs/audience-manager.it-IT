---
description: Descrive i metodi nello spazio dei nomi DIL.module. Questi moduli consentono di raccogliere i dati a livello di programmazione e di lavorare con  oggetti Audience Manager.
seo-description: Descrive i metodi nello spazio dei nomi DIL.module. Questi moduli consentono di raccogliere i dati a livello di programmazione e di lavorare con  oggetti Audience Manager.
seo-title: Moduli DIL
solution: Audience Manager
title: Moduli DIL
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 4%

---


# Moduli DIL{#dil-modules}

Descrive i metodi nello `DIL.modules` spazio dei nomi. Questi moduli consentono di raccogliere i dati a livello di programmazione e di lavorare con  oggetti Audience Manager.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Funziona con [!UICONTROL DIL] l’invio di elementi di [!DNL Analytics] tag (variabili, proprietà, eVar, ecc.)  Audience Manager. Restituisce i dati in un elenco separato da virgole. Disponibile nella versione 2.6.

**Firma funzione:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>È necessario inserire questo codice nella pagina *prima* della `s.t();` funzione.

<!-- 

r_dil_sc_init.xml

 -->

**Parametri**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nomi </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> Stringa </td> 
   <td colname="col3"> <p>Un array di stringhe che contiene <span class="keyword"> variabili Analytics non enumerate </span> come <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>ecc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Un array di oggetti che contiene enumerate <span class="keyword"> variabili Analytics </span> come prop ed evar (ad esempio <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Intero </td> 
   <td colname="col3"> <p>Indica quanti nomi iterati si desidera restituire. Ad esempio, per restituire due prop o evar, impostate <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Un oggetto che rappresenta l' <span class="keyword"> oggetto Analytics </span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Un oggetto che rappresenta <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Opzioni aggiuntive: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Se non si specifica altro, i punti vengono sostituiti con il carattere di sottolineatura predefinito ( _ ). </p> <p>Ad esempio, <code> s.contextData = {abc.def = '123'} </code>risulterebbe <code> c_contextData_abc_def=123 </code> nella stringa di query della chiamata dell'evento. </p> <p>Questa opzione è disponibile solo nella <span class="wintitle"> versione DIL </span> 5.0 o successiva. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Ad esempio, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> l'array di stringhe viene filtrato dalla raccolta di dati contestuali. Questa opzione esclude le informazioni personali (PII). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Dati acquisiti da siteCatalyst.init**

Questa funzione restituisce dettagli sulle seguenti [!DNL Analytics] proprietà:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**Codice di esempio**

Questo codice crea un elenco separato da virgole di [!DNL Analytics] eventi (proprietà, eVar, ecc.) se esistono dei valori per essi.

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

Per tenere traccia di tutti i [!DNL Analytics] punti dati monitorati senza la funzione aggiuntiva sopra indicata, invocare `siteCatalyst.init` di per sé come segue:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

La `GA.submitUniversalAnalytics();` funzione invia i dati da Google [!DNL Universal Analytics] a  Audience Manager. Questa [!UICONTROL DIL] funzione è progettata per funzionare con `analytics.js`, che è la libreria di codici più recente per Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] non dispone di alcuna conoscenza o controllo sulla libreria di `analytics.js` codici Google. È necessario verificare che [!UICONTROL DIL] la raccolta dati funzioni ancora se o quando Google rilascia nuove versioni di `analytics.js`.
   >
   >
* Non puoi utilizzare `GA.submitUniversalAnalytics();` se stai ancora lavorando con il codice legacy di tracciamento delle analisi di Google (ad esempio, `ga.js` o `dc.js`). Vedi [GA.init](../dil/dil-modules.md#ga-init) .

>



**Firma funzione:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Proprietà**

La `GA.submitUniversalAnalytics();` funzione accetta le seguenti proprietà.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Proprietà </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p>Variabile globale per l’istanza di <span class="keyword"> Google  Analytics </span>. Di solito questo è <code> ga </code> per impostazione predefinita, a meno che tu non abbia personalizzato il tuo <span class="keyword"> Google  il </span> codice Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>Variabile che rappresenta l’istanza di <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Facoltativo)</i> Nella <code> analytics.js </code> libreria, la proprietà interna è la variabile minified <code> 'b' </code>. Questa variabile contiene <span class="keyword"> i dati di Google  Analytics </span> . </p> <p>Questa proprietà è facoltativa perché non è necessario impostarla a meno che Google non modifichi il nome della propria variabile interna. Ad esempio, se la variabile minified viene modificata in <code> 'a' </code>, si effettua la chiamata <code> GA.submitUniversalAnalytics(); </code> come segue: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Ricordare di definire prima l&#39; [!DNL Google Analytics] oggetto, prima della chiamata `ga` e [!UICONTROL DIL] `GA.submitUniversalAnalytics();`. Il codice potrebbe essere simile al seguente:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

La `GA.init()` funzione invia i dati dalla versione precedente o obsoleta di [!DNL Google Analytics] Audience Manager a .

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` funziona solo con il codice di tracciamento legacy di Google Analytics `ga.js` o `dc.js`. Non è possibile richiamare questa [!UICONTROL DIL] funzione se si utilizza `analytics.js`, ovvero la libreria di codici più recente per Google [!DNL Universal Analytics]. [!DNL Audience Manager] i clienti che utilizzano [!UICONTROL DIL] e [!DNL Universal Analytics] devono visualizzare [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Firma funzione:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `_gaq` | Array | Un array che contiene comandi GA. |
| `dilInstance` | Oggetto | Un oggetto che contiene l&#39;istanza DIL. |
| `trackVars` | Oggetto | *(Facoltativo)* Un oggetto costituito dalla `names` proprietà. Questa proprietà è un array di nomi di comandi GA che si desidera tracciare. |

**Chiamate di funzioni GA supportate**

Per impostazione predefinita, `GA.init` acquisisce i dati dalle seguenti funzioni:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL crea chiavi per i dati GA**

 Audience Manager accetta dati sotto forma di coppie chiave-valore, mentre GA funziona con elementi in un array. Per lavorare con i dati GA, [!UICONTROL DIL] crea automaticamente una coppia chiave-valore e forma una chiave come quella riportata di seguito: `c_ <key name>`. Inoltre, gli elementi negli array GA vengono visualizzati in un ordine specifico. Di conseguenza, è necessario fornire tutti i parametri in tale ordine, anche quando non contengono dati. [!UICONTROL DIL] mappa le chiavi per i seguenti metodi GA:

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**Codice di esempio**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

Per tenere traccia di tutte le metriche GA monitorate senza la funzione aggiuntiva sopra indicata, invocare `GA.init` di per sé come segue:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Chiamata evento di esempio**

La chiamata dell&#39;evento URL a  Audience Manager potrebbe essere simile alla seguente:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google  Analytics Tracking Code](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Aggiornamento Web completo: ga.js/dc.js to analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [Aggiunta di analytics.js al sito](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [riferimento ai metodi dell&#39;oggetto ga](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

