---
description: Descrive i metodi nello spazio dei nomi DIL.tools. Queste funzioni di utilità consentono di eseguire attività specifiche.
seo-description: Descrive i metodi nello spazio dei nomi DIL.tools. Queste funzioni di utilità consentono di eseguire attività specifiche.
seo-title: Strumenti DIL
solution: Audience Manager
title: Strumenti DIL
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: Implementazione di DIL
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 4%

---

# Strumenti DIL

Descrive i metodi nello spazio dei nomi `DIL.tools` . Queste funzioni di utilità consentono di eseguire attività specifiche.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Restituisce i termini di ricerca utilizzati per raggiungere la pagina corrente.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Scopo di `getSearchReferrer`

In DIL, `getSearchReferrer` restituisce i risultati di ricerca (nomi e parole chiave) utilizzati per raggiungere il sito. Puoi passare termini di ricerca specifici a questa funzione o lasciare che esegua la ricerca nei motori di ricerca supportati ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google] e [!DNL Yahoo]) rispetto a `document.referrer` per impostazione predefinita.

### Firma della funzione

Firma della funzione: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Parametri della funzione

`getSearchReferrer` accetta:

* *`{string}`*:  *(Facoltativo)* Una stringa contenente l&#39;URL di ricerca (utilizza  `document.referrer` se non definito).
* *`{object}`*:  *(Facoltativo)* Un oggetto contenente la configurazione per  `hostPattern`,  `queryParam`, o  `queryPattern`.

E restituisce:

* `{object}` Oggetto che contiene nomi e parole chiave validi.

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
   <td> Restituisce i termini di ricerca delle parole chiave utilizzati dai motori di ricerca AOL, Ask, Bing, Google e Yahoo. </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Trasmettere un URL personalizzato</td> 
   <td>Restituisce il referente di ricerca in base a un URL personalizzato.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Nome host con URL simile a un Regex personalizzato</b></td> 
   <td> Passa un regex personalizzato per corrispondere al nome host dell'URL di riferimento. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Pattern di ricerca con un regex personalizzato</b> </td> 
   <td> Passa un regex personalizzato per eseguire una ricerca personalizzata. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Smonta un identificatore di risorsa uniforme ( [!DNL URI]) nei relativi componenti costitutivi: `hash`, `host`, `href`, `pathname`, `protocol`, `search` e `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Firma della funzione: `DIL.tools.decomposeURI`

### Parametri della funzione

`decomposeURI` accetta:

* *`uri {string}`*:  *(Facoltativo)* Una stringa contenente l’URI. Se non specificato, viene impostato il valore predefinito `document.location.href`.

E restituisce:

* *`{object}`*: Oggetto che contiene nomi e parole chiave validi.

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

## getMetaTags

Cerca contenuto specifico definito nei meta tag di una pagina Web e restituisce tali dati in un oggetto.

<!-- 

r_dil_get_metatags.xml

 -->

### Firma della funzione

Firma della funzione: `DIL.tools.getMetaTags( 1 or more parameters)`

### Parametri della funzione

`getMetaTags` accetta uno o più parametri di nome (tipo stringa) da cercare. Restituisce un oggetto composto da coppie chiave-valore.

### Codice di esempio

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
