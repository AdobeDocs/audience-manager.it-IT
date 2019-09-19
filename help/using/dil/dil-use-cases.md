---
description: Esempi di codice e descrizioni per casi di utilizzo DIL specifici.
seo-description: Esempi di codice e descrizioni per casi di utilizzo DIL specifici.
seo-title: Casi di utilizzo DIL ed esempi di codice
solution: Audience Manager
title: Casi di utilizzo DIL ed esempi di codice
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# Casi di utilizzo DIL ed esempi di codice{#dil-use-cases-and-code-samples}

Esempi di codice e descrizioni per casi di utilizzo DIL specifici.

<!-- 

c_dil_use_case.xml

 -->

## Invia elementi dati ad Audience Manager con DIL {#send-data-elements-dil}

Create una variabile oggetto che invia informazioni sugli elementi della pagina ad Audience Manager. Questo è utile per la raccolta dati generale o come alternativa alla raccolta di dati con variabili Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrizione**

Il codice seguente illustra come raccogliere i dati della pagina e inviarli ad Audience Manager con [!UICONTROL DIL]. Questi esempi utilizzano una variabile per contenere gli elementi di dati in un elenco semplice o in un array. Ricorda, trasmetti le variabili come coppie [](../reference/key-value-pairs-explained.md)chiave-valore. Inoltre, prendete nota del `c_` prefisso prima del tasto nella coppia chiave-valore. Questo prefisso [](../features/traits/trait-variable-prefixes.md) obbligatorio identifica le informazioni come dati definiti dall’utente. Nel primo esempio, è necessario aggiungere manualmente `c_` la chiave. Nel secondo esempio, [!UICONTROL DIL] esegue automaticamente questa operazione.

**Mantieni costanti le proprietà del valore**

Durante il trasferimento dei dati, ricordare di mantenere le proprietà del valore uguali. Ad esempio, in presenza di due chiavi identiche con valori diversi, il valore dell'ultima coppia chiave-valore ha la precedenza sugli oggetti valore precedenti. Ad esempio, passando `color:blue` e `color:red` impostando il valore restituito su rosso (sovrascrive il blu).

**Esempio 1: Invia dati come coppie chiave-valore**

Questo esempio di base invia dati su colore e prezzo ad Audience Manager sotto forma di coppie chiave-valore. Il codice potrebbe essere simile al seguente:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signal({ c_color:"blue", c_price:"900" }); 
sample_dil.api.submit();
</code></pre>

**Esempio 2: Invio di dati in un oggetto**

Questo esempio avanzato illustra come inviare dati in un oggetto ad Audience Manager. Quando si utilizza questo metodo, [!UICONTROL DIL] consente di trasmettere un oggetto come parametro di funzione al [!DNL signals()] metodo. [!UICONTROL DIL] Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var my_object = { color : "blue", prezzo : "900" }; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Carica l'oggetto e aggiungi "c_" a tutte le chiavi nelle coppie chiave-valore e invia i dati ad AudienceManager. 
sample_dil.api.signal(my_object,"c_").submit();
</code></pre>

**Esempio 3: Invia dati di pagina in un array**

In questo caso, la variabile `my_object` utilizza un array per contenere i dati. Questo esempio si basa sulle informazioni trasmesse con il metodo consigliato sopra, ma aggiunge un livello aggiuntivo per contenere un tipo di prodotto e un modello. Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var my_objects = [{ color : "blue", prezzo : "900" }, { type : "acura", modello: "tl" }]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i &lt; my_objects.length; i+) //Carica l'oggetto e aggiungi "c_" a tutti i tasti nelle coppie chiave-valore.  
{ sample_dil.api.signal(my_objects[i], "c_"); 
} sample_dil.api.submit();
</code></pre>

>[!MORE_LIKE_this]
>
>* [signal](../dil/dil-instance-methods.md#signals)


## Acquisisci URL di riferimento {#capture-referring-url}

Acquisisci e invia un URL di provenienza ad Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Questo metodo funziona solo quando gli utenti si spostano tra pagine con protocolli simili (HTTP e HTTPS). Ad esempio, il browser mantiene un URL di provenienza quando si passa da un sito protetto a un altro sito protetto. I browser non conservano l'URL di provenienza quando si passa da un sito sicuro a un altro. Questo comportamento è normale funzionalità del browser e non può essere eluso da [!UICONTROL DIL].

**Esempio di codice**

Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signal({ d_referer : document.referrer }).submit();
</code></pre>

## Acquisisci tipi di motore di ricerca e termini di ricerca parole chiave {#capture-search-engine-types}

Inviate ad Audience Manager informazioni sul tipo di motore di ricerca e sulle ricerche di parole chiave.

>[!IMPORTANT]
>
>Questa sezione descrive le funzionalità legacy, non supportate nelle versioni più recenti di DIL.

**Motori di ricerca supportati**

Per impostazione predefinita, `DIL.getSearchReferrer` riconosce le ricerche effettuate da questi motori di ricerca (comprese le variazioni internazionali):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrizione**

Il codice seguente illustra come ottenere il referente di ricerca per uno qualsiasi dei motori di ricerca supportati. In questo caso, supponiamo che un utente abbia cercato il termine "case" dal [!DNL Google] Canada ( `www.google.ca`). Questo codice ti aiuterà a catturare quei termini di ricerca e a inviarli ad Audience Manager.

**Codice di base**

Il codice di base per ottenere il referente di ricerca (ad `google.com`esempio, da) è simile al seguente:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Esempio di codice del motore di ricerca elencato**

In questo caso, supponiamo che un utente abbia cercato il termine "case" dal [!DNL Google] Canada ( `www.google.ca`). Il codice prefissa il `c_` parametro richiesto al motore di ricerca ( `c_se`) e al termine di ricerca ( `c_st`). `c_` è un prefisso [](../features/traits/trait-variable-prefixes.md) obbligatorio che identifica queste variabili come definite dal cliente in Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { adobe_dil.api.signal({ c_se : se.name, c_st : se.keywords }).submit(); 
}</code></pre>

**Esempio di codice del motore di ricerca non elencato**

In questo caso, supponiamo che un utente abbia cercato il termine "case" da `dogpile.com`. Poiché non [!DNL Dogpile] è supportato per impostazione predefinita, puoi configurare DIL per riconoscere questo motore di ricerca e restituire i termini di ricerca ad Audience Manager. Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, { hostPattern:/dogstack\./, queryParam:"q" }); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { adobe_dil.api.signal({ c_se : se.name, c_st : se.keywords }).submit(); 
}</code></pre>

## Mappa valori chiave su altre chiavi {#map-key-values}

Associare il valore da una coppia chiave-valore a un'altra chiave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrizione**

In una coppia chiave-valore, il `c_` prefisso aggiunto alla chiave identifica il segnale come dati definiti dal cliente. I dati definiti dal cliente vengono utilizzati per il targeting sul sito specifico che ha passato i dati in una chiamata all'evento. Tuttavia, a volte tali informazioni sono disponibili per tutte le proprietà dell'account Audience Manager. A tal fine, mappate il valore in una coppia chiave-valore su una chiave a livello di piattaforma. `c_` Una chiave a livello di piattaforma ha il prefisso `d_` e rende il segnale disponibile per il targeting tra tutte le proprietà dell'account.

Ad esempio, raccogliete i dati del codice ZIP da un particolare sito ma desiderate indirizzarli a tutte le proprietà di Audience Manager. Per rendere disponibile il codice ZIP a livello di piattaforma, potete mappare la chiave del codice ZIP definita dal cliente (ad esempio `c_zip`) a una chiave definita dalla piattaforma come mostrato di seguito.

**Esempio di codice**

Il codice potrebbe essere simile al seguente:

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

>[!MORE_LIKE_this]
>
>* [Requisiti del prefisso per le variabili chiave](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## DIL del traffico in Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurate e servite DIL con un tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Questa procedura presuppone che possiate disporre di un [!DNL Google Tag Manager] account, di una certa conoscenza del prodotto e del `dil.js` file Audience Manager.

Per eseguire il traffico del `dil.js` file in GTM:

1. Create un nuovo contenitore o aprite un contenitore esistente.
1. Aggiungete un nuovo tag al contenitore.
1. Aprite il tag per modificarlo e:

   * Denominate il tag .
   * Selezionate **[!UICONTROL Custom HTML Tag]** dall’elenco a **[!UICONTROL Tag Type]** discesa.
   * Nel campo HTML, inserite il [!UICONTROL DIL] codice (libreria + il codice personalizzato) all'interno dei tag di script `<script>DIL code</script>`.
   * Fai clic su **[!UICONTROL Save]**.

1. Pubblicate il contenitore.
1. Generare il codice del tag del contenitore e inserirlo nel magazzino.

>[!MORE_LIKE_this]
>
>* [Guida di Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

