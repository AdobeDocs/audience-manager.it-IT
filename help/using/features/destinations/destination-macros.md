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


# Macro di destinazione definite {#destination-macros-defined}

Descrive le macro che è possibile aggiungere a una destinazione [!DNL URL].

<!-- destination-macros.xml -->

Quando si crea una [!DNL URL] destinazione, è possibile inserire le seguenti macro nella [!DNL URL] stringa. Verificate con i partner di destinazione e di destinazione la posizione corretta della macro all&#39;interno della destinazione [!DNL URL].

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
   <td colname="col2"> <p>Obbligatorio. </p> <p>Definisce la posizione del valore del segmento mappato in un URL di destinazione. In genere si tratta dell'ID <i></i>segmento, ma può anche essere il codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> % did %</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'ID <span class="keyword"> Audience Manager</span> dell'utente nell'URL di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>% dpid_<i>source source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>L'ID di origine <i>dati</i> corrisponde all'identificatore di un'origine dati passata alla macro. </p> <p>Vediamo come funziona in un esempio semplice. In questo caso, abbiamo un <span class="keyword"> partner Audience Manager</span> con i seguenti ID e condizioni: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID origine dati: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Un ID cliente interno: <code> Customerabc</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID dichiarato: Il partner desidera trasmettere questi valori come ID dichiarato <code> 1: Customerabc</code>. </li> 
    </ul> <p>A tal fine, con <code>l'ID di origine % dpid_<i>dati</i>%</code>, il partner <span class="keyword"> Audience Manager</span> formatterebbe la macro come segue: </p> 
    <ul class="simplelist"> 
     <li> <code> % dpid_ 1%</code> </li> 
    </ul> <p>La macro sostituirà <code> 1</code> con <code> customerabc</code>. </p> <p> 
     <draft-comment>
       Basato su AAM -22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % http_ proto %</code> </p> </td> 
   <td colname="col2"> <p>Rileva il protocollo utilizzato nella pagina Web principale e lo inserisce nell'URL di destinazione. Ad esempio: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">se la pagina Web è <b>https://aam_client.com</b>, questa macro verrà sostituita da <b>https://url-destination.com</b> </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">se la pagina Web è <b>http://aam_client.com</b>, questa macro verrà sostituita da <b>http://url-destination.com</b> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % mcid %</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'ID <span class="keyword"> di Experience Cloud</span> nell'URL di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % region %</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'area <span class="wintitle"> Data Collection Server (DCS)</span> nell'URL di destinazione. Per ridurre al minimo la latenza, quando il visitatore effettua una chiamata HTTP ad <span class="keyword"> Audience Manager</span>, viene reindirizzato al <span class="wintitle"> DCS</span> datacenter più vicino. Questo risultato viene ottenuto tramite DNS, che è in grado di rilevare il percorso del visitatore e indirizzarlo al data datacenter appropriato. </p> </td> 
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

## Cache danneggiata con macro di destinazione {#destination-cache-busting}

Le `%rnd%``%timestamp%` macro inseriscono valori univoci in [!DNL URL] una stringa per impedire la memorizzazione nella cache del browser.

## La cache con `%rnd%` e `%timestamp%`{#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

I browser memorizzano nella cache i contenuti di frequente richiesti. Quando una pagina viene caricata, il contenuto salvato viene utilizzato dalla cache anziché da un server remoto. Questo processo consente di mantenere i tempi di download efficienti perché i dati vengono utilizzati localmente anziché da un&#39;altra posizione. Tuttavia, poiché il caching non richiede una chiamata al server, può inclinare i rapporti riducendo artificialmente il numero di richieste univoche.

La cache non consente ai browser di salvare e riutilizzare il contenuto. Questa tecnica utilizza codice che inserisce un numero casuale o un indicatore di ora in una stringa URL, che lo rende univoco per il browser. Di conseguenza, ogni `HTTP` chiamata viene conteggiata come richiesta separata al server. Forzando una nuova chiamata server per ogni richiesta, è possibile mantenere l&#39;accuratezza dei rapporti e ridurre le discrepanze. [!DNL Audience Manager] fornisce due macro per svuotare la cache:

* `%rnd%`: Inserisce un numero casuale in un URL.
* `%timestamp%`: Inserisce la data/l&#39;ora Unix in un URL.

## Confronto `%rnd%` e `%timestamp%`{#compare-rnd-timestamp}

Entrambe le macro impediscono la memorizzazione nella cache, ma `%rnd%` possono essere più efficienti. Ad esempio, con `%timestamp%`, se più utenti visualizzano contemporaneamente una pagina, avranno lo stesso valore data/ora. Come risultato, le [!DNL URL] chiamate univoche e multiple vengono conteggiate solo una volta. `%rnd%` Tuttavia, genera un valore numerico univoco per ogni chiamata (anche quando gli utenti visualizzano contemporaneamente la stessa pagina). Ciò significa che [!DNL URL] la stringa contiene valori diversi e viene conteggiata come univoca.

>[!MORE_ LIKE_ THIS]
>
>* [Macro di destinazione definite](../../features/destinations/destination-macros.md#destination-macros-defined)