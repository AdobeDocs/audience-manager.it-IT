---
description: I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie del visitatore per gli ID richiesti per effettuare chiamate API DCS.
seo-description: I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie del visitatore per gli ID richiesti per effettuare chiamate API DCS.
seo-title: Ottenere gli ID utente e le aree geografiche tramite il servizio identità  Adobe Experience Platform
solution: Audience Manager
title: Ottenere gli ID utente e le aree geografiche tramite il servizio identità  Adobe Experience Platform
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 2%

---


# Ottenere gli ID utente e le aree geografiche tramite il servizio identità  Adobe Experience Platform {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie del visitatore per gli ID richiesti per effettuare chiamate [!DNL DCS] API.

## Ottenere l’ID utente dal cookie del servizio ID {#get-user-ids-from-service-cookie}

Il [Servizio](https://docs.adobe.com/content/help/en/id-service/using/home.html) identità Adobe Experience Platform assegna gli ID visitatore e regione agli utenti che arrivano sul sito Web. Questi ID identificano gli utenti in tutte le soluzioni del [!DNL Experience Cloud] sito e sono richiesti se si desidera effettuare [!DNL DCS] chiamate.

* L’utente [!UICONTROL user ID] è tenuto a identificare e associare i dati a un particolare visitatore.
* Il [!UICONTROL region ID] campo è obbligatorio perché è associato a un nome di server regionale, che è necessario inviare ai [!DNL DCS]. Le informazioni [!DNL DCS] vengono memorizzate nei centri dati geograficamente più vicini ai visitatori del sito. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

I clienti del servizio ID possono estrarre queste informazioni dal cookie del servizio ID o chiamando una funzione. La tabella seguente descrive le attività o i passaggi da completare per iniziare.

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
   <td colname="col1"> <p> <b>1. Controlla lo stato <span class="keyword"> Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Per usare il servizio ID è necessario un account Experience Cloud <span class="keyword"></span> . Se avete un account Experience Cloud <span class="keyword"></span> , ottimo! </p> <p> Se non fate parte del <span class="keyword">  Experience Cloud</span>, registratevi. Ci piacerebbe avere te e c'è sempre spazio per di più. Per istruzioni su come impostare un account, consultate <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Abilitazione delle soluzioni per i servizi</a>di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configurare il servizio <span class="keyword"> ID</span></b> </p> </td> 
   <td colname="col2"> <p>Il servizio <span class="keyword"></span> ID è costituito dal codice JavaScript che viene inserito in ogni pagina da utilizzare per la raccolta dei dati. Per ulteriori informazioni, consulta le guide <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"></a> all’implementazione del servizio ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Leggi il cookie del servizio <span class="keyword"></span> ID</b> </p> </td> 
   <td colname="col2"> <p>Il servizio <span class="keyword"></span> ID memorizza l’ID utente e l’ID di regione nel cookie AMCV. Il nome completo del cookie è <code>AMCV_<i>###</i>@AdobeOrg</code>. Gli <code><i>###</i></code> elementi sono segnaposto per l'ID organizzazione. Consulta <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e il  Experience Cloud ID</a> per ulteriori dettagli. </p> <p>Analizzare il cookie AMCV per le seguenti coppie chiave-valore: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Questa coppia chiave-valore contiene l’ID utente <span class="keyword"> Experience Cloud</span> . </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Questa coppia chiave-valore contiene l'ID di regione (talvolta denominato <span class="term"> hint</span>di posizione) associato a un nome server regionale. </li> 
     </ul> </p> <p>Puoi effettuare chiamate al <span class="wintitle"> DCS</span> una volta che disponi degli ID utente e regione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recuperare l’ <span class="keyword"> ID</span> Experience Cloud  con getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Facoltativo)</i> Questa funzione restituisce l’ID visitatore <span class="keyword">  Experience Cloud</span> . È progettato per soluzioni personalizzate e casi di utilizzo specifici. Consulta <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilizzo di getMarketingCloudVisitorID</a> di seguito e la documentazione <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> del servizio ID</a>correlata. </p> <p>Non è necessario utilizzarlo se ottieni gli ID utente e posizione dal cookie del servizio ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilizzo `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Un altro modo per ottenere l’ID visitatore è utilizzare la `getMarketingCloudVisitorID` funzione. Quando viene richiamata, questa funzione esegue una query sull&#39;oggetto [!DNL ID service] e restituisce un ID. `getMarketingCloudVisitorID` accetta l&#39; `callback` argomento facoltativo come mostrato:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilizzo e scopo della callback {#callback-usage}

`callback` è facoltativo. Questa funzione funziona senza di essa, ma restituisce un ID solo quando un visitatore ha un [!DNL Experience Cloud] cookie nel suo browser. Se manca il cookie del visitatore o se il visitatore non dispone di un ID, la funzione restituisce un `()` oggetto vuoto. Questo può accadere anche dopo che la pagina viene caricata e il visitatore riceve un nuovo ID. Per evitare questo problema, `callback` forza questa funzione a verificare la presenza di un ID visitatore dopo il caricamento della pagina. In caso contrario, `callback`la funzione ID visitatore non restituirà un ID nemmeno se verrà successivamente scritto nel browser del visitatore.

## Passaggi successivi {#next-steps}

Una volta ottenuto l’ID utente e di regione, potete iniziare a inviare e ricevere [!DNL DCS] i dati. Consultate [Effettuare chiamate](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)DCS API.