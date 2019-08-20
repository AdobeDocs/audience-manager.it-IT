---
description: Esempi di codice e descrizioni per casi di utilizzo DIL specifici.
seo-description: Esempi di codice e descrizioni per casi di utilizzo DIL specifici.
seo-title: Casi di utilizzo DIL e esempi di codice
solution: Audience Manager
title: Casi di utilizzo DIL e esempi di codice
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# Casi di utilizzo DIL e esempi di codice{#dil-use-cases-and-code-samples}

Esempi di codice e descrizioni per casi di utilizzo DIL specifici.

<!-- 

c_dil_use_case.xml

 -->

## Inviare elementi dati ad Audience Manager con DIL {#send-data-elements-dil}

Crea una variabile di oggetto che invia informazioni sugli elementi della pagina ad Audience Manager. Questa funzione è utile per la raccolta dati generale o come alternativa alla raccolta di dati con variabili Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrizione**

Il codice seguente illustra come raccogliere i dati delle pagine e inviarli ad Audience Manager. [!UICONTROL DIL] Questi esempi utilizzano una variabile per contenere elementi dati in un elenco semplice o in un array. Ricorda, passa variabili come coppie [chiave-valore](../reference/key-value-pairs-explained.md). Tenere inoltre presente il `c_` prefisso prima della chiave nella coppia chiave-valore. Questo [prefisso richiesto](../features/traits/trait-variable-prefixes.md) identifica le informazioni come dati definiti dall'utente. Nel primo esempio, occorre aggiungere manualmente `c_` alla chiave. Nel secondo esempio [!UICONTROL DIL] , effettua automaticamente questa operazione.

**Mantieni proprietà valore coerente**

Tenere presente che durante il passaggio dei dati le proprietà del valore sono uguali. Ad esempio, se sono presenti due chiavi identiche con valori diversi, il valore dell'ultima coppia chiave-valore ha la precedenza sugli oggetti valore precedenti. Ad esempio, passando `color:blue` e `color:red` impostando il valore restituito su rosso (sovrascrive il blu).

**Esempio 1: Invia dati come coppie chiave-valore**

Questo esempio di base invia dati di colore e prezzi ad Audience Manager sotto forma di coppie chiave-valore. Il codice potrebbe assomigliare a quanto segue:

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
sample_ dil. api. signals ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**Esempio 2: Inviare dati in un oggetto**

Questo esempio avanzato illustra come inviare dati in un oggetto ad Audience Manager. Quando si utilizza questo metodo, [!UICONTROL DIL] consente di trasmettere un oggetto come parametro di funzione al [!DNL signals()] metodo. [!UICONTROL DIL] Il codice potrebbe assomigliare a quanto segue:

<pre class="java"><code>var my_ object = { 
 color: " blue ", 
 prezzo: " 900 "}; 
 
var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
//Load l'oggetto e aggiungete "c_" a tutte le chiavi nelle coppie chiave-valore e inviate dati a audiencemanager. 
sample_ dil. api. signals (my_ object, "c_"). submit ();</code>
</pre>

**Esempio 3: Inviare dati pagina in un array**

In questo caso, la variabile `my_object` utilizza un array per contenere i dati. Questo esempio si basa sulle informazioni trasmesse dal metodo consigliato sopra, ma aggiunge un livello aggiuntivo per contenere un tipo di prodotto e un modello. Il codice potrebbe assomigliare a quanto segue:

<pre class="java"><code>var my_ objects = [{ 
 color: " blue ", 
 prezzo: " 900 "}, 
{ 
 type: " acura ", 
 modello: " tl "}]; 
 
var sample_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
 
for (var i = 0; i &lt; my_ objects. length; i + +) 
//Load l'oggetto e aggiungete "c_" a tutte le chiavi nelle coppie chiave-valore. 
{{ 
 sample_ dil. api. signals (my_ objects [i], "c_"); 
} 
sample_ dil. api. submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [segnali](../dil/dil-instance-methods.md#signals)


## Acquisisci URL di provenienza {#capture-referring-url}

Acquisisci e invia un URL di provenienza ad Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Questo metodo funziona solo quando gli utenti si spostano tra le pagine con protocolli simili (HTTP vs HTTPS). Ad esempio, il browser mantiene un URL di provenienza quando vi spostate da un sito sicuro a un altro sito protetto. I browser non mantengono l'URL di provenienza quando vi spostate tra siti sicuri e non sicuri. Questo comportamento è normale e non può essere aggirato da [!UICONTROL DIL].

**Esempio di codice**

Il codice potrebbe assomigliare a quanto segue:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
adobe_ dil. api. signals ({d_ referer: document. referrer}). submit ();</code>
</pre>

## Acquisisci i tipi di motore di ricerca e Termini di ricerca parole chiave {#capture-search-engine-types}

Invia informazioni sul tipo di motore di ricerca e sulle ricerche di parole chiave ad Audience Manager.

>[!IMPORTANT]
>
>Questa sezione descrive la funzionalità legacy, che non è supportata nelle versioni più recenti di DIL.

**Motori di ricerca supportati**

Per impostazione predefinita `DIL.getSearchReferrer` , riconosce le ricerche da tali motori di ricerca (comprese le varianti internazionali):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrizione**

Il seguente codice illustra come ottenere il referente di ricerca per i motori di ricerca supportati. In questo caso, supponiamo che un utente abbia cercato il termine "homes" dal [!DNL Google] Canada ( `www.google.ca`). Questo codice ti aiuterà a catturare tali termini di ricerca e a inviarli ad Audience Manager.

**Codice di base**

Il codice di base per ottenere il referente di ricerca (ad `google.com`esempio) è simile al seguente:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Esempio di codice motore di ricerca elencati**

In questo caso, supponiamo che un utente ricerca il termine "homes" dal [!DNL Google] Canada ( `www.google.ca`). Notate come il codice prefissi il parametro richiesto `c_` per il motore di ricerca ( `c_se`) e il termine di ricerca ( `c_st`). `c_` è un [prefisso](../features/traits/trait-variable-prefixes.md) necessario che identifica queste variabili come variabili definite dal cliente ad Audience Manager.

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

In questo caso, supponiamo che un utente ricerca il termine "homes" dal `dogpile.com`titolo. Poiché [!DNL Dogpile] non è supportato per impostazione predefinita, puoi configurare DIL per riconoscere questo motore di ricerca e restituire i termini di ricerca ad Audience Manager. Il codice potrebbe assomigliare a quanto segue:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partner name</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
 Queryparam: " q "}); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signals ({ 
 c_ se: se. name, 
 c_ st: se. keywords 
 }). submit (); 
}</code>
</pre>

## Mappatura dei valori chiave su altri tasti {#map-key-values}

Associare il valore di una coppia chiave-valore a un'altra chiave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrizione**

In una coppia chiave-valore, il `c_` prefisso aggiunto alla chiave identifica il segnale come dati definiti dal cliente. I dati definiti dal cliente vengono utilizzati per il targeting sul sito specifico trasmesso nei dati su una chiamata dell'evento. Tuttavia, a volte desiderate che queste informazioni siano disponibili in tutte le proprietà dell'account Audience Manager. A tal fine, mappare il valore in una coppia `c_` chiave-valore in una chiave a livello di piattaforma. Una chiave a livello di piattaforma ha `d_` il prefisso e rende il segnale disponibile per il targeting in tutte le proprietà dell'account.

Ad esempio, puoi raccogliere i dati del codice ZIP da un particolare sito, ma eseguire il targeting per tutte le proprietà di Audience Manager. Per rendere disponibile il codice ZIP a livello di piattaforma, potete mappare la chiave del codice ZIP definita dal cliente (ad es. `c_zip`) a una chiave definita piattaforma come mostrato di seguito.

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


## DIL traffico in Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurate e servite DIL con un tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Questa procedura presuppone che disponiate di un [!DNL Google Tag Manager] account, di alcune conoscenze di tale prodotto e del `dil.js` vostro file Audience Manager.

Per trasferire il `dil.js` file in GTM:

1. Create un nuovo contenitore o aprite un contenitore esistente.
1. Aggiungere un nuovo tag al contenitore.
1. Aprite il tag per modificarlo e:

   * Denominate il tag.
   * Seleziona **[!UICONTROL Custom HTML Tag]** dall'elenco **[!UICONTROL Tag Type]** a discesa.
   * Nel campo HTML, inserire il [!UICONTROL DIL] codice (libreria + il codice personalizzato) all'interno dei tag `<script>DIL code</script>`script.
   * Fai clic su **[!UICONTROL Save]**.

1. Pubblicate il contenitore.
1. Generate il codice tag contenitore e inseritelo nell'inventario.

>[!MORE_ LIKE_ THIS]
>
>* [Centro di aiuto di Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)

