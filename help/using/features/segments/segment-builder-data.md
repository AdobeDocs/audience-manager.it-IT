---
description: Aggiungi e rimuovi caratteristiche in Segment Builder (Generatore di segmenti) per visualizzare le popolazioni di caratteristiche effettive insieme ai dati sulla popolazione di segmenti effettiva e stimata. I dati sulle dimensioni stimate della popolazione ti aiutano a creare il segmento giusto per la campagna.
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: Dati sulle caratteristiche e sulle popolazioni dei segmenti nel Generatore di segmenti
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 1%

---

# [!UICONTROL Trait] e [!UICONTROL Segment] Dati sulla popolazione in [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Aggiungere e rimuovere [!UICONTROL traits] in [!UICONTROL Segment Builder] per visualizzare i valori effettivi [!UICONTROL trait] popolazioni insieme ai dati di popolazione del segmento effettivi e stimati. I dati sulle dimensioni stimate della popolazione ti aiutano a creare il segmento giusto per la campagna.

## [!UICONTROL Trait] Dati popolazione {#trait-population-data}

[!UICONTROL Segment Builder] mostra [!UICONTROL Total Trait Population] per l&#39;ultimo giorno in cui si aggiunge [!UICONTROL trait] a un segmento. Questi dati vengono visualizzati nel campo blu intorno al campo selezionato [!UICONTROL trait] nel [!UICONTROL Basic View] sezione.

![](assets/trait-size.png)

La tabella seguente definisce le metriche di popolazione delle caratteristiche:


| Metrica | Descrizione |
|---------|----------|
| [!UICONTROL Total Trait Population] | Il numero di ID univoci con la caratteristica selezionata nel profilo. |


## Calcolo delle popolazioni di segmenti reali e stimate {#calculating-real-estimated-populations}

Quando crei un nuovo segmento o ne modifichi uno esistente, in Audience Manager sono necessarie fino a 24 ore per visualizzare i risultati in tempo reale e per le popolazioni di segmenti totali.

Tuttavia, Audience Manager può stimare immediatamente la dimensione di popolazione totale e in tempo reale del segmento. Queste stime si basano su dati storici campionati e restituiscono risultati con un intervallo di confidenza del 95%.

![](assets/confidence-interval.png)

In entrata [!UICONTROL Segment Builder], una barra blu sui grafici della popolazione stimata indica i possibili intervalli superiori e inferiori per la dimensione del segmento. Anche se le prestazioni passate non garantiscono risultati futuri, i dati stimati possono essere utili per comprendere le dimensioni potenziali di un segmento nuovo o modificato.

## Panoramica dei dati sulla popolazione dei segmenti {#segment-populations}

[!UICONTROL Segment Builder] mostra i dati sulla popolazione dei segmenti durante la creazione e la modifica dei segmenti.

* per i dati stimati sulla popolazione del segmento (in tempo reale e totale), [!UICONTROL Segment Builder] non aggiorna i grafici automaticamente quando aggiungi o rimuovi caratteristiche in un segmento. Clic **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati.

* Per i dati sulla popolazione del segmento effettivo (reale) (in tempo reale e totale): [!UICONTROL Segment Builder] aggiorna automaticamente il grafico dei segmenti quando carichi un segmento esistente. Per i nuovi segmenti o quando aggiungi nuove caratteristiche a un segmento esistente, i dati della popolazione effettiva non vengono aggiornati fino a 24 ore dopo la creazione del segmento.

![](assets/segment-data.png)

Per ulteriori informazioni sui dati stimati ed effettivi sulla popolazione del segmento, consulta le definizioni riportate di seguito.

## Definizione dei dati della popolazione stimata del segmento {#estimated-segment-population}

La tabella seguente definisce le metriche di popolazione stimate.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione In Tempo Reale Stimata (Potenziale) </span> </p> </td> 
   <td colname="col2"> <p>Il numero stimato di visitatori univoci visualizzati in tempo reale per l’intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti dagli Audienci Manager. </p> <p>In entrata <span class="wintitle"> Generatore di segmenti</span>, le popolazioni degli ultimi 30 giorni per le caratteristiche (<span class="wintitle"> Popolazioni di caratteristiche totali</span>), può essere diverso per caratteristiche e segmenti valutati in tempo reale. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Per le caratteristiche, l’ultima metrica di 30 giorni conta il numero di utenti univoci che si sono qualificati per quella caratteristica negli ultimi 30 giorni. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Per i segmenti valutati in tempo reale, l’ultima metrica di 30 giorni conta il numero di utenti che si sono qualificati per una caratteristica (in quel segmento) in passato e che sono stati nuovamente visti per Audience Manager negli ultimi 30 giorni. Ad esempio, supponiamo che un utente si sia qualificato per una caratteristica 60 giorni fa ed sia stato nuovamente visitato 10 giorni fa. Nei dati, questo utente non verrà aggiunto al conteggio delle caratteristiche perché per la prima volta si è qualificato per la caratteristica più di 30 giorni fa. Tuttavia, saranno incluse nel conteggio degli ultimi 30 giorni per i segmenti valutati in tempo reale. Questo perché si sono qualificati per il segmento entro l’intervallo di tempo di 30 giorni. </li>
     </ul> </p> <p> <p>Nota: il <span class="wintitle"> Popolazione in tempo reale stimata</span> La metrica non include i dispositivi qualificati per un segmento in base alle connessioni fornite da una <span class="wintitle"> Regola di unione profili</span> che utilizza un <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> opzione device graph</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione Totale Stimata (Potenziale)</span> </p> </td> 
   <td colname="col2"> <p>Il numero stimato di visitatori univoci che potrebbero trovarsi nel segmento nuovo o modificato. Come per quasi tutte le stime, le prestazioni passate non garantiscono risultati futuri, ma puoi utilizzare il totale stimato per: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Scopri quante persone potrebbe raggiungere un segmento nuovo o modificato durante la creazione di un segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Regola il segmento in base agli obiettivi. Ad esempio, i segmenti di grandi dimensioni sono utili per le campagne di brand awareness, mentre i segmenti più piccoli sono utili per campagne di targeting o re-targeting mirate. </li> 
     </ul> </p> <p> <p>Nota: il <span class="wintitle"> Popolazione totale stimata</span> La metrica non include i dispositivi qualificati per un segmento in base alle connessioni fornite da una <span class="wintitle"> Regola di unione profili</span> che utilizza un <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> opzione device graph</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dati di popolazione del segmento esistenti (effettivi) definiti {#existing-segment-population}

[!UICONTROL Profile Merge Rules] influenzano i numeri effettivi in tempo reale e di popolazione totale. Questi totali variano a seconda che [!UICONTROL Profile Merge Rule] un segmento appartiene a utilizza o meno un’opzione del grafico dei dispositivi. Vedi anche, [Definizione delle opzioni delle regole di unione profili](../../features/profile-merge-rules/merge-rule-definitions.md).

### Dati sulla popolazione del segmento per [!UICONTROL Merge Rules] Senza un [!UICONTROL Device Graph Option]

La tabella seguente definisce le metriche di popolazione effettive, in tempo reale e totali, quando i segmenti vengono utilizzati da un [!UICONTROL Profile Merge Rule] creato senza [!UICONTROL device graph] opzione. Queste sono le impostazioni delle opzioni dispositivo **[!UICONTROL No Device Options]** e **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione in tempo reale (esistente)</span> </p> </td> 
   <td colname="col2"> <p>Il numero effettivo di visitatori univoci visualizzati in tempo reale per l’intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti dagli Audienci Manager. </p> <p>In entrata <span class="wintitle"> Generatore di segmenti</span>, le popolazioni degli ultimi 30 giorni per le caratteristiche (<span class="wintitle"> Popolazioni di caratteristiche totali</span>), può essere diverso per caratteristiche e segmenti valutati in tempo reale. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Per le caratteristiche, l’ultima metrica di 30 giorni conta il numero di utenti univoci che si sono qualificati per quella caratteristica negli ultimi 30 giorni. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Per i segmenti valutati in tempo reale, l’ultima metrica di 30 giorni conta il numero di utenti che si sono qualificati per una caratteristica (in quel segmento) in passato e che sono stati nuovamente visti per Audience Manager negli ultimi 30 giorni. Ad esempio, supponiamo che un utente si sia qualificato per una caratteristica 60 giorni fa ed sia stato nuovamente visitato 10 giorni fa. Nei dati, questo utente non verrà aggiunto al conteggio delle caratteristiche perché per la prima volta si è qualificato per la caratteristica più di 30 giorni fa. Tuttavia, saranno incluse nel conteggio degli ultimi 30 giorni per i segmenti valutati in tempo reale. Questo perché si sono qualificati per il segmento entro l’intervallo di tempo di 30 giorni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione totale (esistente)</span> </p> </td> 
   <td colname="col2"> <p>Il numero effettivo di visitatori univoci qualificati per il segmento al momento di ieri. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Dati sulla popolazione del segmento per [!UICONTROL Merge Rules] Con un [!UICONTROL Device Graph] Opzione

La tabella seguente definisce le metriche di popolazione effettive, in tempo reale e totali, quando i segmenti vengono utilizzati da un [!UICONTROL Profile Merge Rule] creato con un [!DNL device graph] opzione. Queste sono le impostazioni delle opzioni del dispositivo per [!UICONTROL Profile Link Device Graph], il [!DNL Adobe] [!DNL device graph], e altri terzi [!DNL device graph] le opzioni disponibili.


| Colonna A | Colonna B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | Il numero effettivo di dispositivi visualizzati in tempo reale con i profili correnti che, quando uniti a un massimo di 100 altri profili di dispositivi connessi dal grafico dei dispositivi, contengono le caratteristiche da qualificare per il segmento nel momento in cui è stato visto da Audience Manager. |
| [!UICONTROL Total Population (Existing)] | Il numero totale di dispositivi con profili che, quando uniti a un massimo di 100 altri profili dispositivo connessi dal grafico dei dispositivi, erano tutti qualificati per il segmento. |

### Limitazioni dovute alle espressioni di frequenza e recency nella stima delle popolazioni dei segmenti

[!UICONTROL Segment Builder] supporta le stime delle dimensioni dei segmenti per le regole dei segmenti che contengono fino a 4 espressioni di attualità e frequenza. Se si scelgono più di 4 espressioni di attualità e frequenza durante la creazione di una regola di segmento, il calcolatore del segmento mostra un errore durante la stima della popolazione.

### Limitazioni dovute a [!UICONTROL Merge Rules] Durante La Stima Delle Popolazioni Dei Segmenti

Attualmente, esiste un limite noto perché il nostro stimatore delle dimensioni del segmento non tiene conto di [!UICONTROL profile merge rules]. Ad esempio, osserva i segmenti con **[!UICONTROL No Authenticated Profile + Current Device Profile]** [regola di unione](../../features/profile-merge-rules/merge-rule-definitions.md). A causa del modo in cui attualmente calcoliamo i numeri di stima del segmento, le popolazioni stimate includeranno profili autenticati. Tuttavia, le popolazioni dei segmenti esistenti ignoreranno correttamente i profili autenticati.

>[!MORELIKETHIS]
>
>* [Domande frequenti su regole di unione profili e grafico dei dispositivi](../../faq/faq-profile-merge.md)
>* [Collegamento profilo](../profile-merge-rules/merge-rules-overview.md)

