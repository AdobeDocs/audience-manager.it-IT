---
description: I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie del visitatore per gli ID richiesti per effettuare chiamate API DCS.
seo-description: I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie del visitatore per gli ID richiesti per effettuare chiamate API DCS.
seo-title: Ottieni ID utente e regioni tramite il servizio Experience Cloud ID
solution: Audience Manager
title: Ottieni ID utente e regioni tramite il servizio Experience Cloud ID
uuid: 80 de 6 cf 2-5 d 9 e -4 ef 8-a 0 f 2-d 53 b 5 d 574 c 89
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ottieni ID utente e regioni tramite il servizio Experience Cloud ID {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie del visitatore per gli ID richiesti per effettuare [!UICONTROL DCS] chiamate API.

## Ottenere l&#39;ID utente dal cookie del servizio ID {#get-user-ids-from-service-cookie}

Il [servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/) assegna gli ID visitatore e regione agli utenti che arrivano sul tuo sito Web. Questi ID identificano gli utenti in tutte le soluzioni in [!DNL Experience Cloud] e sono necessari per [!UICONTROL DCS] effettuare chiamate.

* È [!UICONTROL user ID] necessario identificare e associare dati a un particolare visitatore.
* È [!UICONTROL region ID] obbligatorio perché è associato a un nome server regionale, che dovrà inviare dati all &#39; [!UICONTROL DCS]. Le [!UICONTROL DCS] informazioni memorizzano informazioni nei centri dati geograficamente più vicini ai visitatori del sito. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

I clienti del servizio ID possono estrarre queste informazioni dal cookie del servizio ID o chiamando una funzione. La tabella seguente descrive le attività o i passaggi necessari per iniziare.

Il codice in *corsivo* rappresenta un segnaposto variabile.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attività </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Check your <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>Per utilizzare <span class="keyword"> il servizio ID è necessario</span> un account Experience Cloud. Se hai un account <span class="keyword"> Experience Cloud</span> , fantastico! </p> <p> Se non fai parte di <span class="keyword"> Experience Cloud</span>, registrati. Ci piacerebbe averti e troverai sempre spazio per altri scopi. Per istruzioni su come configurare un account, vedi Servizi <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> principali - Abilitazione delle soluzioni</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configurare il servizio <span class="keyword"> ID</span></b> </p> </td> 
   <td colname="col2"> <p>Il servizio <span class="keyword"> ID</span> è costituito da codice javascript che viene inserito in ogni pagina che desideri utilizzare per la raccolta dati. Per ulteriori <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> informazioni, consulta le guide</a> sull'implementazione del servizio ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Leggete <span class="keyword"> il cookie del servizio</span> ID</b> </p> </td> 
   <td colname="col2"> <p>Il <span class="keyword"> servizio ID</span> memorizza l'ID utente e l'ID di regione nel cookie AMCV. Il nome completo del cookie è <code>AMCV_<i># # #</i>@ adobeorg</code>. Gli <code><i>ID # # #</i></code> sono segnaposto per l'ID organizzazione. Per informazioni, vedi <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookie e Experience Cloud ID</a> . </p> <p>Analizzare il cookie AMCV per queste coppie chiave-valore: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid =<i>ID utente</i></code>: Questa coppia chiave/valore contiene l' <span class="keyword"> ID</span> utente di Experience Cloud. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh =<i>region ID</i></code>: Questa coppia chiave/valore contiene l'ID regione (talvolta denominato hint <span class="term"> di posizione</span>) associato a un nome server regionale. </li> 
     </ul> </p> <p>Puoi effettuare chiamate al <span class="wintitle"> DCS</span> una volta che hai gli ID di utenti e regione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recuperare l'ID <span class="keyword"> Experience Cloud</span> con getmarketingcloudvisitorid</b> </p> </td> 
   <td colname="col2"> <p><i>(Facoltativo)</i> Questa funzione restituisce l' <span class="keyword"> ID</span> visitatore Experience Cloud. È progettato per soluzioni personalizzate e casi di utilizzo specifici. Consultate <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilizzo di getmarketingcloudvisitorid</a> di seguito e <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> la relativa documentazione del servizio ID</a>. </p> <p>Non devi usarlo se ottieni gli ID utente e posizione dal cookie del servizio ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilizzo di `getMarketingCloudVisitorID`{#working-with-getmarketingcloudvisitorid}

Un altro modo per ottenere l&#39;ID visitatore è la `getMarketingCloudVisitorID` funzione. Quando richiamato, questa funzione query l&#39; [!DNL ID service] e restituisce un ID. `getMarketingCloudVisitorID` accetta l&#39;argomento opzionale `callback` come mostrato:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilizzo e utilizzo del callback {#callback-usage}

`callback` è facoltativo. Questa funzione funziona senza di essa, ma restituisce un ID solo quando un visitatore ha un [!DNL Experience Cloud] cookie nel browser. Se il cookie del visitatore non è presente, o se un visitatore non ha un ID, la funzione restituisce un `()` oggetto vuoto. Questo può verificarsi anche dopo che la pagina viene caricata e che il visitatore riceve un nuovo ID. Per evitare questa situazione `callback` , forza questa funzione a controllare l&#39;ID visitatore dopo il caricamento della pagina. Senza `callback`, la funzione ID visitatore non restituirà un ID anche se viene scritta nel browser del visitatore successivamente.

## Passaggi successivi {#next-steps}

Una volta ottenuto l&#39;ID utente e l&#39;ID di regione, puoi iniziare a inviare e ricevere [!UICONTROL DCS] dati. Consultate [Creazione di chiamate DCS API](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).