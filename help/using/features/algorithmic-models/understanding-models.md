---
description: Crea e gestisci le caratteristiche o i segmenti utilizzati nella modellazione lookalike.
keywords: peso relativo, simile al lookalike
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: Modellazione lookalike
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# Informazioni su [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Trova nuovi utenti con [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] consente di individuare nuovi tipi di pubblico univoci tramite l&#39;analisi automatizzata dei dati. Il processo viene avviato quando si seleziona un [!UICONTROL trait] o un [!UICONTROL segment], un intervallo di tempo e un [!UICONTROL data sources] di prime e terze parti. Le scelte effettuate forniscono gli input per il modello algoritmico. Durante l’esecuzione del processo di analisi, vengono cercati gli utenti idonei in base alle caratteristiche condivise della popolazione selezionata. Al termine, questi dati sono disponibili in [Generatore di caratteristiche](../../features/traits/about-trait-builder.md) dove puoi utilizzarli per creare caratteristiche basate sulla [precisione e portata](../../features/traits/trait-accuracy-reach.md). Inoltre, puoi creare segmenti che combinano caratteristiche algoritmiche con [!UICONTROL rules-based traits] e aggiungere altri requisiti di qualificazione con [!DNL Boolean] espressioni e operatori di confronto. [!UICONTROL Look-Alike Modeling] offre un modo dinamico per estrarre valore da tutti i dati delle caratteristiche disponibili.

## Vantaggi {#advantages}

I principali vantaggi dell&#39;utilizzo di [!UICONTROL Look-Alike Modeling] includono:

* **Precisione dei dati:** l&#39;algoritmo viene eseguito regolarmente, per mantenere i risultati aggiornati e pertinenti.
* **Automazione:** Non è necessario gestire un set elevato di regole statiche. L’algoritmo troverà i tipi di pubblico per te.
* **Risparmia tempo e riduci l&#39;impegno:** Con il nostro processo di modellazione non devi indovinare a cosa [!UICONTROL traits]/[!UICONTROL segments] può funzionare o spendere tempo nelle risorse per le campagne per scoprire nuovi tipi di pubblico. Il modello può farlo per voi.
* **Affidabilità:** la modellazione funziona con processi di individuazione e qualificazione lato server che valutano i dati personali e i dati di terze parti selezionati a cui hai accesso. Ciò significa che non è necessario visualizzare i visitatori sul sito per qualificarli per una caratteristica.

## Flusso di lavoro {#workflow}

I modelli vengono gestiti in **[!UICONTROL Audience Data > Models]**. Ad alto livello, il processo del flusso di lavoro prevede quanto segue:

* Selezionare i dati della baseline che si desidera vengano valutati dall&#39;algoritmo. Sono inclusi [!UICONTROL trait] o [!UICONTROL segment], intervallo di tempo e [!UICONTROL data sources] (dati personalizzati e dati di terze parti a cui si ha già accesso tramite [!DNL Audience Manager]). Nel flusso di lavoro di creazione del modello è possibile escludere [!UICONTROL traits] che non si desidera interferire con il modello.
* Salva il modello. Una volta salvato, il processo di valutazione algoritmica viene eseguito automaticamente. Tuttavia, il completamento di questo processo può richiedere fino a 7 giorni. [!DNL Audience Manager] ti invia un&#39;e-mail quando l&#39;algoritmo è terminato e i risultati sono disponibili per la creazione di [!UICONTROL trait].
* Genera algoritmo [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Combinare [!UICONTROL traits] in [!UICONTROL segments] in [!UICONTROL Segment Builder].
* Crea e invia dati [!UICONTROL segment] a [!UICONTROL destination].

## Risoluzione dei problemi {#troubleshooting}

Disattiviamo qualsiasi [!UICONTROL Look-Alike Model] che non riesce a generare dati per tre esecuzioni consecutive. Non potete riattivare lo stato del modello in seguito. Per garantire che i modelli generino dati, è consigliabile creare modelli da origini dati con un numero di [!UICONTROL traits] sufficiente per accumulare dati da.

## Informazioni su [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] è un algoritmo proprietario progettato per individuare automaticamente il nuovo [!UICONTROL traits]. Confronta i dati di [!UICONTROL trait] dei tuoi [!UICONTROL traits] e [!UICONTROL segments] correnti con tutti gli altri dati di prime e terze parti a cui hai accesso tramite [!DNL Audience Manager]. Fare riferimento a questa sezione per una descrizione del processo di individuazione algoritmica di [!UICONTROL TraitWeight].

![](assets/algo_model.png)

I passaggi seguenti descrivono il processo di valutazione [!UICONTROL TraitWeight].

### Passaggio 1: creare una baseline per il confronto [!UICONTROL Trait]

Per generare una linea di base, [!UICONTROL TraitWeight] misura tutti i [!UICONTROL traits] associati a un pubblico per un intervallo di 30, 60 o 90 giorni. Successivamente, classifica [!UICONTROL traits] in base alla loro frequenza e correlazione. Il conteggio delle frequenze misura la compatibilità. La correlazione misura la probabilità che un [!UICONTROL trait] sia presente solo nel pubblico di base. Si dice che [!UICONTROL Traits] che appaiono spesso presentino un&#39;elevata compatibilità, una caratteristica importante utilizzata per impostare un punteggio ponderato quando combinati con [!UICONTROL traits] individuati nel [!UICONTROL data sources] selezionato.

### Passaggio 2: trovare lo stesso [!UICONTROL Traits] in [!UICONTROL Data Source]

Dopo aver creato una linea di base per il confronto, l&#39;algoritmo cerca [!UICONTROL traits] identico nel [!UICONTROL data sources] selezionato. In questo passaggio, [!UICONTROL TraitWeight] esegue un conteggio di frequenza di tutti i [!UICONTROL traits] individuati e li confronta con la linea di base. Tuttavia, a differenza della linea di base, [!UICONTROL traits] non comuni sono classificati più in alto di quelli che appaiono più spesso. Si dice che [!UICONTROL traits] rari presentino un elevato grado di specificità. [!UICONTROL TraitWeight] valuta le combinazioni della linea di base comune [!UICONTROL traits] e non comune (altamente specifico) [!UICONTROL data source] [!UICONTROL traits] come più influente o desiderabile di [!UICONTROL traits] comune a entrambi i set di dati. In effetti, il nostro modello riconosce questi [!UICONTROL traits] grandi e comuni e non assegna un&#39;eccessiva priorità ai set di dati con correlazioni elevate. [!UICONTROL traits] rari hanno priorità più alta perché hanno maggiori probabilità di rappresentare nuovi utenti univoci rispetto a [!UICONTROL traits] con elevata compatibilità in tutto il mondo.

### Passaggio 3: assegnare il peso

In questo passaggio, [!UICONTROL TraitWeight] classifica i nuovi [!UICONTROL traits] individuati in ordine di influenza o desiderabilità. La scala del peso è una percentuale compresa tra 0% e 100%. [!UICONTROL Traits] si è classificato più vicino al 100% significa che è più simile al pubblico nella popolazione linea di base. Inoltre, [!UICONTROL traits] pesantemente ponderati sono preziosi perché rappresentano nuovi utenti univoci che possono comportarsi in modo simile al pubblico consolidato e di base. Ricorda che [!UICONTROL TraitWeight] considera [!UICONTROL traits] con elevata compatibilità nella linea di base e alta specificità nelle origini dati confrontate più preziose di [!UICONTROL traits] comuni in ogni set di dati.

### Passaggio 4: assegnazione del punteggio agli utenti

A ogni utente nella [!UICONTROL data sources] selezionata viene assegnato un punteggio pari alla somma di tutti i pesi della [!UICONTROL traits] influente sul profilo dell&#39;utente. I punteggi utente vengono quindi normalizzati tra 0 e 100%.

### Passaggio 5: visualizzare e utilizzare i risultati

[!DNL Audience Manager] visualizza i risultati del modello ponderato in [!UICONTROL Trait Builder]. Quando desideri generare un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] ti consente di creare [!UICONTROL traits] in base al punteggio ponderato generato dall&#39;algoritmo durante un&#39;esecuzione dei dati. Puoi scegliere una precisione più elevata per qualificare solo gli utenti con punteggi molto elevati e quindi molto simili al pubblico di riferimento, anziché al resto del pubblico. Se desideri raggiungere un pubblico più ampio (portata), puoi ridurne la precisione.

### Passaggio 6: rivalutare la significatività di un [!UICONTROL Trait] in tutti i cicli di elaborazione

Periodicamente [!UICONTROL TraitWeight] rivaluta l&#39;importanza di [!UICONTROL trait] in base alle dimensioni e alla modifica della popolazione di [!UICONTROL trait]. Questo accade quando il numero di utenti qualificati per [!UICONTROL trait] aumenta o diminuisce nel tempo. Questo comportamento si nota soprattutto nelle caratteristiche che diventano molto grandi. Si supponga ad esempio che l&#39;algoritmo utilizzi [!UICONTROL trait A] per la modellazione. Con l&#39;aumento della popolazione di [!UICONTROL trait A], [!UICONTROL TraitWeight] rivaluta l&#39;importanza di [!UICONTROL trait] e può assegnare un punteggio inferiore o ignorarlo. In questo caso, [!UICONTROL trait A] è troppo comune o troppo grande per fornire informazioni significative sulla popolazione. Quando [!UICONTROL TraitWeight] riduce il valore di [!UICONTROL trait A] (o lo ignora nel modello), la popolazione della caratteristica algoritmica diminuisce. L&#39;elenco di [!UICONTROL traits] influenti riflette l&#39;evoluzione della popolazione linea di base. Utilizza l&#39;elenco degli [!UICONTROL traits] influenti per capire perché si verificano queste modifiche.

Collegamenti correlati:

* [Generatore di modelli](../../features/algorithmic-models/create-model.md)
* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)

## Aggiorna pianificazione per [!UICONTROL Look-Alike Models] e [!UICONTROL Traits] {#update-schedule}

Creazione e aggiornamento delle pianificazioni per [!UICONTROL algorithmic models] e [!UICONTROL traits] nuovi o esistenti.

### [!UICONTROL Look-Alike Model] pianificazione creazione e aggiornamento

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
   <td colname="col2"> <p>Per [!UICONTROL Look-Alike Models] nuovi o clonati, il processo di creazione viene eseguito una volta al giorno alle: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17:00 CET (novembre - marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18.00 EDT (marzo - novembre) </li> 
     </ul> </p> <p>I modelli generati o clonati dopo la scadenza per la creazione vengono elaborati il giorno successivo. </p> <p>Se la prima esecuzione di un modello non genera dati, verrà eseguita una seconda volta, ovvero il giorno successivo. Se anche il secondo tentativo non genera dati, verrà effettuato un terzo tentativo, il giorno successivo. Il modello terminerà l’esecuzione se anche il terzo tentativo non genera dati. In questo caso, il modello verrà disattivato. Ulteriori informazioni sono disponibili in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Risoluzione dei problemi relativi ai modelli lookalike</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Aggiorna modello</b> </td> 
   <td colname="col2"> <p>In condizioni ideali, i modelli esistenti vengono eseguiti nei giorni feriali, almeno una volta ogni 7 giorni. Ad esempio, se crei un modello (entro la scadenza) il lunedì, questo aggiorna al più tardi il lunedì successivo. </p> <p>Un modello viene rieseguito se soddisfa una delle seguenti condizioni: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">L’ultima esecuzione non è andata a buon fine. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">È stato eseguito correttamente prima E non è stato eseguito affatto negli ultimi 7 giorni E al modello è associata almeno una caratteristica attiva. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] pianificazione creazione e aggiornamento

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di attività </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Crea una caratteristica</b> </td> 
   <td colname="col2"> <p>Il processo di creazione delle caratteristiche viene eseguito ogni giorno, dal lunedì al venerdì. In genere, le nuove caratteristiche algoritmiche vengono visualizzate nell’interfaccia utente entro 48 ore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aggiorna una caratteristica</b> </td> 
   <td colname="col2"> <p>Le caratteristiche esistenti vengono aggiornate almeno una volta ogni 7 giorni e seguono la pianificazione per gli aggiornamenti dei modelli. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vista a elenco modelli {#models-list-view}

La vista a elenco è un’area di lavoro centrale che consente di creare, esaminare e gestire i modelli.

La pagina dell&#39;elenco [!UICONTROL Models] contiene funzionalità e strumenti utili per:

* Creare nuovi modelli.
* Gestisci i modelli esistenti (modifica, pausa, eliminazione o clonazione).
* Cerca i modelli per nome.
* Crea [!UICONTROL algorithmic traits] utilizzando un dato modello.

## Visualizzazione riepilogo modelli {#models-summary-view}

Nella pagina di riepilogo vengono visualizzati i dettagli del modello quali nome, portata/precisione, cronologia di elaborazione e [!UICONTROL traits] creato dal modello. La pagina include anche impostazioni che consentono di creare e gestire i modelli. Fare clic sul nome di un modello nell&#39;elenco di riepilogo per visualizzarne i dettagli.

La pagina di riepilogo del modello include le sezioni riportate di seguito.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sezione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> informazioni di base</span> </p> </td>
   <td colname="col2"> <p>Include informazioni di base sul modello, ad esempio il nome e l’ultima esecuzione. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> portata e precisione del modello</span> </p> </td> 
   <td colname="col2"> <p>Mostra la precisione di <a href="../../features/traits/trait-accuracy-reach.md"> e i dati di portata </a> per l'ultima esecuzione del modello. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> cronologia elaborazione modello</span> </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l'ora di elaborazione per le ultime 10 esecuzioni e indica se i dati sono stati generati in tali esecuzioni. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> caratteristiche influenti</span> </p> </td> 
   <td colname="col2"> <p>Tabella delle caratteristiche influenti <span class="wintitle"></span>: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Elenca le prime 50 caratteristiche influenti meglio rappresentate nella popolazione linea di base del modello. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica ogni caratteristica in base al relativo peso relativo <span class="wintitle"></span>. Il peso relativo <span class="wintitle"></span> ordina le caratteristiche appena scoperte in ordine di influenza o desiderabilità. La scala del peso è una percentuale compresa tra 0% e 100%. Le caratteristiche classificate più vicino al 100% indicano che sono più simili al pubblico nella popolazione linea di base. Vedi <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Informazioni su TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra gli univoci di 30 giorni e la popolazione totale delle caratteristiche per ogni caratteristica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> caratteristiche con modello</span> </p> </td>
   <td colname="col2"> <p>Mostra un elenco delle caratteristiche algoritmiche basate sul modello selezionato. Per ulteriori informazioni sulla caratteristica, fai clic sul nome o sull’ID della caratteristica. Selezionare <b><span class="uicontrol"> Crea nuova caratteristica con modello</span></b> per passare al processo di creazione delle caratteristiche algoritmiche. </p> <p>L’etichetta della sezione cambia in base al nome del modello. Ad esempio, supponiamo di creare un modello e di denominarlo Modello A. Quando carichi la pagina di riepilogo, il nome di questa sezione viene modificato in <span class="wintitle"> caratteristiche utilizzando il modello A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinazioni](../../features/destinations/destinations.md)
>* [Caratteristiche](../../features/traits/trait-details-page.md)
>* [Segmenti](../../features/segments/segments-purpose.md)
