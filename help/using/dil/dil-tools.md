---
description: Descrive i metodi nello spazio dei nomi DIL.tools. Queste funzioni consentono di eseguire attività specifiche.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: Strumenti DIL
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
TQID: https://experienceleague.adobe.com/W3xzJ172rBhQ9Flqs5towA5pE3-nJHpwnJ1jd1mXIyo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 343
ht-degree: 2%

---

# Strumenti DIL

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo di [!DNL Data Integration Library (DIL)] e dell&#39;estensione [!DNL DIL].
>
>I clienti esistenti possono continuare a utilizzare l&#39;implementazione [!DNL DIL]. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

Descrive i metodi nello spazio dei nomi `DIL.tools`. Queste funzioni consentono di eseguire attività specifiche.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Restituisce i termini di ricerca utilizzati per raggiungere la pagina corrente.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Scopo di `getSearchReferrer`

In DIL, `getSearchReferrer` restituisce i risultati della ricerca (nomi e parole chiave) utilizzati per raggiungere il sito. È possibile passare termini di ricerca specifici a questa funzione o consentire la ricerca nei motori di ricerca supportati ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google] e [!DNL Yahoo]) rispetto a `document.referrer` per impostazione predefinita.

### Firma della funzione

Firma funzione: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Parametri funzione

`getSearchReferrer` accetta:

* *`{string}`*: *(Facoltativo)* Stringa contenente l&#39;URL di ricerca (utilizza `document.referrer` se non definito).
* *`{object}`*: *(facoltativo)* Oggetto contenente la configurazione per `hostPattern`, `queryParam` o `queryPattern`.

E restituisce:

* `{object}` Oggetto contenente nomi e parole chiave validi.

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
   <td> Restituisce i termini di ricerca per parole chiave utilizzati dai motori di ricerca AOL, Ask, Bing, Google e Yahoo. </td> 
   <td>
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Passa un URL personalizzato</td> 
   <td>Restituisce il referente di ricerca in base a un URL personalizzato.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Corrispondenza nome host URL con un regex personalizzato</b></td> 
   <td> Passa un regex personalizzato in modo che corrisponda al nome host dell’URL di riferimento. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Abbina modelli di ricerca con un Regex personalizzato</b> </td> 
   <td> Passa un regex personalizzato per eseguire una ricerca personalizzata. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Disassembla un identificatore di risorsa uniforme ( [!DNL URI]) nei componenti: `hash`, `host`, `href`, `pathname`, `protocol`, `search` e `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Firma funzione: `DIL.tools.decomposeURI`

### Parametri funzione

`decomposeURI` accetta:

* *`uri {string}`*: *(Facoltativo)* Stringa contenente l&#39;URI. Valore predefinito: `document.location.href` se non specificato.

E restituisce:

* *`{object}`*: oggetto contenente nomi e parole chiave validi.

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

Cerca contenuto specifico definito nei metatag di una pagina Web e restituisce tali dati in un oggetto.

<!-- 

r_dil_get_metatags.xml

 -->

### Firma della funzione

Firma funzione: `DIL.tools.getMetaTags( 1 or more parameters)`

### Parametri funzione

`getMetaTags` accetta uno o più parametri di nome (tipo stringa) da cercare. Restituisce un oggetto composto da coppie chiave-valore.

### Codice di esempio

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
