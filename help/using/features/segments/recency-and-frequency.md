---
description: In Segment Builder (Generatore segmenti), recency e frequenza ti consente di segmentare i visitatori in base alle azioni che avvengono o ripetere un intervallo giornaliero impostato.
seo-description: In Segment Builder (Generatore segmenti), recency e frequenza ti consente di segmentare i visitatori in base alle azioni che avvengono o ripetere un intervallo giornaliero impostato.
seo-title: Recency e frequenza
solution: Audience Manager
title: Recency e frequenza
uuid: faadd 18 a-bf 27-4 b 73-995 e -9809 f 52 f 5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]:** Numero di giorni in cui un utente ha visualizzato o qualificato per una o più caratteristiche.
* **[!UICONTROL Frequency]:** La frequenza di visualizzazione o di qualifica di un utente per una o più caratteristiche.

[!UICONTROL Recency][!UICONTROL Frequency] e le impostazioni aiutano a segmentare i visitatori in base al loro livello di interesse reale (percepito) in un sito, sezione o particolare creativo. Ad esempio, gli utenti idonei per un segmento con requisiti di recency/frequenza elevati possono essere più interessati a un sito o a un prodotto rispetto a quelli che visita meno spesso o meno.

## Location of Recency and Frequency Settings {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. Fate clic sull'icona dell'orologio per esporre questi controlli.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

Leggi e comprendi questi limiti e regole quando vuoi applicare recency e frequenza alle caratteristiche nei tuoi segmenti.

### Recency

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limite o Regola </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Valore minimo</b> </p> </td> 
   <td colname="col2"> <p>Il recency deve essere maggiore di 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche di terze parti</b> </p> </td> 
   <td colname="col2"> <p>Non potete impostare regole di aggiornamento su singole caratteristiche di terze parti o gruppi di caratteristiche contenenti caratteristiche di terze parti. L'aggiornamento e la frequenza sono applicabili solo alle caratteristiche personali. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Frequenza

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limite o Regola </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche di terze parti</b> </p> </td> 
   <td colname="col2"> <p>Non potete impostare regole di frequenza su singole caratteristiche di terze parti o gruppi di caratteristiche contenenti caratteristiche di terze parti. L'aggiornamento e la frequenza sono applicabili solo alle caratteristiche personali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisiti di aggiornamento</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. È sufficiente impostare un valore di frequenza e lasciare vuoto il campo di aggiornamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regole di unione profilo</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#frequency-capping}

Le espressioni di estremità della frequenza includono tutti gli utenti il cui numero di realizzazioni è sotto un valore desiderato. Di seguito sono riportati alcuni esempi:

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. Questa espressione include tutti gli utenti che hanno realizzato la caratteristica con l'ID «1000» negli ultimi 2 giorni di almeno cinque volte. Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_ LIKE_ THIS]
>
>* [Controlli del Generatore di segmenti: Sezione Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintassi codice utilizzata nell'Editor di espressioni segmento](../../features/segments/segment-code-syntax.md)

