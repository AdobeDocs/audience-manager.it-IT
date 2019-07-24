---
description: Risposte alle domande comuni su Regola unione profilo e grafico dispositivo.
keywords: ID organizzazione
seo-description: Risposte alle domande comuni su Regola unione profilo e grafico dispositivo.
seo-title: Domande frequenti su Profile Merge Rules e Device Graph
solution: Audience Manager
title: Domande frequenti su Profile Merge Rules e Device Graph
uuid: ba 7986 f 1-078 f -4162-aef 3-b 5 c 8740 cebf 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

Risposte alle domande comuni su Regola unione profilo e grafico dispositivo.

<!-- 

profile-merge-faq.xml

 -->

## Device Graph Basics {#device-graph-basics}

**Cos'è un grafico di dispositivo?**

Un grafico del dispositivo è un set di mappature ID che definiscono gruppi di dispositivi anonimi. Associa questi dispositivi a una persona o a una famiglia in base agli elementi comuni dei segnali raccolti da ciascun dispositivo. Questi segnali aiutano a identificare i dispositivi a livello individuale o familiare.

<br> 

**Cos'è un grafico dispositivo esterno?**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you're working with an external device graph. See [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**Quali sono alcuni casi d'uso comuni per utilizzare un grafico dispositivo esterno in un[!UICONTROL Profile Merge Rule]'interfaccia?**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. Il segmento stesso potrebbe avere più usi, ad esempio, targeting di un pubblico di potenziali prospect con annunci pubblicitari gestiti da una DSP o personalizzazione dell'esperienza on-site di un cliente tramite una piattaforma di personalizzazione on-site. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**Audience Manager fornisce supporto globale per grafici dispositivo esterni?**

No. I grafici dei dispositivi esterni sono disponibili solo negli Stati Uniti e in Canada.

<br> 

**Con quale frequenza[!DNL Audience Manager]aggiorna i dati del grafico del dispositivo esterno?**

Una volta a settimana.

<br> 

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**Come[!DNL Audience Manager]si utilizza un grafico dispositivo?**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* Unisce insieme più profili dispositivo. Viene creato un singolo superset di caratteristiche.
* Valuta il superset di caratteristiche per la qualifica del segmento (piuttosto che valutare singolarmente ciascun profilo dispositivo).
* Aggiungere dispositivi idonei ai segmenti disponibili.

<br> 

**Quanti[!UICONTROL Profile Merge Rules]è possibile creare?**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**Quanti profili dispositivo[!DNL Audience Manager]vengono uniti e letti quando si utilizza un grafico dispositivo in un[!UICONTROL Profile Merge Rule]'interfaccia?**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**Quali dispositivi si qualificano per un segmento quando si utilizza un grafico dispositivo in un[!UICONTROL Profile Merge Rule]?**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

>[!NOTE]
>
>For external device graphs, [!DNL Audience Manager] stores the mapping between devices at the platform level and selects 3 without evaluating their relationship to the devices seen in your instance of [!DNL Audience Manager].

<br> 

**Quali dispositivi **possono essere idonei per un segmento utilizzando un[!UICONTROL Profile Merge Rule]grafico dispositivo?**

To qualify for a segment, devices must have been seen by Audience Manager on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created. Inoltre, i server periferici:

* Archivia i dati di profilo per un massimo di 14 giorni.
* Eliminate un profilo dispositivo se resta inattivo per più di 14 giorni. Nota: Questa azione rimuove solo i dati dal margine. Altri sistemi conserveranno i record per intervalli di tempo più lunghi. See the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).
* Reset the 14-day interval if [!DNL Audience Manager] records any activity for that profile across the entire platform.

See also, [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**Dove[!DNL Audience Manager]può inviare segmenti idonei da un[!UICONTROL Profile Merge Rule]grafico che usa un grafico dispositivo?**

[!DNL Audience Manager] può inviare segmenti a una destinazione in file batch o in tempo reale. And, as noted in the FAQ entry above, To qualify for a segment, devices must have been seen by [!DNL Audience Manager] on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created.

<br> 

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**How does[!DNL Audience Manager]desegment a device when it is no longer qualified for a segment with a[!UICONTROL Profile Merge Rule]that uses a device graph?**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. Se viene emesso il segnale di annullamento del segmento, il dispositivo corrente e tre dispositivi aggiuntivi visualizzati in tempo reale verranno rimossi dal segmento nella destinazione. Ad esempio, in un cluster di sei dispositivi, fino a quattro dispositivi vengono uniti, valutati e qualificati per un segmento. Analogamente, fino a quattro dispositivi vengono uniti, valutati e non segmentati.

<br> 

**Se una destinazione può non segmentare i dispositivi, i dispositivi verranno rimossi dai segmenti tramite[!UICONTROL Profile Merge Rules]un grafico dispositivo?**

Sì. Vedi la spiegazione sopra.

<br> 

**Se crei un segmento con un[!UICONTROL Profile Merge Rule]grafico che usa un grafico di dispositivo e il segmento utilizza dati in tempo reale e su smartphone, il mio segmento sarà aggiornato con la modifica dei dati on-boarded?**

No. Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. Updates made to on-boarded traits after the segment has been evaluated will be used to qualify the segment when the device is next seen by our [edge data servers](../reference/system-components/components-edge.md). Questo presuppone che il profilo dispositivo sia ancora attivo nei server periferici e che i dati on-boarded siano stati resi disponibili a tali sistemi. See also, the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**Le stime di dimensioni del segmento includono dispositivi idonei per un segmento basato su connessioni fornite da un'[!UICONTROL Profile Merge Rule]opzione di grafico dispositivo?**

No. See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**[!UICONTROL Addressable Audiences]Comprende dispositivi idonei per un segmento basato su connessioni fornite da un'[!UICONTROL Profile Merge Rule]opzione di grafico dispositivo?**

Sì. 

<br> 

**Se un segmento utilizza un[!UICONTROL Profile Merge Rule]insieme e[!UICONTROL No Authenticated Profile]le caratteristiche idonee ai dispositivi per il segmento sono memorizzate solo rispetto al profilo autenticato, la popolazione totale del segmento sarà 0?**

No. Oggi Audience Manager conta i dispositivi mappati al profilo autenticato come idonei per il segmento.

<br> 

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**Come[!DNL Audience Manager]calcola la frequenza delle caratteristiche con un[!UICONTROL Profile Merge Rule]grafico di dispositivo?**

La frequenza delle caratteristiche è definita dalla somma del numero di qualifiche per una caratteristica specifica su più dispositivi. Per comprenderlo, osserva il seguente caso d'uso.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condizioni</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Il dispositivo A e il dispositivo B sono collegati da un grafico del dispositivo. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un segmento singolo (segmento 1) composto di una caratteristica singola (caratteristica 1), dove Trait 1 ha una frequenza di 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Azioni</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> legge e unisce i profili dispositivo per Device A e Device B. Sono disponibili i seguenti elementi: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Il dispositivo A è qualificato per tre volte. Ha una frequenza di 3 per Caratteristica 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Il dispositivo B ha qualificato la caratteristica per 1 volte. Ha una frequentazione di 5 per Trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> somma la frequenza per Trait 1 e utilizza 8 (3 + 5 = 8) per stabilire la qualifica del segmento. Il dispositivo A e il dispositivo B sono idonei per il segmento 1 perché hanno una frequenza di 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**Posso visualizzare il numero di dispositivi che possono essere raggiunti con un[!UICONTROL Profile Merge Rule]grafico di dispositivo?**

Sì. Reports return data at the [!UICONTROL Profile Merge Rule] level. I dati dei report vengono aggiornati ogni giorno. I dati si basano sui dispositivi visualizzati nell'account, non quelli collegati da un grafico del dispositivo. See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**Posso visualizzare il numero di dispositivi idonei per un segmento specifico in *tempo reale*con[!UICONTROL Profile Merge Rules]l'utilizzo di un grafico dispositivo?**

Sì. La metrica popolazione in tempo reale acquisisce le qualifiche del segmento per il dispositivo corrente (il dispositivo visualizzato in tempo reale) utilizzando i profili provenienti da tutti i dispositivi collegati da un grafico del dispositivo.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento del caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condizioni</b> </p> </td> 
   <td colname="col2"> <p>Si supponga di: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segmento 1 basato su queste caratteristiche e sulla logica di qualifica: Segmento 1 = Caratteristica A e Caratteristica B e Caratteristica C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 profili dispositivo: Dispositivo 1 (dispositivo corrente), Dispositivo 2 (grafico dispositivo), Dispositivo 3 (grafico dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Azioni</b> </p> </td> 
   <td colname="col2"> <p>Ogni caratteristica disponibile è associata a un dispositivo: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Device 1: Caratteristica A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Device 2: Caratteristica B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Device 3: Caratteristica C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>In base agli elementi precedenti, la popolazione totale per il segmento 1 è una. </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Ciò significa che i dispositivi 1, 2 e 3 sono idonei per il segmento 1, ma, come indicato sopra, solo il dispositivo 1 è incluso nella popolazione dei segmenti in tempo reale. poiché: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">I dispositivi 2 e 3 sono associati al Device 1 da un grafico del dispositivo, ma non interagiscono con il DCS contemporaneamente al dispositivo 1. </li> 
     </ul> </p> <p>Di conseguenza, i dispositivi 2 e 3 non sono inclusi nella metrica relativa alla popolazione del segmento in tempo reale. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Posso visualizzare il numero totale di dispositivi idonei per un segmento specifico con un[!UICONTROL Profile Merge Rule]grafico di dispositivo?**

Sì. La metrica relativa alla popolazione del segmento totale include i dispositivi aggiuntivi che hanno qualificato un segmento in base alle connessioni da un grafico del dispositivo.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento del caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Condizioni</b> </p> </td> 
   <td colname="col2"> <p>Si supponga di: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segmento 1 basato su queste caratteristiche e sulla logica di qualifica: Segmento 1 = Caratteristica A e Caratteristica B e Caratteristica C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 profili dispositivo: Dispositivo 1 (dispositivo corrente), Dispositivo 2 (grafico dispositivo), Dispositivo 3 (grafico dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associazioni</b> </p> </td> 
   <td colname="col2"> <p>Ogni caratteristica disponibile è associata a un dispositivo: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Device 1: Caratteristica A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Device 2: Caratteristica B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Device 3: Caratteristica C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>In base agli elementi precedenti, la popolazione totale per Segmento 1 è costituita da tre (3). </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Ciò significa che i dispositivi 1, 2 e 3 sono idonei per il segmento 1 e tutti e tre sono inclusi nella popolazione totale. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**I dispositivi idonei per un segmento sono dotati[!UICONTROL Profile Merge Rule]di un grafico dispositivo incluso nei[!UICONTROL Interactive]report,[!UICONTROL Overlap]nei report e nei[!UICONTROL Audience Optimization]report?**

No

>[!MORE_ LIKE_ THIS]
>
>* [Collegamento profilo](../features/profile-merge-rules/merge-rules-overview.md)

