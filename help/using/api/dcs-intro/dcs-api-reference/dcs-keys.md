---
description: Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai server di raccolta dati (DCS). Queste informazioni possono essere utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
seo-description: Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai server di raccolta dati (DCS). Queste informazioni possono essere utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
seo-title: Attributi supportati per chiamate API DCS
solution: Audience Manager
title: Attributi supportati per chiamate API DCS
uuid: 0 b 98 ed 11-314 b -4500-afde -45 a 041112150
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Attributi supportati per chiamate API DCS {#supported-attributes-for-dcs-api-calls}

Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere a [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]). Queste informazioni possono essere utili per formattare [!UICONTROL DCS] le richieste e comprendere i parametri restituiti dal sistema.

## Prefissi attributi {#attribute-prefixes}

I [!UICONTROL DCS] prerequisiti richiedono prefissi specifici aggiunti alle chiavi in coppie chiave-valore per classificare il tipo di dati in fase di trasferimento.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefisso chiave </th> 
   <th colname="col2" class="entry"> Riservato per </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Attributi definiti dal cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Attributi di Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>Dati dell'intestazione HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Attributi privati definiti dal cliente. </p> <p> Il DCS accetta i dati privati quando la chiave ha un <code> p_</code> prefix. I dati privati vengono utilizzati per la valutazione delle caratteristiche, ma non saranno registrati o memorizzati nel sistema. Ad esempio, supponiamo che sia presente una caratteristica definita <code> come customers = p_ age &lt; 25</code> e passate <code> in p_ age = 23</code> in una chiamata dell'evento. Considerate queste condizioni, l'utente che soddisfa i criteri di qualificazione basati su age è idoneo per la caratteristica, ma la coppia chiave-valore viene rilasciata dopo <span class="keyword"> che Audience Manager</span> riceve la richiesta e non viene registrato. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_ Attributes {#d-attributes}

Tutti questi elementi sono facoltativi, a meno che non desideriate una risposta dall &#39; [!UICONTROL DCS]. Se desiderate [!UICONTROL DCS] restituire una risposta, è `d_rtbd=json` necessario.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attributo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_ caller</code> </p> </td> 
   <td colname="col2"> <p>Utilizzato per identificare il chiamante che sta effettuando la chiamata all'API <span class="wintitle"> DCS</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Specifica una funzione javascript da eseguire utilizzando la <span class="wintitle"> risposta DCS</span> come parametro di funzione della funzione callback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contiene una o più coppie di ID di fornitori di dati (<code> DPID</code>) e ID utente (<code> DPUUID</code>) assegnati da <span class="keyword"> Audience Manager</span>. Se utilizzate più coppie di <code> DPID</code>e <code> dpuuid</code>, separate ciascuna coppia con il carattere non stampabile <code> % 01</code>. Ad esempio: <code><i>DPID</i>% 01<i>DPUUUID</i></code>. </p> <p><code> d_ cid</code> sostituisce <code> d_ dpid</code> e <code> d_ dpuuid</code>, che sono obsoleti ma continuano a essere supportati. Consultate <a href="../../../reference/cid.md">CID sostituisce DPID e DPUUID</a> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cid_ ic</code> </p> </td> 
   <td colname="col2"> <p>Contiene un codice di integrazione e un ID utente univoco associato in una singola coppia chiave-valore. </p> <p><code> d_ cid_ ic</code> sostituisce <code> d_ dpid</code> e <code> d_ dpuuid</code>, che sono obsoleti ma continuano a essere supportati. Consultate <a href="../../../reference/cid.md">CID sostituisce DPID e DPUUID</a> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ coppa</code> </p> </td> 
   <td colname="col2"> <p>Disattivazione dell'utilizzo dei cookie di terze parti per conformarsi alle normative sulla protezione secondarie. Questo parametro viene impostato in modo dinamico dal servizio Adobe Experience Cloud ID e dipende dalla <code> configurazione idsyncdisable 3 rdpartysyncing</code> . Consulta <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_coppa.html" format="https" scope="external"> Supporto COPPA nel servizio Experience Cloud ID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cts = 1</code> </p> <p><code> d_ cts = 2</code> </p> </td> 
   <td colname="col2"> <p>Facoltativo. Abilitata sulla richiesta del cliente. Contatta il tuo consulente Adobe Audience Manager o l'Assistenza clienti. </p> <p>Indica che le caratteristiche e i segmenti devono essere restituiti all'interno della <code> risposta JSON</code> . </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_ cts = 1</code> restituisce <a href="../../../reference/ids-in-aam.md"> ID segmento precedenti</a> per i segmenti. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_ cts = 2</code> restituisce ID segmento per i segmenti. </p> </li>
     </ul> </p> <p>Un esempio di risposta potrebbe essere simile a quello di seguito: </p> <p>
     <code class="syntax javascript">{"stuff": [], "uuid": " 07955261652886032950143702505894272138 "," dcs_ region ": 7, "traits": [420020, 5421506], "segments": [984263, 985264], "tid": " ss 3 otqpiqp 0 = "} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Vedere <code> d_ cid</code> e <code> d_ cid_ ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Vedere <code> d_ cid</code> e <code> d_ cid_ ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dst = 1</code> </p> </td> 
   <td colname="col2"> <p>Restituisce dati di destinazione URL nella risposta <code> JSON</code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dst_ filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_ dst_ filter</code> è un attributo riservato, usato nell'integrazione tra Adobe Analytics e Audience Manager. </p> <p>Consigliamo di creare caratteristiche che utilizzano attributi riservati. Adobe può modificare gli attributi riservati in qualsiasi momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ jsonv = 1|0</code> </p> </td> 
   <td colname="col2"> <p>Indica la versione <code> JSON</code> da utilizzare nella risposta. Normalmente, impostate questo valore su <code> d_ jsonv = 1</code>. L'impostazione <code> d_ jsonv = 0</code> disabilita le sincronizzazioni ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Specifica il set Experience Cloud ID impostato e utilizzato <span class="keyword"> dal servizio Experience Cloud</span> ID. Per ulteriori informazioni sull'ECID, vedi <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_cookies.html" format="https" scope="external"> Cookie e Experience Cloud ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ nsid</code> </p> </td> 
   <td colname="col2"> <p>ID spazio. Indica quale contenitore javascript è utilizzato. Utilizzato da <span class="wintitle"> DIL</span> a scopo di sincronizzazione ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ ptfm </code> </p> </td> 
   <td colname="col2"> <p>Consente a Audience Manager di distinguere le richieste mobili dalle richieste desktop. I valori supportati includono: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ rs</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. <code> d_ rs</code> è un attributo riservato, usato nell'integrazione legacy tra <span class="keyword"> Adobe Analytics</span> e <span class="keyword"> Audience Manager</span>. </p> <p>Consigliamo di creare caratteristiche che utilizzano attributi riservati. Adobe può modificare gli attributi riservati in qualsiasi momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ rtbd = json</code> </p> </td> 
   <td colname="col2"> <p>Richiesto se desiderate una risposta <code> JSON</code> dal <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Se si omette questo valore, <span class="wintitle"> il DCS</span> restituisce un pixel nell'intestazione. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">In tal caso, <span class="wintitle"> il DCS</span> restituisce un <code> oggetto JSON</code> nel corpo della risposta. Vedere l'esempio seguente. La risposta potrebbe essere più complessa. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">{"stuff": [], "uuid": " 22920112968019678612904394744954398990 "," dcs_ region ": 7, "tid": " ss 3 otqpiqp 0 = "} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> sta per <span class="term"> ID score</span>. Si tratta di un ID univoco per una caratteristica o un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid</code> </p> </td> 
   <td colname="col2"> <p>Trasmette un'origine dati per la valutazione delle caratteristiche. Vengono valutate solo le caratteristiche provenienti da questa origine dati. </p> <p>Ad esempio, supponiamo che: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Caratteristica T 1</b> con: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Regola caratteristica: "<code> key 1 = = val 1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Origine dati (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Codice integrazione DPID: ic 1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Caratteristica T 2</b> con: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Regola caratteristica: "<code> key 2 = = val 2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Origine dati (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Codice integrazione DPID: ic 2 </li> 
     </ul> </p> <p>In una chiamata di esempio, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, viene restituito solo T 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid_ ic</code> </p> </td> 
   <td colname="col2"> <p>Lo scopo è identico al parametro <code> d_ tdpid</code> descritto in precedenza. In questo caso, tuttavia, l'origine dati viene trasmessa utilizzando il codice di integrazione. </p> <p>Tenendo le caratteristiche descritte qui sopra, prendete in considerazione la chiamata di esempio: </p> <p>Per <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>viene restituito solo T 2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ uuid</code> </p> </td> 
   <td colname="col2"> <p>ID utente univoco. Identifica un visitatore quando questo valore non è disponibile da un cookie. </p> </td> 
  </tr>
 </tbody>
</table>