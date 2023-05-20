---
description: In Segment Builder (Generatore di segmenti), recency e frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un intervallo giornaliero impostato.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Attualità e frequenza
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 2%

---

# Attualità e frequenza {#recency-and-frequency}

In entrata [!UICONTROL Segment Builder], recency e frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un intervallo giornaliero impostato.

Audience Manager definisce [!DNL recency] e [!DNL frequency] come segue:

* **[!UICONTROL Recency]:** Ultima data di visualizzazione o qualificazione di un utente per uno (o più) [!UICONTROL traits].
* **[!UICONTROL Frequency]:** Frequenza con cui un utente ha visualizzato o qualificato per uno (o più) [!UICONTROL traits].

[!UICONTROL Recency] e [!UICONTROL Frequency] Le impostazioni consentono di segmentare i visitatori in base al loro livello reale (o percepito) di interesse in un sito, una sezione o una particolare creatività. Ad esempio, gli utenti che si qualificano per un segmento con requisiti di frequenza/attualità elevati possono essere più interessati a un sito o a un prodotto rispetto agli utenti che visitano meno spesso o meno frequentemente.

## Posizione di [!UICONTROL Recency and Frequency] Impostazioni {#location}

In entrata [!UICONTROL Segment Builder], [!UICONTROL Recency] e [!UICONTROL Frequency] Le impostazioni di si trovano in [!UICONTROL Basic View] sezione del [!UICONTROL Traits] pannello. Fare clic sull&#39;icona dell&#39;orologio per esporre questi controlli.

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
   <td colname="col2"> <p>Il valore di recency deve essere maggiore di 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Tipi di caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Puoi applicare i controlli di attualità solo alle caratteristiche basate su regole e cartelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche di terze parti</b> </p> </td> 
   <td colname="col2"> <p>Non è possibile impostare regole di attualità su singole caratteristiche di terze parti o su gruppi di caratteristiche contenenti caratteristiche di terze parti. L’attualità e la frequenza si applicano solo alle caratteristiche dell’utente. </p> </td> 
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
   <td colname="col2"> <p>Non puoi impostare regole di frequenza per caratteristiche di terze parti singole o gruppi di caratteristiche che contengono caratteristiche di terze parti. L’attualità e la frequenza si applicano solo alle caratteristiche dell’utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tipi di caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Puoi applicare i controlli di frequenza solo alle caratteristiche basate su regole e cartelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisiti di recency</b> </p> </td> 
   <td colname="col2"> <p>È possibile configurare i requisiti di frequenza <i>senza</i> configurazione dei requisiti di aggiornamento. È sufficiente impostare un valore di frequenza e lasciare vuoto il campo di aggiornamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regole di unione profili</b> </p> </td> 
   <td colname="col2"> <p>Consulta <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frequenza delle caratteristiche, grafici dei dispositivi esterni e regole di unione profili</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di attualità {#recency-examples}

Di seguito sono riportati due esempi di funzionamento di recency, a seconda della selezione effettuata nell’interfaccia utente:

### Utilizzo di un operatore minore o uguale a (&lt;=)

![Less-than-equal-to](assets/less-than-equal-to.png)

In questo esempio, seleziona l’operatore &lt;=, come mostrato nella schermata. Questo qualifica l’utente per [!UICONTROL segment] se sono idonei per uno dei tre [!UICONTROL traits] almeno tre volte negli ultimi cinque giorni. La timeline che segue mostra [!UICONTROL segment] qualifica al momento della [!UICONTROL segment] viene creato il 1° ottobre e dieci giorni dopo.

![Ultimi cinque giorni](assets/last-5-days.png)

### Utilizzo di un operatore maggiore o uguale a (=>)

![Maggiore di uguale a](assets/greater-than-equal-to.png)

In questo esempio, seleziona l’operatore =>, come mostrato nella schermata. Questo qualifica l’utente per [!UICONTROL segment] se sono idonei per uno dei tre [!UICONTROL traits] almeno tre volte tra la prima qualificazione sulla piattaforma di Audience Manager e il cut-off di cinque giorni fa. La timeline che segue mostra [!UICONTROL segment] qualifica al momento della [!UICONTROL segment] viene creato il 1° ottobre e dieci giorni dopo.

![Qualificazione precedente](assets/earlier-qualification.png)


## Esempi di limite di frequenza {#frequency-capping}

Le espressioni di quota limite includono tutti gli utenti il cui numero di [!UICONTROL trait] Le realizzazioni sono inferiori al valore desiderato. Di seguito sono riportati alcuni esempi di utilizzo corretto e non corretto:

* Sbagliato: l’espressione `frequency([1000T]) <= 5` include tutti gli utenti che hanno realizzato [!UICONTROL trait] con l’ID &quot;1000&quot; un massimo di cinque volte, ma include anche gli utenti che non hanno realizzato [!UICONTROL trait]. Pertanto, Audience Manager non convalida questa espressione per motivi di prestazioni, in quanto qualificherebbe troppi utenti per la [!UICONTROL segment].

* A destra: per includere tutti gli utenti che hanno realizzato [!UICONTROL trait] con l’ID &quot;1000&quot; un massimo di cinque volte, aggiungi un’altra condizione all’espressione, per assicurarti che gli utenti siano qualificati per [!UICONTROL trait] almeno una volta:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* A destra: quando i requisiti di recency/frequenza devono essere inferiori a un numero specifico di volte o giorni, unisciti a quello [!UICONTROL trait] a un altro con un `AND` operatore. Utilizzando l&#39;esempio nel primo punto elenco, questa espressione diventa valida quando viene unita con un&#39;altra [!UICONTROL trait] come mostrato di seguito: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* A destra: per i casi di utilizzo dei limiti di frequenza per la pubblicità, puoi creare una [!UICONTROL segment] regola simile a questa: `(frequency([1000T] <= 2D) >= 5)`. Questa espressione include tutti gli utenti che hanno realizzato [!UICONTROL trait] con l’ID &quot;1000&quot; almeno cinque volte negli ultimi 2 giorni. Imposta il limite di frequenza inviando questo [!UICONTROL segment] al server di annunci con un `NOT` impostato su [!UICONTROL segment] nel server di annunci. Questo approccio migliora le prestazioni in [!DNL Audience Manager] pur continuando a servire lo stesso scopo per il limite di frequenza.

>[!MORELIKETHIS]
>
>* [Controlli del Generatore di segmenti: sezione Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintassi di codice utilizzata nell’editor di espressioni di segmenti](../../features/segments/segment-code-syntax.md)

