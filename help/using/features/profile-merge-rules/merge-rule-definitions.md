---
description: Le opzioni Regola di unione consentono di controllare il tipo di dati  Audience Manager utilizzato per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del dispositivo Collegamento profilo, da Adobe Experience Cloud Device Co-op e/o da altri fornitori di grafici per dispositivi di terze parti integrati con  Audience Manager. Potete creare un massimo di 4 regole di unione dei profili.
seo-description: Le opzioni Regola di unione consentono di controllare il tipo di dati  Audience Manager utilizzato per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del dispositivo Collegamento profilo, da Adobe Experience Cloud Device Co-op e/o da altri fornitori di grafici per dispositivi di terze parti integrati con  Audience Manager. Potete creare un massimo di 4 regole di unione dei profili.
seo-title: Definizione delle opzioni delle regole di unione profili.
solution: Audience Manager
title: Definizione delle opzioni delle regole di unione profili.
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 6%

---


# [!UICONTROL Profile Merge Rules] Opzioni definite  {#profile-merge-rule-options-defined}

Le opzioni [!UICONTROL profile merge rule] consentono di controllare il tipo di dati [!DNL Audience Manager] utilizzati per la segmentazione. Un [!UICONTROL profile merge rule] può includere profili dispositivo mappati dal grafico [!UICONTROL Profile Link] del dispositivo, dai provider di grafici per dispositivi [!UICONTROL Adobe Experience Cloud Device Co-op] e/o da altri fornitori di grafici per dispositivi di terze parti integrati con [!DNL Audience Manager]. È possibile creare un massimo di 4 [!UICONTROL Profile Merge Rules]. Il quarto [!UICONTROL Profile Merge Rule] è disponibile esclusivamente per i clienti che hanno acquistato il componente aggiuntivo [!UICONTROL People-Based Destinations].

È possibile creare un [!UICONTROL Profile Merge Rule] effettuando una selezione tra le opzioni descritte di seguito, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Panoramica delle opzioni  {#overview}

[!UICONTROL Profile Merge Rules] consentire una serie di combinazioni di regole, ciascuna orientata a casi d&#39;uso specifici. Per informazioni dettagliate sull&#39;utilizzo di ogni combinazione di regole, vedere la tabella seguente.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilità | Tipo di valutazione | [!UICONTROL Audience Lab]Supporto  | Casi d&#39;uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting dei dispositivi](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (include  [!UICONTROL Co-op Device Graph]) | Tutti i clienti | Tempo reale e batch | No | [Targeting esteso dei dispositivi](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Tutti i clienti | Solo in tempo reale | No | [Targeting dei dispositivi condivisi](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting tra dispositivi](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (include  [!UICONTROL Co-op Device Graph]) | Tutti i clienti | Tempo reale e batch | No | [Targeting cross-device avanzato](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Esclusivo per i clienti [Destinazioni basate sulle persone](../destinations/people-based-destinations-overview.md) | Solo batch | No | [Targeting per destinazioni basate su persone](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Valutazione  {#segment-evaluation}

A seconda della configurazione [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] può eseguire la valutazione [!UICONTROL segment] in tempo reale, in batch o in entrambi.

* La valutazione in tempo reale [!UICONTROL segment] richiede che [!DNL DCS] i visitatori accedano alle proprie proprietà digitali in tempo reale, per qualificarsi come [!UICONTROL segment].
* La valutazione del batch [!UICONTROL segment] viene eseguita rispetto a [!UICONTROL traits] precedentemente qualificato.
* [!UICONTROL Profile Merge Rules] che supportano sia la  [!UICONTROL segment] valutazione in tempo reale che quella in batch, combinano l’attività in tempo reale dei visitatori con quella precedentemente qualificata  [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latenza report  {#reporting-latency}

La valutazione in tempo reale [!UICONTROL segment] viene immediatamente riflessa nei report [!UICONTROL Profile Merge Rules].

La valutazione batch [!UICONTROL segment] può richiedere fino a 24 ore per riflettere nei report [Profile Merge Rules](profile-link-metrics.md) (Regole di unione profilo).

## [!UICONTROL Cross-Device Options] {#auth-options}

[!UICONTROL Cross-Device Options] consente di selezionare utenti autenticati e non autenticati e di sfruttare il loro profilo cross-device per la segmentazione. Queste opzioni consentono di identificare e raggiungere utenti specifici su un dispositivo condiviso. Per ulteriori informazioni sugli utenti anonimi e autenticati, vedere [Stati di autenticazione dei visitatori in  Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione multi-dispositivo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nessun profilo multi-dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a <span class="keyword">  Audience Manager</span> di non utilizzare i dati raccolti dagli utenti autenticati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profili autenticati correnti</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a <span class="keyword">  Audience Manager</span> di leggere e scrivere i dati nel profilo autenticato se un visitatore ha eseguito l'accesso al sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ultimi profili autenticati</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a <span class="keyword">  Audience Manager</span> di leggere i dati dal profilo autenticato dell'utente che ha eseguito l'ultimo accesso al dispositivo. </p> <p>Se questa opzione è selezionata, <span class="keyword">  Audience Manager</span> non scriverà i nuovi dati delle caratteristiche nel profilo autenticato se l'utente è anonimo. Al momento dell'autenticazione, i nuovi dati sulle caratteristiche vengono scritti nel profilo autenticato dell'utente. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tutti i profili multi-dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica  Audience Manager di leggere i dati da tutti i profili cross-device, indipendentemente dallo stato di autenticazione. Questa opzione è disponibile solo per  clienti di Audience Manager che hanno acquistato il componente aggiuntivo Destinazioni basate su persone.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

Il [!UICONTROL Cross-Device Profile Options] elenca il [!UICONTROL cross-device data sources]. Queste opzioni utilizzano i nomi forniti al momento della creazione di una [!UICONTROL cross-device] [!UICONTROL data source] (vedere [Crea un&#39;origine dati multi-dispositivo](merge-rules-start.md#create-data-source)). È possibile selezionare fino a 3 [!UICONTROL cross-device data sources] da utilizzare con ciascuna regola di profilo. La [!UICONTROL Authenticated Profile Options] è disponibile quando si sceglie **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

[!UICONTROL Device Options] consente di selezionare il tipo di *`device profile`* utilizzato da un [!UICONTROL Profile Merge Rule]. Un profilo dispositivo è creato da [!UICONTROL traits] raccolte da attività di navigazione anonime. Come minimo, un [!UICONTROL profile merge rule] include un [!UICONTROL authenticated option] e un [!UICONTROL device option].

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
   <td colname="col2"> <p>Indica a <span class="keyword">  Audience Manager</span> di non utilizzare le caratteristiche contenute nel profilo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a <span class="keyword">  Audience Manager</span> di utilizzare il profilo dispositivo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Grafico dispositivo di collegamento profilo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a <span class="keyword">  Audience Manager</span> di leggere i profili dal dispositivo corrente e fino a 100 altri dispositivi da cui l'utente ha eseguito l'autenticazione. Questo grafico del dispositivo è basato sui dati di prime parti in <span class="keyword">  Audience Manager</span>. È ideale per i clienti che hanno un elevato livello di autenticazione nelle loro proprietà digitali. Il grafico del dispositivo <span class="wintitle"> Profile Link</span> viene aggiornato in tempo reale. Questa opzione è disponibile quando si seleziona <b><span class="uicontrol"> Profilo autenticato corrente</span></b> o <b><span class="uicontrol"> Ultimo profilo autenticato</span></b>. Quando si utilizza questa opzione, è possibile scegliere solo un singolo profilo autenticato (<span class="keyword">  Audience Manager</span> viene automaticamente visualizzato in grigio gli altri). Vedi anche <a href="profile-link-use-case.md"> Profile Link Device Graph Use Case</a> (Casi di utilizzo del grafico dei collegamenti di profilo). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Indica a <span class="keyword">  Audience Manager</span> di leggere i profili dal dispositivo corrente e fino a 100 altri dispositivi utilizzando i collegamenti forniti da <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external">  Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> è una cooperativa digitale in cui i clienti partecipanti condividono informazioni sul collegamento dei dispositivi. Il <span class="keyword"> Device Co-op</span> elabora questi dati in un grafico <span class="term"> del dispositivo</span>. Un grafico a dispositivi collega i dispositivi ai cluster di dispositivi. Questi collegamenti sono generati da <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> dati probabilistici e deterministici</a>. I cluster rappresentano un gruppo di dispositivi utilizzati da una persona sconosciuta. <span class="keyword">Device Co-op</span> condivide i cluster tra i suoi membri, aiutandoli a fornire ai loro clienti esperienze cross-device coerenti e di valore. </p> <p> Per ulteriori informazioni su <span class="wintitle"> Device Co-op</span>, vedi: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Panoramica di Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Requisiti di iscrizione</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Device Graph: Processi e output interni</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opzioni</b>  di Device Graph di terze parti (Persona e Famiglia) </p> </td>
   <td colname="col2"> <p>Queste opzioni consentono di creare regole di unione basate sulla tecnologia del grafico del dispositivo fornita da un fornitore di terze parti. Un grafico dei dispositivi di terze parti fornisce: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dati probabilistici e/o deterministici. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dati a livello di persona o di famiglia. </li> 
     </ul> </p> <p>Per utilizzare queste opzioni, devi essere un cliente di un grafico del dispositivo che fornisce chi è già integrato con <span class="keyword">  Audience Manager</span>. Per ulteriori informazioni o per iniziare, contatta il tuo account manager. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

I segmenti di audience creati automaticamente da altre soluzioni [!DNL Experience Cloud], basati su regole di unione definite all&#39;esterno di [!DNL Audience Manager], sono contrassegnati come utilizzando un [!UICONTROL External Merge Policy]. Ad esempio, vedere [Condivisione dell&#39;audience tra  Audience Manager e Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

