---
description: Esempi di codice e descrizioni per casi di utilizzo di DIL specifici.
seo-description: Esempi di codice e descrizioni per casi di utilizzo di DIL specifici.
seo-title: Casi d’uso DIL ed esempi di codice
solution: Audience Manager
title: Casi d’uso DIL ed esempi di codice
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---


# Casi d’uso DIL ed esempi di codice{#dil-use-cases-and-code-samples}

Esempi di codice e descrizioni per casi di utilizzo di DIL specifici.

<!-- 

c_dil_use_case.xml

 -->

## Invia elementi dati a  Audience Manager con DIL {#send-data-elements-dil}

Creare una variabile oggetto che invia informazioni sugli elementi della pagina  Audience Manager. Questo è utile per la raccolta dati generale o come alternativa alla raccolta di dati con variabili Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrizione**

Il codice seguente illustra come raccogliere i dati della pagina e inviarli al Audience Manager  con [!UICONTROL DIL]. Questi esempi utilizzano una variabile per contenere gli elementi di dati in un elenco semplice o in un array. Ricordate, passate le variabili come [coppie chiave-valore](../reference/key-value-pairs-explained.md). Inoltre, prendete nota del prefisso `c_` prima della chiave nella coppia chiave-valore. Questo [prefisso richiesto](../features/traits/trait-variable-prefixes.md) identifica le informazioni come dati definiti dall&#39;utente. Nel primo esempio, è necessario aggiungere manualmente `c_` alla chiave. Nel secondo esempio, [!UICONTROL DIL] esegue automaticamente questa operazione.

**Mantieni costanti le proprietà del valore**

Durante il trasferimento dei dati, ricordare di mantenere le proprietà del valore invariate. Ad esempio, in presenza di due chiavi identiche con valori diversi, il valore dell&#39;ultima coppia chiave-valore ha la precedenza sugli oggetti valore precedenti. Ad esempio, passando `color:blue` e `color:red` il valore restituito viene impostato su rosso (sovrascrive il blu).

**Esempio 1: Invia dati come coppie chiave-valore**

In questo esempio di base i dati relativi a colori e prezzi vengono inviati  Audience Manager sotto forma di coppie chiave-valore. Il codice potrebbe essere simile al seguente:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Esempio 2: Invio di dati in un oggetto**

Questo esempio avanzato illustra come inviare dati in un oggetto al Audience Manager . Quando si utilizza questo metodo, [!UICONTROL DIL] consente di passare un oggetto come parametro di funzione nel metodo [!DNL signals()]. [!UICONTROL DIL] Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Esempio 3: Invia dati di pagina in un array**

In questo caso, la variabile `my_object` utilizza un array per contenere i dati. Questo esempio si basa sulle informazioni trasmesse con il metodo consigliato sopra, ma aggiunge un livello aggiuntivo per contenere un tipo di prodotto e un modello. Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## Acquisisci URL di riferimento {#capture-referring-url}

Acquisite e inviate un URL di provenienza a  Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Questo metodo funziona solo quando gli utenti si spostano tra pagine con protocolli simili (HTTP e HTTPS). Ad esempio, il browser mantiene un URL di provenienza quando si passa da un sito protetto a un altro sito protetto. I browser non conservano l&#39;URL di provenienza quando si passa da un sito sicuro a un altro. Questo comportamento è normale funzionalità del browser e non può essere aggirato da [!UICONTROL DIL].

**Esempio di codice**

Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Acquisisci tipi di motore di ricerca e termini di ricerca parole chiave {#capture-search-engine-types}

Inviate informazioni sul tipo di motore di ricerca e sulle ricerche di parole chiave al Audience Manager .

>[!IMPORTANT]
>
>Questa sezione descrive le funzionalità legacy, che non sono supportate nelle versioni più recenti di DIL.

**Motori di ricerca supportati**

Per impostazione predefinita, `DIL.getSearchReferrer` riconosce le ricerche effettuate da questi motori di ricerca (comprese le varianti internazionali):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrizione**

Il codice seguente illustra come ottenere il referente di ricerca per uno qualsiasi dei motori di ricerca supportati. In questo caso, supponiamo che un utente abbia cercato il termine &quot;home&quot; dal Canada [!DNL Google] ( `www.google.ca`). Questo codice ti aiuterà a catturare quei termini di ricerca e a inviarli  Audience Manager.

**Codice di base**

Il codice di base per ottenere il referente di ricerca (ad esempio da `google.com`) è simile al seguente:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Esempio di codice del motore di ricerca elencato**

In questo caso, supponiamo che un utente abbia cercato il termine &quot;home&quot; da [!DNL Google] Canada ( `www.google.ca`). Il codice prefissa il parametro `c_` richiesto al motore di ricerca ( `c_se`) e al termine di ricerca ( `c_st`). `c_` è un  [predefinito ](../features/traits/trait-variable-prefixes.md) richiesto che identifica queste variabili come definite dal cliente per  Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**Esempio di codice del motore di ricerca non elencato**

In questo caso, supponiamo che un utente abbia cercato il termine &quot;home&quot; da `dogpile.com`. Poiché [!DNL Dogpile] non è supportato per impostazione predefinita, puoi configurare il DIL per riconoscere questo motore di ricerca e restituire i termini di ricerca al Audience Manager . Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Mappa valori chiave su altre chiavi {#map-key-values}

Associare il valore da una coppia chiave-valore a un&#39;altra chiave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrizione**

In una coppia chiave-valore, il prefisso `c_` aggiunto alla chiave identifica il segnale come dati definiti dal cliente. I dati definiti dal cliente vengono utilizzati per il targeting sul sito specifico che ha passato i dati in una chiamata all&#39;evento. Tuttavia, a volte tali informazioni sono disponibili per tutte le proprietà dell&#39;account  Audience Manager. A tal fine, mappate il valore in una coppia chiave-valore `c_` su una chiave a livello di piattaforma. Una chiave a livello di piattaforma ha il prefisso `d_` e rende il segnale disponibile per il targeting tra tutte le proprietà dell&#39;account.

Ad esempio, potete raccogliere i dati del codice ZIP da un particolare sito, ma desiderate indirizzarli a tutte le proprietà del vostro Audience Manager . Per rendere disponibile il codice ZIP a livello di piattaforma, potete mappare la chiave del codice ZIP definita dal cliente (ad es. `c_zip`) a una chiave definita dalla piattaforma come mostrato di seguito.

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

## DIL Traffico in Google Tag Manager (GTM) {#traffic-dil-gtm}

Configurate e servite il DIL con un tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Questa procedura presuppone che si disponga di un account [!DNL Google Tag Manager], che si disponga di una buona conoscenza del prodotto e del file di Audience Manager  `dil.js`.

Per eseguire il traffico del file `dil.js` in GTM:

1. Create un nuovo contenitore o aprite un contenitore esistente.
1. Aggiungete un nuovo tag al contenitore.
1. Aprite il tag per modificarlo e:

   * Denominate il tag .
   * Selezionare **[!UICONTROL Custom HTML Tag]** dall&#39;elenco a discesa **[!UICONTROL Tag Type]**.
   * Nel campo HTML, inserite il codice [!UICONTROL DIL] (libreria + codice personalizzato) all&#39;interno dei tag di script `<script>DIL code</script>`.
   * Clic **[!UICONTROL Save]**.

1. Pubblicate il contenitore.
1. Generate il codice del tag del contenitore e inseritelo nell&#39;inventario.

>[!MORELIKETHIS]
>
>* [Guida di Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Segnali](../dil/dil-instance-methods.md#signals)
>* [Requisiti di prefisso delle variabili chiave](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

