---
description: Le opzioni della regola di unione consentono di controllare il tipo di dati utilizzato dall’Audience Manager per la segmentazione. Una regola di unione può includere profili dispositivo mappati dal grafico dei dispositivi Collegamento profilo e/o altri fornitori di grafici dei dispositivi di terze parti integrati con Audience Manager. Puoi creare un massimo di 4 regole di unione profili.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Definizione delle opzioni delle regole di unione profili.
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 2%

---

# [!UICONTROL Profile Merge Rules] Opzioni definite {#profile-merge-rule-options-defined}

La [!UICONTROL profile merge rule] le opzioni consentono di controllare il tipo di dati [!DNL Audience Manager] utilizza per la segmentazione. A [!UICONTROL profile merge rule] può includere profili dispositivo mappati da [!UICONTROL Profile Link] grafico dei dispositivi e/o altri fornitori di grafici dei dispositivi di terze parti integrati con [!DNL Audience Manager]. Puoi creare un massimo di 4 [!UICONTROL Profile Merge Rules]. Il quarto [!UICONTROL Profile Merge Rule] è disponibile esclusivamente per i clienti che hanno acquistato il [!UICONTROL People-Based Destinations] add-on.

Crea un [!UICONTROL Profile Merge Rule] effettuando una selezione tra le opzioni descritte di seguito, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Panoramica delle opzioni {#overview}

[!UICONTROL Profile Merge Rules] consentire una serie di combinazioni di regole, ciascuna orientata a casi d&#39;uso specifici. Vedi la tabella seguente per i dettagli su quando utilizzare ogni combinazione di regole.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilità | Tipo di valutazione | [!UICONTROL Audience Lab]Supporto  | Casi d&#39;uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting dei dispositivi](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Tutti i clienti | Tempo reale e batch | No | [Targeting esteso dei dispositivi](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Tutti i clienti | Solo in tempo reale | No | [Targeting dei dispositivi condivisi](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Tutti i clienti | Tempo reale e batch | Sì | [Targeting tra dispositivi](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Tutti i clienti | Tempo reale e batch | No | [Targeting avanzato tra dispositivi](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Esclusivo in [Destinazioni basate su persone](../destinations/people-based-destinations-overview.md) clienti | Solo batch | No | [Targeting per destinazioni basate su persone](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Valutazione {#segment-evaluation}

A seconda del [!UICONTROL Profile Merge Rules] configurazione, [!DNL Audience Manager] può eseguire [!UICONTROL segment] valutazione in tempo reale, in batch o entrambi.

* Tempo reale [!UICONTROL segment] la valutazione richiede [!DNL DCS] per vedere i visitatori accedere alle tue proprietà digitali in tempo reale, per qualificarsi come [!UICONTROL segment].
* Batch [!UICONTROL segment] la valutazione viene eseguita sulla base di un certificato precedentemente qualificato [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] che supportano sia in tempo reale che batch [!UICONTROL segment] la valutazione combina l’attività visitatore in tempo reale con quella precedentemente qualificata [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latenza reporting {#reporting-latency}

Tempo reale [!UICONTROL segment] la valutazione si riflette immediatamente nella [!UICONTROL Profile Merge Rules] rapporti.

Batch [!UICONTROL segment] La valutazione può richiedere fino a 24 ore per riflettere nel [Rapporti sulle regole di unione profili](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

La [!UICONTROL Cross-Device Options] consente di selezionare utenti autenticati e non autenticati e di sfruttare il loro profilo multi-dispositivo per la segmentazione. Queste opzioni consentono di identificare e raggiungere utenti specifici su un dispositivo condiviso. Per ulteriori informazioni sugli utenti anonimi e autenticati, consulta [Audience Manager degli stati di autenticazione dei visitatori](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione tra dispositivi </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nessun profilo tra dispositivi</span></b> </p> </td> 
   <td colname="col2"> <p>Talloncini <span class="keyword"> Audience Manager</span> non utilizzare i dati raccolti dagli utenti autenticati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profili autenticati correnti</span></b> </p> </td> 
   <td colname="col2"> <p>Talloncini <span class="keyword"> Audience Manager</span> per leggere e scrivere i dati sul profilo autenticato se un visitatore ha effettuato l'accesso al tuo sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ultimi profili autenticati</span></b> </p> </td> 
   <td colname="col2"> <p>Talloncini <span class="keyword"> Audience Manager</span> per leggere i dati dal profilo autenticato dell'utente che ha effettuato l'ultimo accesso al dispositivo. </p> <p>Se selezionato, <span class="keyword"> Audience Manager</span> non scriverà nuovi dati sulle caratteristiche al profilo autenticato se l’utente è anonimo. Al momento dell’autenticazione, i nuovi dati delle caratteristiche vengono scritti sul profilo autenticato dell’utente. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tutti i profili multidispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Audience Manager di leggere i dati da tutti i profili multi-dispositivo, indipendentemente dallo stato di autenticazione. Questa opzione è disponibile solo per i clienti Audienci Manager che hanno acquistato il componente aggiuntivo Destinazioni basate su persone .</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

La [!UICONTROL Cross-Device Profile Options] elenca [!UICONTROL cross-device data sources]. Queste opzioni utilizzano i nomi forniti al momento della creazione di un [!UICONTROL cross-device] [!UICONTROL data source] (vedi [Creare un’origine dati tra dispositivi](merge-rules-start.md#create-data-source)). Puoi selezionare fino a 3 [!UICONTROL cross-device data sources] da utilizzare con ogni regola di profilo. La [!UICONTROL Authenticated Profile Options] sono disponibili quando si sceglie **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

La [!UICONTROL Device Options] consente di selezionare il tipo di *`device profile`* utilizzato da un [!UICONTROL Profile Merge Rule]. Un profilo dispositivo è generato da [!UICONTROL traits] raccolti da attività di navigazione anonima. Almeno un [!UICONTROL profile merge rule] include [!UICONTROL authenticated option] e [!UICONTROL device option].

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
   <td colname="col2"> <p>Talloncini <span class="keyword"> Audience Manager</span> non utilizzare le caratteristiche contenute nel profilo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Talloncini <span class="keyword"> Audience Manager</span> per utilizzare il profilo dispositivo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Grafico dei dispositivi di collegamento del profilo</span></b> </p> </td> 
   <td colname="col2"> <p>Talloncini <span class="keyword"> Audience Manager</span> per leggere i profili dal dispositivo corrente e fino a 100 altri dispositivi da cui l’utente ha eseguito l’autenticazione. Questo grafico dei dispositivi è basato su dati di prime parti personalizzati in <span class="keyword"> Audience Manager</span>. È ideale per i clienti che hanno un elevato livello di autenticazione nelle loro proprietà digitali. La <span class="wintitle"> Collegamento profilo</span> il grafico dei dispositivi viene aggiornato in tempo reale. Questa opzione è disponibile quando si seleziona <b><span class="uicontrol"> Profilo autenticato corrente</span></b> o <b><span class="uicontrol"> Ultimo profilo autenticato</span></b>. Quando utilizzi questa opzione, puoi scegliere un solo profilo autenticato (<span class="keyword"> Audience Manager</span> grida automaticamente gli altri). Vedi anche <a href="profile-link-use-case.md"> Casi d’uso del grafico dei dispositivi di collegamento del profilo</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Opzioni del grafico dei dispositivi di terze parti</b> (Persona e famiglia) </p> </td>
   <td colname="col2"> <p>Queste opzioni consentono di creare regole di unione basate sulla tecnologia del grafico dei dispositivi fornita da un fornitore di terze parti. Un grafico dei dispositivi di terze parti fornisce: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dati probabilistici e/o deterministici. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dati a livello di persona o famiglia. </li> 
     </ul> </p> <p>Per utilizzare queste opzioni, devi essere un cliente di un grafico dei dispositivi con gli utenti già integrati con <span class="keyword"> Audience Manager</span>. Per ulteriori informazioni o per iniziare, contatta il tuo account manager. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Segmenti di pubblico creati automaticamente da altri [!DNL Experience Cloud] soluzioni, in base a regole di unione definite al di fuori di [!DNL Audience Manager], sono contrassegnate come [!UICONTROL External Merge Policy]. Ad esempio, vedi [Condivisione del pubblico tra Audience Manager e Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

