---
description: Descrive le macro che è possibile aggiungere a un URL di destinazione.
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: Definizione delle macro di destinazione
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 1%

---

# Definizione delle macro di destinazione {#destination-macros-defined}

Descrive le macro che è possibile aggiungere a una destinazione [!DNL URL].

<!-- destination-macros.xml -->

Durante la creazione di una destinazione [!DNL URL], è possibile inserire le macro seguenti nella stringa [!DNL URL]. Verificare con il partner dati/destinazione il corretto posizionamento della macro nella destinazione [!DNL URL].

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
   <td colname="col2"> <p>Obbligatorio. </p> <p>Definisce la posizione del valore del segmento mappato in un URL di destinazione. In genere si tratta dell'<i>ID segmento</i>, ma potrebbe anche essere il codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'ID Audience Manager </span> dell'utente <span class="keyword"> nell'URL di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>L'<i>ID origine dati</i> corrisponde all'identificatore di un'origine dati passata alla macro. </p> <p>Vediamo come funziona in un semplice esempio. In questo caso, abbiamo un partner <span class="keyword"> Audience Manager</span> con i seguenti ID e condizioni: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID origine dati: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Un ID cliente interno: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID dichiarato: Il partner desidera passare questi valori come ID dichiarato <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Per eseguire questa operazione con <code>%dpid_<i>data source id</i>%</code>, il partner dell'Audience Manager <span class="keyword"></span> formatterà la macro come segue: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>La macro sostituirà <code> 1</code> con <code> CustomerABC</code>. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Indica se le normative RGPD si applicano o meno al visitatore. Utilizza questa macro per includere il consenso nei segmenti inviati a destinazioni URL integrate con IAB. Per ulteriori informazioni, vedere <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in Audience Manager per IAB TCF</a>.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>La stringa di consenso (incluso l’ID fornitore IAB) raccolta quando i visitatori forniscono o negano il consenso sul sito. Utilizza questa macro per includere la stringa di consenso nei segmenti inviati a destinazioni URL integrate con IAB. Sostituisci <code>XXXX</code> con l'ID partner di destinazione. Per ulteriori informazioni, vedere <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in Audience Manager per IAB TCF</a>. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Rileva il protocollo utilizzato nella pagina Web padre e lo inserisce nell'URL di destinazione. Ad esempio:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">se la pagina Web è <b>https</b>://aam_client.com, la macro verrà sostituita con <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">se la pagina Web è <b>http</b>://aam_client.com, la macro verrà sostituita con <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'ID Experience Cloud <span class="keyword"></span> nell'URL di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'area <span class="wintitle"> Data Collection Server (DCS)</span> nell'URL di destinazione. Per ridurre al minimo la latenza, quando il visitatore effettua una chiamata HTTP all'Audience Manager <span class="keyword"></span>, viene reindirizzato al datacenter <span class="wintitle"> DCS</span> più vicino. Ciò si ottiene tramite DNS, che è in grado di rilevare la posizione del visitatore e indirizzarlo al centro dati appropriato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Esegue una funzione di cache busting inserendo un numero casuale nell'URL di destinazione. Questo impedisce ai browser di gestire i contenuti memorizzati nella cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce una marca temporale UNIX nell'URL di destinazione per impedire che i browser distribuiscano il contenuto memorizzato nella cache. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache busting con macro di destinazione {#destination-cache-busting}

Le macro `%rnd%` e `%timestamp%` inseriscono valori univoci in una stringa [!DNL URL] per impedire la memorizzazione nella cache del browser.

## Cache busting con `%rnd%` e `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

I browser memorizzano in cache (salvano) i contenuti richiesti di frequente. Quando viene caricata una pagina, il contenuto salvato viene distribuito dalla cache anziché da un server remoto. Questo processo consente di mantenere efficienti i tempi di download, perché i dati vengono trasmessi localmente anziché da un&#39;altra posizione. Tuttavia, poiché il caching non richiede una chiamata al server, può distorcere il reporting riducendo artificialmente il numero di richieste univoche.

Il mancato funzionamento della cache impedisce ai browser di salvare e riutilizzare il contenuto. Questa tecnica utilizza un codice che inserisce un numero casuale o un timestamp in una stringa URL, rendendolo univoco per il browser. Di conseguenza, ogni chiamata `HTTP` viene conteggiata come una richiesta separata al server. L’imposizione di una nuova chiamata al server per ogni richiesta consente di mantenere l’accuratezza della generazione rapporti e di ridurre le discrepanze. [!DNL Audience Manager] fornisce due macro per il busting della cache:

* `%rnd%`: inserisce un numero casuale in un URL.
* `%timestamp%`: inserisce la data/ora Unix in un URL.

## Confronto tra `%rnd%` e `%timestamp%` {#compare-rnd-timestamp}

Entrambe le macro impediscono il caching, ma `%rnd%` potrebbe essere più efficiente. Ad esempio, con `%timestamp%`, se più utenti visualizzano una pagina contemporaneamente, otterranno lo stesso valore data/ora. Di conseguenza, [!DNL URL] non è univoco e più chiamate vengono conteggiate una sola volta. Tuttavia, `%rnd%` genera un valore numerico univoco per ogni chiamata (anche quando gli utenti visualizzano la stessa pagina contemporaneamente). Ciò significa che la stringa [!DNL URL] contiene valori diversi e viene conteggiata come univoca.

>[!MORELIKETHIS]
>
>* [Definizione delle macro delle destinazioni](../../features/destinations/destination-macros.md#destination-macros-defined)
