---
description: Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai Data Collection Servers (DCS). Queste informazioni sono utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
seo-description: Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai Data Collection Servers (DCS). Queste informazioni sono utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
seo-title: Attributi supportati per le chiamate API DCS
solution: Audience Manager
title: Attributi supportati per le chiamate API DCS
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Attributi supportati per le chiamate API DCS {#supported-attributes-for-dcs-api-calls}

Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che potete trasmettere al [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]). Queste informazioni sono utili per formattare [!UICONTROL DCS] le richieste e comprendere i parametri restituiti dal sistema.

## Prefissi di attributi {#attribute-prefixes}

Per classificare il tipo di dati che si sta trasmettendo, le chiavi [!UICONTROL DCS] si basano su specifici prefissi aggiunti alle chiavi in coppie chiave-valore.

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
   <td colname="col2"> <p>Dati dell’intestazione HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Attributi privati definiti dal cliente. </p> <p> Il DCS accetta dati personali e privati quando la chiave ha un <code> p_</code> prefisso. I dati privati vengono utilizzati per la valutazione delle caratteristiche, ma non vengono registrati o memorizzati nel nostro sistema. Ad esempio, consente di specificare che la caratteristica è definita come <code> customers = p_age&lt;25</code> e di passare <code> p_age=23</code> in una chiamata all'evento. Date queste condizioni, l'utente che soddisfa i criteri di qualifica basati sull'età si qualifica per la caratteristica, ma la coppia chiave-valore viene eliminata dopo che <span class="keyword"> Audience Manager</span> riceve la richiesta e non viene registrato. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_Attributes {#d-attributes}

Tutte queste opzioni sono facoltative, a meno che non desideriate una risposta da parte del [!UICONTROL DCS]. Se si desidera che [!UICONTROL DCS] restituisca una risposta, `d_rtbd=json` è necessario.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attributo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>Utilizzato per identificare il chiamante che sta effettuando la chiamata all'API <span class="wintitle"> DCS</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Specifica una funzione JavaScript da eseguire utilizzando la risposta <span class="wintitle"> DCS</span> come parametro di funzione della funzione di callback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contiene una o più coppie di ID provider di dati (<code> DPID</code>) e ID utente provider di dati (<code> DPUUID</code>) assegnati da <span class="keyword"> Audience Manager</span>. Se utilizzate più coppie di <code> DPID</code>s e <code> DPUUID</code>s, separate ogni coppia con il carattere non stampabile <code> %01</code>. Ad esempio: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> sostituisce <code> d_dpid</code> e <code> d_dpuuid</code>, che sono obsoleti ma sono ancora supportati. Consultate <a href="../../../reference/cid.md">CID sostituisce DPID e DPUUID</a> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Contiene un codice di integrazione e un ID utente univoco associato in una coppia chiave-valore singola. </p> <p><code> d_cid_ic</code> sostituisce <code> d_dpid</code> e <code> d_dpuuid</code>, che sono obsoleti ma sono ancora supportati. Consultate <a href="../../../reference/cid.md">CID sostituisce DPID e DPUUID</a> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Disabilitare l'uso di cookie di terze parti per conformarsi alle norme sulla protezione dei bambini. Questo parametro viene impostato dinamicamente da Adobe Experience Platform Identity Service e dipende dalla <code> idSyncDisable3rdPartySyncing</code> configurazione. Consulta <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/coppa.html" format="https" scope="external"> Supporto COPPA nel servizio</a>Adobe Experience Platform Identity. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Facoltativo. Abilitato su richiesta del cliente. Contatta il tuo consulente Adobe Audience Manager o l'Assistenza clienti. </p> <p>Indica che le caratteristiche e i segmenti devono essere restituiti all'interno della <code> JSON</code> risposta. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> restituisce ID segmento <a href="../../../reference/ids-in-aam.md"> legacy</a> per i segmenti. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> restituisce gli ID del segmento per i segmenti. </p> </li>
     </ul> </p> <p>Esempio di risposta: </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Vedere <code> d_cid</code> e <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Vedere <code> d_cid</code> e <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>Restituisce i dati di destinazione URL nella <code> JSON</code> risposta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> è un attributo riservato, utilizzato nell'integrazione tra Adobe Analytics e Audience Manager. </p> <p>È consigliabile non creare caratteristiche che utilizzano attributi riservati. Adobe può modificare gli attributi riservati in qualsiasi momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Indica la <code> JSON</code> versione da utilizzare nella risposta. In genere, è necessario impostare questo valore su <code> d_jsonv=1</code>. L’impostazione <code> d_jsonv=0</code> disattiva le sincronizzazioni ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Specifica l’Experience Cloud ID impostato e utilizzato dal servizio <span class="keyword"> Experience Cloud</span> ID. Per ulteriori informazioni sull’ECID, vedi <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e il servizio</a>Experience Cloud Identity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>Nome ID spazio. Indica il contenitore JavaScript utilizzato. Usato da <span class="wintitle"> DIL</span> per la sincronizzazione ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Consente a Audience Manager di distinguere le richieste per dispositivi mobili dalle richieste desktop. I valori supportati includono: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. <code> d_rs</code> è un attributo riservato, utilizzato nell'integrazione legacy tra <span class="keyword"> Adobe Analytics</span> e <span class="keyword"> Audience Manager</span>. </p> <p>È consigliabile non creare caratteristiche che utilizzano attributi riservati. Adobe può modificare gli attributi riservati in qualsiasi momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Obbligatorio se si desidera una <code> JSON</code> risposta dal <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Se si omette questa opzione, il <span class="wintitle"> DCS</span> restituisce un pixel nell’intestazione. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Se includete questo, il <span class="wintitle"> DCS</span> restituisce un <code> JSON</code> oggetto nel corpo della risposta. Vedere l'esempio seguente. La vostra risposta potrebbe essere più complessa. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> sta per ID <span class="term"></span>punteggio. Si tratta di un ID univoco per una caratteristica o un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Passa un'origine dati per la valutazione delle caratteristiche. Vengono valutate solo le caratteristiche di questa origine dati. </p> <p>Ad esempio, supponiamo che: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Caratteristica T1</b> con: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Regola caratteristica: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Origine dati (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Codice di integrazione DPID: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Caratteristica T2</b> con: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Regola caratteristica: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Origine dati (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Codice di integrazione DPID: ic2 </li> 
     </ul> </p> <p>In una chiamata di esempio <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, viene restituita solo la caratteristica T1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>Lo scopo è identico al <code> d_tdpid</code> parametro descritto in precedenza. Tuttavia, in questo caso, l'origine dati viene passata utilizzando il codice di integrazione. </p> <p>Tenendo le caratteristiche descritte sopra, prendete in considerazione la chiamata di esempio: </p> <p>Ad <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>esempio, viene restituita solo la caratteristica T2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>ID utente univoco. Identifica un visitatore quando questo valore non è disponibile da un cookie. </p> </td> 
  </tr>
 </tbody>
</table>