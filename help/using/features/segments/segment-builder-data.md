---
description: Aggiungi e rimuovi le caratteristiche nel Generatore di segmenti per visualizzare le popolazioni di caratteristiche effettive insieme ai dati sulla popolazione dei segmenti effettivi e stimati. I dati stimati sulle dimensioni della popolazione consentono di creare il segmento giusto per la campagna.
seo-description: Aggiungi e rimuovi le caratteristiche nel Generatore di segmenti per visualizzare le popolazioni di caratteristiche effettive insieme ai dati sulla popolazione dei segmenti effettivi e stimati. I dati stimati sulle dimensioni della popolazione consentono di creare il segmento giusto per la campagna.
seo-title: Dati sulle caratteristiche e sulle popolazioni dei segmenti nel Generatore di segmenti
solution: Audience Manager
title: Dati sulle caratteristiche e sulle popolazioni dei segmenti nel Generatore di segmenti
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: 'Segmenti '
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 2%

---

# [!UICONTROL Trait] e dati  [!UICONTROL Segment] sulla popolazione in  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Aggiungi e rimuovi [!UICONTROL traits] in [!UICONTROL Segment Builder] per visualizzare le popolazioni effettive [!UICONTROL trait] insieme ai dati sulla popolazione dei segmenti effettivi e stimati. I dati stimati sulle dimensioni della popolazione consentono di creare il segmento giusto per la campagna.

## [!UICONTROL Trait] Dati sulla popolazione  {#trait-population-data}

[!UICONTROL Segment Builder] ti mostra  [!UICONTROL Total Trait Population] per l’ultimo giorno in cui aggiungi una  [!UICONTROL trait] a un segmento. Questi dati vengono visualizzati nel campo blu intorno alla [!UICONTROL trait] selezionata nella sezione [!UICONTROL Basic View] .

![](assets/trait-size.png)

La tabella seguente definisce le metriche della popolazione delle caratteristiche:


| Metrica | Descrizione |
---------|----------|
| [!UICONTROL Total Trait Population] | Il numero di ID univoci con la caratteristica selezionata nel profilo. |


## Calcolo delle popolazioni di segmenti reali e stimate {#calculating-real-estimated-populations}

Quando crei un nuovo segmento o ne modifichi uno esistente, l’Audience Manager impiega fino a 24 ore per visualizzare i risultati per le popolazioni effettive di segmenti in tempo reale e totale.

Tuttavia, Audience Manager può stimare immediatamente la dimensione della popolazione in tempo reale e totale del segmento. Queste stime si basano su dati storici campionati e restituiscono risultati con un intervallo di affidabilità del 95%.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], una barra blu sui grafici della popolazione stimati indica gli eventuali intervalli superiori e inferiori per la dimensione del segmento. Anche se le prestazioni passate non garantiscono risultati futuri, i dati stimati possono aiutarti a comprendere le dimensioni potenziali di un segmento nuovo o modificato.

## Panoramica dei dati sulla popolazione dei segmenti {#segment-populations}

[!UICONTROL Segment Builder] mostra i dati della popolazione dei segmenti durante la creazione e la modifica dei segmenti.

* Per i dati sulla popolazione stimata del segmento (in tempo reale e totale), [!UICONTROL Segment Builder] non aggiorna automaticamente i grafici quando aggiungi o rimuovi caratteristiche in un segmento. Fai clic su **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati.

* Per i dati effettivi (reali) sulla popolazione del segmento (in tempo reale e totale), [!UICONTROL Segment Builder] aggiorna automaticamente il grafico del segmento quando carichi un segmento esistente. Per i nuovi segmenti o quando aggiungi nuove caratteristiche a un segmento esistente, i dati della popolazione effettiva non vengono aggiornati fino a 24 ore dopo la creazione del segmento.

![](assets/segment-data.png)

Per ulteriori informazioni sui dati sulla popolazione dei segmenti stimati ed effettivi, consulta le definizioni riportate di seguito.

## Dati sulla popolazione del segmento stimato {#estimated-segment-population}

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
   <td colname="col1"> <p> <span class="wintitle"> Popolazione in tempo reale stimata (potenziale)  </span> </p> </td> 
   <td colname="col2"> <p>Il numero stimato di visitatori unici visti in tempo reale per l’intervallo di tempo specificato e che sono stati qualificati per il segmento nel momento in cui sono stati visti dall’Audience Manager. </p> <p>In <span class="wintitle"> Generatore di segmenti</span>, le ultime popolazioni di caratteristiche per 30 giorni (<span class="wintitle"> Popolazioni di caratteristiche totali</span>) possono essere diverse per caratteristiche e segmenti valutati in tempo reale. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Per le caratteristiche, l’ultima metrica di 30 giorni conta il numero di utenti univoci che si sono qualificati per quella caratteristica negli ultimi 30 giorni. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Per i segmenti valutati in tempo reale, l’ultima metrica di 30 giorni conta il numero di utenti che si sono qualificati per una caratteristica (in quel segmento) ad un certo punto nel passato e che sono stati visti nuovamente per Audience Manager negli ultimi 30 giorni. Ad esempio, supponiamo che tu abbia un utente qualificato per una caratteristica 60 giorni fa e sia stato visto di nuovo 10 giorni fa. Nei dati, questo utente non verrà aggiunto al conteggio delle caratteristiche perché si è qualificato per la caratteristica per la prima volta più di 30 giorni fa. Tuttavia, saranno inclusi nell’ultimo conteggio di 30 giorni per i segmenti valutati in tempo reale. Questo perché si sono qualificati per il segmento entro l’intervallo di 30 giorni. </li>
     </ul> </p> <p> <p>Nota: La metrica <span class="wintitle"> Popolazione in tempo reale stimata</span> non include i dispositivi qualificati per un segmento in base alle connessioni fornite da una <span class="wintitle"> Regola di unione profili</span> che utilizza un'opzione <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> grafico dei dispositivi</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione totale stimata (potenziale)</span> </p> </td> 
   <td colname="col2"> <p>Numero stimato di visitatori unici che potrebbero trovarsi nel segmento nuovo o modificato. Come per quasi tutte le stime, le prestazioni passate non garantiscono risultati futuri, ma è possibile utilizzare il totale stimato per: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Scopri quante persone potrebbe raggiungere un segmento nuovo o rivisto durante la creazione di un segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ottimizza il segmento in base ai tuoi obiettivi. Ad esempio, i segmenti di grandi dimensioni sono utili per le campagne di brand awareness e i segmenti più piccoli sono utili per campagne di targeting mirate o di re-targeting. </li> 
     </ul> </p> <p> <p>Nota: La metrica <span class="wintitle"> Popolazione totale stimata</span> non include i dispositivi qualificati per un segmento in base alle connessioni fornite da una <span class="wintitle"> Regola di unione profili</span> che utilizza un'opzione <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> grafico dei dispositivi</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dati sulla popolazione del segmento esistenti (effettivi) definiti {#existing-segment-population}

[!UICONTROL Profile Merge Rules] influenzano i numeri effettivi della popolazione in tempo reale e totale. Questi totali variano a seconda che il [!UICONTROL Profile Merge Rule] segmento appartenga o meno a utilizzi un’opzione del grafico dei dispositivi. Vedi anche [Opzioni regola di unione profili definite](../../features/profile-merge-rules/merge-rule-definitions.md).

### Dati sulla popolazione del segmento per [!UICONTROL Merge Rules] senza un [!UICONTROL Device Graph Option]

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
   <td colname="col2"> <p>Il numero effettivo di visitatori unici visti in tempo reale per l’intervallo di tempo specificato e che sono stati qualificati per il segmento nel momento in cui sono stati visti dall’Audience Manager. </p> <p>In <span class="wintitle"> Generatore di segmenti</span>, le ultime popolazioni di 30 giorni per le caratteristiche (<span class="wintitle"> Popolazioni di caratteristiche totali</span>) possono essere diverse per le caratteristiche e i segmenti valutati in tempo reale. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Per le caratteristiche, l’ultima metrica di 30 giorni conta il numero di utenti univoci che si sono qualificati per quella caratteristica negli ultimi 30 giorni. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Per i segmenti valutati in tempo reale, l’ultima metrica di 30 giorni conta il numero di utenti che si sono qualificati per una caratteristica (in quel segmento) ad un certo punto nel passato e che sono stati visti nuovamente per Audience Manager negli ultimi 30 giorni. Ad esempio, supponiamo che tu abbia un utente qualificato per una caratteristica 60 giorni fa e sia stato visto di nuovo 10 giorni fa. Nei dati, questo utente non verrà aggiunto al conteggio delle caratteristiche perché si è qualificato per la caratteristica per la prima volta più di 30 giorni fa. Tuttavia, saranno inclusi nell’ultimo conteggio di 30 giorni per i segmenti valutati in tempo reale. Questo perché si sono qualificati per il segmento entro l’intervallo di 30 giorni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione totale (esistente)</span> </p> </td> 
   <td colname="col2"> <p>Il numero effettivo di visitatori unici qualificati per il segmento a partire da ieri. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Dati sulla popolazione del segmento per [!UICONTROL Merge Rules] con un&#39;opzione [!UICONTROL Device Graph]

La tabella seguente definisce le metriche effettive della popolazione in tempo reale e totale quando i segmenti vengono utilizzati da un [!UICONTROL Profile Merge Rule] creato con un&#39;opzione [!DNL device graph]. Queste sono le impostazioni delle opzioni del dispositivo per le scelte [!UICONTROL Profile Link Device Graph], [!DNL Adobe] [!DNL device graph] e di altre [!DNL device graph] di terze parti disponibili.


| Colonna A | Colonna B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | Il numero effettivo di dispositivi visualizzati in tempo reale con i profili correnti che, quando uniti con un massimo di 100 altri profili dispositivo collegati dal grafico dei dispositivi, contengono le caratteristiche per qualificarsi per il segmento nel momento in cui è stato visto dall’Audience Manager. |
| [!UICONTROL Total Population (Existing)] | Il numero totale di dispositivi con profili che, se uniti con un massimo di 100 altri profili dispositivo collegati dal grafico dei dispositivi, erano tutti qualificati per il segmento. |

### Limitazioni dovute a espressioni di aggiornamento e frequenza durante la stima delle popolazioni dei segmenti

[!UICONTROL Segment Builder] supporta le stime delle dimensioni del segmento per le regole del segmento che contengono fino a 4 espressioni di recency e frequenza. Se si scelgono più di 4 espressioni di aggiornamento e frequenza durante la creazione di una regola del segmento, il calcolatore del segmento mostra un errore durante la stima della popolazione.

### Limitazioni dovute a [!UICONTROL Merge Rules] durante la stima delle popolazioni dei segmenti

Al momento, esiste una limitazione nota perché il nostro calcolatore delle dimensioni del segmento non tiene conto di [!UICONTROL profile merge rules]. Ad esempio, osserva i segmenti con la **[!UICONTROL No Authenticated Profile + Current Device Profile]** [regola di unione](../../features/profile-merge-rules/merge-rule-definitions.md). A causa del modo in cui attualmente calcoliamo i numeri di stima del segmento, le popolazioni stimate includeranno profili autenticati. Tuttavia, le popolazioni di segmenti esistenti ignoreranno correttamente i profili autenticati.

>[!MORELIKETHIS]
>
>* [Domande frequenti su regole di unione profili e grafico dei dispositivi](../../faq/faq-profile-merge.md)
* [Collegamento profilo](../profile-merge-rules/merge-rules-overview.md)

