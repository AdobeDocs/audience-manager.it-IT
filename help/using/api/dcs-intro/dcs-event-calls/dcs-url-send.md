---
description: Per informazioni su come effettuare chiamate /event al DCS, fate clic qui. Questa sezione include informazioni sulla sintassi delle chiamate, sui parametri, sulla formattazione e su un esempio di richiesta.
seo-description: Per informazioni su come effettuare chiamate /event al DCS, fate clic qui. Questa sezione include informazioni sulla sintassi delle chiamate, sui parametri, sulla formattazione e su un esempio di richiesta.
seo-title: Inviare dati al DCS
solution: Audience Manager
title: Inviare dati al DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 2%

---


# Inviare dati al DCS {#send-data-to-the-dcs}

Per informazioni su come effettuare `/event` chiamate al [!DNL DCS]. Questa sezione include informazioni sulla sintassi delle chiamate, sui parametri, sulla formattazione e su un esempio di richiesta.

>[!NOTE]
>
>Nel codice e negli esempi, il *corsivo* rappresenta un segnaposto variabile. Sostituire un valore reale per il segnaposto quando si inviano dati all&#39; [!DNL DCS] utente con questo metodo.

## Sintassi chiamata {#dcs-call-syntax}

Una `URL` stringa di base che invia dati al [!DNL DCS] gruppo utilizza la sintassi indicata di seguito.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>È inoltre possibile inviare dati al [!DNL DCS] sito utilizzando il `POST` metodo. La sintassi della chiamata è descritta in Metodi [API](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)DCS.

## Parametri di chiamata {#dcs-call-parameters}

La tabella seguente definisce i componenti di base di una semplice [!DNL DCS] chiamata.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">L’alias di dominio assegnato da <span class="keyword"> Audience Manager</span> (ad esempio, <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Il dominio di destinazione, che è sempre <code> demdex.net</code>. Vedi <a href="../../../reference/demdex-calls.md">Informazioni sulle chiamate al dominio demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Questa parte dell'invito: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la chiamata come chiamata di evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definisce l'inizio della stringa URL che contiene i dati da inviare al <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Identificatore univoco nella coppia chiave-valore. </p> <p>Queste coppie chiave-valore utilizzano un prefisso specifico per identificare il tipo di dati che state inviando al <span class="wintitle"> DCS</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Un valore variabile che appartiene a un insieme definito da una chiave nella coppia chiave-valore. </p> <p>Quando si utilizzano i valori: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Racchiudere i dati stringa tra virgolette (ad esempio, <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">È possibile passare più chiavi in un singolo valore (ad esempio, <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formattazione delle coppie chiave-valore nelle chiamate</a>DCS. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parametri di risposta facoltativi. </p> <p> Nessuno di questi è richiesto per inviare dati al <span class="wintitle"> DCS</span>. Tuttavia, se desiderate che il <span class="wintitle"> DCS</span> restituisca una risposta, dovete includere <code> d_rtbd=json</code> nella richiesta. </p> <p>Vedere <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Coppie chiave-valore definite</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Chiamata di esempio {#dcs-sample-call}

Questo esempio mostra la società fittizia che [!DNL Acme, Inc.] invia i dati al [!DNL DCS] tramite una [!DNL HTTP] chiamata. Questa chiamata include i parametri facoltativi `d_dst=1`, `d_rtbd=json`e `d_cb=callback`. Ciò indica che [!DNL Acme] si desidera ricevere una [!DNL JSON] risposta dall&#39;utente [!DNL DCS] con una funzione call back. Ricordate, questo è solo un esempio. Non tagliare e incollare questo codice.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Passaggi successivi {#dcs-next-steps}

Ora che hai familiarità con l&#39;invio dei dati al [!DNL DCS]sito, è ora di vedere come recuperare i dati e analizzare le informazioni. Consultate [Ricevere dati dal DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Spiegazione delle coppie chiave-valore](../../../reference/key-value-pairs-explained.md)

