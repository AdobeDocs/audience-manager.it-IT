---
description: Le opzioni delle regole di unione ti consentono di controllare il tipo di dati utilizzati dall’Audience Manager per la segmentazione. Una regola di unione può includere profili di dispositivi mappati dal grafico dei dispositivi Collegamento profilo e/o altri provider di grafici dei dispositivi di terze parti integrati con Audience Manager. Puoi creare un massimo di 4 regole di unione profili.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Definizione delle opzioni delle regole di unione profili
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] opzioni definite {#profile-merge-rule-options-defined}

Le opzioni [!UICONTROL profile merge rule] consentono di controllare il tipo di dati utilizzati da [!DNL Audience Manager] per la segmentazione. Un [!UICONTROL profile merge rule] può includere profili dispositivo mappati dal grafo dispositivi [!UICONTROL Profile Link] e/o altri provider di grafi dispositivi di terze parti integrati con [!DNL Audience Manager]. È possibile creare un massimo di 4 [!UICONTROL Profile Merge Rules]. Il quarto [!UICONTROL Profile Merge Rule] è disponibile esclusivamente per i clienti che hanno acquistato il componente aggiuntivo [!UICONTROL People-Based Destinations].

Per creare un [!UICONTROL Profile Merge Rule], effettuare una selezione tra le opzioni descritte di seguito, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Panoramica delle opzioni di [!UICONTROL Profile Merge Rule] {#overview}

[!UICONTROL Profile Merge Rules] consentono una serie di combinazioni di regole, ognuna orientata a casi d&#39;uso specifici. Per informazioni dettagliate su quando utilizzare ciascuna combinazione di regole, consulta la tabella seguente.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilità | Tipo di valutazione | Supporto [!UICONTROL Audience Lab] | Casi d&#39;uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Tutti i clienti | In tempo reale e in batch | Sì | [Impostazione destinazione dispositivo](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Tutti i clienti | In tempo reale e in batch | No | [Destinazione dispositivo espanso](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Tutti i clienti | Solo in tempo reale | No | [Impostazione destinazione dispositivo condiviso](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Tutti i clienti | In tempo reale e in batch | Sì | [Targeting online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Tutti i clienti | In tempo reale e in batch | Sì | [Targeting multidispositivo](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Tutti i clienti | In tempo reale e in batch | No | [Targeting avanzato tra dispositivi](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Esclusivo per [clienti con destinazioni basate su persone](../destinations/people-based-destinations-overview.md) | Solo batch | No | [Impostazione destinazione per destinazioni basate su persone](merge-rule-targeting-options.md#all-cross-device) |

## Valutazione [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] {#segment-evaluation}

A seconda della configurazione di [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] può eseguire la valutazione di [!UICONTROL segment] in tempo reale, in batch o in entrambi.

* La valutazione di [!UICONTROL segment] in tempo reale richiede che [!DNL DCS] veda i visitatori accedere alle tue proprietà digitali in tempo reale, per qualificarsi per [!UICONTROL segment].
* Valutazione del batch [!UICONTROL segment] eseguita su [!UICONTROL traits] precedentemente qualificati.
* [!UICONTROL Profile Merge Rules] che supporta sia la valutazione in tempo reale che quella batch [!UICONTROL segment] combinano l&#39;attività del visitatore in tempo reale con [!UICONTROL traits] precedentemente qualificati.

## Latenza report [!UICONTROL Profile Merge Rules] {#reporting-latency}

La valutazione di [!UICONTROL segment] in tempo reale viene riflessa immediatamente nei report di [!UICONTROL Profile Merge Rules].

La valutazione del batch [!UICONTROL segment] può richiedere fino a 24 ore per essere riflessa nei [report sulle regole di unione profili](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

[!UICONTROL Cross-Device Options] consente di selezionare utenti autenticati e non autenticati e di sfruttare il loro profilo multi-dispositivo per la segmentazione. Queste opzioni consentono di identificare e raggiungere utenti specifici su un dispositivo condiviso. Per ulteriori informazioni sugli utenti anonimi e autenticati, vedi [Stati di autenticazione del visitatore nell&#39;Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione tra dispositivi </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nessun profilo multi-dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica all'Audience Manager <span class="keyword"></span> di non utilizzare i dati raccolti dagli utenti autenticati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> profili autenticati correnti</span></b> </p> </td> 
   <td colname="col2"> <p>Indica all'Audience Manager <span class="keyword"></span> di leggere e scrivere dati nel profilo autenticato se un visitatore ha effettuato l'accesso al sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ultimi profili autenticati</span></b> </p> </td> 
   <td colname="col2"> <p>Indica all'Audience Manager <span class="keyword"></span> di leggere i dati dal profilo autenticato dell'ultimo utente che ha eseguito l'accesso al dispositivo. </p> <p>Se questa opzione è selezionata, l'Audience Manager <span class="keyword"></span> non scriverà nuovi dati sulle caratteristiche nel profilo autenticato se l'utente è anonimo. Al momento dell’autenticazione, i nuovi dati delle caratteristiche vengono scritti nel profilo autenticato dell’utente. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tutti I Profili Cross-Device</span></b> </p> </td> 
   <td colname="col2"> <p>Indica ad Audience Manager di leggere dati da tutti i profili multi-dispositivo, indipendentemente dallo stato di autenticazione. Questa opzione è disponibile solo per gli Audienci Manager di clienti che hanno acquistato il componente aggiuntivo Destinazioni basate su persone.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

[!UICONTROL Cross-Device Profile Options] elenca [!UICONTROL cross-device data sources]. Queste opzioni utilizzano i nomi forniti al momento della creazione di [!UICONTROL cross-device] [!UICONTROL data source] (vedi [Creare un Source dati multi-dispositivo](merge-rules-start.md#create-data-source)). È possibile selezionare fino a 3 [!UICONTROL cross-device data sources] da utilizzare con ogni regola di profilo. I [!UICONTROL Authenticated Profile Options] sono disponibili quando si sceglie **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

[!UICONTROL Device Options] consente di selezionare il tipo di *`device profile`* utilizzato da un [!UICONTROL Profile Merge Rule]. Un profilo dispositivo è stato creato da [!UICONTROL traits] raccolto da un&#39;attività di esplorazione anonima. Almeno, un [!UICONTROL profile merge rule] include un [!UICONTROL authenticated option] e un [!UICONTROL device option].

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
   <td colname="col2"> <p>Indica all'Audience Manager <span class="keyword"></span> di non utilizzare le caratteristiche contenute nel profilo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> profilo dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Indica all'Audience Manager <span class="keyword"></span> di utilizzare il profilo dispositivo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Grafico dei dispositivi di collegamento del profilo <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Indica all'Audience Manager <span class="keyword"></span> di leggere i profili dal dispositivo corrente e fino a 100 altri dispositivi da cui l'utente ha eseguito l'autenticazione. Questo grafo di dispositivi è basato sui tuoi dati di prime parti nell'Audience Manager </span> di <span class="keyword">. È ideale per i clienti che hanno un elevato livello di autenticazione nelle loro proprietà digitali. Il grafico dei dispositivi <span class="wintitle"> Profile Link</span> è stato aggiornato in tempo reale. Questa opzione è disponibile quando si seleziona <b><span class="uicontrol"> profilo corrente autenticato</span></b> o <b><span class="uicontrol"> ultimo profilo autenticato</span></b>. Quando si utilizza questa opzione, è possibile scegliere un solo profilo autenticato (<span class="keyword"> Audience Manager</span> elimina automaticamente gli altri). Vedi anche <a href="profile-link-use-case.md"> casi d'uso del grafico dei dispositivi di collegamento dei profili</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Opzioni del grafico dei dispositivi di terze parti</b> (persona e famiglia) </p> </td>
   <td colname="col2"> <p>Queste opzioni consentono di creare regole di unione basate sulla tecnologia dei grafici dei dispositivi fornita da un fornitore di terze parti. Un grafico dei dispositivi di terze parti fornisce: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dati probabilistici e/o deterministici. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dati a livello della persona o della famiglia. </li> 
     </ul> </p> <p>Per utilizzare queste opzioni, è necessario essere un cliente di un provider di Device Graph che è già integrato con <span class="keyword"> Audience Manager</span>. Contatta il tuo account manager per ulteriori informazioni o per iniziare. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

I segmenti di pubblico creati automaticamente da altre soluzioni [!DNL Experience Cloud], in base alle regole di unione definite al di fuori di [!DNL Audience Manager], sono contrassegnati come segmenti che utilizzano [!UICONTROL External Merge Policy]. Vedi [Condivisione del pubblico tra Audience Manager e Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Domande frequenti sulle regole di unione profili](../../faq/faq-profile-merge.md)
