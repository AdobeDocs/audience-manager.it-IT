---
description: Descrive le macro che è possibile aggiungere a un URL di destinazione.
seo-description: Descrive le macro che è possibile aggiungere a un URL di destinazione.
seo-title: Definizione delle macro delle destinazioni
solution: Audience Manager
title: Definizione delle macro delle destinazioni
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Nozioni di base sulle destinazioni
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 3%

---

# Definizione delle macro delle destinazioni {#destination-macros-defined}

Descrive le macro che è possibile aggiungere a una destinazione [!DNL URL].

<!-- destination-macros.xml -->

Quando crei una destinazione [!DNL URL], puoi inserire le seguenti macro nella stringa [!DNL URL] . Controlla con il tuo partner dati/destinazione il posizionamento corretto delle macro all&#39;interno della destinazione [!DNL URL].

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
   <td colname="col2"> <p>Obbligatorio. </p> <p>Definisce la posizione del valore del segmento mappato in un URL di destinazione. Di solito si tratta dell' <i>ID segmento</i>, ma potrebbe anche essere il codice di integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'ID Audience Manager <span class="keyword"> dell'utente</span> nell'URL di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>L' <i>id origine dati</i> corrisponde all'identificatore di un'origine dati passata alla macro. </p> <p>Vediamo come funziona in un semplice esempio. In questo caso, disponiamo di un partner <span class="keyword"> Audience Manager</span> con i seguenti ID e condizioni: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">ID origine dati: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Un ID cliente interno: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">ID dichiarato: Il partner desidera trasmettere questi valori come ID dichiarato <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Per eseguire questa operazione con <code>%dpid_<i>data source id</i>%</code>, il partner <span class="keyword"> Audience Manager</span> formatta la macro in questo modo: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>La macro sostituirà <code> 1</code> con <code> CustomerABC</code>. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Indica se le normative RGPD si applicano o meno al visitatore. Utilizza questa macro per includere il consenso nei segmenti inviati a destinazioni URL integrate con IAB. Per ulteriori informazioni, consulta <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in di Audience Manager per IAB TCF</a> .</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>La stringa di consenso (incluso l’ID fornitore IAB) raccolta quando i visitatori forniscono o negano il consenso sul sito. Utilizza questa macro per includere la stringa di consenso nei segmenti inviati a destinazioni URL integrate con IAB. Sostituisci <code>XXXX</code> con l'ID partner di destinazione. Per ulteriori informazioni, consulta <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in di Audience Manager per IAB TCF</a> . </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Rileva il protocollo utilizzato nella pagina web principale e lo inserisce nell’URL di destinazione. Ad esempio:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">se la pagina web è <b>https</b>://aam_client.com, questa macro verrà sostituita con <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">se la pagina web è <b>http</b>://aam_client.com, questa macro verrà sostituita con <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l'ID <span class="keyword"> Experience Cloud</span> nell'URL di destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce l’area <span class="wintitle"> Data Collection Server (DCS)</span> nell’URL di destinazione. Per ridurre al minimo la latenza, quando il visitatore effettua una chiamata HTTP all' <span class="keyword"> Audience Manager</span>, viene reindirizzato al datacenter <span class="wintitle"> DCS</span> più vicino. Questo si ottiene tramite il DNS, che è in grado di rilevare la posizione del visitatore e indirizzarlo al datacenter appropriato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Esegue una funzione di svuotamento della cache inserendo un numero casuale nell’URL di destinazione. Questo impedisce ai browser di servire il contenuto nella cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Inserisce una marca temporale UNIX nell’URL di destinazione per impedire ai browser di servire il contenuto nella cache. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Busting della cache con macro di destinazione {#destination-cache-busting}

Le macro `%rnd%` e `%timestamp%` inseriscono valori univoci in una stringa [!DNL URL] per impedire la memorizzazione in cache del browser.

## Busting della cache con `%rnd%` e `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

La cache dei browser (salva) richiede spesso il contenuto in memoria. Quando una pagina viene caricata, il contenuto salvato viene distribuito dalla cache anziché da un server remoto. Questo processo consente di mantenere i tempi di download efficienti perché i dati vengono inviati localmente anziché da un’altra posizione. Tuttavia, poiché la memorizzazione in cache non richiede una chiamata al server, può distorcere la generazione di rapporti riducendo artificialmente il numero di richieste univoche.

La memorizzazione nella cache impedisce ai browser di salvare e riutilizzare il contenuto. Questa tecnica utilizza un codice che inserisce un numero casuale o una marca temporale in una stringa URL, rendendola univoca per il browser. Di conseguenza, ogni chiamata `HTTP` viene conteggiata come richiesta separata al server. L&#39;imposizione di una nuova chiamata al server per ogni richiesta consente di mantenere l&#39;accuratezza del reporting e di ridurre le discrepanze. [!DNL Audience Manager] fornisce due macro per lo svuotamento della cache:

* `%rnd%`: Inserisce un numero casuale in un URL.
* `%timestamp%`: Inserisce la data/ora Unix in un URL.

## Confronto tra `%rnd%` e `%timestamp%` {#compare-rnd-timestamp}

Entrambe le macro impediscono la memorizzazione in cache, ma `%rnd%` potrebbe essere più efficiente. Ad esempio, con `%timestamp%`, se più utenti visualizzano una pagina contemporaneamente ottengono lo stesso valore di data/ora. Di conseguenza, il [!DNL URL] non è univoco e più chiamate vengono conteggiate una sola volta. Tuttavia, `%rnd%` genera un valore numerico univoco per ogni chiamata (anche quando gli utenti visualizzano la stessa pagina contemporaneamente). Ciò significa che la stringa [!DNL URL] contiene valori diversi e viene conteggiata come univoca.

>[!MORELIKETHIS]
>
>* [Definizione delle macro delle destinazioni](../../features/destinations/destination-macros.md#destination-macros-defined)

