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


# Domande frequenti su Profile Merge Rules e Device Graph{#profile-merge-rules-and-device-graph-faq}

Risposte alle domande comuni su Regola unione profilo e grafico dispositivo.

<!-- 

profile-merge-faq.xml

 -->

## Nozioni di base sui grafici {#device-graph-basics}

**Cos&#39;è un grafico di dispositivo?**

Un grafico del dispositivo è un set di mappature ID che definiscono gruppi di dispositivi anonimi. Associa questi dispositivi a una persona o a una famiglia in base agli elementi comuni dei segnali raccolti da ciascun dispositivo. Questi segnali aiutano a identificare i dispositivi a livello individuale o familiare.

<br> 

**Cos&#39;è un grafico dispositivo esterno?**

Un grafico dispositivo esterno è un grafico del dispositivo in cui [!DNL Audience Manager] non è stato creato esclusivamente dalle tue origini dati cross-device. Ad esempio, quando create una regola [di unione profili](../features/profile-merge-rules/merge-rules-start.md) e scegliete le [!UICONTROL Co-op Device Graph] opzioni di grafico o grafico dispositivo di terze parti, state lavorando con un grafico dispositivo esterno. Consultate [Opzioni dispositivo](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**Quali sono alcuni casi d&#39;uso comuni per utilizzare un grafico dispositivo esterno in un[!UICONTROL Profile Merge Rule]&#39;interfaccia?**

L&#39;obiettivo principale di utilizzare un grafico dispositivo in un grafico [!UICONTROL Profile Merge Rule] è valutare e qualificare più dispositivi appartenenti a una singola persona o famiglia per un segmento specifico. Il segmento stesso potrebbe avere più usi, ad esempio, targeting di un pubblico di potenziali prospect con annunci pubblicitari gestiti da una DSP o personalizzazione dell&#39;esperienza on-site di un cliente tramite una piattaforma di personalizzazione on-site. Consulta [Casi d&#39;uso grafici esterni](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**Audience Manager fornisce supporto globale per grafici dispositivo esterni?**

No. I grafici dei dispositivi esterni sono disponibili solo negli Stati Uniti e in Canada.

<br> 

**Con quale frequenza[!DNL Audience Manager]aggiorna i dati del grafico del dispositivo esterno?**

Una volta a settimana.

<br> 

## Grafici dispositivo e regole di unione profilo {#device-graph-profile-merge-rules}

**Come[!DNL Audience Manager]si utilizza un grafico dispositivo?**

In [!DNL Audience Manager], i grafici dei dispositivi appaiono come opzioni di configurazione quando [crei una regola unione profilo](../features/profile-merge-rules/merge-rules-start.md). Tramite la vostra [!UICONTROL Profile Merge Rules], questi grafici dispositivo sono utili [!DNL Audience Manager]:

* Unisce insieme più profili dispositivo. Viene creato un singolo superset di caratteristiche.
* Valuta il superset di caratteristiche per la qualifica del segmento (piuttosto che valutare singolarmente ciascun profilo dispositivo).
* Aggiungere dispositivi idonei ai segmenti disponibili.

<br> 

**Quanti[!UICONTROL Profile Merge Rules]è possibile creare?**

Al momento, potete creare un massimo di 3 [!UICONTROL Profile Merge Rules].

<br> 

**Quanti profili dispositivo[!DNL Audience Manager]vengono uniti e letti quando si utilizza un grafico dispositivo in un[!UICONTROL Profile Merge Rule]&#39;interfaccia?**

Quando si qualifica un dispositivo per un segmento utilizzando un componente, [!UICONTROL Profile Merge Rule]Audience Manager unisce e legge il profilo dispositivo corrente e un massimo di 3 profili dispositivo aggiuntivi collegati dall&#39;opzione di grafico dispositivo selezionata.

<br> 

**Quali dispositivi si qualificano per un segmento quando si utilizza un grafico dispositivo in un[!UICONTROL Profile Merge Rule]?**

I dispositivi [!DNL Audience Manager] uniscono e leggono gli stessi dispositivi idonei per un segmento.

>[!NOTE]
>
>Per i grafici dei dispositivi esterni [!DNL Audience Manager] , memorizza la mappatura tra i dispositivi a livello di piattaforma e seleziona 3 senza valutare la loro relazione con i dispositivi visualizzati nell&#39;istanza [!DNL Audience Manager].

<br> 

**Quali dispositivi**possono essere idonei per un segmento utilizzando un[!UICONTROL Profile Merge Rule]grafico dispositivo?**

Per qualificarsi per un segmento, i dispositivi devono essere stati visti da Audience Manager sui nostri [server di dati periferici](../reference/system-components/components-edge.md) dopo la creazione del segmento. Inoltre, i server periferici:

* Archivia i dati di profilo per un massimo di 14 giorni.
* Eliminate un profilo dispositivo se resta inattivo per più di 14 giorni. Nota: Questa azione rimuove solo i dati dal margine. Altri sistemi conserveranno i record per intervalli di tempo più lunghi. Consulta le domande frequenti [sulla privacy e sulla conservazione dei dati](../faq/faq-privacy.md).
* Ripristina l&#39;intervallo di 14 giorni se [!DNL Audience Manager] registra qualsiasi attività per tale profilo nell&#39;intera piattaforma.

Vedi anche Componenti raccolta [dati](../reference/system-components/components-data-collection.md).

<br> 

**Dove[!DNL Audience Manager]può inviare segmenti idonei da un[!UICONTROL Profile Merge Rule]grafico che usa un grafico dispositivo?**

[!DNL Audience Manager] può inviare segmenti a una destinazione in file batch o in tempo reale. Inoltre, come indicato nella voce FAQ sopra, per qualificarvi su un segmento, i dispositivi devono essere stati visti dai [!DNL Audience Manager] server [di dati periferici](../reference/system-components/components-edge.md) dopo la creazione del segmento.

<br> 

## Segmenti, Grafici dispositivo e regole di unione profilo {#segments-device-graphs-rules}

**How does[!DNL Audience Manager]desegment a device when it is no longer qualified for a segment with a[!UICONTROL Profile Merge Rule]that uses a device graph?**

Audience Manager unisce fino a quattro dispositivi durante la valutazione dei segmenti con un [!UICONTROL Profile Merge Rule] grafico del dispositivo. Se viene emesso il segnale di annullamento del segmento, il dispositivo corrente e tre dispositivi aggiuntivi visualizzati in tempo reale verranno rimossi dal segmento nella destinazione. Ad esempio, in un cluster di sei dispositivi, fino a quattro dispositivi vengono uniti, valutati e qualificati per un segmento. Analogamente, fino a quattro dispositivi vengono uniti, valutati e non segmentati.

<br> 

**Se una destinazione può non segmentare i dispositivi, i dispositivi verranno rimossi dai segmenti tramite[!UICONTROL Profile Merge Rules]un grafico dispositivo?**

Sì. Vedi la spiegazione sopra.

<br> 

**Se crei un segmento con un[!UICONTROL Profile Merge Rule]grafico che usa un grafico di dispositivo e il segmento utilizza dati in tempo reale e su smartphone, il mio segmento sarà aggiornato con la modifica dei dati on-boarded?**

No. Al momento [!DNL Audience Manager] , valuta i segmenti con un [!UICONTROL Profile Merge Rule] grafico di dispositivo in tempo reale. Gli aggiornamenti apportati alle caratteristiche allineate dopo l&#39;esame del segmento saranno utilizzati per qualificare il segmento quando il dispositivo viene visualizzato successivamente dai nostri [server di dati periferici](../reference/system-components/components-edge.md). Questo presuppone che il profilo dispositivo sia ancora attivo nei server periferici e che i dati on-boarded siano stati resi disponibili a tali sistemi. Vedi anche le domande frequenti [sulla privacy e sulla conservazione dei dati](../faq/faq-privacy.md).

<br> 

**Le stime di dimensioni del segmento includono dispositivi idonei per un segmento basato su connessioni fornite da un&#39;[!UICONTROL Profile Merge Rule]opzione di grafico dispositivo?**

No. Consulta le definizioni per [!UICONTROL Estimated Real-Time Population] i [!UICONTROL Estimated Total Population] dati [della popolazione e dei segmenti in Segment Builder](../features/segments/segment-builder-data.md)(Generatore segmenti).

<br> 

**[!UICONTROL Addressable Audiences]Comprende dispositivi idonei per un segmento basato su connessioni fornite da un&#39;[!UICONTROL Profile Merge Rule]opzione di grafico dispositivo?**

Sì. 

<br> 

**Se un segmento utilizza un[!UICONTROL Profile Merge Rule]insieme e[!UICONTROL No Authenticated Profile]le caratteristiche idonee ai dispositivi per il segmento sono memorizzate solo rispetto al profilo autenticato, la popolazione totale del segmento sarà 0?**

No. Oggi Audience Manager conta i dispositivi mappati al profilo autenticato come idonei per il segmento.

<br> 

## Frequenza caratteristica, Grafici dispositivo e regole di unione profilo {#trait-freq-device-rules}

**Come[!DNL Audience Manager]calcola la frequenza delle caratteristiche con un[!UICONTROL Profile Merge Rule]grafico di dispositivo?**

La frequenza delle caratteristiche è definita dalla somma del numero di qualifiche per una caratteristica specifica su più dispositivi. Per comprenderlo, osserva il seguente caso d&#39;uso.

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
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Hai una <span class="wintitle"> regola Unione profilo</span> che usa un'opzione grafico dispositivo. </li> 
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

## Rapporti, Grafici dispositivo e regole di unione profilo {#reports-device-graphs-rules}

**Posso visualizzare il numero di dispositivi che possono essere raggiunti con un[!UICONTROL Profile Merge Rule]grafico di dispositivo?**

Sì. I rapporti restituiscono i dati a [!UICONTROL Profile Merge Rule] livello. I dati dei report vengono aggiornati ogni giorno. I dati si basano sui dispositivi visualizzati nell&#39;account, non quelli collegati da un grafico del dispositivo. Consultate [Metriche di report per regole di unione profilo](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**Posso visualizzare il numero di dispositivi idonei per un segmento specifico in*tempo reale*con[!UICONTROL Profile Merge Rules]l&#39;utilizzo di un grafico dispositivo?**

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
   <td colname="col2"> <p>In base agli elementi precedenti, la popolazione totale per il segmento 1 è una. </p> <p>In questo caso, la Regola Unione <span class="wintitle"> profili</span> utilizza tutti i dispositivi e le relative caratteristiche per stabilire la qualifica del segmento. Ciò significa che i dispositivi 1, 2 e 3 sono idonei per il segmento 1, ma, come indicato sopra, solo il dispositivo 1 è incluso nella popolazione dei segmenti in tempo reale. poiché: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 è il dispositivo corrente che interagisce con i server di raccolta <span class="wintitle"> dati di Audience Manager</span> (<span class="wintitle"> DCS</span>) in tempo reale. </li> 
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
   <td colname="col2"> <p>In base agli elementi precedenti, la popolazione totale per Segmento 1 è costituita da tre (3). </p> <p>In questo caso, la Regola Unione <span class="wintitle"> profili</span> utilizza tutti i dispositivi e le relative caratteristiche per stabilire la qualifica del segmento. Ciò significa che i dispositivi 1, 2 e 3 sono idonei per il segmento 1 e tutti e tre sono inclusi nella popolazione totale. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**I dispositivi idonei per un segmento sono dotati[!UICONTROL Profile Merge Rule]di un grafico dispositivo incluso nei[!UICONTROL Interactive]report,[!UICONTROL Overlap]nei report e nei[!UICONTROL Audience Optimization]report?**

No

>[!MORE_ LIKE_ THIS]
>
>* [Collegamento profilo](../features/profile-merge-rules/merge-rules-overview.md)

