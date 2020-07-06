---
description: Risposte alle domande comuni sulle Regole di unione profili e sul grafico dei dispositivi.
keywords: Organization ID
seo-description: Risposte alle domande comuni sulle Regole di unione profili e sul grafico dei dispositivi.
seo-title: Domande frequenti su regole di unione profili e grafico dei dispositivi
solution: Audience Manager
title: Domande frequenti su regole di unione profili e grafico dei dispositivi
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 86%

---


# Domande frequenti su regole di unione profili e grafico dei dispositivi {#profile-merge-rules-and-device-graph-faq}

Risposte alle domande comuni sulle Regole di unione profili e sul grafico dei dispositivi.

<!-- profile-merge-faq.xml -->

## Informazioni di base sul grafico dei dispositivi {#device-graph-basics}

**Cos’è un grafico dei dispositivi?**

Un grafico dei dispositivi è un set di mappature ID che definisce gruppi di dispositivi anonimi. Associa questi dispositivi a una persona o a una famiglia sulla base di elementi comuni nei segnali raccolti da ciascun dispositivo. Questi segnali aiutano a identificare i dispositivi a livello individuale o familiare.

 

**Cos’è un grafico dei dispositivi esterno?**

Un grafico dei dispositivi esterno è un qualsiasi grafico dei dispositivi in [!DNL Audience Manager] che non è stato creato esclusivamente dalle tue sorgenti di dati multi-dispositivo. Ad esempio, quando crei una [Regola di unione profili](../features/profile-merge-rules/merge-rules-start.md) e scegli le opzioni [!UICONTROL Co-op Device Graph] o grafico dei dispositivi di terze parti, stai lavorando con un grafico dei dispositivi esterno. Consulta [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Quali sono alcuni casi d’uso comuni per l’utilizzo di un grafico dei dispositivi esterno in una [!UICONTROL Profile Merge Rule]?**

L’obiettivo principale di utilizzare un grafico dei dispositivi in una [!UICONTROL Profile Merge Rule] è valutare e qualificare più dispositivi appartenenti a una singola persona o famiglia per un segmento specifico. Il segmento stesso può essere utilizzato per usi diversi, ad esempio per il targeting di un pubblico di potenziali clienti con un annuncio proposto da una DSP o per personalizzare l’esperienza di un cliente sul sito tramite una piattaforma di personalizzazione all’interno del sito. Consulta [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Audience Manager fornisce supporto globale per grafici dei dispositivi esterni?**

No. I grafici dei dispositivi esterni sono disponibili solo negli Stati Uniti e in Canada.

 

**Con quale frequenza vengono [!DNL Audience Manager] aggiorna i dati dei grafici dei dispositivi esterni?**

Una volta alla settimana.

 

## Grafici dei dispositivi e regole di unione profili {#device-graph-profile-merge-rules}

**In che modo [!DNL Audience Manager] utilizza un grafico dei dispositivi?**

In [!DNL Audience Manager], i grafici dei dispositivi vengono visualizzati come opzioni di configurazione quando [crei una Regola di unione profili](../features/profile-merge-rules/merge-rules-start.md). Attraverso le [!UICONTROL Profile Merge Rules], i grafici dei dispositivi aiutano [!DNL Audience Manager] a:

* Unire più profili dispositivo. Questo crea un singolo superset di caratteristiche.
* Valutare il superset di caratteristiche per la qualifica dei segmenti (anziché valutare singolarmente ciascun profilo dispositivo).
* Aggiungere dispositivi qualificati ai segmenti disponibili.

 

**Quante [!UICONTROL Profile Merge Rules] posso creare?**

Attualmente, puoi creare un massimo di 4 [!UICONTROL Profile Merge Rules]. La quarta Regola di unione profili ([!UICONTROL All Cross-Device Profiles]) è disponibile solo per i clienti che acquistano il componente aggiuntivo [!UICONTROL People-Based Destinations].

 

**Quanti profili dispositivo unisce e legge [!DNL Audience Manager] quando si utilizza un grafico dei dispositivi in una [!UICONTROL Profile Merge Rule]?**

Quando si qualifica un dispositivo per un segmento utilizzando una [!UICONTROL Profile Merge Rule], Audience Manager unisce e legge il profilo dispositivo corrente e un massimo di 99 altri profili dispositivo collegati dall’opzione grafico dei dispositivi selezionata.

 

**Quali dispositivi sono qualificati per un segmento quando si utilizza un grafico dei dispositivi in una [!UICONTROL Profile Merge Rule]?**

I dispositivi che [!DNL Audience Manager] unisce e legge sono gli stessi dispositivi qualificati per un segmento.

 

**dove può inviare [!DNL Audience Manager] i segmenti qualificati da una [!UICONTROL Profile Merge Rule] che utilizza un grafico dei dispositivi?**

[!DNL Audience Manager] può inviare i segmenti a una destinazione in file batch o in tempo reale.

 

## Segmenti, grafici dei dispositivi e regole di unione dei profili {#segments-device-graphs-rules}

**In che modo [!DNL Audience Manager] rimuove da un segmento un dispositivo quando non è più qualificato per tale segmento con una [!UICONTROL Profile Merge Rule] che utilizza un grafico dei dispositivi?**

Audience Manager unisce fino a 100 dispositivi durante la valutazione dei segmenti con una [!UICONTROL Profile Merge Rule] che utilizza un grafico dei dispositivi. Se viene emesso il segnale di rimozione dai segmenti, il dispositivo corrente e fino a 99 dispositivi aggiuntivi verranno rimossi dal segmento nella destinazione. Per ulteriori informazioni sulla rimozione dai segmenti, consulta [Profile Merge Rules and Device Un-Segmentation Processes](../features/profile-merge-rules/merge-rule-unsegment.md).

 

**Se una destinazione può rimuovere dispositivi dai segmenti, i dispositivi verranno rimossi dai segmenti dalle [!UICONTROL Profile Merge Rules] che utilizzano un grafico dei dispositivi?**

Sì. Vedi la spiegazione riportata sopra.

 

**Se creo un segmento con una [!UICONTROL Profile Merge Rule] che utilizza un grafico dei dispositivi e il segmento utilizza sia dati in tempo reale che dati onboarded, il segmento verrà aggiornato quando i dati onboarded cambiano?**

Sì.

 

**Le stime delle dimensioni dei segmenti includono i dispositivi qualificati per un segmento in base alle connessioni fornite da una [!UICONTROL Profile Merge Rule] che utilizza un’opzione del grafico dei dispositivi?**

No. Vedi le definizioni di [!UICONTROL Estimated Real-Time Population] e [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](https://docs.adobe.com/content/help/it-IT/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**[!UICONTROL Addressable Audiences] include i dispositivi qualificati per un segmento in base alle connessioni fornite da una [!UICONTROL Profile Merge Rule] che utilizza un’opzione del grafico dei dispositivi?**

Sì.

 

**Se un segmento utilizza una [!UICONTROL Profile Merge Rule] con [!UICONTROL No Cross-Device Profile] e le caratteristiche che qualificano i dispositivi per il segmento sono memorizzate solo sul profilo multi-dispositivo, la popolazione totale del segmento sarà 0?**

Sì. Audience Manager non conteggerà le caratteristiche memorizzate sul profilo multi-dispositivo nella valutazione del segmento quando la regola di unione profili è impostata su [!UICONTROL No Cross-Device Profile].

 

## Frequenza delle caratteristiche, grafici dei dispositivi e regole di unione profili {#trait-freq-device-rules}

**In che modo [!DNL Audience Manager] calcola la frequenza delle caratteristiche con una [!UICONTROL Profile Merge Rule] che utilizza un grafico dei dispositivi?**

La frequenza delle caratteristiche è definita dalla somma del numero di qualifiche per una caratteristica specifica in più dispositivi. Per comprendere meglio questo aspetto, osserva il seguente caso d’uso.

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Il dispositivo A e il dispositivo B sono collegati da un grafico dei dispositivi. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Hai una <span class="wintitle">regola di unione profili</span> che utilizza un’opzione del grafico dei dispositivi. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un singolo segmento (segmento 1) composto da una singola caratteristica (caratteristica 1), dove la caratteristica 1 ha una frequenza di 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Azioni</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> legge e unisce i profili dispositivo per i dispositivi A e B. Da ciò osserviamo che: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Il dispositivo A è qualificato per la caratteristica 1 tre volte. Ha una frequenza di 3 per la caratteristica 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Il dispositivo B è qualificato per la caratteristica 1 cinque volte. Ha una frequenza di 5 per la caratteristica 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> somma la frequenza per la caratteristica 1 e utilizza 8 (3 + 5 = 8) per decidere la qualifica per il segmento. Il dispositivo A e il dispositivo B sono qualificati per il segmento 1 poiché ha una frequenza di 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Rapporti, grafici dei dispositivi e regole di unione profili {#reports-device-graphs-rules}

**Posso visualizzare il numero di dispositivi raggiungibili da una [!UICONTROL Profile Merge Rule] che utilizza un grafico dei dispositivi?**

Sì. I report restituiscono i dati a livello della [!UICONTROL Profile Merge Rule]. I dati dei report vengono aggiornati quotidianamente. I dati si basano sui dispositivi visualizzati nel tuo account, non su quelli collegati da un grafico dei dispositivi. Consulta [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

 

**Posso visualizzare il numero di dispositivi qualificati per uno specifico segmento in *tempo reale* con [!UICONTROL Profile Merge Rules] che utilizzano un grafico dei dispositivi?**

Sì. La metrica di popolazione in tempo reale acquisisce le qualifiche dei segmenti per il dispositivo corrente (il dispositivo visualizzato in tempo reale) utilizzando i profili di tutti i dispositivi collegati da un grafico dei dispositivi.

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
   <td colname="col2"> <p>Supponiamo di avere: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Un segmento 1 generato secondo queste caratteristiche e logica di qualifica: segmento 1 = caratteristica A, caratteristica B e caratteristica C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 profili dispositivo: dispositivo 1 (dispositivo corrente), dispositivo 2 (grafico dei dispositivi), dispositivo 3 (grafico dei dispositivi). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Azioni</b> </p> </td> 
   <td colname="col2"> <p>Ogni caratteristica disponibile è associata a un dispositivo: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Dispositivo 1: caratteristica A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Dispositivo 2: caratteristica B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Dispositivo 3: caratteristica C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Dati gli elementi precedenti, la popolazione totale del segmento 1 è uno. </p> <p>In questo caso, la <span class="wintitle">regola di unione profili</span> utilizza tutti i dispositivi e le loro caratteristiche per decidere la qualifica del segmento. Ciò significa che i dispositivi 1, 2 e 3 sono qualificati per il segmento 1, ma, come indicato in precedenza, solo il dispositivo 1 è incluso nella popolazione in tempo reale del segmento. Ciò è dovuto al fatto che: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Il dispositivo 1 è il dispositivo corrente che interagisce con i <span class="wintitle">server di raccolta dati</span> (<span class="wintitle">DCS</span>, Data Collection Servers) di Audience Manager in tempo reale. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">I dispositivi 2 e 3 sono associati al dispositivo 1 da un grafico dei dispositivi, ma non interagiscono con i DCS contemporaneamente al dispositivo 1. </li> 
     </ul> </p> <p>Di conseguenza, i dispositivi 2 e 3 non sono inclusi nella metrica di popolazione del segmento in tempo reale. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Posso visualizzare il numero totale di dispositivi qualificati per un segmento specifico con una [!UICONTROL Profile Merge Rule] che utilizza un grafico dei dispositivi?**

Sì. La metrica della popolazione totale del segmento include i dispositivi aggiuntivi che si sono qualificati per un segmento in base alle connessioni di un grafico dei dispositivi.

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
   <td colname="col2"> <p>Supponiamo di avere: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Un segmento 1 generato secondo queste caratteristiche e logica di qualifica: segmento 1 = caratteristica A, caratteristica B e caratteristica C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 profili dispositivo: dispositivo 1 (dispositivo corrente), dispositivo 2 (grafico dei dispositivi), dispositivo 3 (grafico dei dispositivi). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associazioni</b> </p> </td> 
   <td colname="col2"> <p>Ogni caratteristica disponibile è associata a un dispositivo: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Dispositivo 1: caratteristica A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Dispositivo 2: caratteristica B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Dispositivo 3: caratteristica C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Dati gli elementi precedenti, la popolazione totale per il segmento 1 è tre (3). </p> <p>In questo caso, la <span class="wintitle">regola di unione profili</span> utilizza tutti i dispositivi e le loro caratteristiche per decidere la qualifica del segmento. Ciò significa che i dispositivi 1, 2 e 3 sono qualificati per il segmento 1 e che tutti e tre sono inclusi nella popolazione totale. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**I dispositivi idonei per un segmento con una [!UICONTROL Profile Merge Rule] che utilizza un grafico dei dispositivi sono inclusi nei report [!UICONTROL Interactive], nei report [!UICONTROL Overlap] e nei report [!UICONTROL Audience Optimization]?**

No.

**Perché vedo una popolazione di segmento pari a zero per le esportazioni di segmenti  Adobe Campaign dopo il 16 marzo 2020?**

Alla fine del 2019, è disponibile una serie di miglioramenti delle regole di unione dei profili per migliorare la precisione dei file batch generati utilizzando ID cross-device. Questi miglioramenti saranno rigorosamente rispettati nell&#39;istanza di Audience Manager  a partire da lunedì 16 marzo 2020. Di conseguenza, i segmenti mappati a una destinazione utilizzando ID cross-device cesseranno di produrre esportazioni in alcune configurazioni di regole di unione profilo.

Per garantire la corretta integrazione tra l&#39;istanza  Audience Manager e le destinazioni utilizzando ID cross-device, come  Adobe Campaign, accertatevi di soddisfare i seguenti requisiti:

1. Controlla la regola di unione dei profili utilizzata dai segmenti mappati alla destinazione ID dichiarata del Adobe Campaign . La regola di unione dei profili deve utilizzare l&#39; [!UICONTROL Last Authenticated Profile] opzione, in modo che tutti i profili autenticati possano essere inclusi nelle esportazioni. Se la regola di unione dei profili utilizza un&#39;altra opzione, selezionatela [!UICONTROL Last Authenticated Profile].
2. Seleziona l&#39;origine dati ID dichiarato del Adobe Campaign  nelle impostazioni Regola unione profilo.

>[!NOTE]
>
> È stato aumentato il limite della regola di unione profilo di 1 per i clienti che si trovano in questa situazione, in modo da poter creare una regola di unione profilo dedicata per i segmenti mappati alla destinazione ID dichiarata del Adobe Campaign , senza modificare le regole di unione profilo per altri casi di utilizzo.

>[!MORELIKETHIS]
>
>* [Collegamento profilo](../features/profile-merge-rules/profile-link-use-case.md)

