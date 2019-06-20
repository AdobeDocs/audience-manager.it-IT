---
description: Descrive i metodi nello spazio nomi DIL. tools. Queste funzioni di utilità consentono di eseguire attività specifiche.
seo-description: Descrive i metodi nello spazio nomi DIL. tools. Queste funzioni di utilità consentono di eseguire attività specifiche.
seo-title: Strumenti DIL
solution: Audience Manager
title: Strumenti DIL
uuid: 2 bc 62 ce 2-16 bd -4 e 80-b 493-c 816 ba 643 b 59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# Strumenti DIL

Descrive i metodi nello `DIL.tools` spazio nomi. Queste funzioni di utilità consentono di eseguire attività specifiche.

<!-- 

c_dil_functions.xml

 -->

## Getsearchreferrer

Restituisce termini di ricerca utilizzati per raggiungere la pagina corrente.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Scopo di `getSearchReferrer`

In DIL `getSearchReferrer` restituisce i risultati della ricerca (nomi e parole chiave) utilizzati per raggiungere il sito. È possibile trasmettere termini di ricerca specifici a questa funzione o consentire la ricerca nei motori di ricerca supportati ( [!DNL AOL][!DNL Ask][!DNL Bing], [!DNL Google]e [!DNL Yahoo]) per `document.referrer` impostazione predefinita.

### Firma della funzione

Firma della funzione: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Parametri della funzione

`getSearchReferrer` accetta:

* *`{string}`*: *(Facoltativo)* Stringa contenente l&#39;URL di ricerca (se `document.referrer` non è definita).
* *`{object}`*: *(Facoltativo)* Un oggetto contenente la configurazione per `hostPattern``queryParam`, o `queryPattern`.

e restituisce:

* `{object}` Un oggetto che contiene nomi e parole chiave validi.

### Esempi

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Tipo di ricerca </th> 
   <th> Descrizione </th> 
   <th> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Ricerca predefinita</td> 
   <td> Restituisce termini di ricerca parole chiave utilizzati dai motori di ricerca AOL, Ask, Bing, Google e Yahoo. </td> 
   <td>
      <code>var &amp; amp; nbsp; results &amp; amp; nbsp; = &amp; amp; nbsp; DIL. tools. getsearchreferrer ();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Passa a un URL personalizzato</td> 
   <td>Restituisce il referente di ricerca basato su un URL personalizzato.</td> 
   <td> 
  <code>
        var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Corrispondenza nome host URL con un regex personalizzato</b></td> 
   <td> Passa un regex personalizzato per far corrispondere il nome host dell'URL di provenienza. </td> 
   <td> 
  <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/
    search.aspx?q=adobe+rules",{ 
       hostPattern:/ehow\./, 
         queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Corrispondenza con pattern di ricerca con un regex personalizzato</b> </td> 
   <td> Passa un regex personalizzato per eseguire una ricerca personalizzata. </td> 
   <td> 
    <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
    {
       hostPattern:/ehow\./, 
           search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## Decomposeuri

Disassembla un Uniform Resource Identifier ( [!DNL URI]) nei componenti costituenti: `hash``host``href``pathname``protocol`, `search`and `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Firma della funzione: `DIL.tools.decomposeURI`

### Parametri della funzione

`decomposeURI` accetta:

* *`uri {string}`*: *(Facoltativo)* Stringa contenente l&#39;URI. Se non `document.location.href` viene specificato, predefinito.

e restituisce:

* *`{object}`*: Un oggetto che contiene nomi e parole chiave validi.

### Codice di esempio


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## Getmetatag

Cerca contenuti specifici definiti nei tag meta in una pagina Web e li restituisce in un oggetto.

<!-- 

r_dil_get_metatags.xml

 -->

### Firma della funzione

Firma della funzione: `DIL.tools.getMetaTags( 1 or more parameters)`

### Parametri della funzione

`getMetaTags` accetta uno o più parametri di nome (tipo stringa) da cercare. Restituisce un oggetto composto da coppie chiave-valore.

### Codice di esempio

<pre class="&ldquo;javascript&rdquo;"><code>var datalib = DIL. create ({ 
 partner: '<i>Partnernamè</i>, 
 Containernsid: <i>Containernsid</i> }); 
Datalib. api. segnali (DIL. tools. getmetatags ('<i>application</i>','<i>keywords</i>','<i>description</i>'),'c_'). submit ();</code>
</pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 
dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
