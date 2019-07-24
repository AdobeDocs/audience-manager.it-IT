---
description: Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni relative alle caratteristiche sono scritte sul profilo autenticato del visitatore o sul profilo dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce gli stati UNKNOWN e LOGGED_ OUT delle chiamate dell'evento nello stesso modo.
keywords: dpm.demdex.net
seo-description: Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni relative alle caratteristiche sono scritte sul profilo autenticato del visitatore o sul profilo dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce gli stati UNKNOWN e LOGGED_ OUT delle chiamate dell'evento nello stesso modo.
seo-title: Stati di autenticazione dei visitatori in Audience Manager
solution: Audience Manager
title: Stati di autenticazione dei visitatori in Audience Manager
uuid: d 748 c 0 c 3-5833-4 fb 9-ab 3 e -793 f 5 f 252 e 47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni relative alle caratteristiche sono scritte sul profilo autenticato del visitatore o sul profilo dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce gli stati UNKNOWN e LOGGED_ OUT delle chiamate dell'evento nello stesso modo.

Beginning with [!DNL Experience Cloud] ID service v1.5+, the `setCustomerID` method includes the optional `AuthState` object. `AuthState` identifica i visitatori in base al loro [stato di autenticazione](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). [!DNL Audience Manager] gestisce le caratteristiche realizzate in modo diverso, a seconda dello stato di autenticazione passato nella chiamata e della [Regola](../features/profile-merge-rules/merge-rules-dashboard.md) Unione profilo utilizzata per la segmentazione.

## Authentication Status: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leggere</b> le informazioni dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Scrivere</b> nuove caratteristiche nel profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sì, se l'opzione Opzione Autenticato unione = "Last Authenticated Profiles" (Ultimo profilo autenticato). </p> </td> 
   <td colname="col3" morerows="1"> <p>No, i dati delle caratteristiche vengono aggiunti al profilo dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, se la regola Unione dell'opzione è selezionata = "Profili autenticati correnti" o "Nessun profilo autenticato". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leggere</b> le informazioni dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Scrivere</b> nuove caratteristiche nel profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sì, se l'opzione Unisci regole autenticate = "Profili autenticati correnti" o "Profili autenticati recenti". </p> </td> 
   <td colname="col3" morerows="1"> <p>Sì, i dati relativi alle caratteristiche vengono aggiunti al profilo autenticato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, se l'opzione Unisci regola è selezionata = "Nessun profilo autenticato". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Leggere</b> le informazioni dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Scrivere</b> nuove caratteristiche nel profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Sì, se l'opzione Opzione Autenticato unione = "Ultimi profili autenticati" </td> 
   <td colname="col3" morerows="1"> <p>No, i dati relativi alle caratteristiche vengono scritti nel profilo del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> No, se l'opzione Unisci regole autenticate = "Profili autenticati correnti" o "Nessun profilo autenticato" </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (il valore della richiesta corrispondente allo stato di autenticazione è evidenziato):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] esegue una sincronizzazione ID tra [CID e UUID](../reference/ids-in-aam.md) in tutti e tre i casi.

>[!MORE_ LIKE_ THIS]
>
>* [ID cliente e stati di autenticazione](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

