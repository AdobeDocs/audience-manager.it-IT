---
description: I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie visitatore per gli ID richiesti per effettuare chiamate all’API DCS.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Ottenere ID utente e aree geografiche tramite il servizio Adobe Experience Platform Identity
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---

# Ottenere ID utente e aree geografiche tramite il servizio Adobe Experience Platform Identity {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

I clienti del servizio ID devono fare riferimento a questa sezione per informazioni su come leggere il cookie visitatore per gli ID richiesti per effettuare chiamate API [!DNL DCS].

## Ottenere l&#39;ID utente dal cookie del servizio ID {#get-user-ids-from-service-cookie}

Il servizio [Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) assegna gli ID visitatore e regione agli utenti che accedono al tuo sito Web. Questi ID identificano gli utenti in tutte le soluzioni di [!DNL Experience Cloud] e sono necessari se si desidera effettuare [!DNL DCS] chiamate.

* [!UICONTROL user ID] è necessario per identificare e associare i dati a un visitatore specifico.
* [!UICONTROL region ID] è obbligatorio perché è associato a un nome di server regionale, che è necessario inviare dati a [!DNL DCS]. [!DNL DCS] memorizza le informazioni nei data center geograficamente più vicini ai visitatori del sito. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

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
   <td colname="col1"> <p> <b>1. Controlla il tuo stato di <span class="keyword"> Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Per utilizzare il servizio ID è necessario un account Experience Cloud<span class="keyword"> di </span>. Se hai un account <span class="keyword"> Experience Cloud</span>, benissimo! </p> <p> Se non fai parte dell'Experience Cloud <span class="keyword"></span>, iscriviti. Ci piacerebbe averti e c'è sempre spazio per altro. Per istruzioni sulla configurazione di un account, vedere <a href="https://experienceleague.adobe.com/it/docs/core-services/interface/services/getting-started" format="https" scope="external"> Abilitazione delle soluzioni per i servizi principali</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configura il servizio ID <span class="keyword"></span></b> </p> </td> 
   <td colname="col2"> <p>Il servizio ID <span class="keyword"></span> è costituito da codice JavaScript inserito in ogni pagina che si desidera utilizzare per la raccolta dati. Per ulteriori informazioni, consulta le guide all'implementazione del servizio ID <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=it" format="https" scope="external"></a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Leggi il cookie <span class="keyword"> del servizio ID </span></b> </p> </td> 
   <td colname="col2"> <p>Il servizio ID <span class="keyword"></span> memorizza l'ID utente e di regione nel cookie AMCV. Nome cookie completo: <code>AMCV_<i>###</i>@AdobeOrg</code>. Gli elementi <code><i>###</i></code> sono segnaposto per l'ID organizzazione. Per informazioni dettagliate, consulta Cookie <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=it" format="https" scope="external"> e Experience Cloud ID</a>. </p> <p>Analizza il cookie AMCV per queste coppie chiave-valore: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: questa coppia chiave-valore contiene l'ID utente <span class="keyword"> di Experience Cloud</span>. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: questa coppia chiave-valore contiene l'ID di regione (talvolta denominato <span class="term"> hint di posizione</span>) associato a un nome di server regionale. </li> 
     </ul> </p> <p>È possibile effettuare chiamate al DCS<span class="wintitle"> di </span> dopo aver ottenuto gli ID utente e di regione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Recupera l'Experience Cloud ID <span class="keyword"></span> con getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Facoltativo)</i> Questa funzione restituisce l'ID visitatore <span class="keyword"> Experience Cloud</span>. È progettato per soluzioni personalizzate e casi d’uso specifici. Consulta <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilizzo di getMarketingCloudVisitorID</a> di seguito e la documentazione relativa al servizio ID <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html?lang=it" format="https" scope="external"></a>. </p> <p>Non è necessario utilizzarlo se ottieni gli ID utente e posizione dal cookie del servizio ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilizzo di `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Un altro modo per ottenere l&#39;ID visitatore è con la funzione `getMarketingCloudVisitorID`. Quando viene richiamata, questa funzione esegue una query su [!DNL ID service] e restituisce un ID. `getMarketingCloudVisitorID` accetta l&#39;argomento facoltativo `callback` come mostrato:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilizzo e scopo del callback {#callback-usage}

`callback` è facoltativo. Questa funzione funziona senza di essa, ma restituisce un ID solo quando un visitatore ha un cookie [!DNL Experience Cloud] nel browser. Se manca il cookie visitatore o un visitatore non ha un ID, la funzione restituisce un oggetto `()` vuoto. Questo può accadere anche dopo il caricamento della pagina e il visitatore riceve un nuovo ID. Per evitare questo problema, `callback` forza questa funzione a verificare la presenza di un ID visitatore dopo il caricamento della pagina. Senza `callback`, la funzione ID visitatore non restituirà un ID anche se viene scritto nel browser del visitatore in un secondo momento.

## Passaggi successivi {#next-steps}

Una volta ottenuto l&#39;ID utente e di regione, puoi iniziare a inviare e ricevere [!DNL DCS] dati. Consulta [Esecuzione di chiamate API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
