---
description: Aggiungi e rimuovi caratteristiche in Segment Builder (Generatore di segmenti) per visualizzare le popolazioni di caratteristiche effettive insieme ai dati sulla popolazione effettiva e stimata del segmento. I dati stimati sulla dimensione della popolazione consentono di creare il segmento giusto per la campagna.
seo-description: Aggiungi e rimuovi caratteristiche in Segment Builder (Generatore di segmenti) per visualizzare le popolazioni di caratteristiche effettive insieme ai dati sulla popolazione effettiva e stimata del segmento. I dati stimati sulla dimensione della popolazione consentono di creare il segmento giusto per la campagna.
seo-title: Dati sulle caratteristiche e sulle popolazioni dei segmenti nel Generatore di segmenti
solution: Audience Manager
title: Dati sulle caratteristiche e sulle popolazioni dei segmenti nel Generatore di segmenti
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---


# [!UICONTROL Trait] e dati sulla  [!UICONTROL Segment] popolazione in  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Aggiungete e rimuovete [!UICONTROL traits] in [!UICONTROL Segment Builder] per visualizzare le popolazioni effettive [!UICONTROL trait] insieme ai dati effettivi e stimati sulla popolazione dei segmenti. I dati stimati sulla dimensione della popolazione consentono di creare il segmento giusto per la campagna.

## [!UICONTROL Trait] Dati popolazione  {#trait-population-data}

[!UICONTROL Segment Builder] viene visualizzato  [!UICONTROL Total Trait Population] per l’ultimo giorno in cui si aggiunge un segmento  [!UICONTROL trait] a un segmento. Questi dati vengono visualizzati nel campo blu intorno alla [!UICONTROL trait] selezionata nella sezione [!UICONTROL Basic View].

![](assets/trait-size.png)

La tabella seguente definisce le metriche della popolazione delle caratteristiche:


| Metrica | Descrizione |
---------|----------|
| [!UICONTROL Total Trait Population] | Numero di ID univoci con la caratteristica selezionata nel relativo profilo. |


## Calcolo delle popolazioni di segmenti reali e stimati {#calculating-real-estimated-populations}

Quando create un nuovo segmento o ne modificate uno esistente,  Audience Manager impiega fino a 24 ore per visualizzare i risultati per le popolazioni effettive di segmenti in tempo reale e totale.

Tuttavia,  Audience Manager può stimare immediatamente la dimensione della popolazione in tempo reale e totale del segmento. Tali stime si basano su dati storici campionati e su risultati di ritorno a un intervallo di confidenza del 95%.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], una barra blu sul grafico della popolazione stimata indica gli eventuali intervalli superiore e inferiore per la dimensione del segmento. Anche se le prestazioni passate non garantiscono risultati futuri, i dati stimati possono aiutarti a comprendere la dimensione potenziale di un segmento nuovo o modificato.

## Panoramica sulla popolazione dei segmenti {#segment-populations}

[!UICONTROL Segment Builder] mostra i dati sulla popolazione durante la creazione e la modifica dei segmenti.

* Per i dati sulla popolazione stimata del segmento (tempo reale e totale), [!UICONTROL Segment Builder] non aggiorna automaticamente i grafici quando si aggiungono o rimuovono caratteristiche in un segmento. Fare clic su **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati.

* Per i dati effettivi (reali) della popolazione del segmento (tempo reale e totale), [!UICONTROL Segment Builder] aggiorna automaticamente il grafico del segmento quando carichi un segmento esistente. Per i nuovi segmenti, o quando aggiungi nuove caratteristiche a un segmento esistente, i dati sulla popolazione effettiva non vengono aggiornati fino a 24 ore dopo la creazione del segmento.

![](assets/segment-data.png)

Per ulteriori informazioni sui dati sulla popolazione stimata e effettiva dei segmenti, vedi le definizioni riportate di seguito.

## Dati sulla popolazione di segmenti stimati {#estimated-segment-population}

La tabella seguente definisce le metriche della popolazione stimata.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione stimata in tempo reale (potenziale)  </span> </p> </td> 
   <td colname="col2"> <p>Numero stimato di visitatori univoci visti in tempo reale per l'intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti dal Audience Manager . </p> <p>In <span class="wintitle"> Segment Builder</span>, le ultime popolazioni di 30 giorni per le caratteristiche (<span class="wintitle"> Total Trait Populations</span>) possono essere diverse per le caratteristiche e i segmenti valutati in tempo reale. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Per le caratteristiche, l'ultima metrica di 30 giorni include il numero di utenti univoci che hanno acquisito la caratteristica in questione negli ultimi 30 giorni. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Per i segmenti valutati in tempo reale, l’ultima metrica di 30 giorni conta il numero di utenti che hanno acquisito le qualifiche per una caratteristica (in quel segmento) in un determinato momento nel passato e che sono stati visti di nuovo da  Audience Manager negli ultimi 30 giorni. Ad esempio, supponiamo che tu abbia un utente qualificato per una caratteristica 60 giorni fa e che sia stato nuovamente visto 10 giorni fa. Nei dati, l'utente non verrà aggiunto al conteggio delle caratteristiche perché è stato qualificato per la caratteristica più di 30 giorni fa. Tuttavia, saranno inclusi nell'ultimo conteggio di 30 giorni per i segmenti valutati in tempo reale. Questo perché sono qualificati per il segmento entro l'intervallo di 30 giorni. </li>
     </ul> </p> <p> <p>Nota: La metrica <span class="wintitle"> Popolazione stimata in tempo reale</span> non include dispositivi qualificati per un segmento in base alle connessioni fornite da una <span class="wintitle"> Regola di unione profilo</span> che utilizza un'opzione di grafico dispositivi <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione totale stimata (potenziale)</span> </p> </td> 
   <td colname="col2"> <p>Numero stimato di visitatori univoci che potrebbero essere nel segmento nuovo o modificato. Come per quasi tutte le stime, le prestazioni passate non garantiscono risultati futuri, ma potete utilizzare il totale stimato per: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Scopri quante persone potrebbe raggiungere un segmento nuovo o rivisto al momento della creazione di un segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Regola il segmento in base agli obiettivi. Ad esempio, i segmenti di grandi dimensioni sono utili per campagne di sensibilizzazione del marchio e i segmenti più piccoli sono utili per campagne di targeting mirate o di ridefinizione del targeting. </li> 
     </ul> </p> <p> <p>Nota: La metrica <span class="wintitle"> Popolazione totale stimata</span> non include dispositivi qualificati per un segmento in base alle connessioni fornite da una <span class="wintitle"> Regola di unione profilo</span> che utilizza un'opzione di grafico dispositivi <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dati sulla popolazione di segmenti esistenti (effettivi) definiti {#existing-segment-population}

[!UICONTROL Profile Merge Rules] influiscono sul numero effettivo di popolazione in tempo reale e totale. Questi totali variano a seconda che il [!UICONTROL Profile Merge Rule] segmento appartenga o meno a un&#39;opzione di grafico del dispositivo. Vedere anche, [Opzioni regole di unione profilo definite](../../features/profile-merge-rules/merge-rule-definitions.md).

### Dati popolazione segmento per [!UICONTROL Merge Rules] senza [!UICONTROL Device Graph Option]

La tabella seguente definisce le metriche effettive della popolazione in tempo reale e totale quando i segmenti vengono utilizzati da una [!UICONTROL Profile Merge Rule] creata senza un&#39;opzione [!UICONTROL device graph]. Queste sono le impostazioni delle opzioni del dispositivo **[!UICONTROL No Device Options]** e **[!UICONTROL Current Device Proflie]**.

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
   <td colname="col2"> <p>Il numero effettivo di visitatori univoci visti in tempo reale per l'intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti dal Audience Manager . </p> <p>In <span class="wintitle"> Segment Builder</span>, le ultime popolazioni di 30 giorni per le caratteristiche (<span class="wintitle"> Total Trait Populations</span>) possono essere diverse per le caratteristiche e i segmenti valutati in tempo reale. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Per le caratteristiche, l'ultima metrica di 30 giorni include il numero di utenti univoci che hanno acquisito la caratteristica in questione negli ultimi 30 giorni. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Per i segmenti valutati in tempo reale, l’ultima metrica di 30 giorni conta il numero di utenti che hanno acquisito le qualifiche per una caratteristica (in quel segmento) in un determinato momento nel passato e che sono stati visti di nuovo da  Audience Manager negli ultimi 30 giorni. Ad esempio, supponiamo che tu abbia un utente qualificato per una caratteristica 60 giorni fa e che sia stato nuovamente visto 10 giorni fa. Nei dati, l'utente non verrà aggiunto al conteggio delle caratteristiche perché è stato qualificato per la caratteristica più di 30 giorni fa. Tuttavia, saranno inclusi nell'ultimo conteggio di 30 giorni per i segmenti valutati in tempo reale. Questo perché sono qualificati per il segmento entro l'intervallo di 30 giorni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione totale (esistente)</span> </p> </td> 
   <td colname="col2"> <p>Numero effettivo di visitatori unici idonei per il segmento a partire da ieri. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Dati popolazione segmento per [!UICONTROL Merge Rules] con un&#39;opzione [!UICONTROL Device Graph]

La tabella seguente definisce le metriche effettive della popolazione in tempo reale e totale quando i segmenti vengono utilizzati da una [!UICONTROL Profile Merge Rule] creata con un&#39;opzione [!DNL device graph]. Queste sono le impostazioni delle opzioni del dispositivo per le scelte [!UICONTROL Profile Link Device Graph], [!DNL Adobe] [!DNL device graph] e di altre [!DNL device graph] di terze parti disponibili.


| Colonna A | Colonna B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | Il numero effettivo di dispositivi visti in tempo reale con i profili correnti che, se uniti con fino a 100 altri profili dispositivo collegati dal grafico del dispositivo, contengono le caratteristiche per qualificarsi per il segmento nel momento in cui è stato visto dal Audience Manager . |
| [!UICONTROL Total Population (Existing)] | Il numero totale di dispositivi con profili che, se uniti con un massimo di 100 altri profili dispositivo collegati dal grafico del dispositivo, erano tutti idonei per il segmento. |

### Limitazioni dovute a espressioni di aggiornamento e frequenza durante la stima delle popolazioni di segmenti

[!UICONTROL Segment Builder] supporta le stime delle dimensioni del segmento per le regole del segmento che contengono fino a 4 espressioni di recency e di frequenza. Se si scelgono più di 4 espressioni di recency e frequenza al momento della creazione di una regola di segmento, lo stimatore del segmento mostra un errore durante la stima della popolazione.

### Limitazioni dovute a [!UICONTROL Merge Rules] durante la stima della popolazione del segmento

Al momento esiste un limite noto perché il nostro stimatore delle dimensioni del segmento non tiene conto di [!UICONTROL profile merge rules]. Ad esempio, osservare i segmenti con la **[!UICONTROL No Authenticated Profile + Current Device Profile]** [regola di unione](../../features/profile-merge-rules/merge-rule-definitions.md). A causa del modo in cui attualmente calcoliamo i numeri di stima dei segmenti, le popolazioni stimate includeranno profili autenticati. Tuttavia, le popolazioni di segmenti esistenti ignoreranno correttamente i profili autenticati.

>[!MORELIKETHIS]
>
>* [Domande frequenti su regole di unione profili e grafico dei dispositivi](../../faq/faq-profile-merge.md)
>* [Collegamento profilo](../profile-merge-rules/merge-rules-overview.md)

