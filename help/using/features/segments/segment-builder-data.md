---
description: Aggiungi e rimuovi caratteristiche in Segment Builder (Generatore segmenti) per visualizzare le popolazioni di caratteristiche effettive insieme ai dati effettivi e stimati sulla popolazione. I dati stimati sulla dimensione demografica consentono di creare il segmento giusto per la campagna.
seo-description: Aggiungi e rimuovi caratteristiche in Segment Builder (Generatore segmenti) per visualizzare le popolazioni di caratteristiche effettive insieme ai dati effettivi e stimati sulla popolazione. I dati stimati sulla dimensione demografica consentono di creare il segmento giusto per la campagna.
seo-title: Dati sulla caratteristica e sulla popolazione in Segment Builder (Generatore segmenti)
solution: Audience Manager
title: Dati sulla caratteristica e sulla popolazione in Segment Builder (Generatore segmenti)
uuid: e 1 e 59 c 0 a-b 4 c 7-4 cad -8485-3667 e 0 a 95 e 83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Dati sulla caratteristica e sulla popolazione in Segment Builder (Generatore segmenti) {#trait-and-segment-population-data-in-segment-builder}

Aggiungi e rimuovi caratteristiche in [!UICONTROL Segment Builder] modo da visualizzare le popolazioni di caratteristiche effettive e i dati effettivi e stimati sulla popolazione. I dati stimati sulla dimensione demografica consentono di creare il segmento giusto per la campagna.

## Dati popolazione caratteristiche {#trait-population-data}

[!UICONTROL Segment Builder] indica l [!UICONTROL Total Trait Population] &#39;ultimo giorno quando aggiungi una caratteristica a un segmento. Questi dati vengono visualizzati nel campo blu attorno alla caratteristica selezionata nella [!UICONTROL Basic View] sezione.

![](assets/trait-size.png)

La tabella seguente definisce le metriche popolazione caratteristiche

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione caratteristica totale</span> </p> </td>
   <td colname="col2"> <p>Il numero di ID univoci con caratteristiche selezionate nel profilo. </p> </td>
  </tr> 
 </tbody> 
</table>

## Calcolo delle popolazioni di segmenti reali e stimate {#calculating-real-estimated-populations}

Quando crei un nuovo segmento, o cambi un segmento esistente, Audience Manager dura fino a 24 ore per visualizzare i risultati per le popolazioni dei segmenti reali e in tempo reale.

Tuttavia, Audience Manager può stimare immediatamente le dimensioni della popolazione in tempo reale e totale del segmento. Queste stime sono basate su dati storici campionati e restituiscono risultati all&#39;intervallo di confidenza del 95%.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], una barra blu sui grafici popolazione stimati indica i possibili intervalli superiori e inferiori per le dimensioni del segmento. Sebbene le prestazioni passate non garantiscano risultati futuri, i dati stimati possono aiutarti a comprendere le dimensioni potenziali di un segmento nuovo o modificato.

## Panoramica dei dati relativi alla popolazione segmento {#segment-populations}

[!UICONTROL Segment Builder] mostra i dati di popolazione durante la creazione e la modifica dei segmenti.

* Per i dati sulla popolazione dei segmenti stimati (in tempo reale e totale), [!UICONTROL Segment Builder] i grafici non vengono aggiornati automaticamente quando si aggiungono o si rimuovono caratteristiche in un segmento. Fate clic per **[!UICONTROL Calculate Estimates]** visualizzare (o aggiornare) i numeri stimati della popolazione.

* Per i dati effettivi sulla popolazione (reale) dei segmenti (in tempo reale e totale), [!UICONTROL Segment Builder] aggiorna automaticamente il grafico dei segmenti quando carichi un segmento esistente. Per i nuovi segmenti, o quando aggiungi nuove caratteristiche a un segmento esistente, i dati effettivi della popolazione non vengono aggiornati fino a 24 ore dopo la creazione del segmento.

![](assets/segment-data.png)

Per ulteriori informazioni sui dati sulla popolazione dei segmenti stimati e effettivi, vedi le definizioni di seguito.

## Dati popolazione segmenti stimati definiti {#estimated-segment-population}

Nella tabella seguente sono definite le metriche di popolazione stimate.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione in tempo reale stimata (potenziale) </span> </p> </td> 
   <td colname="col2"> <p>Numero stimato di visitatori unici visti in tempo reale per l'intervallo di tempo specificato e che sono stati qualificati per il segmento nel momento in cui sono stati visti da Audience Manager. </p> <p>Nel <span class="wintitle"> Generatore di segmenti</span>, le ultime popolazioni di 30 giorni per le caratteristiche (<span class="wintitle"> Totale caratteristiche caratteristiche</span>) possono essere diverse per le caratteristiche e i segmenti valutati in tempo reale. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Per le caratteristiche, l'ultima metrica di 30 giorni conta il numero di utenti unici che sono idonei per quella caratteristica negli ultimi 30 giorni. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Per i segmenti valutati in tempo reale, l'ultima metrica di 30 giorni conta il numero di utenti che hanno qualificato una caratteristica (in quel segmento) in passato e sono stati visti di nuovo da Audience Manager negli ultimi 30 giorni. Ad esempio, supponiamo che un utente sia qualificato per una caratteristica di 60 giorni fa ed è stato rivisto 10 giorni fa. Nei dati, questo utente non verrà aggiunto al conteggio delle caratteristiche perché per la prima volta è qualificato più di 30 giorni fa. Tuttavia, saranno inclusi nell'ultimo conteggio di 30 giorni per i segmenti valutati in tempo reale. perché sono idonei per il segmento entro l'intervallo di 30 giorni. </li>
     </ul> </p> <p> <p>Nota: La <span class="wintitle"> metrica Popolazione</span> reale stimata non include i dispositivi che hanno qualificato un segmento in base alle connessioni fornite da una Regola unione <span class="wintitle"> profilo</span> che utilizza un'opzione grafico <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> dispositivo</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione totale stimata (potenziale)</span> </p> </td> 
   <td colname="col2"> <p>Numero stimato di visitatori univoci che potrebbero trovarsi nel segmento nuovo o modificato. Come per quasi qualsiasi stima, le prestazioni passate non garantiscono i risultati futuri, ma potete utilizzare il totale stimato a: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Scopri quante persone possono raggiungere un segmento nuovo o rivisto quando crei un segmento. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Ottimizza il segmento in base agli obiettivi. Ad esempio, i segmenti di grandi dimensioni sono utili per campagne di riconoscibilità del marchio e segmenti più piccoli sono utili per targeting mirati o per retargeting delle campagne. </li> 
     </ul> </p> <p> <p>Nota: La <span class="wintitle"> metrica Popolazione</span> totale stimata non include i dispositivi che hanno qualificato un segmento in base alle connessioni fornite da una Regola unione <span class="wintitle"> profilo</span> che utilizza un'opzione di grafico <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> dispositivo</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dati popolazione segmenti esistenti (effettivi) definiti {#existing-segment-population}

[!UICONTROL Profile Merge Rules] influiscono sui numeri effettivi e in tempo reale della popolazione. Questi totali variano a seconda se un [!UICONTROL Profile Merge Rule] segmento appartiene a un&#39;opzione di grafico dispositivo o meno. Consultate anche Opzioni regola unione [profilo definite](../../features/profile-merge-rules/merge-rule-definitions.md).

### Dati popolazione segmenti per regole di unione senza un&#39;opzione Grafico dispositivo

La tabella seguente definisce le metriche di popolazione effettive in tempo reale e totale quando i segmenti vengono utilizzati da un [!UICONTROL Profile Merge Rule] &#39;opzione creata senza l&#39;opzione di grafico dispositivo. Queste sono le impostazioni delle opzioni del dispositivo **[!UICONTROL No Device Options]** e **[!UICONTROL Current Device Proflie]**.

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
   <td colname="col2"> <p>Il numero effettivo di visitatori unici visti in tempo reale per l'intervallo di tempo specificato e che sono stati qualificati per il segmento nel momento in cui sono stati visti da Audience Manager. </p> <p>Nel <span class="wintitle"> Generatore di segmenti</span>, le ultime popolazioni di 30 giorni per le caratteristiche (<span class="wintitle"> Totale caratteristiche caratteristiche</span>) possono essere diverse per le caratteristiche e i segmenti valutati in tempo reale. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Per le caratteristiche, l'ultima metrica di 30 giorni conta il numero di utenti unici che sono idonei per quella caratteristica negli ultimi 30 giorni. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Per i segmenti valutati in tempo reale, l'ultima metrica di 30 giorni conta il numero di utenti che hanno qualificato una caratteristica (in quel segmento) in passato e sono stati visti di nuovo da Audience Manager negli ultimi 30 giorni. Ad esempio, supponiamo che un utente sia qualificato per una caratteristica di 60 giorni fa ed è stato rivisto 10 giorni fa. Nei dati, questo utente non verrà aggiunto al conteggio delle caratteristiche perché per la prima volta è qualificato più di 30 giorni fa. Tuttavia, saranno inclusi nell'ultimo conteggio di 30 giorni per i segmenti valutati in tempo reale. perché sono idonei per il segmento entro l'intervallo di 30 giorni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione totale (esistente)</span> </p> </td> 
   <td colname="col2"> <p>Il numero effettivo di visitatori univoci che erano stati qualificati per il segmento a partire da ieri. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Dati popolazione segmenti per regole di unione con un&#39;opzione Grafico dispositivo

La tabella seguente definisce le metriche di popolazione effettive in tempo reale e totale quando i segmenti vengono utilizzati da un [!UICONTROL Profile Merge Rule] &#39;opzione di grafico dispositivo. Queste sono le impostazioni delle opzioni dispositivo per il [!UICONTROL Profile Link Device Graph]grafico, il [!DNL Adobe] grafico del dispositivo e altre scelte del grafico di terze parti disponibili per voi.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione in tempo reale (esistente)</span> </p> </td> 
   <td colname="col2"> <p>Il numero effettivo di dispositivi visti in tempo reale con profili correnti che, se uniti con un massimo di 3 profili dispositivi collegati dal grafico del dispositivo, contiene le caratteristiche per qualificarlo nel segmento appena sono stati visti da <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Popolazione totale (esistente)</span> </p> </td> 
   <td colname="col2"> <p>Il numero totale di dispositivi con profili che, se uniti con un massimo di 3 altri profili dispositivo collegati dal grafico del dispositivo, erano tutti idonei per il segmento. </p> </td>
  </tr>
 </tbody>
</table>

### Limitazioni a causa di espressione di aggiornamento e frequenza durante la stima delle popolazioni segmenti

[!UICONTROL Segment Builder] supporta stime di dimensioni dei segmenti per regole di segmento contenenti fino a 4 espressioni di aggiornamento e frequenza. Se si scelgono più di 4 espressioni di aggiornamento e frequenza durante la creazione di una regola di segmento, l&#39;utilità di stima segmenti mostra un errore durante la stima della popolazione.

### Limitazioni derivanti dalle regole di unione durante la stima delle popolazioni segmenti

Al momento, esiste un limite noto, perché il nostro estimatore di dimensioni del segmento non tiene conto delle regole di unione dei profili. Ad esempio, osserva i segmenti con la regola **Nessun profilo autenticato + profilo dispositivo**[corrente](../../features/profile-merge-rules/merge-rule-definitions.md). A causa del modo in cui stiamo calcolando i numeri di stima dei segmenti, le popolazioni stimate includeranno profili autenticati. Tuttavia, le popolazioni dei segmenti esistenti ignoreranno correttamente i profili autenticati.

>[!MORE_ LIKE_ THIS]
>
>* [Domande frequenti su Profile Merge Rules e Device Graph](../../faq/faq-profile-merge.md)
>* [Collegamento profilo](../../features/profile-merge-rules/merge-rules-overview.md)

