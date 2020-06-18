---
description: Le opzioni della regola di unione consentono di controllare il tipo di dati  Audience Manager utilizzato per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del dispositivo Collegamento profilo, da Adobe Experience Cloud Device Co-op e/o da altri fornitori di grafici per dispositivi di terze parti integrati con  Audience Manager. Potete creare un massimo di 4 regole di unione dei profili.
seo-description: Le opzioni della regola di unione consentono di controllare il tipo di dati  Audience Manager utilizzato per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico del dispositivo Collegamento profilo, da Adobe Experience Cloud Device Co-op e/o da altri fornitori di grafici per dispositivi di terze parti integrati con  Audience Manager. Potete creare un massimo di 4 regole di unione dei profili.
seo-title: Opzioni Regola di unione profilo definite
solution: Audience Manager
title: Opzioni Regola di unione profilo definite
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 4%

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

The merge rule options let you control the type of data [!DNL Audience Manager] uses for segmentation. Una regola di unione può includere profili dispositivo mappati dal grafico del [!UICONTROL Profile Link] dispositivo, dai provider di grafici [!UICONTROL Adobe Experience Cloud Device Co-op]di dispositivi e/o da altri fornitori di grafici di terze parti integrati con [!DNL Audience Manager]. Potete creare un massimo di 4 [!UICONTROL Profile Merge Rules]. Il quarto [!UICONTROL Profile Merge Rule] è disponibile esclusivamente per i clienti che hanno acquistato il [!UICONTROL People-Based Destinations] componente aggiuntivo.

Per creare un [!UICONTROL Profile Merge Rule] oggetto, effettuate una selezione tra le opzioni descritte di seguito, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

[!UICONTROL Profile Merge Rules] consentire una serie di combinazioni di regole, ciascuna orientata a casi d&#39;uso specifici. Per informazioni dettagliate sull&#39;utilizzo di ogni combinazione di regole, vedere la tabella seguente.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilità | Tipo di valutazione | [!UICONTROL Audience Lab]Supporto  | Casi d&#39;uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting dei dispositivi](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (include [!UICONTROL Co-op Device Graph]) | Tutti i clienti | Tempo reale e batch | No | [Targeting esteso dei dispositivi](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Tutti i clienti | Solo in tempo reale | No | [Targeting dei dispositivi condivisi](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting tra dispositivi](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (include [!UICONTROL Co-op Device Graph]) | Tutti i clienti | Tempo reale e batch | No | [Targeting cross-device avanzato](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Esclusivo ai clienti delle destinazioni [basate sulle](../destinations/people-based-destinations-overview.md) persone | Solo batch | No | [Targeting per destinazioni basate su persone](merge-rule-targeting-options.md#all-cross-device) |

## Valutazione segmento regola unione profilo {#segment-evaluation}

A seconda della [!UICONTROL Profile Merge Rules] configurazione, [!DNL Audience Manager] è possibile eseguire la valutazione del segmento in tempo reale, in batch o in entrambi.

* La valutazione dei segmenti in tempo reale richiede che [!DNL DCS] i visitatori accedano alle proprie proprietà digitali in tempo reale, per qualificarsi per il segmento.
* La valutazione del segmento batch viene eseguita rispetto alle caratteristiche precedentemente qualificate.
* [!UICONTROL Profile Merge Rules] che supportano sia la valutazione in tempo reale che la valutazione dei segmenti batch, combinano l’attività dei visitatori in tempo reale con caratteristiche precedentemente qualificate.

## Latenza rapporti regole unione profilo {#reporting-latency}

La valutazione dei segmenti in tempo reale viene immediatamente riflessa nei [!UICONTROL Profile Merge Rules] rapporti.

La valutazione del segmento batch può richiedere fino a 24 ore per essere riflessa nei rapporti [sulle regole di unione dei](profile-link-metrics.md)profili.

## Opzioni multi-dispositivo {#auth-options}

Consente di [!UICONTROL Cross-Device Options] selezionare utenti autenticati e non autenticati e di sfruttare il loro profilo cross-device per la segmentazione. Queste opzioni consentono di identificare e raggiungere utenti specifici su un dispositivo condiviso. Per ulteriori informazioni sugli utenti anonimi e autenticati, consulta Stati di autenticazione [visitatore in  Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Indica <span class="keyword"> Audience Manager</span> di non utilizzare i dati raccolti dagli utenti autenticati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profili autenticati correnti</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> Audience Manager</span> di leggere e scrivere i dati nel profilo autenticato se un visitatore ha eseguito l'accesso al sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ultimi profili autenticati</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> Audience Manager</span> di leggere i dati dal profilo autenticato dell'utente che ha eseguito l'ultimo accesso al dispositivo. </p> <p>Se questa opzione è selezionata, <span class="keyword">  Audience Manager</span> non scriverà nuovi dati sulle caratteristiche nel profilo autenticato se l'utente è anonimo. Al momento dell'autenticazione, i nuovi dati sulle caratteristiche vengono scritti nel profilo autenticato dell'utente. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tutti i profili multi-dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica  Audience Manager di leggere i dati da tutti i profili cross-device, indipendentemente dallo stato di autenticazione. Questa opzione è disponibile solo per  clienti Audience Manager che hanno acquistato il componente aggiuntivo Destinazioni basate sulle persone.</p> </td>
  </tr>
 </tbody>
</table>

## Opzioni profilo multi-dispositivo {#profile-options}

Vengono [!UICONTROL Cross-Device Profile Options] elencate le origini dati cross-device. Queste opzioni utilizzano i nomi forniti al momento della creazione di un&#39;origine dati multi-dispositivo (vedere [Creazione di un&#39;origine](merge-rules-start.md#create-data-source)dati multi-dispositivo). È possibile selezionare fino a 3 origini dati cross-device da utilizzare con ciascuna regola di profilo. Le opzioni [!UICONTROL Authenticated Profile Options] sono disponibili quando scegliete **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## Opzioni dispositivo {#device-options}

Consente [!UICONTROL Device Options] di selezionare il tipo di *`device profile`* utilizzato da un [!UICONTROL Profile Merge Rule]. Un profilo dispositivo è basato sulle caratteristiche raccolte dall&#39;attività di navigazione anonima. Come minimo, una regola di unione dei profili include un&#39;opzione autenticata e un&#39;opzione dispositivo.

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
   <td colname="col2"> <p>Indica <span class="keyword"> Audience Manager</span> di non utilizzare le caratteristiche contenute nel profilo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> Audience Manager</span> di utilizzare il profilo dispositivo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Grafico dispositivo di collegamento profilo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> Audience Manager</span> di leggere i profili dal dispositivo corrente e fino a 100 altri dispositivi da cui l'utente ha eseguito l'autenticazione. Questo grafico del dispositivo è basato sui dati di prime parti in <span class="keyword"> Audience Manager</span>. È ideale per i clienti che hanno un elevato livello di autenticazione nelle loro proprietà digitali. Il grafico del dispositivo Collegamento <span class="wintitle"></span> profilo viene aggiornato in tempo reale. Questa opzione è disponibile quando selezionate <b><span class="uicontrol"> Profilo</span></b> autenticato corrente o <b><span class="uicontrol"> Ultimo profilo</span></b>autenticato. Quando si utilizza questa opzione, è possibile scegliere un solo profilo autenticato (<span class="keyword">  Audience Manager</span> emette automaticamente un grigio per gli altri). Vedi anche <a href="profile-link-use-case.md"> Casi</a>di utilizzo di Profile Link Device Graph. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Indica <span class="keyword"> Audience Manager</span> di leggere i profili dal dispositivo corrente e fino a 100 altri dispositivi utilizzando i collegamenti forniti da <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external">  Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> è una cooperativa digitale in cui i clienti partecipanti condividono informazioni sul collegamento dei dispositivi. Device Co-op <span class="keyword"> elabora questi dati in un grafico</span> del <span class="term"></span>dispositivo. Un grafico a dispositivi collega i dispositivi ai cluster di dispositivi. Questi collegamenti sono generati da dati <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"></a>probabilistici e deterministici. I cluster rappresentano un gruppo di dispositivi utilizzati da una persona sconosciuta. <span class="keyword">Device Co-op</span> condivide i cluster tra i suoi membri, aiutandoli a fornire ai loro clienti esperienze cross-device coerenti e di valore. </p> <p> Per ulteriori informazioni su <span class="wintitle"> Device Co-op</span>, vedi: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Panoramica di Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Requisiti di iscrizione</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Device Graph: Processi e output interni</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Opzioni</b> di Device Graph di terze parti (Persona e Famiglia) </p> </td>
   <td colname="col2"> <p>Queste opzioni consentono di creare regole di unione basate sulla tecnologia del grafico del dispositivo fornita da un fornitore di terze parti. Un grafico dei dispositivi di terze parti fornisce: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dati probabilistici e/o deterministici. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dati a livello di persona o di famiglia. </li> 
     </ul> </p> <p>Per utilizzare queste opzioni, devi essere un cliente di un grafico del dispositivo che fornisce chi è già integrato con <span class="keyword"> Audience Manager</span>. Per ulteriori informazioni o per iniziare, contatta il tuo account manager. </p> </td>
  </tr>
 </tbody>
</table>

## Criteri di unione esterni {#external-merge-policies}

I segmenti di pubblico creati automaticamente da altre soluzioni Experience Cloud , basati su regole di unione definite all&#39;esterno di [!DNL Audience Manager], sono contrassegnati come [!UICONTROL External Merge Policy]utenti. Ad esempio, vedete Condivisione [dell&#39;audience tra  Audience Manager e  Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

