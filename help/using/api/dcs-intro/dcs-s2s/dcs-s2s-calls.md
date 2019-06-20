---
seo-title: Effettuare chiamate API Server-to-Server DCS
solution: Audience Manager
title: Effettuare chiamate API Server-to-Server DCS
uuid: bdfe 3430-e 27 f -4 a 5 c -88 d 9-ae 164 d 28 f 601
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Effettuare chiamate API Server-to-Server DCS {#making-server-to-server-dcs-api-calls}

Le chiamate richiedono il nome host del server DCS regionale e l&#39;ID utente. Se non disponi degli ID utente e di regione richiesti, consulta [Ottenere ID utente e regioni da DCS Response](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) e/o [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Se hai ID di utenti e regione, puoi effettuare chiamate server-to-server al DCS. Fate riferimento a questa sezione per sintassi ed esempi.

>[!NOTE]
>
>Nel codice ed esempi, *il corsivo* rappresenta un segnaposto variabile. Sostituire un valore reale per il segnaposto quando si effettuano chiamate server-to-server al [!UICONTROL DCS].

## Chiama sintassi e esempio {#call-syntax-example}

Una richiesta server-to-server di base che invia dati alla [!UICONTROL DCS] sintassi mostrata di seguito.

<pre><code>" Host:<i>domain alias</i>. demdex. net "" https://DCS<i>host name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>.</code>
</pre>

Un esempio di chiamata è simile all&#39;esempio seguente.

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
   <td colname="col1"> <p><code><i>domain alias</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Questa parte della chiamata contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">L'alias di dominio assegnato da <span class="keyword"> Audience Manager</span> (ad esempio <i><code> , my_ domain. demdex. net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Il dominio di destinazione, che è sempre <i><code> demdex. net</code></i>. Vedi <a href="../../../reference/demdex-calls.md">Informazioni sulle chiamate al dominio demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>DCS host name</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Il parametro host dell'intestazione http che mostra il nome del server <span class="wintitle"> DCS</span> regionale. Il nome host è associato a un ID di regione, per questo è necessario prima di effettuare tali chiamate. Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Questa parte della chiamata: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la chiamata come chiamata evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definisce l'inizio della stringa URL che contiene i dati da inviare al DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ uuid = <i>ID utente Audience Manager</i></code> </p> </td> 
   <td colname="col2"> <p>Questa è la chiave ID utente univoca che contiene il <span class="keyword"> valore ID</span> utente Audience Manager in una coppia chiave-valore. </p> <p>Utilizza <code><i>d_ uuid</i></code> se stai trasferendo l'ID utente <span class="keyword"> di Audience Manager</span> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid =<i>ID utente Experience Cloud</i></code> </p> </td> 
   <td colname="col2"> <p>Questa è la chiave ID utente univoca che contiene il <span class="keyword"> valore ID</span> utente Experience Cloud in una coppia chiave-valore. Vedi anche <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Ottenere l'ID utente dal cookie del servizio ID</a>. </p> <p>Utilizza <i><code> d_ mid</code></i> se stai trasferendo un <span class="keyword"> Experience Cloud</span> ID acquisito dal <span class="keyword"> servizio Experience Cloud</span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb =<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Parametri di risposta facoltativi. </p> <p> Nessuno di questi deve inviare dati al <span class="wintitle"> DCS</span>. Tuttavia, se desiderate che il <span class="wintitle"> DCS</span> restituisca una risposta, dovete includere <i><code> d_ rtbd = json</code></i> nella richiesta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risposta di esempio {#sample-response}

Consultate [Ricezione dei dati dal DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
