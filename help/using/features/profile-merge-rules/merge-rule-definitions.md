---
description: Le opzioni delle regole di unione ti consentono di controllare il tipo di dati utilizzati dall’Audience Manager per la segmentazione. Una regola di unione può includere profili di dispositivi mappati dal grafico dei dispositivi Collegamento profilo e/o altri provider di grafici dei dispositivi di terze parti integrati con Audience Manager. Puoi creare un massimo di 4 regole di unione profili.
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

Il [!UICONTROL profile merge rule] Le opzioni consentono di controllare il tipo di dati [!DNL Audience Manager] utilizza per la segmentazione. A [!UICONTROL profile merge rule] può includere profili dispositivo mappati da [!UICONTROL Profile Link] device graph e/o altri fornitori di grafici per dispositivi di terze parti integrati con [!DNL Audience Manager]. Puoi creare un massimo di 4 [!UICONTROL Profile Merge Rules]. Il quarto [!UICONTROL Profile Merge Rule] è disponibile esclusivamente per i clienti che hanno acquistato [!UICONTROL People-Based Destinations] componente aggiuntivo.

Si crea un [!UICONTROL Profile Merge Rule] selezionando una delle opzioni descritte di seguito, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Panoramica delle opzioni {#overview}

[!UICONTROL Profile Merge Rules] consente una serie di combinazioni di regole, ciascuna orientata a casi d’uso specifici. Per informazioni dettagliate su quando utilizzare ciascuna combinazione di regole, consulta la tabella seguente.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilità | Tipo di valutazione | [!UICONTROL Audience Lab]Supporto  | Casi d&#39;uso |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Tutti i clienti | In tempo reale e in batch | Sì | [Targeting dei dispositivi](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Tutti i clienti | In tempo reale e in batch | No | [Targeting dispositivo espanso](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Tutti i clienti | Solo in tempo reale | No | [Targeting dei dispositivi condivisi](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Tutti i clienti | In tempo reale e in batch | Sì | [Targeting online/offline](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Tutti i clienti | In tempo reale e in batch | Sì | [Targeting tra dispositivi](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Tutti i clienti | In tempo reale e in batch | No | [Targeting avanzato tra dispositivi](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N/D | Esclusivo per [Destinazioni basate su persone](../destinations/people-based-destinations-overview.md) clienti | Solo batch | No | [Targeting per destinazioni basate su persone](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Valutazione {#segment-evaluation}

A seconda del [!UICONTROL Profile Merge Rules] configurazione, [!DNL Audience Manager] può eseguire [!UICONTROL segment] valutazione in tempo reale, in batch o in entrambi.

* Tempo reale [!UICONTROL segment] la valutazione richiede [!DNL DCS] per vedere i visitatori accedere alle tue proprietà digitali in tempo reale, per qualificarsi per [!UICONTROL segment].
* Batch [!UICONTROL segment] la valutazione viene eseguita su pazienti precedentemente qualificati [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] che supportano sia in tempo reale che in batch [!UICONTROL segment] valutazione combinare l’attività del visitatore in tempo reale con quella precedentemente qualificata [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latenza di reporting {#reporting-latency}

Tempo reale [!UICONTROL segment] la valutazione si riflette immediatamente nel [!UICONTROL Profile Merge Rules] rapporti.

Batch [!UICONTROL segment] la valutazione può richiedere fino a 24 ore per essere riflessa nel [Rapporti sulle regole di unione profili](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

Il [!UICONTROL Cross-Device Options] consente di selezionare utenti autenticati e non autenticati e di sfruttare il loro profilo multi-dispositivo per la segmentazione. Queste opzioni consentono di identificare e raggiungere utenti specifici su un dispositivo condiviso. Per ulteriori informazioni sugli utenti anonimi e autenticati, consulta [Stati di autenticazione dei visitatori in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> non utilizzare i dati raccolti da utenti autenticati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profili attuali autenticati</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> leggere e scrivere dati nel profilo autenticato se un visitatore ha effettuato l’accesso al sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ultimi profili autenticati</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> per leggere i dati dal profilo autenticato dell’ultimo utente che ha effettuato l’accesso al dispositivo. </p> <p>Se selezionata, <span class="keyword"> Audience Manager</span> non scrive nuovi dati sulle caratteristiche nel profilo autenticato se l’utente è anonimo. Al momento dell’autenticazione, i nuovi dati delle caratteristiche vengono scritti nel profilo autenticato dell’utente. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tutti i profili tra dispositivi</span></b> </p> </td> 
   <td colname="col2"> <p>Indica ad Audience Manager di leggere dati da tutti i profili multi-dispositivo, indipendentemente dallo stato di autenticazione. Questa opzione è disponibile solo per gli Audienci Manager di clienti che hanno acquistato il componente aggiuntivo Destinazioni basate su persone.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

Il [!UICONTROL Cross-Device Profile Options] elenca il tuo [!UICONTROL cross-device data sources]. Queste opzioni utilizzano i nomi forniti al momento della creazione di un [!UICONTROL cross-device] [!UICONTROL data source] (vedere [Creare un’origine dati multi-dispositivo](merge-rules-start.md#create-data-source)). Puoi selezionare fino a 3 [!UICONTROL cross-device data sources] da utilizzare con ogni regola di profilo. Il [!UICONTROL Authenticated Profile Options] sono disponibili quando si sceglie **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

Il [!UICONTROL Device Options] consente di selezionare il tipo di *`device profile`* utilizzato da un [!UICONTROL Profile Merge Rule]. Un profilo dispositivo è creato da [!UICONTROL traits] raccolte da attività di navigazione anonime. Come minimo, un [!UICONTROL profile merge rule] include un [!UICONTROL authenticated option] e un [!UICONTROL device option].

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> non utilizzare le caratteristiche contenute nel profilo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profilo dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> per utilizzare il profilo dispositivo anonimo per la segmentazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Grafico dei dispositivi di collegamento profilo</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> per leggere i profili dal dispositivo corrente e fino a 100 altri dispositivi da cui l’utente si è autenticato. Questo grafico dei dispositivi è basato sui tuoi dati di prime parti in <span class="keyword"> Audience Manager</span>. È ideale per i clienti che hanno un elevato livello di autenticazione nelle loro proprietà digitali. Il <span class="wintitle"> Collegamento profilo</span> il grafico dei dispositivi viene aggiornato in tempo reale. Questa opzione è disponibile quando si seleziona <b><span class="uicontrol"> Profilo autenticato corrente</span></b> o <b><span class="uicontrol"> Ultimo profilo autenticato</span></b>. Quando utilizzi questa opzione, puoi scegliere un solo profilo autenticato (<span class="keyword"> Audience Manager</span> disattiva automaticamente gli altri). Vedi anche, <a href="profile-link-use-case.md"> Casi d’uso del grafico dei dispositivi di collegamento dei profili</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Opzioni del grafico dei dispositivi di terze parti</b> (Persona e famiglia) </p> </td>
   <td colname="col2"> <p>Queste opzioni consentono di creare regole di unione basate sulla tecnologia dei grafici dei dispositivi fornita da un fornitore di terze parti. Un grafico dei dispositivi di terze parti fornisce: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Dati probabilistici e/o deterministici. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Dati a livello della persona o della famiglia. </li> 
     </ul> </p> <p>Per utilizzare queste opzioni, devi essere un cliente di un fornitore di grafici dei dispositivi che è già integrato con <span class="keyword"> Audience Manager</span>. Contatta il tuo account manager per ulteriori informazioni o per iniziare. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Segmenti di pubblico creati automaticamente da altri [!DNL Experience Cloud] soluzioni, in base a regole di unione definite al di fuori di [!DNL Audience Manager], sono contrassegnati come utilizzando un [!UICONTROL External Merge Policy]. Ad esempio, consulta [Condivisione del pubblico tra Audience Manager e Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Domande frequenti sulle regole di unione profili](../../faq/faq-profile-merge.md)

