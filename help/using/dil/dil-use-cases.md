---
description: Esempi di codice e descrizioni per casi d’uso specifici di DIL.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: Casi d’uso di DIL ed esempi di codice
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# Casi d’uso di DIL ed esempi di codice{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo di [!DNL Data Integration Library (DIL)] e dell&#39;estensione [!DNL DIL].
>
>I clienti esistenti possono continuare a utilizzare l&#39;implementazione [!DNL DIL]. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

Esempi di codice e descrizioni per casi d’uso specifici di DIL.

<!-- 

c_dil_use_case.xml

 -->

## Inviare elementi dati ad Audience Manager con DIL {#send-data-elements-dil}

Crea una variabile oggetto che invia informazioni sugli elementi della pagina ad Audience Manager. Questa funzione è utile per la raccolta dati generali o in alternativa alla raccolta di dati con variabili di Analytics.

<!-- 

c_dil_send_page_objects.xml

 -->

**Descrizione**

Il codice seguente illustra come raccogliere i dati della pagina e inviarli ad Audience Manager con [!UICONTROL DIL]. In questi esempi viene utilizzata una variabile per contenere gli elementi dati in un elenco semplice o in una matrice. Ricorda, passa le variabili come [coppie chiave-valore](../reference/key-value-pairs-explained.md). Inoltre, annota il prefisso `c_` prima della chiave nella coppia chiave-valore. Questo [prefisso obbligatorio](../features/traits/trait-variable-prefixes.md) identifica le informazioni come dati definiti dall&#39;utente. Nel primo esempio, devi aggiungere manualmente `c_` alla chiave. Nel secondo esempio, [!UICONTROL DIL] esegue automaticamente questa operazione.

**Mantieni le proprietà dei valori coerenti**

Ricorda di mantenere le stesse proprietà del valore quando si trasmettono i dati. Ad esempio, se disponi di due chiavi identiche con valori diversi, il valore dell’ultima coppia chiave-valore ha la precedenza rispetto agli oggetti valore precedenti. Ad esempio, passando `color:blue` e `color:red`, il valore restituito viene impostato su rosso (sovrascrive il blu).

**Esempio 1: inviare dati come coppie chiave-valore**

Questo esempio di base invia i dati su colore e prezzo ad Audience Manager sotto forma di coppie chiave-valore. Il codice sarà simile al seguente:

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Esempio 2: inviare dati in un oggetto**

Questo esempio avanzato illustra come inviare dati in un oggetto ad Audience Manager. Quando si utilizza questo metodo, [!UICONTROL DIL] consente di passare un oggetto come parametro di funzione nel metodo [!DNL signals()]. [!UICONTROL DIL] Il codice potrebbe essere simile al seguente:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Esempio 3: inviare dati di pagina in un array**

In questo caso, la variabile `my_object` utilizza un array per contenere i dati. Questo esempio si basa sulle informazioni trasmesse dal metodo consigliato in precedenza, ma aggiunge un livello aggiuntivo per ospitare un tipo e un modello di prodotto. Il codice sarà simile al seguente:

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

Acquisisci e invia un URL di riferimento ad Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Questo metodo funziona solo quando gli utenti si spostano tra pagine con protocolli simili (HTTP vs HTTPS). Ad esempio, il browser mantiene un URL di riferimento quando ci si sposta da un sito protetto a un altro. I browser non mantengono l’URL di riferimento quando si passa da un sito protetto a uno non protetto. Questo comportamento è una normale funzionalità del browser e non può essere aggirato da [!UICONTROL DIL].

**Esempio di codice**

Il codice sarà simile al seguente:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Acquisire i tipi di motore di ricerca e i termini di ricerca per parola chiave {#capture-search-engine-types}

Invia ad Audience Manager informazioni sul tipo di motore di ricerca e sulle ricerche per parole chiave.

>[!IMPORTANT]
>
>Questa sezione descrive le funzionalità legacy, non supportate nelle versioni più recenti di DIL.

**Motori di ricerca supportati**

Per impostazione predefinita, `DIL.getSearchReferrer` riconosce le ricerche da questi motori di ricerca (incluse le varianti internazionali):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Descrizione**

Il codice seguente illustra come ottenere il referente di ricerca per uno qualsiasi dei motori di ricerca supportati. In questo caso, supponiamo che un utente abbia eseguito una ricerca nel termine &quot;home&quot; da [!DNL Google] Canada ( `www.google.ca`). Questo codice ti aiuterà a catturare questi termini di ricerca e a inviarli ad Audience Manager.

**Codice di base**

Il codice di base per ottenere il referente di ricerca (ad esempio da `google.com`) è simile al seguente:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Esempio di codice del motore di ricerca elencato**

In questo caso, supponiamo che un utente abbia cercato il termine &quot;home&quot; da [!DNL Google] Canada ( `www.google.ca`). Si noti che il codice prefissa il parametro `c_` richiesto al motore di ricerca ( `c_se`) e al termine di ricerca ( `c_st`). `c_` è un [prefisso obbligatorio](../features/traits/trait-variable-prefixes.md) che identifica questi elementi come variabili definite dal cliente in Audience Manager.

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

In questo caso, supponiamo che un utente abbia cercato il termine &quot;home&quot; da `dogpile.com`. Poiché [!DNL Dogpile] non è supportato per impostazione predefinita, è possibile configurare DIL per riconoscere questo motore di ricerca e restituire i termini di ricerca ad Audience Manager. Il codice sarà simile al seguente:

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

## Mappare i valori delle chiavi ad altre chiavi {#map-key-values}

Associa il valore da una coppia chiave-valore a un&#39;altra chiave.

<!-- 

c_dil_map_keys.xml

 -->

**Descrizione**

In una coppia chiave-valore, il prefisso `c_` aggiunto alla chiave identifica il segnale come dati definiti dal cliente. I dati definiti dal cliente vengono utilizzati per il targeting sul sito specifico che ha trasmesso i dati in una chiamata evento. Tuttavia, a volte potresti desiderare che queste informazioni siano disponibili in tutte le proprietà del tuo account Audience Manager. A questo scopo, mappare il valore di una coppia chiave-valore `c_` a una chiave a livello di piattaforma. Una chiave a livello di piattaforma ha il prefisso `d_` e rende il segnale disponibile per il targeting in tutte le proprietà del tuo account.

Ad esempio, puoi raccogliere i dati del codice postale da un particolare sito, ma desideri eseguirne il targeting per tutte le proprietà di Audience Manager. Per rendere disponibile il codice postale a livello di piattaforma, puoi mappare il codice postale definito dal cliente (ad esempio `c_zip`) su una chiave definita dalla piattaforma come mostrato di seguito.

**Esempio di codice**

Il codice sarà simile al seguente:

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

## DIL traffico in Google Tag Manager (GTM) {#traffic-dil-gtm}

Configura e distribuisci DIL con un tag GTM.

<!-- 

t_dil_google_tagmanager.xml

 -->

Questa procedura presuppone che tu disponga di un account [!DNL Google Tag Manager], di alcune conoscenze operative di quel prodotto e del tuo file Audience Manager `dil.js`.

Per inviare il traffico al file `dil.js` in GTM:

1. Crea un nuovo contenitore o apri un contenitore esistente.
1. Aggiungi un nuovo tag al contenitore.
1. Apri il tag per modificarlo e:

   * Denomina il tag.
   * Selezionare **[!UICONTROL Custom HTML Tag]** dall&#39;elenco a discesa **[!UICONTROL Tag Type]**.
   * Nel campo HTML, inserire il codice [!UICONTROL DIL] (libreria + codice personalizzato) all&#39;interno dei tag script `<script>DIL code</script>`.
   * Fare clic su **[!UICONTROL Save]**.

1. Pubblica il contenitore.
1. Genera il codice tag contenitore e inseriscilo nel tuo inventario.

>[!MORELIKETHIS]
>
>* [Centro assistenza di Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Segnali](../dil/dil-instance-methods.md#signals)
>* [Requisiti di prefisso delle variabili chiave](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)
