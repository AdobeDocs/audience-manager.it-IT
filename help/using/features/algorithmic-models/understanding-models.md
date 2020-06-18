---
description: Crea e gestisci le caratteristiche o i segmenti utilizzati nella modellazione simile.
keywords: relative weight, lookalike
seo-description: Crea e gestisci le caratteristiche o i segmenti utilizzati nella modellazione simile.
seo-title: La Modellazione Con Aspetto
solution: Audience Manager
title: La Modellazione Con Aspetto
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 0%

---


# Modellazione con aspetto simile {#about-algorithmic-models}

## Trova nuovi utenti con un modello di aspetto simile {#find-new-users}

[!UICONTROL Look-Alike Modeling] consente di scoprire audience nuove e uniche tramite l&#39;analisi automatizzata dei dati. Il processo inizia quando si seleziona una caratteristica o un segmento, un intervallo di tempo e origini dati di prime e terze parti. Le scelte forniscono gli input per il modello algoritmico. Quando il processo di analisi viene eseguito, cerca gli utenti idonei in base alle caratteristiche condivise della popolazione selezionata. Al termine, questi dati sono disponibili in Generatore di [caratteristiche](../../features/traits/about-trait-builder.md) , dove è possibile utilizzarli per creare caratteristiche in base alla [precisione e alla portata](../../features/traits/trait-accuracy-reach.md). Inoltre, puoi creare segmenti che combinano caratteristiche algoritmiche con caratteristiche basate su regole e aggiungere altri requisiti di qualifica con espressioni booleane e operatori di confronto. [!UICONTROL Look-Alike Modeling] offre un metodo dinamico per estrarre valore da tutti i dati sulle caratteristiche disponibili.

## Vantaggi {#advantages}

I principali vantaggi dell&#39;utilizzo [!UICONTROL Look-Alike Modeling] comprendono:

* **Precisione dei dati:** L&#39;algoritmo viene eseguito regolarmente, in modo da mantenere i risultati aggiornati e pertinenti.
* **Automazione:** Non è necessario gestire un ampio insieme di regole statiche. L&#39;algoritmo troverà audience per voi.
* **Risparmiate tempo e riducete lo sforzo:** Con il nostro processo di modellazione non è necessario indovinare quali caratteristiche/segmenti possono funzionare o spendere tempo nelle campagne per scoprire nuovi tipi di pubblico. Il modello può fare questo per voi.
* **Affidabilità:** La modellazione funziona con processi di individuazione e qualificazione lato server che valutano i dati personali e i dati di terze parti selezionati a cui hai accesso. Ciò significa che non è necessario visualizzare i visitatori sul sito per qualificarli per una caratteristica.

## Flusso di lavoro {#workflow}

Puoi gestire i modelli in **[!UICONTROL Audience Data > Models]**. A un livello elevato, il processo di workflow comprende le seguenti attività:

* Selezionare i dati di base che si desidera valutare dall&#39;algoritmo. Questo include caratteristiche o segmento, intervallo di tempo e origini dati (dati personali e dati di terze parti a cui hai già accesso tramite [!DNL Audience Manager]). Nel flusso di lavoro per la creazione del modello, potete escludere le caratteristiche che non desiderate interferire con il modello.
* Salvare il modello. Una volta salvato, il processo di valutazione algoritmica viene eseguito automaticamente. Tuttavia, il completamento di questo processo può richiedere fino a 7 giorni. [!DNL Audience Manager] invia un messaggio e-mail al termine dell’algoritmo e i risultati sono disponibili per la creazione delle caratteristiche.
* Creazione di caratteristiche algoritmiche in [!UICONTROL Trait Builder].
* Combinare caratteristiche in segmenti in [!UICONTROL Segment Builder].
* Crea e invia i dati del segmento a una destinazione.

## Risoluzione dei problemi {#troubleshooting}

Disattiviamo tutti [!UICONTROL Look-Alike Model] quelli che non generano dati per tre esecuzioni consecutive. Non è possibile impostare nuovamente lo stato del modello su attivo in seguito. Per garantire che i modelli generino dati, è consigliabile creare modelli da origini dati con caratteristiche sufficienti per accumulare dati.

## Comprensione di TraitWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] è un algoritmo proprietario progettato per scoprire automaticamente nuove caratteristiche. Confronta i dati sulle caratteristiche delle caratteristiche e dei segmenti correnti con tutti gli altri dati di prime e terze parti a cui hai accesso [!DNL Audience Manager]. Fare riferimento a questa sezione per una descrizione del processo di individuazione [!UICONTROL TraitWeight] algoritmica.

<!-- traitweight.xml -->

![](assets/algo_model.png)

I passaggi seguenti descrivono il processo di [!UICONTROL TraitWeight] valutazione.

### Passaggio 1: Creare una baseline per il confronto delle caratteristiche

Per generare una linea di base, [!UICONTROL TraitWeight] misura tutte le caratteristiche associate a un pubblico per un intervallo di 30, 60 o 90 giorni. Successivamente, classifica le caratteristiche in base alla loro frequenza e correlazione. Il conteggio delle frequenze misura la comunanza. La correlazione misura la probabilità che una caratteristica sia presente solo nel pubblico di riferimento. Le caratteristiche che appaiono spesso sono caratterizzate da un&#39;elevata comunanza, una caratteristica importante utilizzata per impostare un punteggio ponderato in combinazione con le caratteristiche scoperte nelle origini dati selezionate.

### Passaggio 2: Trova le stesse caratteristiche nell&#39;origine dati

Dopo aver creato una baseline per il confronto, l&#39;algoritmo cerca caratteristiche identiche nelle origini dati selezionate. In questo passaggio, [!UICONTROL TraitWeight] esegue un conteggio di frequenza di tutte le caratteristiche scoperte e le confronta con la linea di base. Tuttavia, a differenza della linea di base, le caratteristiche non comuni sono più alte di quelle visualizzate più spesso. Si dice che i tratti rari mostrino un alto grado di specificità. [!UICONTROL TraitWeight] valuta le combinazioni di tratti di base comuni e tratti di origine dati non comuni (altamente specifici) come più influenti o desiderabili rispetto alle caratteristiche comuni a entrambi i set di dati. In realtà, il nostro modello riconosce questi tratti grandi e comuni e non assegna priorità eccessiva ai set di dati con correlazioni elevate. Le caratteristiche rare hanno una priorità più alta perché hanno più probabilità di rappresentare nuovi utenti unici rispetto alle caratteristiche con un&#39;elevata comunanza.

### Passaggio 3: Assegna spessore

In questo passaggio, [!UICONTROL TraitWeight] classifica le caratteristiche scoperte di recente in ordine di influenza o desiderabilità. La scala del peso è una percentuale compresa tra 0% e 100%. Le caratteristiche con una classificazione più vicina al 100% indicano che sono più simili al pubblico della popolazione di riferimento. Inoltre, le caratteristiche pesantemente ponderate sono preziose perché rappresentano nuovi utenti unici che possono comportarsi in modo simile al pubblico di riferimento stabilito. Ricorda che [!UICONTROL TraitWeight] i tratti con elevata comunanza nella linea di base e un&#39;elevata specificità nelle origini dati confrontate sono più importanti dei tratti comuni in ciascun set di dati.

### Passaggio 4: Punteggio utenti

A ogni utente delle origini dati selezionate viene assegnata una valutazione utente pari alla somma di tutti i pesi delle caratteristiche influenti del profilo dell&#39;utente. I punteggi utente vengono quindi normalizzati tra 0 e 100%.

### Passaggio 5: Visualizzazione e utilizzo dei risultati

[!DNL Audience Manager] visualizza i risultati ponderati del modello in [!UICONTROL Trait Builder]. Per creare una caratteristica algoritmica, [!UICONTROL Trait Builder] è possibile creare caratteristiche basate sulla valutazione ponderata generata dall&#39;algoritmo durante un&#39;esecuzione dei dati. Potete scegliere una precisione più elevata per qualificare solo gli utenti con un punteggio utente molto elevato e quindi molto simile al pubblico previsto, anziché il resto del pubblico. Se desiderate raggiungere un pubblico più vasto (portata), potete ridurre la precisione.

### Passaggio 6: Rivalutare l&#39;importanza di una caratteristica nei cicli di elaborazione

Periodicamente, [!UICONTROL TraitWeight] rivaluta l&#39;importanza di un tratto in base alle dimensioni e ai cambiamenti nella popolazione di quel tratto. Questo accade quando il numero di utenti idonei per quella caratteristica aumenta o diminuisce nel tempo. Questo comportamento è più chiaro nelle caratteristiche che diventano molto grandi. Ad esempio, supponiamo che l&#39;algoritmo utilizzi la caratteristica A per la modellazione. Con l&#39;aumento della popolazione di caratteristiche A, [!UICONTROL TraitWeight] rivaluta l&#39;importanza di tale caratteristica e può assegnare un punteggio inferiore o ignorarlo. In questo caso, la caratteristica A è troppo comune o grande per dire qualcosa di significativo sulla sua popolazione. Dopo aver [!UICONTROL TraitWeight] ridotto il valore della caratteristica A (o ignorarla nel modello), la popolazione della caratteristica algoritmica diminuisce. L&#39;elenco delle caratteristiche influenti riflette l&#39;evoluzione della popolazione di base. Utilizzate l&#39;elenco delle caratteristiche influenti per comprendere il motivo per cui tali modifiche si verificano.

Collegamenti correlati:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [Precisione e raggiungimento](../../features/traits/trait-accuracy-reach.md)

## Programma di aggiornamento per modelli e caratteristiche simili {#update-schedule}

Creazione e aggiornamento di programmi per modelli e caratteristiche algoritmici nuovi o esistenti.

<!-- c_model_update_schedule.xml -->

### Creazione e aggiornamento di modelli simili

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

### Creazione e aggiornamento delle caratteristiche simili

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

<!-- c_models_list_view.xml -->

La pagina dell&#39;elenco Modelli contiene funzioni e strumenti utili per:

* Creare nuovi modelli.
* Gestire i modelli esistenti (modificare, mettere in pausa, eliminare o duplicare).
* Cercare modelli per nome.
* Create caratteristiche algoritmiche utilizzando qualsiasi modello specificato.

## Visualizzazione riepilogo modelli {#models-summary-view}

Nella pagina di riepilogo sono visualizzati i dettagli del modello, ad esempio il nome, la portata/precisione, la cronologia di elaborazione e le caratteristiche create dal modello. La pagina include inoltre impostazioni che consentono di creare e gestire i modelli. Fate clic sul nome di un modello dall&#39;elenco di riepilogo per visualizzarne i dettagli.

<!-- c_models_summary.xml -->

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
>* [Destinazioni](../../features/destinations/destinations.md)
>* [Caratteristiche](../../features/traits/trait-details-page.md)
>* [Segmenti](../../features/segments/segments-purpose.md)

