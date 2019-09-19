---
description: Le opzioni della regola di unione consentono di controllare il tipo di dati utilizzato da Audience Manager per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del dispositivo Collegamento profilo, da Adobe Experience Cloud Device Co-op e/o da altri fornitori di grafici per dispositivi di terze parti integrati con Audience Manager. Potete creare un massimo di 3 regole di unione dei profili.
seo-description: Le opzioni della regola di unione consentono di controllare il tipo di dati utilizzato da Audience Manager per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del dispositivo Collegamento profilo, da Adobe Experience Cloud Device Co-op e/o da altri fornitori di grafici per dispositivi di terze parti integrati con Audience Manager. Potete creare un massimo di 3 regole di unione dei profili.
seo-title: Opzioni Regola di unione profilo definite
solution: Audience Manager
title: Opzioni Regola di unione profilo definite
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

Le opzioni della regola di unione consentono di controllare il tipo di dati utilizzato da Audience Manager per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del [!UICONTROL Profile Link] dispositivo, dai fornitori di grafici [!UICONTROL Adobe Experience Cloud Device Co-op]di dispositivi e/o da altri fornitori di grafici di terze parti integrati con Audience Manager. Potete creare un massimo di 3 [!UICONTROL Profile Merge Rules].

Per creare un [!UICONTROL Profile Merge Rule] oggetto, effettuate una selezione tra le seguenti opzioni:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> Opzioni autenticate</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> Opzioni profilo autenticato</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Opzioni dispositivo</a> </li>
</ul>

## Opzioni autenticate {#auth-options}

Consente di [!UICONTROL Authenticated Options] selezionare utenti autenticati e non autenticati e di sfruttare il loro profilo cross-device per la segmentazione. Queste opzioni consentono di identificare e raggiungere utenti specifici su un dispositivo condiviso. Per ulteriori informazioni sugli utenti anonimi e autenticati, consulta Stati di autenticazione [visitatore in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Indica ad <span class="keyword"> Audience Manager</span> di non utilizzare i dati raccolti dagli utenti autenticati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo autenticato corrente</span></b> </p> </td> 
   <td colname="col2"> <p>Indica ad <span class="keyword"> Audience Manager</span> di leggere e scrivere i dati nel profilo autenticato se un visitatore ha eseguito l'accesso al sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ultimo profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>Indica ad <span class="keyword"> Audience Manager</span> di leggere i dati dal profilo autenticato dell'ultimo utente che ha eseguito l'accesso sul dispositivo. </p> <p>Se questa opzione è selezionata, <span class="keyword"> Audience Manager</span> non scriverà nuovi dati sulle caratteristiche nel profilo autenticato se l'utente è anonimo. Al momento dell'autenticazione, i nuovi dati sulle caratteristiche vengono scritti nel profilo autenticato dell'utente. </p> </td>
  </tr> 
 </tbody>
</table>

## Opzioni profilo autenticato {#profile-options}

Vengono [!UICONTROL Authenticated Profile Options] elencate le origini dati cross-device. Queste opzioni utilizzano i nomi forniti al momento della creazione di un'origine dati multi-dispositivo (vedere [Creazione di un'origine](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)dati multi-dispositivo). Puoi selezionare fino a 3 origini dati cross-device da utilizzare con ciascuna regola di profilo. Le opzioni [!UICONTROL Authenticated Profile Options] sono disponibili quando scegliete **[!UICONTROL Current Authenticated Profile]** o **[!UICONTROL Last Authenticated Profile]**.

## Opzioni dispositivo {#device-options}

Consente [!UICONTROL Device Options] di selezionare il tipo di *`device profile`* utilizzato da un [!UICONTROL Profile Merge Rule]. Un profilo dispositivo è composto dalle caratteristiche raccolte dagli utenti che navigano sul Web in modo anonimo. Come minimo, una regola di unione dei profili include un'opzione autenticata e un'opzione dispositivo.

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
   <td colname="col2"> <p>Indica ad <span class="keyword"> Audience Manager</span> di non utilizzare per la segmentazione le caratteristiche contenute nel profilo anonimo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo dispositivo corrente</span></b> </p> </td> 
   <td colname="col2"> <p>Indica ad <span class="keyword"> Audience Manager</span> di utilizzare il profilo dispositivo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Grafico dispositivo di collegamento profilo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica ad <span class="keyword"> Audience Manager</span> di leggere i profili dal dispositivo corrente e dagli ultimi 3 dispositivi da cui l'utente ha eseguito l'autenticazione. Questo grafico del dispositivo è basato sui dati di prime parti in <span class="keyword"> Audience Manager</span>. È ideale per i clienti che hanno un elevato livello di autenticazione nelle loro proprietà digitali. Il grafico del dispositivo Collegamento <span class="wintitle"></span> profilo viene aggiornato in tempo reale. Questa opzione è disponibile quando selezionate <b><span class="uicontrol"> Profilo</span></b> autenticato corrente o <b><span class="uicontrol"> Ultimo profilo</span></b>autenticato. Quando utilizzate questa opzione, potete scegliere un solo profilo autenticato (<span class="keyword"> Audience Manager</span> ne visualizza automaticamente gli altri). Vedi anche <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Casi</a>di utilizzo di Profile Link Device Graph. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Indica ad <span class="keyword"> Audience Manager</span> di unire i profili dei dispositivi utilizzando i collegamenti forniti da <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> è una cooperativa digitale in cui i clienti partecipanti condividono informazioni sul collegamento dei dispositivi. Device Co-op <span class="keyword"> elabora questi dati in un grafico</span> del <span class="term"></span>dispositivo. Un grafico a dispositivi collega i dispositivi ai cluster di dispositivi. Questi collegamenti sono generati da dati <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"></a>probabilistici e deterministici. I cluster rappresentano un gruppo di dispositivi utilizzati da una persona sconosciuta. <span class="keyword">Device Co-op</span> condivide i cluster tra i suoi membri, aiutandoli a fornire ai loro clienti esperienze cross-device coerenti e di valore. </p> <p> Per ulteriori informazioni su <span class="wintitle"> Device Co-op</span>, vedi: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Panoramica di Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Requisiti di iscrizione</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Device Graph: Processi e output interni</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Grafici</a> Audience Manager e dispositivi esterni (download PDF). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opzioni</b> di Device Graph di terze parti (Persona e Famiglia) </p> </td>
   <td colname="col2"> <p>Queste opzioni consentono di creare regole di unione basate sulla tecnologia del grafico del dispositivo fornita da un fornitore di terze parti. Un grafico dei dispositivi di terze parti fornisce: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dati probabilistici e/o deterministici. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dati a livello di persona o di famiglia. </li> 
     </ul> </p> <p>Per utilizzare queste opzioni, devi essere un cliente di un grafico del dispositivo che fornisce chi è già integrato con <span class="keyword"> Audience Manager</span>. Per ulteriori informazioni o per iniziare, contatta il tuo account manager. </p> <p>Vedere anche &lt;a href="../../features/profile-merge-rules/external-graph-use-cases.md). </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_LIKE_this]
>
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

