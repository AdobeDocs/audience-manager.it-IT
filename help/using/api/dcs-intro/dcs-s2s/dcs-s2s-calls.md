---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: Esecuzione di chiamate API DCS server-to-server
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: Sintassi, esempio e parametri delle chiamate quando si effettuano chiamate API DCS server-to-server
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 8%

---

# Esecuzione di chiamate API DCS server-to-server {#making-server-to-server-dcs-api-calls}

Le chiamate richiedono il nome host del server DCS regionale e l’ID utente. Se non disponi degli ID utente e di regione richiesti, consulta [Ottenere ID utente e aree geografiche da una risposta DCS](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) e/o [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Una volta che disponi di ID utente e di regione, puoi effettuare chiamate server-to-server al DCS. Fai riferimento a questa sezione per sintassi ed esempi.

>[!NOTE]
>
>Nel codice e negli esempi, *corsivo* rappresenta un segnaposto variabile. Sostituire un valore reale per il segnaposto quando si effettua una chiamata server-to-server al [!DNL DCS].

## Sintassi e esempio di chiamata {#call-syntax-example}

Una richiesta di base server-to-server che invia dati al [!DNL DCS] utilizza la sintassi mostrata di seguito.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Una chiamata di esempio è simile a quella dell’esempio seguente.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Parametri di chiamata {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Questa parte della chiamata contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Alias di dominio assegnato da <span class="keyword"> Audience Manager</span> (ad esempio, <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Il dominio di destinazione, che è sempre <i><code> demdex.net</code></i>. Consulta <a href="../../../reference/demdex-calls.md">Understanding Calls to the Demdex Domain</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Il parametro host dell’intestazione http che mostra il nome dell’area geografica <span class="wintitle"> DCS</span> server. Il nome host è associato a un ID di regione, ed è per questo che ne hai bisogno prima di effettuare questi tipi di chiamate. Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Questa parte dell'invito: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la chiamata come chiamata evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definisce l’inizio della stringa URL contenente i dati da inviare al DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Chiave ID utente univoca che contiene <span class="keyword"> Audience Manager</span> valore ID utente in una coppia chiave-valore. </p> <p>Utilizzare <code><i>d_uuid</i></code> se stai passando il <span class="keyword"> Audience Manager</span> ID utente. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Chiave ID utente univoca che contiene <span class="keyword"> Experience Cloud</span> valore ID utente in una coppia chiave-valore. Vedi anche <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Ottenere l'ID utente dal cookie del servizio ID</a>. </p> <p>Utilizzare <i><code> d_mid</code></i> se stai passando un <span class="keyword"> Experience Cloud</span> ID acquisito da <span class="keyword"> Experience Cloud</span> Servizio ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parametri di risposta facoltativi. </p> <p> Nessuna di queste è necessaria per inviare dati al <span class="wintitle"> DCS</span>. Tuttavia, se desideri <span class="wintitle"> DCS</span> per restituire una risposta, devi includere <i><code> d_rtbd=json</code></i> nella tua richiesta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risposta di esempio {#sample-response}

Consulta [Ricevere dati dal DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
