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
source-wordcount: '1576'
ht-degree: 1%

---

# Informazioni [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Trova nuovi utenti con [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] consente di scoprire tipi di pubblico nuovi e univoci tramite l’analisi automatizzata dei dati. Il processo viene avviato quando si seleziona una [!UICONTROL trait] o [!UICONTROL segment], un intervallo di tempo e la prima e terza parte [!UICONTROL data sources]. Le scelte effettuate forniscono gli input per il modello algoritmico. Durante l’esecuzione del processo di analisi, vengono cercati gli utenti idonei in base alle caratteristiche condivise della popolazione selezionata. Al termine, questi dati sono disponibili in [Generatore di caratteristiche](../../features/traits/about-trait-builder.md) dove puoi utilizzarlo per creare caratteristiche basate su [precisione e portata](../../features/traits/trait-accuracy-reach.md). Inoltre, puoi creare segmenti che combinano caratteristiche algoritmiche con [!UICONTROL rules-based traits] e aggiungere altri requisiti di qualifica con [!DNL Boolean] espressioni e operatori di confronto. [!UICONTROL Look-Alike Modeling] offre un modo dinamico di estrarre valore da tutti i dati delle caratteristiche disponibili.

## Vantaggi {#advantages}

Vantaggi principali dell&#39;utilizzo di [!UICONTROL Look-Alike Modeling] include:

* **Precisione dei dati:** L’algoritmo viene eseguito regolarmente, il che consente di mantenere i risultati aggiornati e rilevanti.
* **Automazione:** Non è necessario gestire un set elevato di regole statiche. L’algoritmo troverà i tipi di pubblico per te.
* **Risparmio di tempo e riduzione dell&#39;impegno:** Con il nostro processo di modellazione non è necessario indovinare a cosa [!UICONTROL traits]/[!UICONTROL segments] può lavorare o dedicare tempo alle campagne per scoprire nuovi tipi di pubblico. Il modello può farlo per voi.
* **Affidabilità:** La modellazione funziona con processi di individuazione e qualificazione lato server che valutano i tuoi dati e quelli di terze parti selezionati a cui hai accesso. Ciò significa che non è necessario visualizzare i visitatori sul sito per qualificarli per una caratteristica.

## Flusso di lavoro {#workflow}

Gestione dei modelli in **[!UICONTROL Audience Data > Models]**. Ad alto livello, il processo del flusso di lavoro prevede quanto segue:

* Selezionare i dati della baseline che si desidera vengano valutati dall&#39;algoritmo. Ciò include [!UICONTROL trait] o [!UICONTROL segment], intervallo di tempo e [!UICONTROL data sources] (i tuoi dati e i dati di terze parti a cui hai già accesso tramite [!DNL Audience Manager]). Nel flusso di lavoro di creazione del modello, puoi escludere [!UICONTROL traits] che non si desidera interferire con il modello.
* Salva il modello. Una volta salvato, il processo di valutazione algoritmica viene eseguito automaticamente. Tuttavia, il completamento di questo processo può richiedere fino a 7 giorni. [!DNL Audience Manager] ti invia un’e-mail quando l’algoritmo è terminato e i risultati sono disponibili per [!UICONTROL trait] creazione.
* Genera algoritmo [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Combina [!UICONTROL traits] in [!UICONTROL segments] in [!UICONTROL Segment Builder].
* Creare e inviare [!UICONTROL segment] dati in una [!UICONTROL destination].

## Risoluzione dei problemi {#troubleshooting}

Disattiviamo qualsiasi [!UICONTROL Look-Alike Model] che non genera dati per tre esecuzioni consecutive. Non potete riattivare lo stato del modello in seguito. Per garantire che i modelli generino dati, si consiglia di creare modelli da origini dati con [!UICONTROL traits] per accumulare dati da.

## Informazioni [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] è un algoritmo proprietario progettato per scoprire [!UICONTROL traits] automaticamente. Confronta [!UICONTROL trait] dati dal tuo attuale [!UICONTROL traits] e [!UICONTROL segments] rispetto a tutti gli altri dati di prime e terze parti a cui hai accesso tramite [!DNL Audience Manager]. Fai riferimento a questa sezione per una descrizione del [!UICONTROL TraitWeight] processo di individuazione algoritmica.

![](assets/algo_model.png)

I passaggi seguenti descrivono [!UICONTROL TraitWeight] processo di valutazione.

### Passaggio 1: creare una baseline per [!UICONTROL Trait] Confronto

Per creare una linea di base, [!UICONTROL TraitWeight] misura tutte le [!UICONTROL traits] associato a un pubblico per un intervallo di 30, 60 o 90 giorni. Quindi, classifica [!UICONTROL traits] in base alla loro frequenza e correlazione. Il conteggio delle frequenze misura la compatibilità. La correlazione misura la probabilità di un [!UICONTROL trait] essere presente solo nel pubblico di riferimento. [!UICONTROL Traits] che appaiono spesso mostrano un&#39;elevata comunanza, una caratteristica importante utilizzata per impostare un punteggio ponderato quando combinato con [!UICONTROL traits] individuato nel file [!UICONTROL data sources].

### Passaggio 2: Trovare lo stesso [!UICONTROL Traits] nel [!UICONTROL Data Source]

Dopo aver creato una linea di base per il confronto, l&#39;algoritmo cerca lo stesso [!UICONTROL traits] nel file selezionato [!UICONTROL data sources]. In questo passaggio, [!UICONTROL TraitWeight] esegue un conteggio di frequenza di tutti gli elementi individuati [!UICONTROL traits] e li confronta con la linea di base. Tuttavia, a differenza della linea di base, non comune [!UICONTROL traits] sono classificati più in alto di quelli che appaiono più spesso. Raro [!UICONTROL traits] presentano un elevato grado di specificità. [!UICONTROL TraitWeight] valuta le combinazioni di un basale comune [!UICONTROL traits] e non comuni (altamente specifici) [!UICONTROL data source] [!UICONTROL traits] più influente o auspicabile di [!UICONTROL traits] comune a entrambi i set di dati. Infatti, il nostro modello riconosce questi grandi, comuni [!UICONTROL traits] e non assegna una priorità eccessiva a set di dati con correlazioni elevate. Raro [!UICONTROL traits] ottenere una priorità più elevata perché è più probabile che rappresentino nuovi utenti univoci rispetto a [!UICONTROL traits] con un&#39;elevata uniformità a tutti i livelli.

### Passaggio 3: assegnare il peso

In questo passaggio, [!UICONTROL TraitWeight] ranghi appena scoperti [!UICONTROL traits] in ordine di influenza o di desiderabilità. La scala del peso è una percentuale compresa tra 0% e 100%. [!UICONTROL Traits] classificato più vicino al 100% significa che è più simile al pubblico nella popolazione linea di base. Inoltre, pesantemente ponderato [!UICONTROL traits] sono utili perché rappresentano nuovi utenti univoci che possono comportarsi in modo simile al pubblico di base consolidato. Ricorda: [!UICONTROL TraitWeight] considera [!UICONTROL traits] con elevata compatibilità nella linea di base e alta specificità nelle fonti di dati confrontate per essere più preziosi di [!UICONTROL traits] comuni in ciascun set di dati.

### Passaggio 4: assegnazione del punteggio agli utenti

Ogni utente nella [!UICONTROL data sources] viene assegnato un punteggio utente uguale alla somma di tutti i pesi dell’influente [!UICONTROL traits] sul profilo di tale utente. I punteggi utente vengono quindi normalizzati tra 0 e 100%.

### Passaggio 5: visualizzare e utilizzare i risultati

[!DNL Audience Manager] visualizza i risultati del modello ponderato in [!UICONTROL Trait Builder]. Quando desideri creare un’ [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] consente di creare [!UICONTROL traits] in base al punteggio ponderato generato dall’algoritmo durante un’esecuzione dei dati. Puoi scegliere una precisione più elevata per qualificare solo gli utenti con punteggi molto elevati e quindi molto simili al pubblico di riferimento, anziché al resto del pubblico. Se desideri raggiungere un pubblico più ampio (portata), puoi ridurne la precisione.

### Passaggio 6: rivalutare il significato di una [!UICONTROL Trait] Tra cicli di elaborazione

periodicamente, [!UICONTROL TraitWeight] rivaluta l&#39;importanza di un [!UICONTROL trait] in base alle dimensioni e alla variazione della popolazione di tale [!UICONTROL trait]. Questo accade quando il numero di utenti qualificati per tale operazione [!UICONTROL trait] aumenta o diminuisce nel tempo. Questo comportamento si nota soprattutto nelle caratteristiche che diventano molto grandi. Ad esempio, supponiamo che l’algoritmo utilizzi [!UICONTROL trait A] per modellare. Come popolazione di [!UICONTROL trait A] aumenti, [!UICONTROL TraitWeight] rivaluta l&#39;importanza di tale [!UICONTROL trait] e possono assegnare un punteggio inferiore o ignorarlo. In questo caso, [!UICONTROL trait A] è troppo comune o grande per dire qualcosa di significativo sulla sua popolazione. Dopo [!UICONTROL TraitWeight] riduce il valore di [!UICONTROL trait A] (o lo ignora nel modello), la popolazione della caratteristica algoritmica diminuisce. L&#39;elenco degli influenti [!UICONTROL traits] riflette l’evoluzione della popolazione al basale. Utilizza l’elenco delle influenti [!UICONTROL traits] per capire perché si verificano questi cambiamenti.

Collegamenti correlati:

* [Generatore di modelli](../../features/algorithmic-models/create-model.md)
* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)

## Aggiorna pianificazione per [!UICONTROL Look-Alike Models] e [!UICONTROL Traits] {#update-schedule}

Creazione e aggiornamento di pianificazioni per nuove o esistenti [!UICONTROL algorithmic models] e [!UICONTROL traits].

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
   <td colname="col2"> <p>Per nuovo o clonato [!UICONTROL Look-Alike Models], il processo di creazione viene eseguito una volta al giorno alle: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17:00 CET (novembre - marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18.00 EDT (marzo - novembre) </li> 
     </ul> </p> <p>I modelli generati o clonati dopo la scadenza per la creazione vengono elaborati il giorno successivo. </p> <p>Se la prima esecuzione di un modello non genera dati, verrà eseguita una seconda volta, ovvero il giorno successivo. Se anche il secondo tentativo non genera dati, verrà effettuato un terzo tentativo, il giorno successivo. Il modello terminerà l’esecuzione se anche il terzo tentativo non genera dati. In questo caso, il modello verrà disattivato. Ulteriori informazioni in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Risoluzione dei problemi dei modelli lookalike</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Aggiornare un modello</b> </td> 
   <td colname="col2"> <p>In condizioni ideali, i modelli esistenti vengono eseguiti nei giorni feriali, almeno una volta ogni 7 giorni. Ad esempio, se crei un modello (entro la scadenza) il lunedì, questo aggiorna al più tardi il lunedì successivo. </p> <p>Un modello viene rieseguito se soddisfa una delle seguenti condizioni: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">L’ultima esecuzione non è andata a buon fine. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">È stato eseguito correttamente prima E non è stato eseguito affatto negli ultimi 7 giorni E al modello è associata almeno una caratteristica attiva. </li>
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
   <td colname="col2"> <p>Le caratteristiche esistenti vengono aggiornate almeno una volta ogni 7 giorni e seguono la pianificazione per gli aggiornamenti dei modelli. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vista a elenco modelli {#models-list-view}

La vista a elenco è un’area di lavoro centrale che consente di creare, esaminare e gestire i modelli.

Il [!UICONTROL Models] La pagina dell’elenco contiene funzioni e strumenti che consentono di:

* Creare nuovi modelli.
* Gestisci i modelli esistenti (modifica, pausa, eliminazione o clonazione).
* Cerca i modelli per nome.
* Crea [!UICONTROL algorithmic traits] utilizzando un dato modello.

## Visualizzazione riepilogo modelli {#models-summary-view}

La pagina di riepilogo mostra i dettagli del modello come nome, portata/precisione, cronologia di elaborazione e [!UICONTROL traits] creato dal modello. La pagina include anche impostazioni che consentono di creare e gestire i modelli. Fare clic sul nome di un modello nell&#39;elenco di riepilogo per visualizzarne i dettagli.

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
   <td colname="col1"> <p> <span class="wintitle"> Informazioni di base</span> </p> </td>
   <td colname="col2"> <p>Include informazioni di base sul modello, ad esempio il nome e l’ultima esecuzione. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Portata e precisione del modello</span> </p> </td> 
   <td colname="col2"> <p>Show <a href="../../features/traits/trait-accuracy-reach.md"> precisione e portata</a> dati per l’ultima esecuzione del modello. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Cronologia elaborazione modello</span> </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l'ora di elaborazione per le ultime 10 esecuzioni e indica se i dati sono stati generati in tali esecuzioni. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caratteristiche influenti</span> </p> </td> 
   <td colname="col2"> <p>Il <span class="wintitle"> Caratteristiche influenti</span> tabella: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Elenca le prime 50 caratteristiche influenti meglio rappresentate nella popolazione linea di base del modello. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica ogni caratteristica in ordine di <span class="wintitle"> Peso relativo</span> grado. Il <span class="wintitle"> Peso relativo</span> ordina le caratteristiche appena scoperte in ordine di influenza o desiderabilità. La scala del peso è una percentuale compresa tra 0% e 100%. Le caratteristiche classificate più vicino al 100% indicano che sono più simili al pubblico nella popolazione linea di base. Consulta <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Informazioni su TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra gli univoci di 30 giorni e la popolazione totale delle caratteristiche per ogni caratteristica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caratteristiche che utilizzano il modello</span> </p> </td>
   <td colname="col2"> <p>Mostra un elenco delle caratteristiche algoritmiche basate sul modello selezionato. Per ulteriori informazioni sulla caratteristica, fai clic sul nome o sull’ID della caratteristica. Seleziona <b><span class="uicontrol"> Creare una nuova caratteristica con il modello</span></b> per passare al processo di creazione delle caratteristiche algoritmiche. </p> <p>L’etichetta della sezione cambia in base al nome del modello. Ad esempio, supponiamo di creare un modello e di denominarlo Modello A. Quando carichi la pagina di riepilogo, il nome di questa sezione viene modificato in <span class="wintitle"> Caratteristiche che utilizzano il modello A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinazioni ](../../features/destinations/destinations.md)
>* [Caratteristiche ](../../features/traits/trait-details-page.md)
>* [Segmenti ](../../features/segments/segments-purpose.md)

