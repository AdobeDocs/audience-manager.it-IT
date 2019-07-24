---
description: Le opzioni Regola di unione consentono di controllare il tipo di dati utilizzati da Audience Manager per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del dispositivo Collegamento profilo, da Adobe Experience Cloud Device Co-op e/o da altri fornitori di grafici dispositivi di terze parti integrati con Audience Manager. Potete creare un massimo di 3 regole di unione profilo.
seo-description: Le opzioni Regola di unione consentono di controllare il tipo di dati utilizzati da Audience Manager per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del dispositivo Collegamento profilo, da Adobe Experience Cloud Device Co-op e/o da altri fornitori di grafici dispositivi di terze parti integrati con Audience Manager. Potete creare un massimo di 3 regole di unione profilo.
seo-title: Opzioni regola unione profilo definite
solution: Audience Manager
title: Opzioni regola unione profilo definite
uuid: 225 eeaf 7-45 e 9-4 f 21-9360-d 80 a 9 f 90520 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

Le opzioni Regola di unione consentono di controllare il tipo di dati utilizzati da Audience Manager per la segmentazione. A merge rule can include device profiles mapped by the [!UICONTROL Profile Link] device graph, the [!UICONTROL Adobe Experience Cloud Device Co-op], and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 3 [!UICONTROL Profile Merge Rules].

You build a [!UICONTROL Profile Merge Rule] by making a selection from these options:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> Opzioni autenticate</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> Opzioni profilo autenticate</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Opzioni dispositivo</a> </li>
</ul>

## Authenticated Options {#auth-options}

The [!UICONTROL Authenticated Options] let you select un-authenticated and authenticated users and leverage their cross-device profile for segmentation. Queste opzioni consentono di identificare e raggiungere utenti specifici su un dispositivo condiviso. For more information on anonymous and authenticated users, see [Visitor Authentication States in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione autenticata </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nessun profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use data collected from authenticated users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo autenticato corrente</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read and write data to the authenticated profile if a visitor has logged in to your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ultimo profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read data from the authenticated profile of the user who last logged in on the device. </p> <p>When selected, <span class="keyword"> Audience Manager</span> will not write new trait data to the authenticated profile if the user is anonymous. All'autenticazione, nuovi dati di caratteristica vengono scritti sul profilo autenticato dell'utente. </p> </td>
  </tr> 
 </tbody>
</table>

## Authenticated Profile Options {#profile-options}

The [!UICONTROL Authenticated Profile Options] lists your cross-device data sources. These options use the names you provided when you created a cross-device data source (see [Create a Cross-Device Data Source](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). Puoi selezionare fino a 3 origini dati cross-device da utilizzare con ciascuna regola di profilo. The [!UICONTROL Authenticated Profile Options] are available when you choose **[!UICONTROL Current Authenticated Profile]** or **[!UICONTROL Last Authenticated Profile]**.

## Device Options {#device-options}

The [!UICONTROL Device Options] let you select the type of *`device profile`* used by a [!UICONTROL Profile Merge Rule]. Un profilo dispositivo è composto da caratteristiche raccolte dagli utenti mentre vengono visualizzate in modo anonimo. Come minimo, una regola di unione profilo include un'opzione autenticata e un'opzione dispositivo.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione dispositivo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nessun profilo dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use the traits contained in the anonymous profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo dispositivo corrente</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to use the anonymous device profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Collegamento profilo Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read the profiles from the current device and the last 3 devices that the user has authenticated from. This device graph is built on your own, first-party data in <span class="keyword"> Audience Manager</span>. È ideale per i clienti che hanno un livello elevato di autenticazione nelle loro proprietà digitali. The <span class="wintitle"> Profile Link</span> device graph is updated in real time. This option is available when you select <b><span class="uicontrol"> Current Authenticated Profile</span></b> or <b><span class="uicontrol"> Last Authenticated Profile</span></b>. When using this option, you can only choose a single authenticated profile (<span class="keyword"> Audience Manager</span> automatically grays out the others). See also, <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Profile Link Device Graph Use Cases</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to merge device profiles using the links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> è una cooperativa digitale in cui i clienti partecipanti condividono informazioni sul collegamento dei dispositivi. <span class="keyword"> Device Co-op</span> elabora questi dati in un grafico <span class="term"> del dispositivo</span>. Un grafico dispositivo collega i dispositivi insieme ai cluster di dispositivi. These links are built from <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistic and deterministic data</a>. I cluster rappresentano un gruppo di dispositivi utilizzati da una persona sconosciuta. <span class="keyword">Device Co-op</span> condivide i cluster tra i suoi membri, aiutandoli a fornire ai loro clienti esperienze cross-device coerenti e di valore. </p> <p> For more information about the <span class="wintitle"> Device Co-op</span>, see the: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Panoramica di Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Requisiti di iscrizione</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Device Graph: Processi interni e output</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Grafici di Audience Manager e dispositivo esterno</a> (download PDF). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opzioni grafico dispositivo di terze parti</b> (Persona e famiglia) </p> </td>
   <td colname="col2"> <p>Queste opzioni consentono di creare regole di unione basate sulla tecnologia grafico dei dispositivi fornita da un fornitore di terze parti. Un grafico dispositivo di terze parti fornisce: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dati probabilistici e/o deterministici. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dati a livello di persona o di famiglia. </li> 
     </ul> </p> <p>To use these options, you must be a customer of a device graph provides who is already integrated with <span class="keyword"> Audience Manager</span>. Per ulteriori informazioni o per iniziare, contatta il tuo account manager. </p> <p>Consultate anche &lt; a href = "../../features/profile-merge-rules/external-graph-use-instances. md. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Domande frequenti sulle regole di unione profilo](../../faq/faq-profile-merge.md)

