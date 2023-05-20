---
description: Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai server di raccolta dati (DCS, Data Collection Servers). Queste informazioni possono essere utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: Attributi supportati per le chiamate API DCS
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_ct=1, d_ct=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: e10211057a87622340fd2c61737c7c7a45c0e99c
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 4%

---

# Attributi supportati per [!DNL DCS] [!DNL API] Chiamate {#supported-attributes-for-dcs-api-calls}

Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere al [!UICONTROL Data Collection Servers] ([!DNL DCS]). Queste informazioni possono essere utili per formattare [!DNL DCS] e comprendere i parametri restituiti dal sistema.

## Prefissi attributo {#attribute-prefixes}

Il [!DNL DCS] si basa su prefissi specifici aggiunti alle chiavi nelle coppie chiave-valore per classificare il tipo di dati che stai trasmettendo.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefisso chiave </th> 
   <th colname="col2" class="entry"> Riservato a </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Attributi definiti dal cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> attributi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>Dati di intestazione HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Attributi privati definiti dal cliente. </p> <p> Il DCS accetta i tuoi dati privati quando la chiave ha un <code> p_</code> prefisso. I dati privati vengono utilizzati per la valutazione delle caratteristiche, ma non verranno registrati o memorizzati nel nostro sistema. Ad esempio, supponiamo che tu abbia una caratteristica definita come <code> customers = p_age&lt;25</code> e si passa <code> p_age=23</code> in una chiamata evento. Date queste condizioni, l’utente che soddisfa i criteri di qualifica basati sull’età è idoneo per la caratteristica, ma la coppia chiave-valore viene rilasciata dopo <span class="keyword"> Audience Manager</span> riceve la richiesta e non è registrato. </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] Attributi {#d-attributes}

Tutti questi elementi sono facoltativi, a meno che non si desideri una risposta da [!DNL DCS]. Se vuoi [!DNL DCS] per restituire una risposta, `d_rtbd=json` è obbligatorio.

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
   <td colname="col2"> <p>Utilizzato per identificare il chiamante che effettua la chiamata al <span class="wintitle"> DCS</span> API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Specifica una funzione JavaScript che si desidera eseguire utilizzando <span class="wintitle"> DCS</span> response come parametro della funzione di callback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contiene una o più coppie di ID provider dati (<code> DPID</code>) e ID utente del provider di dati (<code> DPUUID</code>) assegnato da <span class="keyword"> Audience Manager</span>. Se utilizzi più coppie di <code> DPID</code>s e <code> DPUUID</code>s, separa ogni coppia con il carattere non stampabile <code> %01</code>. Ad esempio: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> sostituisce <code> d_dpid</code> e <code> d_dpuuid</code>, che sono obsoleti ma sono ancora supportati. Consulta <a href="../../../reference/cid.md">CID Replaces DPID and DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Contiene un codice di integrazione e un ID utente univoco associato in una singola coppia chiave-valore. </p> <p><code> d_cid_ic</code> sostituisce <code> d_dpid</code> e <code> d_dpuuid</code>, che sono obsoleti ma sono ancora supportati. Consulta <a href="../../../reference/cid.md">CID Replaces DPID and DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Disattiva l’utilizzo di cookie di terze parti al fine di rispettare le normative a tutela dei minori. Questo parametro viene impostato dinamicamente dal servizio Adobe Adobe Experience Platform Identity e dipende dal <code> idSyncDisable3rdPartySyncing</code> configurazione. Consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html" format="https" scope="external"> Supporto per COPPA nel servizio Adobe Experience Platform Identity</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Facoltativo. Abilitato su richiesta del cliente. Contatta il tuo consulente Adobe Audience Manager o l'Assistenza clienti. </p> <p>Indica che le caratteristiche e i segmenti devono essere restituiti all’interno del <code> JSON</code> risposta. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> restituisce <a href="../../../reference/ids-in-aam.md"> ID segmento legacy</a> per i segmenti. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> restituisce gli ID segmento per i segmenti. </p> </li>
     </ul> </p> <p>Un esempio di risposta potrebbe essere simile a quello riportato di seguito: </p> <p>
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
   <td colname="col2"> <p>Obsoleto. Consulta <code> d_cid</code> e <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. Consulta <code> d_cid</code> e <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>Restituisce i dati di destinazione dell’URL nel <code> JSON</code> risposta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> è un attributo riservato, utilizzato nell’integrazione tra Adobe Analytics e Audience Manager. </p> <p>Consigliamo di non creare caratteristiche che utilizzano attributi riservati. Adobe può modificare gli attributi riservati in qualsiasi momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Indica il <code> JSON</code> versione da utilizzare nella risposta. In genere, è necessario impostare questa opzione su <code> d_jsonv=1</code>. Impostazione <code> d_jsonv=0</code> disabilita le sincronizzazioni ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Specifica l'ID Experience Cloud impostato e utilizzato dal <span class="keyword"> Experience Cloud</span> Servizio ID. Per ulteriori informazioni sull’ECID, consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e il servizio Experience Cloud Identity</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>ID spazio dei nomi. Indica quale contenitore JavaScript viene utilizzato. Utilizzato da <span class="wintitle"> DIL</span> a per la sincronizzazione id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Consente ad Audience Manager di distinguere le richieste da dispositivi mobili da quelle da desktop. I valori supportati includono: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Obsoleto. <code> d_rs</code> è un attributo riservato, utilizzato nell’integrazione legacy tra <span class="keyword"> Adobe Analytics</span> e <span class="keyword"> Audience Manager</span>. </p> <p>Consigliamo di non creare caratteristiche che utilizzano attributi riservati. Adobe può modificare gli attributi riservati in qualsiasi momento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Obbligatorio se si desidera <code> JSON</code> risposta dal <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Se si omette questo, la <span class="wintitle"> DCS</span> restituisce un pixel nell'intestazione. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Se includi questo, il <span class="wintitle"> DCS</span> restituisce un <code> JSON</code> nel corpo della risposta. Vedi l’esempio seguente. La tua risposta potrebbe essere più complessa. </li> 
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
   <td colname="col2"> <p><code> SID</code> sta per <span class="term"> ID punteggio</span>. Questo è un ID univoco per una caratteristica o un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Passa un'origine dati per la valutazione delle caratteristiche. Vengono valutate solo le caratteristiche di questa origine dati. </p> <p>Ad esempio, supponiamo che tu abbia: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Caratteristica T1</b> con: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Regola di caratteristiche: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Origine dati (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Codice di integrazione DPID: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Caratteristica T2</b> con: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Regola di caratteristiche: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Origine dati (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Codice integrazione DPID: ic2 </li> 
     </ul> </p> <p>In una chiamata di esempio, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, viene restituita solo la caratteristica T1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>Lo scopo è identico al <code> d_tdpid</code> parametro descritto sopra. Tuttavia, in questo caso, l’origine dati viene passata utilizzando il codice di integrazione. </p> <p>Mantenendo le caratteristiche descritte in precedenza, considera la chiamata di esempio: </p> <p>Per <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>, viene restituita solo la caratteristica T2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>ID utente univoco. Identifica un visitatore quando questo valore non è disponibile da un cookie. </p> </td> 
  </tr>
 </tbody>
</table>

## h_ Attributes

Queste intestazioni contengono informazioni come richieste di dati e risposte in una chiamata HTTP.

| Attributo | Descrizione |
| --- | --- | 
| `h_host` | È impostato sul nome host specifico del client per la raccolta dati. Viene visualizzato come `host name .demdex.net`. Consulta [Understanding Calls to the Demdex Domain](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=en). |
| `h_user-agent` | Imposta su `User-Agent` valore intestazione. |
| `h_accept-language` | Imposta su  `Accept-Language`  valore intestazione. |
| `h_referer` | Imposta su `Referer` valore intestazione. |
| `h_referrer` | Imposta su `Referrer` valore intestazione. |
| `h_date` | Imposta su `Date` valore intestazione. |