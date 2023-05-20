---
description: I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie visitatore per gli ID richiesti per effettuare chiamate all’API DCS.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Ottenere ID utente e aree geografiche tramite il servizio Adobe Experience Platform Identity
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# Ottenere ID utente e aree geografiche tramite il servizio Adobe Experience Platform Identity {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie visitatore per gli ID richiesti [!DNL DCS] Chiamate API.

## Ottenere l&#39;ID utente dal cookie del servizio ID {#get-user-ids-from-service-cookie}

Il [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html) assegna gli ID visitatore e area geografica agli utenti che accedono al sito web. Questi ID identificano gli utenti in tutte le soluzioni di [!DNL Experience Cloud] e sono necessari se si desidera [!DNL DCS] chiamate.

* Il [!UICONTROL user ID] è richiesto per identificare e associare dati a un particolare visitatore.
* Il [!UICONTROL region ID] è richiesto perché è associato a un nome di server regionale, che è necessario inviare dati al [!DNL DCS]. Il [!DNL DCS] memorizza le informazioni nei data center geograficamente più vicini ai visitatori del sito. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

I clienti del servizio ID possono estrarre queste informazioni dal cookie del servizio ID o chiamando una funzione. La tabella seguente descrive le attività o i passaggi da completare per iniziare.

Codice in *corsivo* rappresenta un segnaposto variabile.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attività </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Controlla il tuo <span class="keyword"> Experience Cloud</span> stato</b> </p> </td> 
   <td colname="col2"> <p>Hai bisogno di un <span class="keyword"> Experience Cloud</span> per usare il servizio ID. Se si dispone di <span class="keyword"> Experience Cloud</span> account, ottimo! </p> <p> Se non fai parte del <span class="keyword"> Experience Cloud</span>, quindi registrati. Ci piacerebbe averti e c'è sempre spazio per altro. Per istruzioni sulla configurazione di un account, consulta <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Abilitazione delle soluzioni per i servizi principali</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configurare <span class="keyword"> Servizio ID</span></b> </p> </td> 
   <td colname="col2"> <p>Il <span class="keyword"> Servizio ID</span> è costituito da codice JavaScript inserito in ogni pagina che desideri utilizzare per la raccolta dati. Consulta il servizio ID <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> guide all'implementazione</a> per ulteriori informazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Leggi le <span class="keyword"> Servizio ID</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>Il <span class="keyword"> Servizio ID</span> memorizza l'utente e l'ID di regione nel cookie AMCV. Nome cookie completo: <code>AMCV_<i>###</i>@AdobeOrg</code>. Il <code><i>###</i></code> Gli elementi di sono segnaposto per l'ID organizzazione. Consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e ID dell’Experience Cloud</a> per i dettagli. </p> <p>Analizza il cookie AMCV per queste coppie chiave-valore: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: questa coppia chiave-valore contiene il <span class="keyword"> Experience Cloud</span> ID utente. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: questa coppia chiave-valore contiene l’ID di regione (talvolta denominato <span class="term"> hint di posizione</span>) associato a un nome di server regionale. </li> 
     </ul> </p> <p>Puoi effettuare chiamate al <span class="wintitle"> DCS</span> una volta che hai gli ID utente e area geografica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recupera il <span class="keyword"> ID EXPERIENCE CLOUD</span> con getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Facoltativo)</i> Questa funzione restituisce il <span class="keyword"> Experience Cloud</span> ID visitatore. È progettato per soluzioni personalizzate e casi d’uso specifici. Consulta <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilizzo di getMarketingCloudVisitorID</a> sotto e <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> documentazione correlata al servizio ID</a>. </p> <p>Non è necessario utilizzarlo se ottieni gli ID utente e posizione dal cookie del servizio ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilizzo di `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Un altro modo per ottenere l&#39;ID visitatore è con `getMarketingCloudVisitorID` funzione. Quando viene richiamata, questa funzione esegue una query su [!DNL ID service] e restituisce un ID. `getMarketingCloudVisitorID` accetta le opzioni `callback` come mostrato:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilizzo e scopo del callback {#callback-usage}

`callback` è facoltativo. Questa funzione funziona senza di essa, ma restituisce un ID solo quando un visitatore ha un [!DNL Experience Cloud] cookie nel browser. Se il cookie del visitatore non è presente, o se un visitatore non ha un ID, la funzione restituisce un valore vuoto `()` oggetto. Questo può accadere anche dopo il caricamento della pagina e il visitatore riceve un nuovo ID. Per evitare questo problema, `callback` forza questa funzione a verificare la presenza di un ID visitatore dopo il caricamento della pagina. Senza `callback`, la funzione ID visitatore non restituisce un ID anche se viene scritto nel browser del visitatore in un secondo momento.

## Passaggi successivi {#next-steps}

Una volta che hai l’ID utente e area geografica, puoi iniziare a inviare e ricevere [!DNL DCS] dati. Consulta [Esecuzione di chiamate API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
