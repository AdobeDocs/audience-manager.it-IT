---
description: Crea e gestisci le caratteristiche o i segmenti utilizzati nella modellazione simile.
keywords: relative weight, lookalike
seo-description: Crea e gestisci le caratteristiche o i segmenti utilizzati nella modellazione simile.
seo-title: La Modellazione Con Aspetto
solution: Audience Manager
title: La Modellazione Con Aspetto
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 1%

---


# Informazioni [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Trova nuovi utenti con [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] consente di scoprire audience nuove e uniche tramite l&#39;analisi automatizzata dei dati. Il processo inizia quando si seleziona uno [!UICONTROL trait] o [!UICONTROL segment], un intervallo di tempo e la prima e terza parte [!UICONTROL data sources]. Le scelte forniscono gli input per il modello algoritmico. Quando il processo di analisi viene eseguito, cerca gli utenti idonei in base alle caratteristiche condivise della popolazione selezionata. Al termine, questi dati sono disponibili in Generatore di [caratteristiche](../../features/traits/about-trait-builder.md) , dove è possibile utilizzarli per creare caratteristiche in base alla [precisione e alla portata](../../features/traits/trait-accuracy-reach.md). Inoltre, puoi creare segmenti che combinano caratteristiche algoritmiche con [!UICONTROL rules-based traits] altri requisiti di qualifica, con [!DNL Boolean] espressioni e operatori di confronto. [!UICONTROL Look-Alike Modeling] offre un metodo dinamico per estrarre valore da tutti i dati sulle caratteristiche disponibili.

## Vantaggi {#advantages}

I principali vantaggi dell&#39;utilizzo [!UICONTROL Look-Alike Modeling] comprendono:

* **Precisione dei dati:** L&#39;algoritmo viene eseguito regolarmente, in modo da mantenere i risultati aggiornati e pertinenti.
* **Automazione:** Non è necessario gestire un ampio insieme di regole statiche. L&#39;algoritmo troverà audience per voi.
* **Risparmiate tempo e riducete lo sforzo:** Con il nostro processo di modellazione non è necessario indovinare cosa [!UICONTROL traits]/[!UICONTROL segments] potrebbe funzionare o spendere tempo nelle campagne per scoprire nuovi tipi di pubblico. Il modello può fare questo per voi.
* **Affidabilità:** La modellazione funziona con processi di individuazione e qualificazione lato server che valutano i dati personali e i dati di terze parti selezionati a cui hai accesso. Ciò significa che non è necessario visualizzare i visitatori sul sito per qualificarli per una caratteristica.

## Flusso di lavoro {#workflow}

Puoi gestire i modelli in **[!UICONTROL Audience Data > Models]**. A un livello elevato, il processo di workflow comprende le seguenti attività:

* Selezionare i dati di base che si desidera valutare dall&#39;algoritmo. Questo include un intervallo di tempo [!UICONTROL trait] o [!UICONTROL segment], e [!UICONTROL data sources] (i tuoi dati personali e i dati di terze parti a cui hai già accesso tramite [!DNL Audience Manager]). Nel flusso di lavoro per la creazione del modello, potete escludere [!UICONTROL traits] che non intendete interferire con il modello.
* Salvare il modello. Una volta salvato, il processo di valutazione algoritmica viene eseguito automaticamente. Tuttavia, il completamento di questo processo può richiedere fino a 7 giorni. [!DNL Audience Manager] invia un messaggio e-mail al termine dell’algoritmo e i risultati sono disponibili per la [!UICONTROL trait] creazione.
* Creare algoritmi [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Unisci [!UICONTROL traits] in [!UICONTROL segments] in [!UICONTROL Segment Builder].
* Creare e inviare [!UICONTROL segment] dati a un [!UICONTROL destination].

## Risoluzione dei problemi {#troubleshooting}

Disattiviamo tutti [!UICONTROL Look-Alike Model] quelli che non generano dati per tre esecuzioni consecutive. Non è possibile impostare nuovamente lo stato del modello su attivo in seguito. Per garantire che i modelli generino dati, si consiglia di creare modelli da origini dati con dati sufficienti [!UICONTROL traits] per accumulare dati.

## Informazioni [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] è un algoritmo proprietario progettato per scoprire nuovi [!UICONTROL traits] automaticamente. Confronta [!UICONTROL trait] i dati correnti [!UICONTROL traits] e [!UICONTROL segments] con tutti gli altri dati di prime e terze parti a cui hai accesso [!DNL Audience Manager]. Fare riferimento a questa sezione per una descrizione del processo di individuazione [!UICONTROL TraitWeight] algoritmica.

![](assets/algo_model.png)

I passaggi seguenti descrivono il processo di [!UICONTROL TraitWeight] valutazione.

### Passaggio 1: Creare una baseline per il [!UICONTROL Trait] confronto

Per generare una linea di base, [!UICONTROL TraitWeight] misura tutti i dati [!UICONTROL traits] associati a un&#39;audience per un intervallo di 30, 60 o 90 giorni. Successivamente, si classifica [!UICONTROL traits] in base alla loro frequenza e correlazione. Il conteggio delle frequenze misura la comunanza. La correlazione misura la probabilità che un [!UICONTROL trait] essere presente solo nel pubblico di riferimento. [!UICONTROL Traits] che appaiono spesso mostrano un&#39;alta comunanza, una caratteristica importante usata per impostare un punteggio ponderato quando combinato con [!UICONTROL traits] scoperto nel vostro selezionato [!UICONTROL data sources].

### Passaggio 2: Trova lo stesso [!UICONTROL Traits] nel pannello [!UICONTROL Data Source]

Dopo aver creato una linea di base per il confronto, l&#39;algoritmo cerca la stessa cosa [!UICONTROL traits] nell&#39;elemento selezionato [!UICONTROL data sources]. In questo passaggio, [!UICONTROL TraitWeight] esegue un conteggio di frequenza di tutti gli elementi rilevati [!UICONTROL traits] e li confronta con la linea di base. Tuttavia, a differenza della linea di base, [!UICONTROL traits] le voci non comuni sono più alte di quelle che appaiono più spesso. Si dice che [!UICONTROL traits] siano rari a mostrare un alto grado di specificità. [!UICONTROL TraitWeight] valuta le combinazioni di riferimento comune [!UICONTROL traits] e non comune (altamente specifico) [!UICONTROL data source] come più influente o desiderabile di quanto [!UICONTROL traits] [!UICONTROL traits] comune a entrambi i set di dati. In realtà, il nostro modello riconosce queste grandi, comuni [!UICONTROL traits] e non assegna priorità in eccesso ai set di dati con alte correlazioni. Rare [!UICONTROL traits] ha una priorità più alta perché è più probabile che rappresentino utenti nuovi e unici che [!UICONTROL traits] con un&#39;alta comunanza.

### Passaggio 3: Assegna spessore

In questo passaggio, [!UICONTROL TraitWeight] classifica scoperti di recente [!UICONTROL traits] in ordine di influenza o desiderabilità. La scala del peso è una percentuale compresa tra 0% e 100%. [!UICONTROL Traits] con un punteggio più vicino al 100%, i dati sono più simili al pubblico della popolazione di riferimento. Inoltre, [!UICONTROL traits] sono molto ponderati perché rappresentano utenti nuovi e unici che possono comportarsi in modo simile al pubblico di riferimento stabilito. Ricorda che [!UICONTROL TraitWeight] considera [!UICONTROL traits] con un&#39;elevata comunanza nella linea di base e con un&#39;elevata specificità nelle origini dati confrontate un valore maggiore di quanto [!UICONTROL traits] sia comune in ciascun set di dati.

### Passaggio 4: Punteggio utenti

A ogni utente selezionato [!UICONTROL data sources] viene assegnata una valutazione utente pari alla somma di tutti i pesi dell&#39;influente [!UICONTROL traits] sul profilo dell&#39;utente. I punteggi utente vengono quindi normalizzati tra 0 e 100%.

### Passaggio 5: Visualizzazione e utilizzo dei risultati

[!DNL Audience Manager] visualizza i risultati ponderati del modello in [!UICONTROL Trait Builder]. Quando si desidera creare un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] consente di creare [!UICONTROL traits] in base al punteggio ponderato generato dall&#39;algoritmo durante un&#39;esecuzione dei dati. Potete scegliere una precisione più elevata per qualificare solo gli utenti con un punteggio utente molto elevato e quindi molto simile al pubblico previsto, anziché il resto del pubblico. Se desiderate raggiungere un pubblico più vasto (portata), potete ridurre la precisione.

### Passaggio 6: Rivalutare il significato di un ciclo di [!UICONTROL Trait] elaborazione trasversale

Periodicamente, [!UICONTROL TraitWeight] rivaluta l&#39;importanza di un [!UICONTROL trait] in base alle dimensioni e al cambiamento della popolazione di tale [!UICONTROL trait]. Questo accade quando il numero di utenti idonei per tale [!UICONTROL trait] aumenta o diminuisce nel tempo. Questo comportamento è più chiaro nelle caratteristiche che diventano molto grandi. Ad esempio, supponiamo che l&#39;algoritmo utilizzi [!UICONTROL trait A] la modellazione. Con l&#39; [!UICONTROL trait A] aumento della popolazione, [!UICONTROL TraitWeight] rivaluta l&#39;importanza di questo [!UICONTROL trait] e può assegnare un punteggio inferiore o ignorarlo. In questo caso, [!UICONTROL trait A] è troppo comune o grande per dire qualcosa di significativo sulla sua popolazione. Dopo aver [!UICONTROL TraitWeight] ridotto il valore di [!UICONTROL trait A] (o ignorato nel modello), la popolazione della caratteristica algoritmica diminuisce. L&#39;elenco delle persone influenti [!UICONTROL traits] riflette l&#39;evoluzione della popolazione di base. Utilizzate l&#39;elenco delle informazioni più importanti [!UICONTROL traits] per comprendere il motivo di tali modifiche.

Collegamenti correlati:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)

## Aggiorna pianificazione per [!UICONTROL Look-Alike Models] e [!UICONTROL Traits] {#update-schedule}

Creazione e aggiornamento di programmi per nuovi o esistenti [!UICONTROL algorithmic models] e [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] Pianificazione creazione e aggiornamento

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Tipo di attività </th>
   <th colname="col2" class="entry"> Descrizione </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Creare o duplicare un modello</b> </td>
   <td colname="col2"> <p>Per i modelli [!UICONTROL Look-Alike Models] nuovi o clonati, il processo di creazione viene eseguito una volta al giorno a: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (novembre - marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> EDT 18 (marzo - novembre) </li> 
     </ul> </p> <p>I modelli generati o clonati dopo la scadenza della creazione vengono elaborati il giorno successivo. </p> <p>Se la prima esecuzione di un modello non genera dati, verrà eseguita una seconda volta, il giorno successivo. Se anche il secondo tentativo non genera dati, verrà effettuato un terzo tentativo, il giorno successivo. Il modello si interrompe se anche il terzo tentativo non genera dati. In questo caso, il modello verrà disattivato. Per ulteriori informazioni, consulta <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Risoluzione dei problemi relativi a modelli</a>simili. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Aggiornamento di un modello</b> </td> 
   <td colname="col2"> <p>In condizioni ideali, i modelli esistenti vengono eseguiti nei giorni feriali, almeno una volta ogni 7 giorni. Ad esempio, se crei un modello (entro la scadenza) il lunedì, il lunedì successivo verrà aggiornato al più tardi. </p> <p>Un modello verrà rieseguito se soddisfa una delle seguenti condizioni: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">L'ultima esecuzione non è riuscita. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">È stato eseguito correttamente prima di E non è stato eseguito affatto negli ultimi 7 giorni E il modello ha almeno un tratto attivo ad esso collegato. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Pianificazione creazione e aggiornamento

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di attività </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Creare una caratteristica</b> </td> 
   <td colname="col2"> <p>Il processo di creazione delle caratteristiche viene eseguito ogni giorno, dal lunedì al venerdì. In genere, nell’interfaccia utente vengono visualizzate nuove caratteristiche algoritmiche entro 48 ore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aggiorna una caratteristica</b> </td> 
   <td colname="col2"> <p>Le caratteristiche esistenti vengono aggiornate almeno una volta ogni 7 giorni e seguono la pianificazione per gli aggiornamenti dei modelli. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Visualizzazione elenco modelli {#models-list-view}

La vista Elenco è un’area di lavoro centrale che consente di creare, rivedere e gestire i modelli.

La pagina [!UICONTROL Models] elenco contiene funzioni e strumenti utili per:

* Creare nuovi modelli.
* Gestire i modelli esistenti (modificare, mettere in pausa, eliminare o duplicare).
* Cercare modelli per nome.
* Create [!UICONTROL algorithmic traits] utilizzando un determinato modello.

## Visualizzazione riepilogo modelli {#models-summary-view}

Nella pagina di riepilogo sono visualizzati i dettagli del modello quali nome, portata/precisione, cronologia di elaborazione e [!UICONTROL traits] creati dal modello. La pagina include inoltre impostazioni che consentono di creare e gestire i modelli. Fate clic sul nome di un modello dall&#39;elenco di riepilogo per visualizzarne i dettagli.

La pagina di riepilogo del modello include le sezioni seguenti.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sezione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Informazioni di base</span> </p> </td>
   <td colname="col2"> <p>Include informazioni di base sul modello, ad esempio il nome e la data dell'ultima esecuzione. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Raggiungimento e precisione dei modelli</span> </p> </td> 
   <td colname="col2"> <p>Mostra <a href="../../features/traits/trait-accuracy-reach.md"> l'accuratezza e i dati di portata</a> per l'ultima esecuzione del modello. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Cronologia elaborazione modello</span> </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l'ora di elaborazione per le ultime 10 esecuzioni e se i dati sono stati generati su tali esecuzioni. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caratteristiche influenti</span> </p> </td> 
   <td colname="col2"> <p>La tabella <span class="wintitle"> Caratteristiche</span> influenti: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Elenca le prime 50 caratteristiche influenti meglio rappresentate nella popolazione della linea di base del modello. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica ogni caratteristica in ordine di classificazione <span class="wintitle"> Relative Weight</span> (Spessorerelativo). Il <span class="wintitle"> Relative Weight</span> ordina le caratteristiche scoperte di recente in ordine di influenza o desiderabilità. La scala del peso è una percentuale compresa tra 0% e 100%. Le caratteristiche con una classificazione più vicina al 100% indicano che sono più simili al pubblico della popolazione di riferimento. Vedere <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Informazioni su TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra le uniche di 30 giorni e la popolazione totale di caratteristiche per ogni caratteristica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caratteristiche che utilizzano il modello</span> </p> </td>
   <td colname="col2"> <p>Mostra un elenco delle caratteristiche algoritmiche basate sul modello selezionato. Per ulteriori informazioni sulla caratteristica, fai clic sul nome o sull’ID della caratteristica. Selezionate <b><span class="uicontrol"> Crea nuova caratteristica con modello</span></b> per passare al processo di creazione delle caratteristiche algoritmiche. </p> <p>L'etichetta della sezione viene modificata in base al nome del modello. Ad esempio, supponiamo di creare un modello e denominarlo Modello A. Quando si carica la pagina di riepilogo, il nome di questa sezione viene modificato in <span class="wintitle"> Caratteristiche utilizzando il modello A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinazioni ](../../features/destinations/destinations.md)
>* [Caratteristiche ](../../features/traits/trait-details-page.md)
>* [Segmenti ](../../features/segments/segments-purpose.md)

