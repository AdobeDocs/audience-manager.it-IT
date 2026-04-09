---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: Esecuzione di chiamate API DCS server-to-server
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: Sintassi, esempio e parametri delle chiamate quando si effettuano chiamate API DCS server-to-server
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
TQID: https://experienceleague.adobe.com/rJ-QjiRGIw2Jc8v0LHDotrWN4VKyZAIcoqEiyjWMknI
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 350
ht-degree: 1%

---

# Esecuzione di chiamate API DCS server-to-server {#making-server-to-server-dcs-api-calls}

Le chiamate richiedono il nome host del server DCS regionale e l’ID utente. Se non disponi degli ID utente e area geografica richiesti, consulta [Ottenere ID utente e aree geografiche da una risposta DCS](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) e/o [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Una volta che disponi di ID utente e di regione, puoi effettuare chiamate server-to-server al DCS. Fai riferimento a questa sezione per sintassi ed esempi.

>[!NOTE]
>
>Nel codice e negli esempi, *corsivo* rappresenta un segnaposto variabile. Sostituire un valore reale per il segnaposto quando si effettua una chiamata server-to-server a [!DNL DCS].

## Sintassi e esempio di chiamata {#call-syntax-example}

Una richiesta di base da server a server che invia dati a [!DNL DCS] utilizza la sintassi mostrata di seguito.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Alias di dominio assegnato da <span class="keyword"> Audience Manager</span> (esempio: <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Il dominio di destinazione, che è sempre <i><code> demdex.net</code></i>. Vedere <a href="../../../reference/demdex-calls.md"> Informazioni sulle chiamate al dominio demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Il parametro host dell'intestazione http che mostra il nome del server DCS<span class="wintitle"> regionale </span>. Il nome host è associato a un ID di regione, ed è per questo che ne hai bisogno prima di effettuare questi tipi di chiamate. Vedi <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> ID regioni DCS, posizioni e nomi host</a>. </p> </td> 
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
   <td colname="col2"> <p>Questa è la chiave ID utente univoca che contiene il valore ID utente di <span class="keyword"> Audience Manager</span> in una coppia chiave-valore. </p> <p>Utilizza <code><i>d_uuid</i></code> se trasmetti l'ID utente di <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Questa è la chiave ID utente univoca che contiene il valore ID utente di <span class="keyword"> Experience Cloud</span> in una coppia chiave-valore. Vedi anche <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Ottenere l'ID utente dal cookie del servizio ID</a>. </p> <p>Utilizza <i><code> d_mid</code></i> se trasmetti un ID <span class="keyword"> Experience Cloud</span> acquisito dal servizio ID <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parametri di risposta facoltativi. </p> <p> Nessuna di queste è necessaria per inviare dati al DCS <span class="wintitle"></span>. Tuttavia, se desideri che il DCS<span class="wintitle"> di </span> restituisca una risposta, devi includere <i><code> d_rtbd=json</code></i> nella richiesta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risposta di esempio {#sample-response}

Vedi [Ricevi dati dal DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
