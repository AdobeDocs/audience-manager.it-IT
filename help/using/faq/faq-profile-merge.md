---
description: Risposte alle domande più comuni sulla regola di unione dei profili e sul grafico del dispositivo.
keywords: Organization ID
seo-description: Risposte alle domande più comuni sulla regola di unione dei profili e sul grafico del dispositivo.
seo-title: Domande frequenti su Regole di unione dei profili e Device Graph
solution: Audience Manager
title: Domande frequenti su Regole di unione dei profili e Device Graph
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: 6876ca5ee0bc5f50c2aa1acd5c683b151a07fd59
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 2%

---


# Domande frequenti su Regole di unione dei profili e Device Graph{#profile-merge-rules-and-device-graph-faq}

Risposte alle domande più comuni sulla regola di unione dei profili e sul grafico del dispositivo.

<!-- profile-merge-faq.xml -->

## Device Graph Basics {#device-graph-basics}

**Cos&#39;è un grafico del dispositivo?**

Un grafico del dispositivo è un set di mappature ID che definisce i gruppi di dispositivi anonimi. Associa questi dispositivi a una persona o a una famiglia sulla base di elementi comuni nei segnali raccolti da ciascun dispositivo. Questi segnali aiutano a identificare i dispositivi a livello individuale o familiare.

 

**Cos’è un grafico per dispositivi esterni?**

Un grafico per dispositivi esterni è un qualsiasi grafico per dispositivi in [!DNL Audience Manager] cui non è stato creato esclusivamente da origini dati cross-device personalizzate. Ad esempio, quando create una regola [di unione](../features/profile-merge-rules/merge-rules-start.md) profilo e scegliete le opzioni per il grafico del dispositivo [!UICONTROL Co-op Device Graph] o di terze parti, state lavorando con un grafico del dispositivo esterno. Consulta Opzioni [](../features/profile-merge-rules/merge-rule-definitions.md#device-options)dispositivo.

 

**Quali sono alcuni casi d’uso comuni per l’utilizzo di un grafico di dispositivi esterni in un[!UICONTROL Profile Merge Rule]?**

L&#39;obiettivo principale di utilizzare un grafico del dispositivo in un [!UICONTROL Profile Merge Rule] segmento è valutare e qualificare più dispositivi appartenenti a una singola persona o famiglia per un segmento specifico. Il segmento stesso può essere utilizzato per più usi, ad esempio per un pubblico di potenziali clienti con un annuncio pubblicato da un DSP o per personalizzare l&#39;esperienza in loco di un cliente tramite una piattaforma di personalizzazione in loco. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Audience Manager fornisce supporto globale per grafici per dispositivi esterni?**

No. I grafici dei dispositivi esterni sono disponibili solo negli Stati Uniti e in Canada.

 

**Con quale frequenza vengono[!DNL Audience Manager]aggiornati i dati del grafico per dispositivi esterni?**

Una volta alla settimana.

 

## Grafici dispositivo e regole di unione profilo {#device-graph-profile-merge-rules}

**Come si[!DNL Audience Manager]utilizza un grafico del dispositivo?**

In [!DNL Audience Manager]questi grafici vengono visualizzati come opzioni di configurazione quando si [crea una regola](../features/profile-merge-rules/merge-rules-start.md)di unione dei profili. I grafici [!UICONTROL Profile Merge Rules]dei dispositivi consentono di [!DNL Audience Manager]:

* Unisci più profili dispositivo. Questo crea un singolo superset di caratteristiche.
* Valutare la caratteristica del superset per la qualifica del segmento (anziché valutare singolarmente ciascun profilo dispositivo).
* Aggiungi dispositivi qualificati ai segmenti disponibili.

 

**Quanti[!UICONTROL Profile Merge Rules]posso creare?**

Attualmente, potete creare un massimo di 4 [!UICONTROL Profile Merge Rules]. La quarta regola di unione dei profili ([!UICONTROL All Cross-Device Profiles]) è disponibile solo per i clienti che acquistano il [!UICONTROL People-Based Destinations] componente aggiuntivo.

 

**Quanti profili dispositivo vengono[!DNL Audience Manager]uniti e letti quando si utilizza un grafico del dispositivo in un[!UICONTROL Profile Merge Rule]?**

Quando si qualifica un dispositivo per un segmento utilizzando un [!UICONTROL Profile Merge Rule], Audience Manager unisce e legge il profilo del dispositivo corrente e un massimo di 99 altri profili dispositivo collegati dall&#39;opzione di grafico del dispositivo selezionata.

 

**Quali dispositivi sono idonei per un segmento quando si utilizza un grafico del dispositivo in un[!UICONTROL Profile Merge Rule]?**

Le [!DNL Audience Manager] unioni e le letture dei dispositivi sono gli stessi dispositivi idonei per un segmento.

 

**Dove è possibile[!DNL Audience Manager]inviare segmenti qualificati da un[!UICONTROL Profile Merge Rule]grafico del dispositivo?**

[!DNL Audience Manager] può inviare segmenti a una destinazione in file batch o in tempo reale.

 

## Segmenti, grafici dispositivo e regole di unione dei profili {#segments-device-graphs-rules}

**In che modo[!DNL Audience Manager]non segmentare un dispositivo quando non è più qualificato per un segmento con un grafico[!UICONTROL Profile Merge Rule]di dispositivi?**

Audience Manager unisce fino a 100 dispositivi durante la valutazione dei segmenti con un grafico [!UICONTROL Profile Merge Rule] che utilizza un dispositivo. Se viene emesso il segnale di dissegmento, il dispositivo corrente e fino a 99 dispositivi aggiuntivi verranno rimossi dal segmento nella destinazione. Per ulteriori informazioni sull&#39;annullamento della segmentazione, consulta Regole di unione [profilo e Processi](../features/profile-merge-rules/merge-rule-unsegment.md)di annullamento della segmentazione del dispositivo.

 

**Se una destinazione può separare i dispositivi, i dispositivi verranno rimossi dai segmenti[!UICONTROL Profile Merge Rules]che utilizzano un grafico del dispositivo?**

Sì. Vedere la spiegazione precedente.

 

**Se creo un segmento con un grafico[!UICONTROL Profile Merge Rule]che utilizza un dispositivo e il segmento utilizza sia dati in tempo reale che dati caricati, il mio segmento verrà aggiornato come i dati caricati cambiano?**

Sì. 

 

**Le stime delle dimensioni del segmento includono i dispositivi idonei per un segmento in base alle connessioni fornite da un[!UICONTROL Profile Merge Rule]utente che utilizza un&#39;opzione di grafico del dispositivo?**

No. Vedi le definizioni per [!UICONTROL Estimated Real-Time Population] e [!UICONTROL Estimated Total Population] in Dati [caratteristiche e popolazione segmenti in Generatore](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html)segmenti.

 

**Sono[!UICONTROL Addressable Audiences]inclusi i dispositivi idonei per un segmento in base alle connessioni fornite da un[!UICONTROL Profile Merge Rule]utente che utilizza un&#39;opzione di grafico del dispositivo?**

Sì. 

 

**Se un segmento utilizza un[!UICONTROL Profile Merge Rule]con[!UICONTROL No Cross-Device Profile]e le caratteristiche che qualificano i dispositivi per il segmento sono memorizzate solo nel profilo cross-device, la popolazione totale del segmento sarà 0?**

Sì. Audience Manager non conteggerà le caratteristiche memorizzate nel profilo cross-device nella valutazione del segmento quando la regola di unione dei profili è impostata su [!UICONTROL No Cross-Device Profile].

 

## Caratteristiche Frequenza, Grafici dispositivo e Regole di unione profilo {#trait-freq-device-rules}

**Come si calcola[!DNL Audience Manager]la frequenza delle caratteristiche con un[!UICONTROL Profile Merge Rule]grafico del dispositivo?**

La frequenza delle caratteristiche è definita dalla somma del numero di qualifiche per una caratteristica specifica su più dispositivi. Per comprendere meglio questo aspetto, consulta i seguenti casi di utilizzo.

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
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Avete una regola <span class="wintitle"></span> di unione profilo che utilizza un'opzione per il grafico del dispositivo. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un singolo segmento (segmento 1) composto da un unico tratto (caratteristica 1), dove il tratto 1 ha una frequenza di 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Azioni</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> legge e unisce i profili dei dispositivi per i dispositivi A e B. Di seguito sono riportati i seguenti elementi: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Il dispositivo A è qualificato per la caratteristica 1 tre volte. Ha una frequenza di 3 per la caratteristica 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Il dispositivo B è qualificato per la caratteristica 1 cinque volte. Ha una frequenza di 5 per la caratteristica 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> somma la frequenza per la caratteristica 1 e utilizza 8 (3 + 5 = 8) per decidere la qualifica del segmento. Il dispositivo A e il dispositivo B sono idonei per il segmento 1 perché ha una frequenza di 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Report, grafici dispositivo e regole di unione dei profili {#reports-device-graphs-rules}

**È possibile visualizzare il numero di dispositivi raggiungibili da un[!UICONTROL Profile Merge Rule]grafico di dispositivi?**

Sì. I report restituiscono i dati a [!UICONTROL Profile Merge Rule] livello. I dati del rapporto vengono aggiornati ogni giorno. I dati si basano sui dispositivi visualizzati nel tuo account, non su quelli collegati da un grafico del dispositivo. Consulta Metriche [report per le regole](../features/profile-merge-rules/profile-link-metrics.md)di unione dei profili.

 

**Posso visualizzare il numero di dispositivi idonei per uno specifico segmento in tempo **reale con[!UICONTROL Profile Merge Rules]cui viene utilizzato un grafico del dispositivo?**

Sì. La metrica popolazione in tempo reale acquisisce le qualifiche del segmento per il dispositivo corrente (il dispositivo visualizzato in tempo reale) utilizzando i profili di tutti i dispositivi collegati da un grafico del dispositivo.

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
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segmento 1 basato su queste caratteristiche e logica di qualifica: Segmento 1 = caratteristica A e caratteristica B e caratteristica C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 profili dispositivo: Dispositivo 1 (dispositivo corrente), Dispositivo 2 (grafico del dispositivo), Dispositivo 3 (grafico del dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Azioni</b> </p> </td> 
   <td colname="col2"> <p>Ogni caratteristica disponibile è associata a un dispositivo: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Dispositivo 1: Caratteristica A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Dispositivo 2: Caratteristica B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Dispositivo 3: Traccia C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Dati gli elementi precedenti, la popolazione totale per il segmento 1 è una. </p> <p>In questo caso, la regola <span class="wintitle"></span> Unione profilo utilizza tutti i dispositivi e le loro caratteristiche per decidere la qualifica del segmento. Ciò significa che i dispositivi 1, 2 e 3 sono idonei per il segmento 1, ma, come indicato in precedenza, solo il dispositivo 1 è incluso nella popolazione del segmento in tempo reale. Ciò è dovuto al fatto che: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 è il dispositivo corrente che interagisce con i server <span class="wintitle"> di raccolta dati di Audience Manager (</span> DCS<span class="wintitle"></span>) in tempo reale. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">I dispositivi 2 e 3 sono associati al Dispositivo 1 da un grafico del dispositivo ma non interagiscono con il DCS contemporaneamente al Dispositivo 1. </li> 
     </ul> </p> <p>Di conseguenza, i dispositivi 2 e 3 non sono inclusi nella metrica popolazione del segmento in tempo reale. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Posso visualizzare il numero totale di dispositivi idonei per un segmento specifico con un[!UICONTROL Profile Merge Rule]grafico del dispositivo?**

Sì. La metrica della popolazione totale del segmento include i dispositivi aggiuntivi che si sono qualificati per un segmento in base alle connessioni da un grafico del dispositivo.

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
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segmento 1 basato su queste caratteristiche e logica di qualifica: Segmento 1 = caratteristica A e caratteristica B e caratteristica C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 profili dispositivo: Dispositivo 1 (dispositivo corrente), Dispositivo 2 (grafico del dispositivo), Dispositivo 3 (grafico del dispositivo). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associazioni</b> </p> </td> 
   <td colname="col2"> <p>Ogni caratteristica disponibile è associata a un dispositivo: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Dispositivo 1: Caratteristica A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Dispositivo 2: Caratteristica B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Dispositivo 3: Traccia C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Risultati</b> </p> </td> 
   <td colname="col2"> <p>Dati gli elementi precedenti, la popolazione totale per il segmento 1 è tre (3). </p> <p>In questo caso, la regola <span class="wintitle"></span> Unione profilo utilizza tutti i dispositivi e le loro caratteristiche per decidere la qualifica del segmento. Ciò significa che i dispositivi 1, 2 e 3 sono idonei per il segmento 1 e che tutti e tre sono inclusi nella popolazione totale. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**I dispositivi idonei per un segmento con un[!UICONTROL Profile Merge Rule]grafico del dispositivo sono inclusi nei[!UICONTROL Interactive]report, nei[!UICONTROL Overlap]report e nei[!UICONTROL Audience Optimization]report?**

No.

**Perché visualizzo una popolazione di segmento pari a zero per le esportazioni di segmenti in Adobe Campaign dopo il 16 marzo 2020?**

Alla fine del 2019, è disponibile una serie di miglioramenti delle regole di unione dei profili per migliorare la precisione dei file batch generati utilizzando ID cross-device. Questi miglioramenti verranno rispettati in modo rigoroso nell’istanza di Audience Manager a partire da lunedì 16 marzo 2020. Di conseguenza, i segmenti mappati a una destinazione utilizzando ID cross-device cesseranno di produrre esportazioni in alcune configurazioni di regole di unione profilo.

Per garantire la corretta integrazione tra l’istanza e le destinazioni di Audience Manager utilizzando ID cross-device, come Adobe Campaign, accertati di soddisfare i seguenti requisiti:

1. Controlla la regola di unione dei profili utilizzata dai segmenti mappati alla destinazione ID dichiarato di Adobe Campaign. La regola di unione dei profili deve utilizzare l&#39; [!UICONTROL Last Authenticated Profile] opzione, in modo che tutti i profili autenticati possano essere inclusi nelle esportazioni. Se la regola di unione dei profili utilizza un&#39;altra opzione, selezionatela [!UICONTROL Last Authenticated Profile].
2. Seleziona l&#39;origine dati ID dichiarato di Adobe Campaign nelle impostazioni Regola unione profilo.

>[!NOTE]
>
> Per i clienti che si trovano in questa situazione è stato aumentato il limite della regola di unione profilo di 1, in modo da poter creare una regola di unione profilo dedicata per i segmenti mappati alla destinazione ID dichiarata di Adobe Campaign, senza modificare le regole di unione profilo per altri casi di utilizzo.

>[!MORELIKETHIS]
>
>* [Collegamento profilo](../features/profile-merge-rules/profile-link-use-case.md)

