---
description: Per informazioni sulla creazione di chiamate /event al DCS, iniziate qui. Questa sezione include informazioni sulla sintassi, i parametri, la formattazione e un esempio di richiesta.
seo-description: Per informazioni sulla creazione di chiamate /event al DCS, iniziate qui. Questa sezione include informazioni sulla sintassi, i parametri, la formattazione e un esempio di richiesta.
seo-title: Inviare dati al DCS
solution: Audience Manager
title: Inviare dati al DCS
uuid: 024 e 307 d-bfcb -46 cf-ac 3 a-fc 71 df 0248 fe
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Inviare dati al DCS {#send-data-to-the-dcs}

Per informazioni sull'esecuzione `/event` di chiamate [!UICONTROL DCS]a. Questa sezione include informazioni sulla sintassi, i parametri, la formattazione e un esempio di richiesta.

>[!NOTE]
>
>Nel codice ed esempi, *il corsivo* rappresenta un segnaposto variabile. Sostituire un valore reale per il segnaposto quando si inviano dati a [!UICONTROL DCS] questo metodo.

## Chiama sintassi {#dcs-call-syntax}

Una stringa di base `URL` che invia dati alla [!UICONTROL DCS] sintassi mostrata di seguito.

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>=<i>val 1</i>, &amp;<i>key 2</i>=<i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code></pre>

>[!NOTE]
>
>È inoltre possibile inviare dati a tale [!UICONTROL DCS]`POST` metodo. La sintassi di chiamata è descritta in [Metodi API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Parametri di chiamata {#dcs-call-parameters}

La tabella seguente definisce i componenti di base di una [!UICONTROL DCS] chiamata semplice.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Questa parte della chiamata contiene: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">L'alias di dominio assegnato da <span class="keyword"> Audience Manager</span> (ad esempio <code> , my_ domain. demdex. net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Il dominio di destinazione, che è sempre <code> demdex. net</code>. Vedi <a href="../../../reference/demdex-calls.md">Informazioni sulle chiamate al dominio demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Questa parte della chiamata: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifica la chiamata come chiamata evento. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definisce l'inizio della stringa URL che contiene i dati da inviare al <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Un identificatore univoco nella coppia chiave-valore. </p> <p>Queste coppie chiave-valore utilizzano un prefisso specifico per identificare il tipo di dati che stai inviando al <span class="wintitle"> DCS</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Un valore di variabile che appartiene a un set definito da una chiave nella coppia chiave-valore. </p> <p>Quando si utilizzano i valori: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Cifra i dati stringa tra virgolette doppie ( <code> ad es. age = "41 a 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Potete trasmettere più chiavi con un singolo valore (ad es <i><code>. chiave</i>=<i>val 1, val 2, val 3</i></code></i>). </i></li> 
     </ul> </p> <p>Consultate <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formattazione delle coppie chiave-valore in DCS Chiamate</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb =<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Parametri di risposta facoltativi. </p> <p> Nessuno di questi deve inviare dati al <span class="wintitle"> DCS</span>. Tuttavia, se desiderate che il <span class="wintitle"> DCS</span> restituisca una risposta, dovete includere <code> d_ rtbd = json</code> nella richiesta. </p> <p>Vedere <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> D_ Key-Value Pairs Defined</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Chiamata di esempio {#dcs-sample-call}

Questo esempio mostra l'azienda fittizia [!DNL Acme, Inc.] che invia dati a [!UICONTROL DCS] tramite [!DNL HTTP] una chiamata. Questa chiamata include i parametri `d_dst=1`facoltativi, `d_rtbd=json`e `d_cb=callback`. Queste indicano che [!DNL Acme] desiderano ricevere una [!DNL JSON] risposta dalla funzione [!UICONTROL DCS] di callback di una chiamata. Ricorda, questo è solo un esempio. Non tagliate e incollate questo codice.

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

## Passaggi successivi {#dcs-next-steps}

Ora che hai familiarità con l'invio di dati all ' [!UICONTROL DCS], è ora di vedere come recuperare i dati e analizzarli. Consultate [Ricezione dei dati dal DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORE_ LIKE_ THIS]
>
>* [Coppie chiave-valore spiegate](../../../reference/key-value-pairs-explained.md)

