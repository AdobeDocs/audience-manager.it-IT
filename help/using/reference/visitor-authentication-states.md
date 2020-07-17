---
description: Lo stato di autenticazione del visitatore in  Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte nel profilo autenticato del visitatore o nel profilo del dispositivo da cui sono stati raccolti i dati.  Audience Manager gestisce allo stesso modo gli stati di autenticazione dell’ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate dell’evento.
keywords: dpm.demdex.net
seo-description: Lo stato di autenticazione del visitatore in  Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte nel profilo autenticato del visitatore o nel profilo del dispositivo da cui sono stati raccolti i dati.  Audience Manager gestisce allo stesso modo gli stati di autenticazione dell’ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate dell’evento.
seo-title: Stati di autenticazione dei visitatori in Audience Manager
solution: Audience Manager
title: Stati di autenticazione dei visitatori in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---


# Stati di autenticazione dei visitatori in Audience Manager{#visitor-authentication-states-in-audience-manager}

Lo stato di autenticazione del visitatore in  Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte nel profilo autenticato del visitatore o nel profilo del dispositivo da cui sono stati raccolti i dati.  Audience Manager gestisce allo stesso modo gli stati di autenticazione dell’ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate dell’evento.

A partire dalla versione 1.5 del servizio [!DNL Experience Cloud] ID, il `setCustomerID` metodo include l’ `AuthState` oggetto facoltativo. `AuthState` identifica i visitatori in base al loro stato [di](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)autenticazione. [!DNL Audience Manager] gestisce le caratteristiche realizzate in modo diverso, a seconda dello stato di autenticazione passato nella chiamata e della regola [di unione dei](../features/profile-merge-rules/merge-rules-dashboard.md) profili utilizzata per la segmentazione.

## Stato autenticazione: SCONOSCIUTO {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leggere</b> le informazioni dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Scrivere</b> nuove caratteristiche al profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sì, se la regola di unione delle opzioni autenticate = "Ultimi profili autenticati". </p> </td> 
   <td colname="col3" morerows="1"> <p>No, i dati sulle caratteristiche vengono aggiunti al profilo del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, se la regola di unione delle opzioni autenticate = "Profili autenticati correnti" o "Nessun profilo autenticato". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Stato autenticazione: AUTENTICATO {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leggere</b> le informazioni dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Scrivere</b> nuove caratteristiche al profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sì, se la regola di unione delle opzioni autenticate = "Profili autenticati correnti" o "Ultimi profili autenticati". </p> </td> 
   <td colname="col3" morerows="1"> <p>Sì, i dati sulle caratteristiche vengono aggiunti al profilo autenticato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, se la regola di unione delle opzioni autenticate è "Nessun profilo autenticato". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Stato autenticazione: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leggere</b> le informazioni dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Scrivere</b> nuove caratteristiche al profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Sì, se la regola di unione delle opzioni autenticate = "Ultimi profili autenticati" </td> 
   <td colname="col3" morerows="1"> <p>No, i dati sulle caratteristiche vengono scritti nel profilo del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> No, se la regola di unione delle opzioni autenticate = "Profili autenticati correnti" o "Nessun profilo autenticato" </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] esegue una sincronizzazione ID tra [CID e UUID](../reference/ids-in-aam.md) in tutti e tre i casi.

>[!MORELIKETHIS]
>
>* [ID cliente e stati di autenticazione](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

