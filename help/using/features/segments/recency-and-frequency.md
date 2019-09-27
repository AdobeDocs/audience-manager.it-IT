---
description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Recency and Frequency
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c7e8b67ccad4479487b471668462937c5be6be34

---


# Recency e frequenza {#recency-and-frequency}

In [!UICONTROL Segment Builder]recency e frequenza potete segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]** : Recente visualizzazione o qualifica di un utente per una o più caratteristiche.
* **[!UICONTROL Frequency]** : The rate at which a user viewed or qualified for one (or more) traits.

[!UICONTROL Recency] e [!UICONTROL Frequency] le impostazioni consentono di segmentare i visitatori in base al loro livello di interesse reale (o percepito) in un sito, una sezione o un particolare contenuto creativo. Ad esempio, gli utenti idonei per un segmento con requisiti di recency/frequenza elevati possono essere più interessati a un sito o a un prodotto rispetto agli utenti che visitano meno spesso o meno frequentemente.

## Posizione delle impostazioni di aggiornamento e frequenza {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] e [!UICONTROL Frequency] le impostazioni si trovano nella [!UICONTROL Basic View] sezione del [!UICONTROL Traits] pannello. Fate clic sull'icona dell'orologio per visualizzare questi controlli.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

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
   <td colname="col2"> <p>Il valore Recency deve essere maggiore di 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche di terze parti</b> </p> </td> 
   <td colname="col2"> <p>Non è possibile impostare regole di aggiornamento per singoli tratti o gruppi di caratteristiche di terze parti contenenti caratteristiche di terze parti. Recency e frequenza si applicano solo alle proprie caratteristiche. </p> </td> 
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
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>Non è possibile impostare regole di frequenza sulle caratteristiche individuali di terze parti o sui gruppi di caratteristiche che contengono caratteristiche di terze parti. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisiti di aggiornamento</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements without configuring recency requirements. <i></i> È sufficiente impostare un valore di frequenza e lasciare vuoto il campo Recency. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profile Merge Rules</b> </p> </td> 
   <td colname="col2"> <p>Consulta <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frequenza caratteristiche, Grafici per dispositivi esterni e Regole</a>di unione profili. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi recenti {#recency-examples}

Di seguito sono riportati due esempi del funzionamento dell’aggiornamento, a seconda della selezione effettuata nell’interfaccia utente:

### Using a less than or equal to operator (&lt;=)

![Less-than-equal-to](assets/less-than-equal-to.png)

In questo esempio, viene selezionato l'operatore &lt;=, come mostrato nella schermata. Questo qualifica l’utente per il segmento se soddisfa i requisiti per una delle tre caratteristiche almeno tre volte negli ultimi cinque giorni. La timeline seguente mostra la qualifica del segmento al momento della creazione del segmento, il 1° ottobre e dieci giorni dopo.

![Ultimi cinque giorni](assets/last-5-days.png)

### Utilizzo di un operatore maggiore o uguale a (=&gt;)

![Greater-than-equal-to](assets/greater-than-equal-to.png)

In questo esempio, si seleziona l'operatore =&gt;, come mostrato nella schermata. This qualifies your user for the segment if they qualify for any of the three traits a minimum of three times anytime between their first qualification on the Audience Manager platform and the cut-off time five days ago. The timeline below shows the segment qualification at the time the segment is created, on October 1st, and ten days later.

![Earlier-qualification](assets/earlier-qualification.png)


## Frequency Capping Examples {#frequency-capping}

Frequency-capping expressions include all the users whose number of trait realizations is below a desired value. Here are a few examples:

* L'espressione `frequency([1000T]) <= 5` include tutti gli utenti che hanno realizzato la caratteristica con l'ID "1000" al massimo cinque volte, inclusi gli utenti che non hanno realizzato la caratteristica.
* Se è necessario che i requisiti di aggiornamento/frequenza siano inferiori a un numero specifico di volte o di giorni, unire tale caratteristica a un altro con un `AND` operatore. Utilizzando l'esempio riportato sopra, questa espressione diventa valida quando vi si unisce un altro tratto come illustrato di seguito: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Per i casi d’uso di limite di frequenza per la pubblicità, potete creare una regola di segmento simile alla seguente: `(frequency([1000T] <= 2D) >= 5)`. Questa espressione include tutti gli utenti che hanno realizzato la caratteristica con l'ID "1000" negli ultimi 2 giorni almeno cinque volte. Set frequency capping by sending this segment to the ad server with a  set on the segment in the ad server. `NOT` Questo approccio consente di ottenere prestazioni migliori [!DNL Audience Manager] pur continuando a servire lo stesso scopo per i limiti di frequenza.

>[!MORE_LIKE_this]
>
>* [Controlli Generatore di segmenti: Sezione Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintassi del codice utilizzata nell'Editor di espressioni di segmento](../../features/segments/segment-code-syntax.md)

