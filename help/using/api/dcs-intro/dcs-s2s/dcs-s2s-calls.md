---
seo-title: Esecuzione di chiamate API DCS da server a server
solution: Audience Manager
title: Esecuzione di chiamate API DCS da server a server
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 5%

---


# Esecuzione di chiamate API DCS da server a server {#making-server-to-server-dcs-api-calls}

Le chiamate richiedono il nome host del server DCS regionale e l&#39;ID utente. Se non disponete degli ID utente e regione richiesti, consultate [Ottenere ID utente e regioni da una risposta](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) DCS e/o da [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Una volta ricevuti gli ID utente e regione, puoi effettuare chiamate server-to-server al DCS. Fare riferimento a questa sezione per sintassi ed esempi.

>[!NOTE]
>
>Nel codice e negli esempi, il *corsivo* rappresenta un segnaposto variabile. Sostituire un valore reale per il segnaposto quando si effettuano chiamate server-to-server al [!DNL DCS].

## Sintassi chiamata ed esempio {#call-syntax-example}

Una richiesta server-to-server di base che invia dati al server [!DNL DCS] utilizza la sintassi indicata di seguito.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Una chiamata di esempio ha un aspetto simile al seguente esempio.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">L’alias di dominio assegnato da <span class="keyword"> Audience Manager</span> (ad esempio, <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Il dominio di destinazione, che è sempre <i><code> demdex.net</code></i>. Vedi <a href="../../../reference/demdex-calls.md">Informazioni sulle chiamate al dominio demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Il parametro host dell'intestazione http che mostra il nome del server <span class="wintitle"> DCS</span> regionale. Il nome host è associato a un ID di regione, motivo per cui questo è necessario prima di effettuare questi tipi di chiamate. Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Questa parte dell'invito: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la chiamata come chiamata di evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definisce l'inizio della stringa URL che contiene i dati da inviare al DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Si tratta della chiave ID utente univoca che contiene il valore ID utente <span class="keyword"> Audience Manager</span> in una coppia chiave-valore. </p> <p>Utilizzate <code><i>d_uuid</i></code> se trasmettete l'ID utente <span class="keyword"> Audience Manager</span> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Si tratta della chiave ID utente univoca che contiene il valore ID utente <span class="keyword"> Experience Cloud</span> in una coppia chiave-valore. Vedi anche <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Ottieni l’ID utente dal cookie</a>del servizio ID. </p> <p>Utilizzate <i><code> d_mid</code></i> se trasmettete un <span class="keyword"> ID Experience Cloud</span>  acquisito dal servizio <span class="keyword">  Experience Cloud</span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parametri di risposta facoltativi. </p> <p> Nessuno di questi è richiesto per inviare dati al <span class="wintitle"> DCS</span>. Tuttavia, se desiderate che il <span class="wintitle"> DCS</span> restituisca una risposta, dovete includere <i><code> d_rtbd=json</code></i> nella richiesta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risposta di esempio {#sample-response}

Consultate [Ricevere dati dal DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
