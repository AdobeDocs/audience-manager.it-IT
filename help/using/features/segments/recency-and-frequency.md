---
description: In Segment Builder (Generatore di segmenti), la frequenza e la frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.
seo-description: In Segment Builder (Generatore di segmenti), la frequenza e la frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.
seo-title: Attualità e frequenza
solution: Audience Manager
title: Attualità e frequenza
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: 'Segmenti '
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---

# Attualità e frequenza {#recency-and-frequency}

In [!UICONTROL Segment Builder], aggiornamento e frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.

L&#39;Audience Manager definisce [!DNL recency] e [!DNL frequency] come segue:

* **[!UICONTROL Recency]:** quanto recentemente un utente ha visualizzato o qualificato per uno (o più)  [!UICONTROL traits].
* **[!UICONTROL Frequency]:** La frequenza con cui un utente ha visualizzato o qualificato uno (o più)  [!UICONTROL traits].

[!UICONTROL Recency] e  [!UICONTROL Frequency] le impostazioni consentono di segmentare i visitatori in base al loro livello di interesse reale (o percepito) in un sito, una sezione o un particolare contenuto creativo. Ad esempio, gli utenti qualificati per un segmento con requisiti di recency/frequenza elevati possono essere più interessati a un sito o a un prodotto rispetto agli utenti che visitano meno spesso o meno frequentemente.

## Posizione delle impostazioni [!UICONTROL Recency and Frequency] {#location}

In [!UICONTROL Segment Builder], le impostazioni [!UICONTROL Recency] e [!UICONTROL Frequency] si trovano nella sezione [!UICONTROL Basic View] del pannello [!UICONTROL Traits]. Fare clic sull&#39;icona dell&#39;orologio per esporre questi controlli.

![](assets/recency_frequency.png)

## Limitazioni e regole {#limitations-rules}

Rivedi e comprendi questi limiti e regole quando desideri applicare recency e frequenza alle caratteristiche nei tuoi segmenti.

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limite o regola </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Valore minimo</b> </p> </td> 
   <td colname="col2"> <p>Il numero di aggiornamento deve essere maggiore di 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Tipi di caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Puoi applicare controlli di aggiornamento solo alle caratteristiche basate su regole e cartelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche di terze parti</b> </p> </td> 
   <td colname="col2"> <p>Non è possibile impostare regole di aggiornamento sulle singole caratteristiche di terze parti o sui gruppi di caratteristiche che contengono caratteristiche di terze parti. La recency e la frequenza si applicano solo alle tue caratteristiche. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limite o regola </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche di terze parti</b> </p> </td> 
   <td colname="col2"> <p>Non puoi impostare regole di frequenza sulle singole caratteristiche di terze parti o sui gruppi di caratteristiche che contengono caratteristiche di terze parti. La recency e la frequenza si applicano solo alle tue caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tipi di caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>È possibile applicare controlli di frequenza solo alle caratteristiche basate su regole e cartelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisiti di aggiornamento</b> </p> </td> 
   <td colname="col2"> <p>È possibile configurare i requisiti di frequenza <i>senza</i> configurare i requisiti di aggiornamento. Imposta un valore di frequenza e lascia vuoto il campo recency. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regole di unione profili</b> </p> </td> 
   <td colname="col2"> <p>Consulta <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frequenza delle caratteristiche, grafici dei dispositivi esterni e regole di unione profili</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi recenti {#recency-examples}

Di seguito sono riportati due esempi del funzionamento della funzione di aggiornamento, a seconda della selezione effettuata nell’interfaccia utente:

### Utilizzo di un operatore minore o uguale a (&lt;=)

![Minore di uguale a](assets/less-than-equal-to.png)

In questo esempio, selezioni l’operatore &lt;= , come mostrato nella schermata . Questo rende l&#39;utente idoneo per [!UICONTROL segment] se si qualifica per uno dei tre [!UICONTROL traits] almeno tre volte negli ultimi cinque giorni. La timeline seguente mostra la [!UICONTROL segment] qualifica al momento della creazione di [!UICONTROL segment], il 1° ottobre e dieci giorni dopo.

![Ultimi cinque giorni](assets/last-5-days.png)

### Utilizzo di un operatore maggiore o uguale a (=>)

![Maggiore di uguale a](assets/greater-than-equal-to.png)

In questo esempio, selezioni l’operatore => , come mostrato nella schermata . Questo rende l’utente idoneo per [!UICONTROL segment] se soddisfa uno dei tre [!UICONTROL traits] almeno tre volte tra la prima qualifica sulla piattaforma di Audience Manager e l’orario limite di cinque giorni fa. La timeline seguente mostra la [!UICONTROL segment] qualifica al momento della creazione di [!UICONTROL segment], il 1° ottobre e dieci giorni dopo.

![Qualificazione precedente](assets/earlier-qualification.png)


## Esempi di limitazione di frequenza {#frequency-capping}

Le espressioni di limitazione della frequenza includono tutti gli utenti il cui numero di [!UICONTROL trait] realizzazioni è inferiore a un valore desiderato. Di seguito sono riportati alcuni esempi corretti e errati:

* Sbagliato : l&#39;espressione `frequency([1000T]) <= 5` include tutti gli utenti che hanno realizzato il [!UICONTROL trait] con l&#39;ID &quot;1000&quot; al massimo cinque volte, ma include anche gli utenti che non hanno realizzato il [!UICONTROL trait]. Pertanto, Audience Manager non convalida questa espressione per motivi di prestazioni, in quanto qualificherebbe troppi utenti per il [!UICONTROL segment].

* A destra: se desideri includere tutti gli utenti che hanno realizzato il [!UICONTROL trait] con l&#39;ID &quot;1000&quot; un massimo di cinque volte, aggiungi un&#39;altra condizione all&#39;espressione, per assicurarti che gli utenti si siano qualificati per il [!UICONTROL trait] almeno una volta:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* A destra: quando hai bisogno di requisiti di recency/frequenza inferiori a un numero specifico di volte o giorni, unisciti a un altro [!UICONTROL trait] con un operatore `AND`. Utilizzando l’esempio nel primo punto elenco, questa espressione diventa valida quando è unita a un altro elemento [!UICONTROL trait] come mostrato di seguito: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* A destra: per i casi di utilizzo di limite di frequenza per pubblicità, puoi creare una regola [!UICONTROL segment] simile a questa: `(frequency([1000T] <= 2D) >= 5)`. Questa espressione include tutti gli utenti che hanno realizzato il [!UICONTROL trait] con l&#39;ID &quot;1000&quot; negli ultimi 2 giorni almeno cinque volte. Imposta il limite di frequenza inviando questo [!UICONTROL segment] al server di annunci con un `NOT` impostato sul [!UICONTROL segment] nel server di annunci. Questo approccio offre prestazioni migliori in [!DNL Audience Manager] pur continuando a fornire lo stesso scopo per i limiti di frequenza.

>[!MORELIKETHIS]
>
>* [Controlli del Generatore di segmenti: Sezione Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits)
* [Sintassi di codice utilizzata nell’editor di espressioni di segmenti](../../features/segments/segment-code-syntax.md)

