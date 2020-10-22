---
description: Descrive le macro che è possibile aggiungere a un URL di destinazione.
seo-description: Descrive le macro che è possibile aggiungere a un URL di destinazione.
seo-title: Definizione delle macro delle destinazioni
solution: Audience Manager
title: Definizione delle macro delle destinazioni
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 3%

---


# Definizione delle macro delle destinazioni {#destination-macros-defined}

Descrive le macro che è possibile aggiungere a una destinazione [!DNL URL].

<!-- destination-macros.xml -->

Durante la creazione di una [!DNL URL] destinazione, è possibile inserire le seguenti macro nella [!DNL URL] stringa. Consultare il partner di dati/destinazione per informazioni sulla corretta posizione delle macro all&#39;interno della destinazione [!DNL URL].

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
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>Obbligatorio. </p> <p>Definisce la posizione del valore del segmento mappato in un URL di destinazione. Solitamente si tratta dell’ID <i></i>segmento, ma potrebbe anche essere il codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'ID Audience Manager <span class="keyword"></span>  utente nell'URL di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>L'ID <i>origine</i> dati corrisponde all'identificatore di un'origine dati passata alla macro. </p> <p>Vediamo come funziona in un semplice esempio. In questo caso, abbiamo un partner <span class="keyword"> Audience Manager</span> con i seguenti ID e condizioni: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID origine dati: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Un ID cliente interno: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID dichiarato: Il partner desidera trasmettere questi valori come ID dichiarato <code> 1:CustomerABC</code>. </li> 
    </ul> <p>A tal fine, il partner del Audience Manager <code>%dpid_<i>data source id</i>%</code>di <span class="keyword"></span> formatta la macro come segue: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>La macro verrà sostituita <code> 1</code> con <code> CustomerABC</code>. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Indica se le regole GDPR si applicano o meno al visitatore. Utilizzare questa macro per includere il consenso nei segmenti inviati a destinazioni URL integrate con IAB. Per informazioni dettagliate, consultate <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in di Audience Manager per IAB TCF</a> .</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>La stringa di consenso (incluso l’ID fornitore IAB) raccolta quando i visitatori forniscono o negano il consenso sul sito. Utilizzare questa macro per includere la stringa di consenso nei segmenti inviati a destinazioni URL integrate con IAB. Sostituire <code>XXXX</code> con l’ID partner di destinazione. Per informazioni dettagliate, consultate <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in di Audience Manager per IAB TCF</a> . </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Rileva il protocollo utilizzato nella pagina Web padre e lo inserisce nell’URL di destinazione. Ad esempio:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">se la pagina Web è <b>https</b>://aam_client.com, la macro verrà sostituita con <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">se la pagina Web è <b>http</b>://aam_client.com, la macro verrà sostituita con <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'ID Experience Cloud <span class="keyword"></span>  nell'URL di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'area <span class="wintitle"> Data Collection Server (DCS)</span> nell'URL di destinazione. Per ridurre al minimo la latenza, quando il visitatore effettua una chiamata HTTP a <span class="keyword"> Audience Manager</span>, viene reindirizzato al datacenter <span class="wintitle"> DCS</span> più vicino. Questo viene ottenuto tramite DNS, in grado di rilevare la posizione del visitatore e indirizzarlo al centro dati appropriato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Esegue una funzione di arresto cache inserendo un numero casuale nell'URL di destinazione. Ciò impedisce ai browser di gestire il contenuto memorizzato nella cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce una marca temporale UNIX nell'URL di destinazione per evitare che i browser distribuiscano contenuto memorizzato nella cache. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Busting cache con macro di destinazione {#destination-cache-busting}

Le `%rnd%` macro e `%timestamp%` le macro inseriscono valori univoci in una [!DNL URL] stringa per impedire il caching del browser.

## Busting cache con `%rnd%` e `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

La cache dei browser (salva) del contenuto richiesto di frequente nella memoria. Quando una pagina viene caricata, il contenuto salvato viene distribuito dalla cache anziché da un server remoto. Questo processo consente di mantenere tempi di download efficienti perché i dati vengono inviati localmente anziché da un&#39;altra posizione. Tuttavia, poiché il caching non richiede una chiamata al server, può distorcere i rapporti riducendo artificialmente il numero di richieste univoche.

La funzione cache impedisce ai browser di salvare e riutilizzare il contenuto. Questa tecnica utilizza codice che inserisce un numero casuale o una marca temporale in una stringa URL, rendendola univoca per il browser. Di conseguenza, ogni `HTTP` chiamata viene conteggiata come una richiesta separata al server. Forzare una nuova chiamata al server per ogni richiesta consente di mantenere la precisione dei rapporti e ridurre le discrepanze. [!DNL Audience Manager] fornisce due macro per l&#39;avvio della cache:

* `%rnd%`: Inserisce un numero casuale in un URL.
* `%timestamp%`: Inserisce la data/ora Unix in un URL.

## Confronto `%rnd%` e `%timestamp%` {#compare-rnd-timestamp}

Entrambe le macro impediscono il caching, ma `%rnd%` possono essere più efficienti. Ad esempio, con `%timestamp%`, se più utenti visualizzano una pagina contemporaneamente, avranno lo stesso valore di data/ora. Di conseguenza, le chiamate non [!DNL URL] sono univoche e più chiamate vengono conteggiate solo una volta. Tuttavia, `%rnd%` genera un valore numerico univoco per ogni chiamata (anche quando gli utenti vedono la stessa pagina contemporaneamente). Ciò significa che la [!DNL URL] stringa contiene valori diversi e viene conteggiata come univoca.

>[!MORELIKETHIS]
>
>* [Definizione delle macro delle destinazioni](../../features/destinations/destination-macros.md#destination-macros-defined)