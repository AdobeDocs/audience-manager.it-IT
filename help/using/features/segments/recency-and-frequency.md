---
description: In Segment Builder (Generatore di segmenti), la frequenza e la frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.
seo-description: In Segment Builder (Generatore di segmenti), la frequenza e la frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.
seo-title: Recency e frequenza
solution: Audience Manager
title: Recency e frequenza
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: 1cbff10b9e978755e139e7d5b996249de5ebb5bd

---


# Recency e frequenza {#recency-and-frequency}

In [!UICONTROL Segment Builder]recency e frequenza potete segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.

Audience Manager definisce [!DNL recency] e [!DNL frequency] come segue:

* **[!UICONTROL Recency]** : Recente visualizzazione o qualifica di un utente per una o più caratteristiche.
* **[!UICONTROL Frequency]** : Frequenza con cui un utente ha visualizzato o qualificato una o più caratteristiche.

[!UICONTROL Recency] e [!UICONTROL Frequency] le impostazioni consentono di segmentare i visitatori in base al loro livello di interesse reale (o percepito) in un sito, una sezione o un particolare contenuto creativo. Ad esempio, gli utenti idonei per un segmento con requisiti di recency/frequenza elevati possono essere più interessati a un sito o a un prodotto rispetto agli utenti che visitano meno spesso o meno frequentemente.

## Posizione delle impostazioni di aggiornamento e frequenza {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] e [!UICONTROL Frequency] le impostazioni si trovano nella [!UICONTROL Basic View] sezione del [!UICONTROL Traits] pannello. Click the clock icon to expose these controls.

![](assets/recency_frequency.png)

## Limitazioni e regole {#limitations-rules}

Controlla e comprendi questi limiti e queste regole quando vuoi applicare recency e frequenza alle caratteristiche dei tuoi segmenti.

### Recency

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
   <td colname="col2"> <p>Recency must be greater than 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Tipi di caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Potete applicare controlli di aggiornamento solo alle caratteristiche basate su regole e alle cartelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche di terze parti</b> </p> </td> 
   <td colname="col2"> <p>You cannot set recency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Frequenza

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
   <td colname="col2"> <p>You cannot set frequency rules on individual third-party traits or trait groups that contain third-party traits. Recency e frequenza si applicano solo alle proprie caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Trait Types</b> </p> </td> 
   <td colname="col2"> <p>You can apply frequency controls to rule-based and folder traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Recency Requirements</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements without configuring recency requirements. <i></i> Just set a frequency value and leave the recency field blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profile Merge Rules</b> </p> </td> 
   <td colname="col2"> <p>See  Trait Frequency, External Device Graphs, and Profile Merge Rules.<a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"></a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recency Examples {#recency-examples}

Here are two examples of how recency works, depending on your selection in the UI:

### Using a less than or equal to operator (&lt;=)

![Minore di uguale a](assets/less-than-equal-to.png)

In questo esempio, viene selezionato l'operatore &lt;=, come mostrato nella schermata. Questo qualifica l’utente per il segmento se soddisfa i requisiti per una delle tre caratteristiche almeno tre volte negli ultimi cinque giorni. La timeline seguente mostra la qualifica del segmento al momento della creazione del segmento, il 1° ottobre e dieci giorni dopo.

![Ultimi cinque giorni](assets/last-5-days.png)

### Utilizzo di un operatore maggiore o uguale a (=&gt;)

![Maggiore di uguale a](assets/greater-than-equal-to.png)

In questo esempio, si seleziona l'operatore =&gt;, come mostrato nella schermata. Questo qualifica l’utente per il segmento se soddisfa le condizioni per una delle tre caratteristiche almeno tre volte tra la prima qualifica sulla piattaforma Audience Manager e l’ora di interruzione cinque giorni fa. La timeline seguente mostra la qualifica del segmento al momento della creazione del segmento, il 1° ottobre e dieci giorni dopo.

![Qualifica precedente](assets/earlier-qualification.png)


## Esempi di maschiatura delle frequenze {#frequency-capping}

Le espressioni di capping delle frequenze includono tutti gli utenti il cui numero di realizzazioni delle caratteristiche è inferiore al valore desiderato. Di seguito sono riportati alcuni esempi Right e Wrong:

* Sbagliato - L'espressione `frequency([1000T]) <= 5` include tutti gli utenti che hanno realizzato la caratteristica con l'ID "1000" al massimo cinque volte, ma include anche gli utenti che non hanno realizzato la caratteristica. Pertanto, Audience Manager non convalida questa espressione per motivi di prestazioni, in quanto qualificherebbe troppi utenti per il segmento.

* Right - Se desiderate includere tutti gli utenti che hanno realizzato la caratteristica con l'ID "1000" al massimo cinque volte, aggiungete un'altra condizione all'espressione, per essere certi che gli utenti abbiano acquisito la caratteristica almeno una volta:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Right - Quando è necessario che i requisiti di recency/frequenza siano inferiori a un numero specifico di volte o giorni, unisci la caratteristica a un altro con un `AND` operatore. Using the example in the first bullet point, this expression becomes valid when joined with another trait as shown here: .`frequency([1000T]) <= 5 AND isSiteVisitorTrait`

* Right - Per i casi di utilizzo di limite di frequenza pubblicitario, potete creare una regola di segmento simile a questa: `(frequency([1000T] <= 2D) >= 5)`. Questa espressione include tutti gli utenti che hanno realizzato la caratteristica con l'ID "1000" negli ultimi 2 giorni almeno cinque volte. Impostare il limite di frequenza inviando questo segmento al server di annunci con un `NOT` set sul segmento nel server di annunci. Questo approccio consente di ottenere prestazioni migliori [!DNL Audience Manager] pur continuando a servire lo stesso scopo per i limiti di frequenza.

>[!MORE_LIKE_this]
>
>* [Controlli Generatore di segmenti: Sezione Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Code Syntax Used in the Segment Expression Editor](../../features/segments/segment-code-syntax.md)

