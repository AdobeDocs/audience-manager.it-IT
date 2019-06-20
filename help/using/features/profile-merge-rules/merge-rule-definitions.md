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


# Opzioni regola unione profilo definite {#profile-merge-rule-options-defined}

Le opzioni Regola di unione consentono di controllare il tipo di dati utilizzati da Audience Manager per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal [!UICONTROL Profile Link] grafico del dispositivo, da [!UICONTROL Adobe Experience Cloud Device Co-op]e/o altri fornitori di grafici dispositivi di terze parti integrati con Audience Manager. Potete creare un massimo di 3 [!UICONTROL Profile Merge Rules].

Creando una [!UICONTROL Profile Merge Rule] selezione da queste opzioni:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> Opzioni autenticate</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> Opzioni profilo autenticate</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Opzioni dispositivo</a> </li>
</ul>

## Opzioni autenticate {#auth-options}

Consente [!UICONTROL Authenticated Options] di selezionare utenti autenticati e autenticati e sfruttare il profilo cross-device per la segmentazione. Queste opzioni consentono di identificare e raggiungere utenti specifici su un dispositivo condiviso. Per ulteriori informazioni sugli utenti anonimi e autenticati, consulta [Stati di autenticazione dei visitatori in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> di non utilizzare i dati raccolti dagli utenti autenticati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo autenticato corrente</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> di leggere e scrivere dati nel profilo autenticato se un visitatore ha eseguito l'accesso al sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ultimo profilo autenticato</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> di leggere i dati dal profilo autenticato dell'utente che ha eseguito l'ultimo accesso al dispositivo. </p> <p>Quando è selezionata, <span class="keyword"> Audience Manager</span> non scrive nuovi dati delle caratteristiche nel profilo autenticato se l'utente è anonimo. All'autenticazione, nuovi dati di caratteristica vengono scritti sul profilo autenticato dell'utente. </p> </td>
  </tr> 
 </tbody>
</table>

## Opzioni profilo autenticate {#profile-options}

Vengono [!UICONTROL Authenticated Profile Options] elencate le origini dati cross-device. Queste opzioni utilizzano i nomi forniti quando hai creato un&#39;origine dati multi-dispositivo (consultate [Creazione di un&#39;origine dati multi-dispositivo](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). Puoi selezionare fino a 3 origini dati cross-device da utilizzare con ciascuna regola di profilo. Sono [!UICONTROL Authenticated Profile Options] disponibili quando scegliete **[!UICONTROL Current Authenticated Profile]** o **[!UICONTROL Last Authenticated Profile]**.

## Opzioni dispositivo {#device-options}

Consente [!UICONTROL Device Options] di selezionare il tipo *`device profile`* di utilizzo da [!UICONTROL Profile Merge Rule]utilizzare. Un profilo dispositivo è composto da caratteristiche raccolte dagli utenti mentre vengono visualizzate in modo anonimo. Come minimo, una regola di unione profilo include un&#39;opzione autenticata e un&#39;opzione dispositivo.

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
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> di non utilizzare le caratteristiche contenute nel profilo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo dispositivo corrente</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> di utilizzare il profilo dispositivo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Collegamento profilo Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> di leggere i profili dal dispositivo corrente e dagli ultimi 3 dispositivi da cui l'utente ha eseguito l'autenticazione. Questo grafico del dispositivo è basato sui tuoi dati di prime parti in <span class="keyword"> Audience Manager</span>. È ideale per i clienti che hanno un livello elevato di autenticazione nelle loro proprietà digitali. Il grafico <span class="wintitle"> del dispositivo Collegamento</span> profilo viene aggiornato in tempo reale. Questa opzione è disponibile quando si seleziona <b><span class="uicontrol"> Profilo autenticato corrente</span></b> o <b><span class="uicontrol"> Ultimo profilo autenticato</span></b>. Quando utilizzate questa opzione, potete scegliere un singolo profilo autenticato (<span class="keyword"> Audience Manager</span> popola automaticamente gli altri). Vedi anche <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Profile Link Device Graph Casi d'uso</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> a Audience Manager</span> di unire profili dispositivo utilizzando i collegamenti forniti da <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> è una cooperativa digitale in cui i clienti partecipanti condividono informazioni sul collegamento dei dispositivi. <span class="keyword"> Device Co-op</span> elabora questi dati in un grafico <span class="term"> del dispositivo</span>. Un grafico dispositivo collega i dispositivi insieme ai cluster di dispositivi. Questi collegamenti sono generati da <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> dati probabilistici e deterministici</a>. I cluster rappresentano un gruppo di dispositivi utilizzati da una persona sconosciuta. <span class="keyword">Device Co-op</span> condivide i cluster tra i suoi membri, aiutandoli a fornire ai loro clienti esperienze cross-device coerenti e di valore. </p> <p> Per ulteriori informazioni su <span class="wintitle"> Device Co-op</span>, vedi: </p> <p> 
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
     </ul> </p> <p>Per utilizzare queste opzioni, devi essere un cliente di un grafico dispositivo che fornisce già l'integrazione con <span class="keyword"> Audience Manager</span>. Per ulteriori informazioni o per iniziare, contatta il tuo account manager. </p> <p>Consultate anche &lt; a href = "../../features/profile-merge-rules/external-graph-use-instances. md. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Domande frequenti sulle regole di unione profilo](../../faq/faq-profile-merge.md)

