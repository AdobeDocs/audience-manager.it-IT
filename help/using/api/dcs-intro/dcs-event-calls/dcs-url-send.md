---
description: Inizia qui per informazioni su come effettuare chiamate /event al DCS. Questa sezione include informazioni sulla sintassi delle chiamate, i parametri, la formattazione e un esempio di richiesta.
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: Inviare dati al DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 6%

---

# Inviare dati al DCS {#send-data-to-the-dcs}

Inizia qui per informazioni su come `/event` chiamate a [!DNL DCS]. Questa sezione include informazioni sulla sintassi delle chiamate, i parametri, la formattazione e un esempio di richiesta.

>[!NOTE]
>
>Nel codice e negli esempi, *corsivo* rappresenta un segnaposto variabile. Sostituire un valore reale per il segnaposto quando si inviano dati al [!DNL DCS] con questo metodo.

## Sintassi di chiamata {#dcs-call-syntax}

Una base `URL` stringa che invia dati al [!DNL DCS] utilizza la sintassi mostrata di seguito.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Puoi anche inviare dati a [!DNL DCS] utilizzando `POST` metodo. La sintassi della chiamata è descritta in [Metodi API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Parametri di chiamata {#dcs-call-parameters}

La tabella seguente definisce i componenti di base di un semplice [!DNL DCS] chiamare.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Questa parte della chiamata contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Alias di dominio assegnato da <span class="keyword"> Audience Manager</span> (ad esempio, <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Il dominio di destinazione, che è sempre <code> demdex.net</code>. Consulta <a href="../../../reference/demdex-calls.md">Understanding Calls to the Demdex Domain</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Questa parte dell'invito: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la chiamata come chiamata evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definisce l’inizio della stringa URL contenente i dati da inviare al <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Un identificatore univoco nella coppia chiave-valore. </p> <p>Queste coppie chiave-valore utilizzano un prefisso specifico per identificare il tipo di dati che stai inviando al <span class="wintitle"> DCS</span>. Per ulteriori informazioni, consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attributi supportati per le chiamate API DCS</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Valore di variabile che appartiene a un set definito da una chiave nella coppia chiave-valore. </p> <p>Quando si lavora con i valori: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Racchiudi i dati stringa tra virgolette doppie (ad esempio, <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Puoi trasmettere più chiavi in un singolo valore (ad esempio, <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formattazione delle coppie chiave-valore nelle chiamate DCS</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parametri di risposta facoltativi. </p> <p> Nessuna di queste è necessaria per inviare dati al <span class="wintitle"> DCS</span>. Tuttavia, se desideri <span class="wintitle"> DCS</span> per restituire una risposta, devi includere <code> d_rtbd=json</code> nella tua richiesta. </p> <p>Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Definite coppie chiave-valore</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Chiamata di esempio {#dcs-sample-call}

Questo esempio mostra l’azienda fittizia [!DNL Acme, Inc.] invio di dati a [!DNL DCS] tramite un [!DNL HTTP] chiamare. Questa chiamata include i parametri facoltativi `d_dst=1`, `d_rtbd=json`, e `d_cb=callback`. Ciò indica che [!DNL Acme] desidera ricevere un [!DNL JSON] risposta dal [!DNL DCS] con una funzione di richiamata. Ricordate, questo è solo un esempio. Non tagliare e incollare questo codice.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Passaggi successivi {#dcs-next-steps}

Ora che hai familiarità con l’invio di dati a [!DNL DCS], è ora di scoprire come recuperare i dati da esso e analizzarli. Consulta [Ricevere dati dal DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Spiegazione delle coppie chiave-valore](../../../reference/key-value-pairs-explained.md)

