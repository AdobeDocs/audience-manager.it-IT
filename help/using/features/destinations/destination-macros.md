---
description: Descrive le macro che è possibile aggiungere a un URL di destinazione.
seo-description: Descrive le macro che è possibile aggiungere a un URL di destinazione.
seo-title: Macro di destinazione definite
solution: Audience Manager
title: Macro di destinazione definite
uuid: 982 cab 05-8 a 3 f -4 f 96-b 4 d 0-291709712 ad 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination Macros Defined {#destination-macros-defined}

Describes the macros you can add to a destination [!DNL URL].

<!-- destination-macros.xml -->

When creating a [!DNL URL] destination, you can insert the following macros into the [!DNL URL] string. Check with your data/destination partner about proper macro placement within the destination [!DNL URL].

>[!NOTE]
>
>Le macro sono facoltative, se non diversamente indicato. Il *corsivo* indica un segnaposto variabile.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Spiegazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> % alias %</code> </p> </td> 
   <td colname="col2"> <p>Obbligatorio. </p> <p>Definisce la posizione del valore del segmento mappato in un URL di destinazione. Usually this is the <i>Segment ID</i>, but could also be the integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> % did %</code> </p> </td> 
   <td colname="col2"> <p>Inserts the user's <span class="keyword"> Audience Manager</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>% dpid_<i>source source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>The <i>data source id</i> corresponds to the identifier for a data source passed in to the macro. </p> <p>Vediamo come funziona in un esempio semplice. In this case, we have an <span class="keyword"> Audience Manager</span> partner with the following IDs and conditions: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Data source ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">An internal customer ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: The partner wants to pass in these values as the declared ID <code> 1:CustomerABC</code>. </li> 
    </ul> <p>To do this with the <code>%dpid_<i>data source id</i>%</code>, the <span class="keyword"> Audience Manager</span> partner would format the macro like this: </p> 
    <ul class="simplelist"> 
     <li> <code> % dpid_ 1%</code> </li> 
    </ul> <p>The macro will replace <code> 1</code> with <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       Basato su AAM -22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % http_ proto %</code> </p> </td> 
   <td colname="col2"> <p>Rileva il protocollo utilizzato nella pagina Web principale e lo inserisce nell'URL di destinazione. Ad esempio: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">if the webpage is <b>https</b>://aam_client.com, this macro will be replaced with <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">if the webpage is <b>http</b>://aam_client.com, this macro will be replaced with <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % mcid %</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="keyword"> Experience Cloud</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % region %</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="wintitle"> Data Collection Server (DCS)</span> region into the destination URL. In order to minimize latency, when the visitor makes an HTTP call to <span class="keyword"> Audience Manager</span>, they are being redirected to the closest <span class="wintitle"> DCS</span> datacenter. Questo risultato viene ottenuto tramite DNS, che è in grado di rilevare il percorso del visitatore e indirizzarlo al data datacenter appropriato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> % rnd %</code> </p> </td> 
   <td colname="col2"> <p>Esegue una funzione di svuotamento della cache inserendo un numero casuale nell'URL di destinazione. Ciò impedisce ai browser di distribuire il contenuto memorizzato nella cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce una marca temporale UNIX nell'URL di destinazione per impedire ai browser di distribuire il contenuto memorizzato nella cache. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache Busting with Destination Macros {#destination-cache-busting}

The `%rnd%` and `%timestamp%` macros insert unique values into a [!DNL URL] string to prevent browser caching.

## Cache Busting with `%rnd%` and `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

I browser memorizzano nella cache i contenuti di frequente richiesti. Quando una pagina viene caricata, il contenuto salvato viene utilizzato dalla cache anziché da un server remoto. Questo processo consente di mantenere i tempi di download efficienti perché i dati vengono utilizzati localmente anziché da un'altra posizione. Tuttavia, poiché il caching non richiede una chiamata al server, può inclinare i rapporti riducendo artificialmente il numero di richieste univoche.

La cache non consente ai browser di salvare e riutilizzare il contenuto. Questa tecnica utilizza codice che inserisce un numero casuale o un indicatore di ora in una stringa URL, che lo rende univoco per il browser. As a result, each `HTTP` call is counted as a separate request to the server. Forzando una nuova chiamata server per ogni richiesta, è possibile mantenere l'accuratezza dei rapporti e ridurre le discrepanze. [!DNL Audience Manager] fornisce due macro per svuotare la cache:

* `%rnd%`: Inserisce un numero casuale in un URL.
* `%timestamp%`: Inserisce la data/l'ora Unix in un URL.

## Comparing `%rnd%` and `%timestamp%` {#compare-rnd-timestamp}

Both macros prevent caching, but `%rnd%` may be more efficient. For example, with `%timestamp%`, if several users view a page simultaneously they'll get the same date/time value. As a result, the [!DNL URL] is not unique and multiple calls are counted only once. `%rnd%` Tuttavia, genera un valore numerico univoco per ogni chiamata (anche quando gli utenti visualizzano contemporaneamente la stessa pagina). This means the [!DNL URL] string contains different values and is counted as unique.

>[!MORE_ LIKE_ THIS]
>
>* [Macro di destinazione definite](../../features/destinations/destination-macros.md#destination-macros-defined)