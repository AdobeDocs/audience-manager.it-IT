---
description: Crea e gestisci le caratteristiche o i segmenti utilizzati nella modellazione lookalike.
keywords: peso relativo, lookalike
seo-description: Crea e gestisci le caratteristiche o i segmenti utilizzati nella modellazione lookalike.
seo-title: Informazioni sulla modellazione lookalike
solution: Audience Manager
title: Informazioni sulla modellazione lookalike
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Modelli algoritmici
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1595'
ht-degree: 1%

---

# Informazioni [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Trova nuovi utenti con [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] consente di scoprire tipi di pubblico nuovi e univoci tramite l’analisi automatizzata dei dati. Il processo viene avviato quando si seleziona un [!UICONTROL trait] o [!UICONTROL segment], un intervallo di tempo e il primo e terzo [!UICONTROL data sources]. Le scelte forniscono gli input per il modello algoritmico. Quando il processo di analisi viene eseguito, cerca gli utenti idonei in base alle caratteristiche condivise della popolazione selezionata. Al termine, questi dati sono disponibili in [Generatore di caratteristiche](../../features/traits/about-trait-builder.md) dove puoi utilizzarli per creare caratteristiche in base alla [precisione e portata](../../features/traits/trait-accuracy-reach.md). Inoltre, puoi creare segmenti che combinano caratteristiche algoritmiche con [!UICONTROL rules-based traits] e aggiungere altri requisiti di qualificazione con espressioni [!DNL Boolean] e operatori di confronto. [!UICONTROL Look-Alike Modeling] offre un modo dinamico di estrarre il valore da tutti i dati sulle caratteristiche disponibili.

## Vantaggi {#advantages}

I principali vantaggi dell&#39;utilizzo di [!UICONTROL Look-Alike Modeling] includono:

* **Precisione dei dati:** l&#39;algoritmo viene eseguito regolarmente, il che aiuta a mantenere i risultati aggiornati e pertinenti.
* **Automazione:** non è necessario gestire un set di regole statiche di grandi dimensioni. L&#39;algoritmo troverà i tipi di pubblico per voi.
* **Risparmia tempo e riduci lo sforzo:** con il nostro processo di modellazione non è necessario indovinare cosa  [!UICONTROL traits]/[!UICONTROL segments] può funzionare o spendere tempo nelle campagne per scoprire nuovi tipi di pubblico. Il modello può fare questo per voi.
* **Affidabilità:** la modellazione funziona con processi di individuazione e qualificazione lato server che valutano i tuoi dati e i dati selezionati di terze parti a cui hai accesso. Questo significa che non devi vedere i visitatori sul tuo sito per qualificarli per una caratteristica.

## Flusso di lavoro {#workflow}

Puoi gestire i modelli in **[!UICONTROL Audience Data > Models]**. Ad un livello elevato, il processo del flusso di lavoro prevede quanto segue:

* Seleziona i dati di base che desideri valutare dall’algoritmo. Questo include un [!UICONTROL trait] o [!UICONTROL segment], un intervallo di tempo e [!UICONTROL data sources] (i tuoi dati personali e i dati di terze parti a cui hai già accesso tramite [!DNL Audience Manager]). Nel flusso di lavoro di creazione del modello, è possibile escludere il [!UICONTROL traits] che non si desidera interferire con il modello.
* Salvare il modello. Una volta salvato, il processo di valutazione algoritmica viene eseguito automaticamente. Nota, tuttavia, il completamento di questo processo può richiedere fino a 7 giorni. [!DNL Audience Manager] invia un messaggio e-mail al termine dell’algoritmo e i risultati sono disponibili per la  [!UICONTROL trait] creazione.
* Crea un algoritmo [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Combina [!UICONTROL traits] in [!UICONTROL segments] in [!UICONTROL Segment Builder].
* Crea e invia i dati [!UICONTROL segment] a un [!UICONTROL destination].

## Risoluzione dei problemi    {#troubleshooting}

Disattiviamo qualsiasi [!UICONTROL Look-Alike Model] che non genera dati per tre esecuzioni consecutive. Non è possibile impostare nuovamente lo stato del modello su attivo in seguito. Per garantire che i modelli generino dati, ti consigliamo di generare modelli da origini dati con un numero sufficiente di [!UICONTROL traits] per accumulare dati.

## Informazioni [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] è un algoritmo proprietario progettato per individuare  [!UICONTROL traits] automaticamente nuovi elementi. Confronta i dati [!UICONTROL trait] del [!UICONTROL traits] e [!UICONTROL segments] correnti con tutti gli altri dati di prime e terze parti a cui hai accesso tramite [!DNL Audience Manager]. Fai riferimento a questa sezione per una descrizione del processo di individuazione algoritmica [!UICONTROL TraitWeight] .

![](assets/algo_model.png)

I passaggi seguenti descrivono il processo di valutazione [!UICONTROL TraitWeight].

### Passaggio 1: Creare una linea di base per il confronto [!UICONTROL Trait]

Per generare una linea di base, [!UICONTROL TraitWeight] misura tutti i valori [!UICONTROL traits] associati a un pubblico per un intervallo di 30, 60 o 90 giorni. Successivamente, classifica [!UICONTROL traits] in base alla loro frequenza e alla loro correlazione. Il conteggio delle frequenze misura la comunanza. La correlazione misura la probabilità che un elemento [!UICONTROL trait] sia presente solo nel pubblico di base. [!UICONTROL Traits] che appaiono spesso mostrano alta comunanza, una caratteristica importante utilizzata per impostare un punteggio ponderato quando combinato con  [!UICONTROL traits] scoperto nel tuo selezionato  [!UICONTROL data sources].

### Passaggio 2: Trova lo stesso [!UICONTROL Traits] nel [!UICONTROL Data Source]

Dopo aver creato una linea di base per il confronto, l&#39;algoritmo cerca [!UICONTROL traits] identici nella [!UICONTROL data sources] selezionata. In questo passaggio, [!UICONTROL TraitWeight] esegue un conteggio di frequenza di tutti i valori rilevati [!UICONTROL traits] e li confronta con la linea di base. Tuttavia, a differenza della linea di base, i valori [!UICONTROL traits] non comuni sono classificati più in alto di quelli visualizzati più spesso. Rare [!UICONTROL traits] si dice che mostrino un alto grado di specificità. [!UICONTROL TraitWeight] valuta le combinazioni della linea di base comune  [!UICONTROL traits] e delle combinazioni non comuni (molto specifiche)  [!UICONTROL data source] [!UICONTROL traits] come più influenti o desiderabili rispetto a quelle  [!UICONTROL traits] comuni a entrambi i set di dati. In realtà, il nostro modello riconosce queste grandi e comuni [!UICONTROL traits] e non assegna priorità in eccesso ai set di dati con correlazioni elevate. Rare [!UICONTROL traits] ha una priorità più alta perché è più probabile che rappresentino utenti nuovi e univoci rispetto a [!UICONTROL traits] con un’elevata comunanza a tutti gli effetti.

### Passaggio 3: Assegna peso

In questo passaggio, [!UICONTROL TraitWeight] classifica i nuovi [!UICONTROL traits] scoperti in ordine di influenza o desiderabilità. La scala del peso è una percentuale che va dallo 0% al 100%. [!UICONTROL Traits] posizionati più vicino al 100% significa che assomigliano più al pubblico nella popolazione di base. Inoltre, le [!UICONTROL traits] pesate pesantemente sono preziose perché rappresentano utenti nuovi e univoci che possono comportarsi in modo simile al pubblico di riferimento stabilito. Ricorda che [!UICONTROL TraitWeight] considera [!UICONTROL traits] con un’elevata comunanza nella linea di base e un’elevata specificità nelle origini dati confrontate più importanti di [!UICONTROL traits] comuni in ogni set di dati.

### Passaggio 4: Punteggio degli utenti

A ciascun utente della [!UICONTROL data sources] selezionata viene assegnato un punteggio utente pari alla somma di tutti i pesi dell’ [!UICONTROL traits] influente sul profilo dell’utente. I punteggi utente vengono quindi normalizzati tra 0 e 100%.

### Passaggio 5: Visualizzazione e utilizzo dei risultati

[!DNL Audience Manager] visualizza i risultati del modello ponderato in  [!UICONTROL Trait Builder]. Quando si desidera generare un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] consente di creare un elemento [!UICONTROL traits] in base al punteggio ponderato generato dall&#39;algoritmo durante un&#39;esecuzione di dati. Puoi scegliere una precisione maggiore per qualificare solo gli utenti con punteggi utente molto elevati e quindi molto simili al pubblico di base, anziché al resto del pubblico. Se desideri raggiungere un pubblico più ampio (portata), puoi abbassare la precisione.

### Passaggio 6: Rivalutare il significato di un [!UICONTROL Trait] nei cicli di elaborazione

Periodicamente, [!UICONTROL TraitWeight] rivaluta l&#39;importanza di un [!UICONTROL trait] in base alle dimensioni e alla variazione della popolazione di tale [!UICONTROL trait]. Questo accade quando il numero di utenti qualificati per quel [!UICONTROL trait] aumenta o diminuisce nel tempo. Questo comportamento è visto più chiaramente nelle caratteristiche che diventano molto grandi. Ad esempio, supponiamo che l’algoritmo utilizzi [!UICONTROL trait A] per la modellazione. Man mano che la popolazione di [!UICONTROL trait A] aumenta, [!UICONTROL TraitWeight] rivaluta l&#39;importanza di tale [!UICONTROL trait] e può assegnare un punteggio inferiore o ignorarlo. In questo caso, [!UICONTROL trait A] è troppo comune o grande per dire qualcosa di significativo sulla sua popolazione. Dopo che [!UICONTROL TraitWeight] riduce il valore di [!UICONTROL trait A] (o lo ignora nel modello), la popolazione della caratteristica algoritmica diminuisce. L&#39;elenco delle persone influenti [!UICONTROL traits] riflette l&#39;evoluzione della popolazione di base. Utilizza l&#39;elenco dei [!UICONTROL traits] influenti per capire perché si verificano queste modifiche.

Collegamenti correlati:

* [Generatore di modelli](../../features/algorithmic-models/create-model.md)
* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)

## Programma di aggiornamento per [!UICONTROL Look-Alike Models] e [!UICONTROL Traits] {#update-schedule}

Creazione e aggiornamento di pianificazioni per [!UICONTROL algorithmic models] e [!UICONTROL traits] nuovi o esistenti.

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
   <td colname="col1"> <b>Creare o clonare un modello</b> </td>
   <td colname="col2"> <p>Per i modelli lookalike nuovi o clonati, il processo di creazione viene eseguito una volta al giorno a: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (novembre - marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> EDT alle 18:00 (marzo - novembre) </li> 
     </ul> </p> <p>I modelli generati o clonati dopo la scadenza della creazione vengono elaborati il giorno successivo. </p> <p>Se la prima esecuzione di un modello non genera dati, verrà eseguita una seconda volta, il giorno successivo. Se anche il secondo tentativo non genera dati, verrà effettuato un terzo tentativo, il giorno successivo. Il modello smetterà di funzionare se anche il terzo tentativo non genera dati. In questo caso, disattiveremo il modello. Per ulteriori informazioni, consulta <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Risoluzione dei problemi relativi ai modelli lookalike</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Aggiornare un modello</b> </td> 
   <td colname="col2"> <p>In condizioni ideali, i modelli esistenti vengono eseguiti nei giorni feriali, almeno una volta ogni 7 giorni. Ad esempio, se crei un modello (entro la scadenza) il lunedì, questo verrà aggiornato al più tardi il lunedì successivo. </p> <p>Un modello viene rieseguito se soddisfa una delle seguenti condizioni: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">L'ultima esecuzione non è riuscita. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">È stato eseguito correttamente prima di AND non è stato eseguito affatto negli ultimi 7 giorni E il modello ha almeno una caratteristica attiva collegata ad esso. </li>
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
   <td colname="col2"> <p>Il processo di creazione delle caratteristiche viene eseguito ogni giorno, dal lunedì al venerdì. In genere, le nuove caratteristiche algoritmiche vengono visualizzate nell’interfaccia utente entro 48 ore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aggiornare una caratteristica</b> </td> 
   <td colname="col2"> <p>Le caratteristiche esistenti vengono aggiornate almeno una volta ogni 7 giorni e seguono la pianificazione per gli aggiornamenti del modello. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Visualizzazione elenco modelli {#models-list-view}

La vista a elenco è un’area di lavoro centrale che consente di creare, rivedere e gestire i modelli.

La pagina dell&#39;elenco [!UICONTROL Models] contiene funzioni e strumenti utili per:

* Crea nuovi modelli.
* Gestisci i modelli esistenti (modifica, pausa, eliminazione o duplicazione).
* Cerca modelli per nome.
* Crea [!UICONTROL algorithmic traits] utilizzando un modello specifico.

## Visualizzazione riepilogo modelli {#models-summary-view}

Nella pagina di riepilogo sono visualizzati i dettagli del modello, quali nome, portata/precisione, cronologia di elaborazione e [!UICONTROL traits] creati dal modello. La pagina include anche impostazioni che consentono di creare e gestire modelli. Fare clic sul nome di un modello nell&#39;elenco di riepilogo per visualizzarne i dettagli.

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
   <td colname="col2"> <p>Include informazioni di base sul modello, ad esempio il nome e la data dell’ultima esecuzione. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Raggiungimento e accuratezza del modello</span> </p> </td> 
   <td colname="col2"> <p>Mostra la precisione <a href="../../features/traits/trait-accuracy-reach.md"> e la portata dei dati</a> per l'ultima esecuzione del modello. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Cronologia elaborazione modello</span> </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l’ora di elaborazione per le ultime 10 esecuzioni e indica se i dati sono stati generati su tali esecuzioni. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caratteristiche influenti</span> </p> </td> 
   <td colname="col2"> <p>La tabella <span class="wintitle"> Caratteristiche influenti</span>: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Elenca le prime 50 caratteristiche influenti meglio rappresentate nella popolazione di base del modello. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica ogni caratteristica in ordine di classificazione <span class="wintitle"> Peso relativo</span>. Il <span class="wintitle"> Peso relativo</span> ordina le caratteristiche appena scoperte in ordine di influenza o desiderabilità. La scala del peso è una percentuale che va dallo 0% al 100%. Le caratteristiche sono più vicine al 100% e corrispondono più al pubblico presente nella popolazione di base. Consultare <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Informazioni su TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra gli univoci da 30 giorni e la popolazione totale delle caratteristiche per ogni caratteristica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caratteristiche che utilizzano il modello</span> </p> </td>
   <td colname="col2"> <p>Mostra un elenco delle caratteristiche algoritmiche in base al modello selezionato. Fai clic sul nome o sull’ID di una caratteristica per ulteriori informazioni sulla caratteristica. Seleziona <b><span class="uicontrol"> Crea nuova caratteristica con modello</span></b> per passare al processo di creazione delle caratteristiche algoritmiche. </p> <p>L’etichetta della sezione viene modificata in base al nome del modello. Ad esempio, supponiamo di creare un modello e di denominarlo Modello A. Quando carichi la pagina di riepilogo, il nome di questa sezione viene modificato in <span class="wintitle"> Caratteristiche utilizzando il modello A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinazioni ](../../features/destinations/destinations.md)
* [Caratteristiche ](../../features/traits/trait-details-page.md)
* [Segmenti ](../../features/segments/segments-purpose.md)

