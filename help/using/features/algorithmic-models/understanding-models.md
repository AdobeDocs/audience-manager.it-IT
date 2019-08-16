---
description: Creazione e gestione delle caratteristiche o dei segmenti utilizzati nella modellazione algoritmica, altrimenti denominato modellazione simile. Le funzionalità del modello si trovano in Audience Data > Modelli.
keywords: spessore relativo, ricerca
seo-description: Creazione e gestione delle caratteristiche o dei segmenti utilizzati nella modellazione algoritmica, altrimenti denominato modellazione simile. Le funzionalità del modello si trovano in Audience Data > Modelli.
seo-title: Informazioni sui modelli algoritmici
solution: Audience Manager
title: Informazioni sui modelli algoritmici
topic: API DIL
uuid: 39441 e 72-5316-453 d -9 aff -0 e 0 b 633 aabcd
translation-type: tm+mt
source-git-commit: 73d670225fb4170d02428a1dd163f442540e3415

---


# Informazioni sui modelli algoritmici {#about-algorithmic-models}

Creazione e gestione delle caratteristiche o dei segmenti utilizzati nella modellazione algoritmica, altrimenti denominato modellazione simile. Le funzioni del modello si trovano **[!UICONTROL Audience Data > Models]** in.

<!-- c_models.xml -->

## Informazioni sui modelli algoritmici {#understanding-models}

Le sezioni seguenti rappresentano una revisione della modellazione algoritmica in [!DNL Audience Manager]. Essi descrivono il funzionamento dei modelli, i vantaggi e il flusso di lavoro.

<!-- understanding-models.xml -->

## Trova nuovi utenti con modellazione algoritmica {#find-new-users}

La modellazione algoritmica consente di scoprire nuove audience univoche tramite analisi automatizzate dei dati. Il processo inizia quando selezionate una caratteristica o un segmento, un intervallo di tempo e le origini dati first e third-party. Le scelte fornite forniscono gli input per il modello algoritmico. Quando il processo di analisi viene eseguito, cerca gli utenti idonei in base alle caratteristiche condivise della popolazione selezionata. Al termine, questi dati sono disponibili nel Generatore [di caratteristiche](../../features/traits/about-trait-builder.md) dove potete utilizzarlo per creare caratteristiche in base [alla precisione e alla portata](../../features/traits/trait-accuracy-reach.md). Inoltre, potete creare segmenti che combinano caratteristiche algoritmiche con caratteristiche basate su regole e aggiungere altri requisiti di qualifica con espressioni booleane e operatori di confronto. La modellazione algoritmica offre un modo dinamico per estrarre il valore da tutti i dati delle caratteristiche disponibili.

## Vantaggi {#advantages}

I principali vantaggi dell'utilizzo [!DNL Audience Manager] della modellazione includono:

* **Precisione dati:** L'algoritmo viene eseguito regolarmente, per mantenere i risultati attuali e rilevanti.
* **Automazione:** Non è necessario gestire un set elevato di regole statiche. L'algoritmo troverà le audience per voi.
* **Risparmiate tempo e riducete le attività:** Con il nostro processo di modellazione non hai bisogno di indovinare quali caratteristiche o segmenti funzionano o di perdere tempo sulle campagne per scoprire nuove audience. Il modello può effettuare questa operazione.
* **Affidabilità:** La modellazione funziona con l'individuazione lato server e i processi di qualificazione che valuta i tuoi dati e i dati di terze parti a cui hai accesso. Questo significa che non è necessario vedere i visitatori sul sito per qualificarli per una caratteristica.

## Flusso di lavoro {#workflow}

Puoi gestire i modelli in **[!UICONTROL Audience Data > Models]**. Ad alto livello, il processo di flusso di lavoro comprende:

* Selezionate i dati della linea di base che desiderate valutare. Include una caratteristica o un segmento, un intervallo di tempo e origini dati (dati personali e dati di terze parti con accesso a tramite [!DNL Audience Manager]). Nel flusso di lavoro di creazione del modello potete escludere le caratteristiche che non desiderate interferire con il modello.
* Salvate il modello. Una volta salvato, il processo algoritmico di valutazione viene eseguito automaticamente. Tuttavia, il completamento del processo può richiedere fino a 7 giorni. [!DNL Audience Manager] invia un'e-mail al termine dell'algoritmo e i risultati sono disponibili per la creazione delle caratteristiche.
* Creare caratteristiche algoritmiche in [!UICONTROL Trait Builder].
* Combinate caratteristiche in segmenti.[!UICONTROL Segment Builder]
* Crea e invia dati di segmenti a una destinazione.

## Risoluzione dei problemi {#troubleshooting}

Disattiviamo qualsiasi modello algoritmico che non genera dati per tre esecuzioni consecutive. Non è possibile impostare lo stato del modello nuovamente su Attivo in seguito. Per garantire che i modelli generino dati, è consigliabile creare modelli da origini dati con caratteristiche sufficienti per accumulare i dati.

>[!MORE_ LIKE_ THIS]
>
>* [Destinazioni](../../features/destinations/destinations.md)
>* [Caratteristiche](../../features/traits/trait-details-page.md)
>* [Segmenti](../../features/segments/segments-purpose.md)


## Informazioni sulle caratteristiche {#understanding-traitweight}

[!UICONTROL TraitWeight] è un algoritmo proprietario progettato per scoprire automaticamente nuove caratteristiche. Confronta i dati delle caratteristiche con le caratteristiche e i segmenti correnti rispetto a tutti gli altri dati di prime e terze parti a cui hai accesso [!DNL Audience Manager]. Fate riferimento a questa sezione per una descrizione del [!UICONTROL TraitWeight] processo di individuazione algoritmica.

<!-- traitweight.xml -->

![](assets/algo_model.png)

La procedura descritta di seguito descrive il processo [!UICONTROL TraitWeight] di valutazione.

### Passaggio 1: Creare una linea di base per il confronto caratteristiche

Per creare una linea di base [!UICONTROL TraitWeight] , vengono misurate tutte le caratteristiche associate a un'audience per un intervallo di 30, 60 o 90 giorni. Successivamente, classifica le caratteristiche in base alla loro frequenza e alla loro correlazione. Il conteggio delle frequenze misura comuni. Correlazione misura la probabilità che una caratteristica sia presente solo nell'audience di base. Le caratteristiche che vengono visualizzate spesso si riferiscono ad alta comunalità, una caratteristica importante utilizzata per impostare un punteggio ponderato, combinato con tratti scoperti nelle origini dati selezionate.

### Passaggio 2: Trova le stesse caratteristiche nell'origine dati

Dopo aver creato una linea di base per il confronto, l'algoritmo cerca caratteristiche identiche nelle origini dati selezionate. In questo passaggio [!UICONTROL TraitWeight] , esegue un conteggio delle frequenze di tutte le caratteristiche rilevate e le confronta con la linea di base. Tuttavia, a differenza della linea di base, le caratteristiche non comuni sono più elevate rispetto a quelle visualizzate più spesso. Si parla di caratteristiche rare che mostrano un elevato grado di specificità. [!UICONTROL TraitWeight] valuta le combinazioni di caratteristiche di linea di base comuni e le caratteristiche di origine dati uncommon (altamente specifiche) in modo più influente o auspicabile rispetto alle caratteristiche comuni a entrambi i set di dati. Infatti, il nostro modello riconosce queste caratteristiche comuni e comuni e non assegna priorità eccessiva ai set di dati con correlazioni elevate. Le caratteristiche rare ottengono priorità più elevata perché sono più propensi a rappresentare utenti nuovi e unici rispetto alle caratteristiche, con un livello elevato di comune nella bacheca.

### Passaggio 3: Assegna spessore

In questo passaggio [!UICONTROL TraitWeight] classifica le caratteristiche appena rilevate in ordine di influenza o di preferenza. La scala weight è una percentuale che va da 0% a 100%. Le caratteristiche più vicine a 100% indicano che l'audience è più simile alla popolazione della linea di base. Inoltre, le caratteristiche ponderate sono preziose perché rappresentano nuovi utenti unici che possono comportarsi in modo simile al pubblico di base definito. Ricorda, [!UICONTROL TraitWeight] considera caratteristiche altamente comuni nella linea di base e specificità elevate nelle origini dati confrontate per essere più utili rispetto alle caratteristiche comuni in ciascun set di dati.

### Passaggio 4: Punteggio utenti

A ogni utente nelle origini dati selezionate viene assegnato un punteggio utente pari alla somma di tutti i tipi di caratteristiche influenti sul profilo dell'utente. I punteggi degli utenti vengono quindi normalizzati tra 0 e 100%.

### Passaggio 5: Visualizzare e lavorare con i risultati

Audience Manager visualizza i risultati del modello ponderato. [!UICONTROL Trait Builder] Quando desiderate creare una caratteristica algoritmica, [!UICONTROL Trait Builder] potete creare caratteristiche basate sulla valutazione ponderata generata dall'algoritmo durante l'esecuzione di un dato. Potete scegliere una precisione più elevata per qualificare solo gli utenti che dispongono di punteggio utente molto elevato e quindi molto simili al pubblico rispetto alla linea di base, anziché al resto del pubblico. Se desiderate raggiungere un pubblico più vasto (raggiungibile), potete ridurre l'accuratezza.

### Passaggio 6: Valutare nuovamente l'importanza di una caratteristica in cicli di elaborazione

Valuta periodicamente [!UICONTROL TraitWeight] l'importanza di una caratteristica in base alle dimensioni e cambia nella popolazione della caratteristica. Ciò si verifica in quanto il numero di utenti idonei per tale caratteristica aumenta o diminuisce nel tempo. Questo comportamento è chiaramente visualizzato nelle caratteristiche che diventano molto grandi. Ad esempio, supponiamo che l'algoritmo usa la caratteristica A per la modellazione. Mentre la popolazione di una caratteristica aumenta, [!UICONTROL TraitWeight] riscontroca l'importanza di tale caratteristica e può assegnare una valutazione inferiore o ignorarla. In questo caso, la caratteristica A è troppo comune o grande per dire qualcosa di significativo sulla popolazione. Dopo [!UICONTROL TraitWeight] aver ridotto il valore di Trait A (o ignorato nel modello), la popolazione della caratteristica algoritmica diminuisce. L'elenco di caratteristiche influenti riflette l'evoluzione della popolazione della linea di base. Utilizzate l'elenco delle caratteristiche influenti per comprendere perché si verificano tali modifiche.

Collegamenti correlati:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)

## Pianificazione aggiornamento per modelli algoritmici e caratteristiche {#update-schedule}

Creazione e aggiornamento delle pianificazioni per modelli algoritmici nuovi o esistenti.

<!-- c_model_update_schedule.xml -->

### Creazione e aggiornamento di modelli algoritmici

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
   <td colname="col2"> <p>Per i modelli algoritmici nuovi o duplicati, il processo di creazione viene eseguito una volta al giorno all'indirizzo: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (novembre - marzo) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (marzo - novembre) </li> 
     </ul> </p> <p>I modelli generati o duplicati dopo la scadenza della creazione vengono elaborati il giorno seguente. </p> <p>Se la prima esecuzione di un modello non genera dati, viene eseguito una seconda volta, il giorno successivo. Se anche il secondo tentativo non genera dati, si verificherà un terzo tentativo, il giorno successivo. Il modello smetterà di funzionare se anche il terzo tentativo non genera dati. In questo caso, il modello verrà disattivato. Ulteriori informazioni in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Risoluzione dei problemi relativi ai modelli algoritmici</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Aggiornare un modello</b> </td> 
   <td colname="col2"> <p>In condizioni ideali, i modelli esistenti vengono eseguiti nei giorni feriali, almeno una volta ogni 7 giorni. Ad esempio, se crei un modello (entro la scadenza) di lunedì, esso viene aggiornato al più recente lunedì. </p> <p>Un modello verrà eseguito nuovamente se soddisfa una delle condizioni seguenti: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">L'ultima esecuzione non è riuscita. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">È stata eseguita prima e non è stata eseguita affatto negli ultimi 7 giorni e al modello è associata almeno una caratteristica attiva. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Creazione di caratteristiche algoritmica e aggiornamento dell'aggiornamento

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
   <td colname="col2"> <p>Il processo di creazione delle caratteristiche viene eseguito ogni giorno, da lunedì a venerdì. In genere, le nuove caratteristiche algoritmiche vengono visualizzate nell'interfaccia utente entro 48 ore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aggiornare una caratteristica</b> </td> 
   <td colname="col2"> <p>Le caratteristiche esistenti vengono aggiornate almeno una volta ogni 7 giorni e seguono la pianificazione per gli aggiornamenti del modello. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Visualizzazione elenco modelli {#models-list-view}

La vista Elenco è un'area di lavoro centrale che consente di creare, rivedere e gestire i modelli.

<!-- c_models_list_view.xml -->

La pagina Elenco modelli contiene funzioni e strumenti utili per:

* Creare nuovi modelli.
* Gestire modelli esistenti (modifica, pausa, eliminazione o duplicazione).
* Cercare modelli per nome.
* Create caratteristiche algoritmiche utilizzando un qualsiasi modello.

## Visualizzazione Riepilogo modelli {#models-summary-view}

La pagina di riepilogo visualizza i dettagli del modello quali nome, portata/accuratezza, cronologia di elaborazione e caratteristiche create dal modello. La pagina comprende inoltre impostazioni che consentono di creare e gestire modelli. Fate clic sul nome di un modello nell'elenco di riepilogo per visualizzarne i dettagli.

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
   <td colname="col2"> <p>Include informazioni di base sul modello, ad esempio il nome e l'ultima esecuzione. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Precisione e precisione del modello</span> </p> </td> 
   <td colname="col2"> <p>Mostra <a href="../../features/traits/trait-accuracy-reach.md"> precisione e dati per</a> l'ultimo modello eseguito. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Cronologia elaborazione modello</span> </p> </td> 
   <td colname="col2"> <p>Visualizza la data e l'ora di elaborazione per l'ultimo 10 e indica se i dati sono stati generati su di essi. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caratteristiche influenti</span> </p> </td> 
   <td colname="col2"> <p>La tabella <span class="wintitle"> Caratteristiche</span> influenti: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Elenca le prime 50 caratteristiche influenti più rappresentate nella popolazione della linea di base del modello. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classifica ogni caratteristica in base <span class="wintitle"> al grado Spessore</span> relativo. Spessore <span class="wintitle"> relativo</span> ordina le caratteristiche appena rilevate in ordine di influenza o di preferenza. La scala weight è una percentuale che va da 0% a 100%. Le caratteristiche più vicine a 100% indicano che l'audience è più simile alla popolazione della linea di base. Vedere <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Informazioni su caratteristica</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Mostra le cifre di 30 giorni e la popolazione totale di caratteristiche per ogni caratteristica. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caratteristiche con modello</span> </p> </td>
   <td colname="col2"> <p>Mostra un elenco delle caratteristiche algoritmiche basate sul modello selezionato. Fai clic su un nome o un ID caratteristica per ulteriori informazioni sul tratto. Selezionate <b><span class="uicontrol"> Crea nuova caratteristica con modello</span></b> per passare al processo di creazione algoritmica delle caratteristiche. </p> <p>L'etichetta della sezione cambia in base al nome del modello. Ad esempio, supponete di creare un modello e denominarlo Model A. Quando si carica la pagina di riepilogo, il nome di questa sezione viene modificato in <span class="wintitle"> Caratteristiche utilizzando il modello A</span>. </p> </td>
  </tr>
 </tbody>
</table>