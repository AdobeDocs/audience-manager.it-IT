---
description: I clienti del servizio ID devono consultare questa sezione per informazioni su come leggere il cookie del visitatore per gli ID necessari per effettuare chiamate API DCS.
seo-description: I clienti del servizio ID devono consultare questa sezione per informazioni su come leggere il cookie del visitatore per gli ID necessari per effettuare chiamate API DCS.
seo-title: Ottenere ID utente e aree geografiche tramite il servizio Adobe Experience Platform Identity
solution: Audience Manager
title: Ottenere ID utente e aree geografiche tramite il servizio Adobe Experience Platform Identity
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 7%

---

# Ottenere ID utente e aree geografiche tramite il servizio Adobe Experience Platform Identity {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

I clienti del servizio ID devono consultare questa sezione per informazioni su come leggere il cookie del visitatore per gli ID richiesti per effettuare chiamate [!DNL DCS] API.

## Ottenere l’ID utente dal cookie del servizio ID {#get-user-ids-from-service-cookie}

Il [servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html) assegna gli ID visitatore e regione agli utenti che visitano il tuo sito web. Questi ID identificano gli utenti in tutte le soluzioni di [!DNL Experience Cloud] e sono necessari se desideri effettuare chiamate [!DNL DCS].

* È necessario [!UICONTROL user ID] per identificare e associare i dati a un particolare visitatore.
* Il [!UICONTROL region ID] è obbligatorio perché è associato a un nome di server regionale, che è necessario inviare ai [!DNL DCS]. Il [!DNL DCS] memorizza le informazioni nei centri dati geograficamente più vicini ai visitatori del sito. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

I clienti del servizio ID possono estrarre queste informazioni dal cookie del servizio ID o chiamando una funzione . La tabella seguente descrive le attività o i passaggi da completare per iniziare.

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
   <td colname="col1"> <p> <b>1. Controlla il tuo stato <span class="keyword"> Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Per usare il servizio ID è necessario un account <span class="keyword"> Experience Cloud</span> . Se disponi di un account <span class="keyword"> Experience Cloud</span>, ottimo! </p> <p> Se non fai parte dell' <span class="keyword"> Experience Cloud</span>, registrati. Ci piacerebbe avere te e c'è sempre spazio per di più. Per istruzioni su come impostare un account, consulta <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Abilitazione delle soluzioni per i servizi di base</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Imposta il <span class="keyword"> servizio ID</span></b> </p> </td> 
   <td colname="col2"> <p>Il <span class="keyword"> servizio ID</span> è costituito da codice JavaScript da inserire in ogni pagina da utilizzare per la raccolta dei dati. Per ulteriori informazioni, consulta le guide all'implementazione del servizio ID <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"></a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Leggi il cookie <span class="keyword"> del servizio ID</span></b> </p> </td> 
   <td colname="col2"> <p>Il <span class="keyword"> servizio ID</span> memorizza l'ID utente e regione nel cookie AMCV. Il nome completo del cookie è <code>AMCV_<i>###</i>@AdobeOrg</code>. Gli elementi <code><i>###</i></code> sono segnaposto per l’ID organizzazione. Per ulteriori informazioni, consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e l'Experience Cloud ID</a> . </p> <p>Analizza il cookie AMCV per queste coppie chiave-valore: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Questa coppia chiave-valore contiene l'ID utente  <span class="keyword"> Experience </span> Cloud. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Questa coppia chiave-valore contiene l'ID di regione (talvolta denominato  <span class="term"> hint di posizione</span>) associato a un nome di server regionale. </li> 
     </ul> </p> <p>Puoi effettuare chiamate al <span class="wintitle"> DCS</span> una volta che disponi degli ID utente e di regione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recupera l' <span class="keyword"> ID Experience Cloud</span> con getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Facoltativo) </i> Questa funzione restituisce l'ID visitatore di  <span class="keyword"> Experience </span> Cloud. È progettato per soluzioni personalizzate e casi d’uso specifici. Consulta <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilizzo di getMarketingCloudVisitorID</a> di seguito e la <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> relativa documentazione del servizio ID</a>. </p> <p>Non devi utilizzarlo se ottieni gli ID utente e posizione dal cookie del servizio ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilizzo di `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Un altro modo per ottenere l’ID visitatore è la funzione `getMarketingCloudVisitorID` . Quando viene invocata, questa funzione esegue una query sul [!DNL ID service] e restituisce un ID. `getMarketingCloudVisitorID` accetta l’ `callback` argomento facoltativo illustrato di seguito:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilizzo e scopo del callback {#callback-usage}

`callback` è facoltativo. Questa funzione funziona senza di essa, ma restituisce un ID solo quando un visitatore ha un cookie [!DNL Experience Cloud] nel proprio browser. Se manca il cookie del visitatore o se un visitatore non dispone di un ID, la funzione restituisce un oggetto `()` vuoto. Questo può accadere anche dopo il caricamento della pagina e il visitatore riceve un nuovo ID. Per evitare questo problema, `callback` forza questa funzione a verificare la presenza di un ID visitatore dopo il caricamento della pagina. Senza `callback`, la funzione ID visitatore non restituisce un ID nemmeno se è scritto nel browser del visitatore in un secondo momento.

## Passaggi successivi {#next-steps}

Una volta ottenuto l’ID utente e di regione, puoi iniziare a inviare e ricevere i dati [!DNL DCS]. Consulta [Effettuare chiamate API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
