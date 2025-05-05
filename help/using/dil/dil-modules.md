---
description: Descrive i metodi nello spazio dei nomi DIL.modules. Questi moduli ti consentono di raccogliere dati in modo programmatico e lavorare con oggetti Audienci Manager.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: Moduli DIL
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 3%

---

# Moduli DIL{#dil-modules}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo di [!DNL Data Integration Library (DIL)] e dell&#39;estensione [!DNL DIL].
>
>I clienti esistenti possono continuare a utilizzare l&#39;implementazione [!DNL DIL]. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) per la strategia di raccolta dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it).

Descrive i metodi nello spazio dei nomi `DIL.modules`. Questi moduli ti consentono di raccogliere dati in modo programmatico e lavorare con oggetti Audienci Manager.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Utilizza [!UICONTROL DIL] per inviare [!DNL Analytics] elementi tag (variabili, prop, eVar, ecc.) all&#39;Audience Manager. Restituisce i dati in un elenco separato da virgole. Disponibile nella versione 2.6.

**Firma funzione:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Inserire il codice nella pagina *prima* della funzione `s.t();`.

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
   <td colname="col3"> <p>Matrice di stringhe che contiene <span class="keyword"> variabili Analytics </span> non enumerate come <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code> e così via. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Matrice di oggetti che contiene <span class="keyword"> variabili Analytics </span> enumerate come prop ed evar (ad esempio <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Intero </td> 
   <td colname="col3"> <p>Indica quanti nomi iterati si desidera restituire. Ad esempio, per restituire due proprietà o evar, impostare <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Oggetto che rappresenta l'oggetto </span> di Analytics <span class="keyword">. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Oggetto che rappresenta <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Opzioni aggiuntive: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Se non si specifica altro, i punti vengono sostituiti con il carattere di sottolineatura predefinito ( _ ). </p> <p>Ad esempio <code> s.contextData = {abc.def = '123'} </code> produrrebbe <code> c_contextData_abc_def=123 </code> nella stringa di query della chiamata dell'evento. </p> <p>Questa opzione è disponibile solo in <span class="wintitle"> DIL </span> versione 5.0 o successiva. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p><code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code>, ad esempio, causerebbe il filtraggio della matrice di stringhe dalla raccolta di dati di contesto. Sono escluse le informazioni personali (PII, Personally Identifiable Information). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Dati acquisiti da siteCatalyst.init**

Questa funzione restituisce dettagli sulle seguenti proprietà [!DNL Analytics]:

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

Questo codice crea un elenco separato da virgole di [!DNL Analytics] eventi (prop, eVar, ecc.) se esistono dei valori per esse.

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

Per tenere traccia di tutti i punti dati [!DNL Analytics] monitorati senza la funzione aggiuntiva mostrata sopra, richiama `siteCatalyst.init` da solo come segue:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

La funzione `GA.submitUniversalAnalytics();` invia i dati da [!DNL Universal Analytics] di Google all&#39;Audience Manager. Questa funzione [!UICONTROL DIL] è progettata per funzionare con `analytics.js`, che è la libreria di codici più recente per Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] non dispone di informazioni approfondite o controllo sulla libreria di codici di Google `analytics.js`. Verificare che la raccolta dati [!UICONTROL DIL] funzioni ancora se o quando Google rilascia nuove versioni di `analytics.js`.
>
>* Non puoi usare `GA.submitUniversalAnalytics();` se lavori ancora con il codice di tracciamento Analytics legacy di Google (ad esempio, `ga.js` o `dc.js`). Vedi [GA.init](../dil/dil-modules.md#ga-init).
>

**Firma funzione:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Proprietà**

La funzione `GA.submitUniversalAnalytics();` accetta le seguenti proprietà.

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
   <td colname="col2"> <p>La variabile globale per l'istanza di <span class="keyword"> Google Analytics </span>. In genere si tratta di <code> ga </code> per impostazione predefinita, a meno che non sia stato personalizzato <span class="keyword"> Google Analytics il codice </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>La variabile che rappresenta l'istanza di <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Facoltativo)</i> Nella libreria <code> analytics.js </code>, la proprietà interna è la variabile minimizzata <code> 'b' </code>. Questa variabile contiene <span class="keyword"> Google Analytics </span> dati. </p> <p>Questa proprietà è facoltativa perché non è necessario impostarla a meno che Google non modifichi il nome della variabile interna. Ad esempio, se questa variabile minimizzata è cambiata in <code> 'a' </code>, chiamerai <code> GA.submitUniversalAnalytics(); </code> come segue: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Ricordarsi di definire l&#39;oggetto [!DNL Google Analytics] `ga` prima di chiamare [!UICONTROL DIL] e `GA.submitUniversalAnalytics();`. Il codice sarà simile al seguente:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

La funzione `GA.init()` invia i dati dalla versione legacy/obsoleta di [!DNL Google Analytics] all&#39;Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` funziona solo con il codice di tracciamento Analytics legacy di Google, `ga.js` o `dc.js`. Impossibile richiamare questa funzione [!UICONTROL DIL] se si utilizza `analytics.js`, che è la libreria di codici più recente per Google [!DNL Universal Analytics]. I clienti [!DNL Audience Manager] che utilizzano [!UICONTROL DIL] e [!DNL Universal Analytics] dovrebbero visualizzare [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Firma funzione:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `_gaq` | Array | Matrice contenente comandi GA. |
| `dilInstance` | Oggetto | Oggetto contenente l’istanza DIL. |
| `trackVars` | Oggetto | *(facoltativo)* Oggetto costituito dalla proprietà `names`. Questa proprietà è una matrice di nomi di comandi GA di cui si desidera tenere traccia. |

**Chiamate di funzione GA supportate**

Per impostazione predefinita, `GA.init` acquisisce i dati dalle seguenti funzioni:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL crea chiavi per dati GA**

Audience Manager accetta i dati sotto forma di coppie chiave-valore, mentre GA funziona con gli elementi in un array. Per utilizzare i dati GA, [!UICONTROL DIL] crea automaticamente una coppia chiave-valore e forma una chiave come questa: `c_ <key name>`. Inoltre, gli elementi negli array GA vengono visualizzati in un ordine specifico. Di conseguenza, è necessario fornire tutti i parametri in tale ordine, anche quando non contengono dati. [!UICONTROL DIL] mappa le chiavi per i seguenti metodi GA:

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

Per tenere traccia di tutte le metriche GA monitorate senza la funzione aggiuntiva mostrata sopra, richiama `GA.init` da solo come segue:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Chiamata evento di esempio**

La chiamata evento URL all’Audience Manager potrebbe essere simile alla seguente:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics codice di tracciamento](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Aggiornamento Web completo: ga.js/dc.js a analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Aggiunta di analytics.js al sito](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [ga Riferimento metodi oggetto](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)
