---
description: Esempi di codice e descrizioni per casi di utilizzo DIL specifici.
seo-description: Esempi di codice e descrizioni per casi di utilizzo DIL specifici.
seo-title: Casi di utilizzo DIL e esempi di codice
solution: Audience Manager
title: Casi di utilizzo DIL e esempi di codice
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL Use Cases and Code Samples{#dil-use-cases-and-code-samples}

Esempi di codice e descrizioni per casi di utilizzo DIL specifici.

<!-- 

c_dil_use_case.xml

 -->

## Send Data Elements to Audience Manager with DIL {#send-data-elements-dil}

Crea una variabile di oggetto che invia informazioni sugli elementi della pagina ad Audience Manager. Questa funzione è utile per la raccolta dati generale o come alternativa alla raccolta di dati con variabili Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrizione**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. Questi esempi utilizzano una variabile per contenere elementi dati in un elenco semplice o in un array. Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../features/traits/trait-variable-prefixes.md) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**Mantieni proprietà valore coerente**

Tenere presente che durante il passaggio dei dati le proprietà del valore sono uguali. Ad esempio, se sono presenti due chiavi identiche con valori diversi, il valore dell'ultima coppia chiave-valore ha la precedenza sugli oggetti valore precedenti. For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**Esempio 1: Invia dati come coppie chiave-valore**

Questo esempio di base invia dati di colore e prezzi ad Audience Manager sotto forma di coppie chiave-valore. Il codice potrebbe assomigliare a quanto segue:

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
sample_ dil. api. signals ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**Esempio 2: Inviare dati in un oggetto**

Questo esempio avanzato illustra come inviare dati in un oggetto ad Audience Manager. When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] Il codice potrebbe assomigliare a quanto segue:

<pre class="java"><code>var my_ object = { 
 color: " blue ", 
 prezzo: " 900 "}; 
 
var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
//Load l'oggetto e aggiungete "c_" a tutte le chiavi nelle coppie chiave-valore e inviate dati a audiencemanager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Esempio 3: Inviare dati pagina in un array**

In this case, the variable `my_object` uses an array to hold data. Questo esempio si basa sulle informazioni trasmesse dal metodo consigliato sopra, ma aggiunge un livello aggiuntivo per contenere un tipo di prodotto e un modello. Il codice potrebbe assomigliare a quanto segue:

<pre class="java"><code>var my_ objects = [{ 
 color: " blue ", 
 prezzo: " 900 "}, 
{ 
 type: " acura ", 
 modello: " tl "}]; 
 
var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
 
for (var i = 0; i &lt; my_ objects. length; i + +) 
//Load l'oggetto e aggiungete "c_" a tutte le chiavi nelle coppie chiave-valore. 
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

>[!MORE_ LIKE_ THIS]
>
>* [segnali](../dil/dil-instance-methods.md#signals)


## Capture Referring URL {#capture-referring-url}

Acquisisci e invia un URL di provenienza ad Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Questo metodo funziona solo quando gli utenti si spostano tra le pagine con protocolli simili (HTTP vs HTTPS). Ad esempio, il browser mantiene un URL di provenienza quando vi spostate da un sito sicuro a un altro sito protetto. I browser non mantengono l'URL di provenienza quando vi spostate tra siti sicuri e non sicuri. This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**Esempio di codice**

Il codice potrebbe assomigliare a quanto segue:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
adobe_ dil. api. signals ({d_ referer: document. referrer}). submit ();</code>
</pre>

## Capture Search Engine Types and Keyword Search Terms {#capture-search-engine-types}

Invia informazioni sul tipo di motore di ricerca e sulle ricerche di parole chiave ad Audience Manager.

<!-- 

c_dil_search_engine_valid.xml

 -->

**Motori di ricerca supportati**

By default, `DIL.getSearchReferrer` recognizes searches from these search engines (including international variations):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrizione**

Il seguente codice illustra come ottenere il referente di ricerca per i motori di ricerca supportati. In this case, let's assume a user searched on the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Questo codice ti aiuterà a catturare tali termini di ricerca e a inviarli ad Audience Manager.

**Codice di base**

Basic code for getting the search referrer (from `google.com`, for example) looks like this:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Esempio di codice motore di ricerca elencati**

In this case, let's assume that a user searched for the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` è un [prefisso](../features/traits/trait-variable-prefixes.md) necessario che identifica queste variabili come variabili definite dal cliente ad Audience Manager.

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signals ({ 
 c_ se: se. name, 
 c_ st: se. keywords 
 }). submit (); 
}</code>
</pre>

**Esempio di codice motore di ricerca non elencato**

In this case, let's assume that a user searched for the term "homes" from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. Il codice potrebbe assomigliare a quanto segue:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Map Key Values to Other Keys {#map-key-values}

Associare il valore di una coppia chiave-valore a un'altra chiave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrizione**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. I dati definiti dal cliente vengono utilizzati per il targeting sul sito specifico trasmesso nei dati su una chiamata dell'evento. Tuttavia, a volte desiderate che queste informazioni siano disponibili in tutte le proprietà dell'account Audience Manager. To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

Ad esempio, puoi raccogliere i dati del codice ZIP da un particolare sito, ma eseguire il targeting per tutte le proprietà di Audience Manager. To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**Esempio di codice**

Il codice potrebbe assomigliare a quanto segue:

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_ LIKE_ THIS]
>
>* [Requisiti di prefisso per variabili chiave](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurate e servite DIL con un tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM:

1. Create un nuovo contenitore o aprite un contenitore esistente.
1. Aggiungere un nuovo tag al contenitore.
1. Aprite il tag per modificarlo e:

   * Denominate il tag.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`.
   * Fai clic su **[!UICONTROL Save]**.

1. Pubblicate il contenitore.
1. Generate il codice tag contenitore e inseritelo nell'inventario.

>[!MORE_ LIKE_ THIS]
>
>* [Centro di aiuto di Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

