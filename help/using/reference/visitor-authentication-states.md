---
description: Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte sul profilo autenticato del visitatore o sul profilo del dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce nello stesso modo gli stati di autenticazione ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate evento.
keywords: dpm.demdex.net
seo-description: Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte sul profilo autenticato del visitatore o sul profilo del dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce nello stesso modo gli stati di autenticazione ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate evento.
seo-title: Stati di autenticazione dei visitatori in Audience Manager
solution: Audience Manager
title: Stati di autenticazione dei visitatori in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Riferimenti '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Stati di autenticazione dei visitatori in Audience Manager{#visitor-authentication-states-in-audience-manager}

Lo stato di autenticazione del visitatore in Audience Manager determina se le nuove informazioni sulle caratteristiche vengono scritte sul profilo autenticato del visitatore o sul profilo del dispositivo da cui sono stati raccolti i dati. Audience Manager gestisce nello stesso modo gli stati di autenticazione ID visitatore UNKNOWN e LOGGED_OUT nelle chiamate evento.

A partire dalla versione 1.5 del servizio ID [!DNL Experience Cloud], il metodo `setCustomerID` include l&#39;oggetto facoltativo `AuthState`. `AuthState` identifica i visitatori in base al loro stato  [di autenticazione](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] gestisce le caratteristiche realizzate in modo diverso, a seconda dello stato di autenticazione trasmesso nella chiamata e della regola di unione  [profili ](../features/profile-merge-rules/merge-rules-dashboard.md) utilizzata per la segmentazione.

## Stato autenticazione: SCONOSCIUTO {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Informazioni di lettura dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> riten nuove caratteristiche al profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Sì, se la regola di unione delle opzioni autenticate = "Ultimi profili autenticati". </p> </td> 
   <td colname="col3" morerows="1"> <p>No, i dati delle caratteristiche vengono aggiunti al profilo del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, se la regola di unione delle opzioni autenticate = "Profili autenticati correnti" o "Nessun profilo autenticato". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (viene evidenziato il valore della richiesta corrispondente allo stato di autenticazione):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Stato autenticazione: AUTENTICATO {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Informazioni di lettura dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> riten nuove caratteristiche al profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Sì, se la regola di unione delle opzioni autenticate = "Profili autenticati correnti" o "Ultimi profili autenticati". </p> </td> 
   <td colname="col3" morerows="1"> <p>Sì, i dati delle caratteristiche vengono aggiunti al profilo autenticato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>No, se la regola di unione delle opzioni autenticate = "Nessun profilo autenticato". </p> </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (viene evidenziato il valore della richiesta corrispondente allo stato di autenticazione):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Stato autenticazione: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valore richiesta </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Informazioni di lettura dal profilo autenticato </p> </th> 
   <th colname="col3" class="entry"> <p> <b></b> riten nuove caratteristiche al profilo autenticato </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Sì, se la regola di unione delle opzioni autenticate = "Ultimi profili autenticati" </td> 
   <td colname="col3" morerows="1"> <p>No, i dati delle caratteristiche vengono scritti nel profilo del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> No, se la regola di unione delle opzioni autenticate = "Profili autenticati correnti" o "Nessun profilo autenticato" </td> 
  </tr> 
 </tbody> 
</table>

Chiamata di esempio (viene evidenziato il valore della richiesta corrispondente allo stato di autenticazione):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] esegue una sincronizzazione ID tra  [CID e ](../reference/ids-in-aam.md) UUID in tutti e tre i casi.

>[!MORELIKETHIS]
>
>* [ID cliente e stati di autenticazione](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

