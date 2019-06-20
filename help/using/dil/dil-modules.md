---
description: Descrive i metodi nello spazio nomi DIL. module. Questi moduli consentono di raccogliere dati e lavorare con gli oggetti Audience Manager in modo programmatico.
seo-description: Descrive i metodi nello spazio nomi DIL. module. Questi moduli consentono di raccogliere dati e lavorare con gli oggetti Audience Manager in modo programmatico.
seo-title: Moduli DIL
solution: Audience Manager
title: Moduli DIL
uuid: d 4 c 0 d 8 dd -79 f 8-448 e-b 17 c-c 935415 dd 449
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Moduli DIL{#dil-modules}

Descrive i metodi nello `DIL.modules` spazio nomi. Questi moduli consentono di raccogliere dati e lavorare con gli oggetti Audience Manager in modo programmatico.

<!-- 

c_dil_mods.xml

 -->

## Sitecatalyst. init {#sitecat-init}

Funziona con [!UICONTROL DIL] l&#39;invio [!DNL Analytics] di elementi tag (variabili, proprietà, evar ecc.) ad Audience Manager. Restituisce dati in un elenco separato da virgole. Disponibile nella versione 2.6.

**Firma funzione:**`DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>È necessario posizionare questo codice sulla pagina *prima* della `s.t();` funzione.

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
   <td colname="col3"> <p>Un array di stringhe che contiene variabili <span class="keyword"> di Analytics </span> non enumerate come <code> pagename </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Iteratednames </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Array di oggetti che contiene variabili <span class="keyword"> di Analytics </span> enumerate come prop ed evar (ad es <code> . prop 1 </code>, <code> prop 2 </code>, <code> evar 3 </code>, <code> evar 4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Maxindex </code> </td> 
   <td colname="col2"> Intero </td> 
   <td colname="col3"> <p>Indica il numero di nomi ripetuti da restituire. Ad esempio, per restituire due proprietà o evar, impostare <code> maxindex: 2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Sitecatalystreportingsuite </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Un oggetto che rappresenta l'oggetto <span class="keyword"> Analytics </span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Dilinstance </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Un oggetto che rappresenta <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Oggetto </td> 
   <td colname="col3"> <p>Opzioni aggiuntive: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> Replacecontextdataperiodswith </code> </p> <p>Se non si specifica altro, i punti vengono sostituiti con il carattere di sottolineatura predefinito (_). </p> <p>Ad esempio <code> , s. contextdata = {abc. def ='123 '} </code>restituisce <code> c_ contextdata_ abc_ def = 123 </code> nella stringa query di chiamata dell'evento. </p> <p>Questa opzione è disponibile solo in <span class="wintitle"> DIL </span> versione 5.0 o successiva. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> Filterfromcontextvariables </code> </p> <p>Ad esempio, <code> filterfromcontextvariables: ['email ','zip ','accountnumber '] </code> restituirebbe l'array di stringhe che vengono filtrate dalla raccolta dati dei dati contestuali. Questa opzione esclude le Informazioni personali (PII). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Dati acquisiti da sitecatalyst. init**

Questa funzione restituisce i dettagli sulle [!DNL Analytics] proprietà seguenti:

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

Questo codice crea un elenco separato da virgole di [!DNL Analytics] eventi (proprietà, evar ecc.) se esistono dei valori.

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

Per tenere traccia di tutti i punti [!DNL Analytics] dati monitorati senza la funzione aggiuntiva visualizzata sopra, richiamate se stesso `siteCatalyst.init` come segue:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA. submituniversalanalytics {#ga-submit-universal-analytics}

La `GA.submitUniversalAnalytics();` funzione invia dati da Google [!DNL Universal Analytics] ad Audience Manager. Questa [!UICONTROL DIL] funzione è progettata per `analytics.js`l&#39;utilizzo, che è la libreria di codici più recente per Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] non ha informazioni o controllo sulla libreria `analytics.js` dei codici Google. Verifica che la raccolta [!UICONTROL DIL] dati funzioni comunque se o quando Google rilascia nuove versioni di `analytics.js`.
   >
   >
* Non puoi usarlo `GA.submitUniversalAnalytics();` se stai ancora lavorando con il codice di tracciamento legacy di Analytics (ad es. `ga.js` , o `dc.js`). Vedi [GA. init](../dil/dil-modules.md#ga-init) .
>



**Firma funzione:**`DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Proprietà**

La `GA.submitUniversalAnalytics();` funzione accetta le proprietà seguenti.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Proprietà </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Gaobject </code> </p> </td> 
   <td colname="col2"> <p>La variabile globale per l'istanza <span class="keyword"> di Google Analytics </span>. In genere <code> questa opzione è predefinita, </code> a meno che non abbiate personalizzato il <span class="keyword"></span> codice Google Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dilinstance </code> </p> </td> 
   <td colname="col2"> <p>La variabile che rappresenta l'istanza <span class="wintitle"> di DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Internalpropertyname </code> </p> </td> 
   <td colname="col2"> <p> <i>(Facoltativo)</i> Nella libreria <code> analytics. js </code> , la proprietà internal è la variabile <code> minged «b» </code>. Questa variabile contiene <span class="keyword"></span> i dati di Google Analytics. </p> <p>Questa proprietà è facoltativa perché non è necessario impostarla a meno che Google non modifichi il nome della loro variabile interna. Ad esempio, se la variabile minged è stata modificata in <code> 'a ' </code>, chiamare <code> GA. submituniversalanalytics (); </code> come segue: </p> <p> <code> DIL. modules. gasubmituniversalanalytics (ga, garcia,'a '); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

Ricordare di definire prima l&#39; [!DNL Google Analytics]`ga` oggetto, prima di richiamare [!UICONTROL DIL] e `GA.submitUniversalAnalytics();`. Il codice potrebbe essere simile al seguente:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

>[!MORE_ LIKE_ THIS]
>
>* [Riferimento ai metodi dell&#39;oggetto ga](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)


## GA. init {#ga-init}

La `GA.init()` funzione invia dati dalla versione legacy o obsoleta di [!DNL Google Analytics] Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` funziona solo con il codice di tracciamento legacy di Analytics `ga.js` o `dc.js`. Non puoi richiamare questa [!UICONTROL DIL] funzione se utilizzi `analytics.js`, che è la libreria di codici più recente per Google [!DNL Universal Analytics]. [!DNL Audience Manager] clienti che usano [!UICONTROL DIL] e [!DNL Universal Analytics] devono vedere [GA. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Firma funzione:**`DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parametri**

| Nome | Tipo | Descrizione |
|---|---|---|
| `_gaq` | Array | Array contenente i comandi GA. |
| `dilInstance` | Oggetto | Un oggetto che contiene l&#39;istanza DIL. |
| `trackVars` | Oggetto | *(Facoltativo)* Un oggetto composto dalla `names` proprietà. Questa proprietà è un array di nomi di comandi GA che si desidera tenere traccia. |

**Chiamate di funzioni GA supportate**

Per impostazione predefinita `GA.init` , acquisisce i dati dalle seguenti funzioni:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL crea tasti per i dati GA**

Audience Manager accetta dati sotto forma di coppie chiave-valore mentre GA funziona con elementi in un array. Per utilizzare i dati GA [!UICONTROL DIL] , crea automaticamente una coppia chiave-valore e crea una chiave come questa: `c_ <key name>`. Inoltre, gli elementi negli array GA vengono visualizzati in un ordine specifico. Di conseguenza, è necessario fornire tutti i parametri in tale ordine, anche quando non contengono dati. [!UICONTROL DIL] le chiavi mappe per i seguenti metodi GA:

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

Per tenere traccia di tutte le metriche GA monitorate senza la funzione aggiuntiva mostrata sopra, richiamate se stesso `GA.init` come segue:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Chiamata evento di esempio**

La chiamata degli eventi URL ad Audience Manager potrebbe essere simile a quella riportata di seguito:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORE_ LIKE_ THIS]
>
>* [Codice di tracciamento di Google Analytics](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Aggiornamento Web completo: ga.js/dc.js to analytics. js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [Aggiunta di analytics. js al sito](https://developers.google.com/analytics/devguides/collection/analyticsjs/)

