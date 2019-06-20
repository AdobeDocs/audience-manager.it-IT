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


# Recency e frequenza {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency e frequenza puoi segmentare i visitatori in base alle azioni che si verificano o ripetere un intervallo giornaliero impostato.

Audience Manager viene definito [!DNL recency] e [!DNL frequency] come segue:

* **[!UICONTROL Recency]:** Numero di giorni in cui un utente ha visualizzato o qualificato per una o più caratteristiche.
* **[!UICONTROL Frequency]:** La frequenza di visualizzazione o di qualifica di un utente per una o più caratteristiche.

[!UICONTROL Recency][!UICONTROL Frequency] e le impostazioni aiutano a segmentare i visitatori in base al loro livello di interesse reale (percepito) in un sito, sezione o particolare creativo. Ad esempio, gli utenti idonei per un segmento con requisiti di recency/frequenza elevati possono essere più interessati a un sito o a un prodotto rispetto a quelli che visita meno spesso o meno.

## Posizione delle impostazioni di aggiornamento e frequenza {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency][!UICONTROL Frequency] le impostazioni si trovano nella [!UICONTROL Basic View] sezione del [!UICONTROL Traits] pannello. Fate clic sull&#39;icona dell&#39;orologio per esporre questi controlli.

![](assets/recency_frequency.png)

## Limitazioni e regole {#limitations-rules}

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
   <td colname="col2"> <p>È possibile configurare i requisiti di frequenza <i>senza</i> configurare i requisiti di aggiornamento. È sufficiente impostare un valore di frequenza e lasciare vuoto il campo di aggiornamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regole di unione profilo</b> </p> </td> 
   <td colname="col2"> <p>Consultate <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frequenza caratteristica, Grafici dispositivo esterni e Regole di unione profilo</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di sottotitoli frequenza {#frequency-capping}

Le espressioni di estremità della frequenza includono tutti gli utenti il cui numero di realizzazioni è sotto un valore desiderato. Di seguito sono riportati alcuni esempi:

* L&#39;espressione `frequency([1000T]) <= 5` include tutti gli utenti che hanno realizzato la caratteristica con l&#39;ID «1000» un massimo di cinque volte, compresi gli utenti che non hanno realizzato la caratteristica.
* Quando è necessario che i requisiti di aggiornamento/frequenza siano inferiori a un numero specifico di volte o giorni, unisciti a tale caratteristica con un `AND` operatore. Utilizzando l&#39;esempio precedente, questa espressione diventa valida se associata con un&#39;altra caratteristica, come illustrato: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Per i casi di utilizzo dei sottotitoli pubblicitari, puoi creare una regola di segmento simile a questa: `(frequency([1000T] <= 2D) >= 5)`. Questa espressione include tutti gli utenti che hanno realizzato la caratteristica con l&#39;ID «1000» negli ultimi 2 giorni di almeno cinque volte. Imposta il passaggio della frequenza inviando questo segmento al server di annunci con un `NOT` set sul segmento nell&#39;ad server. Questo approccio offre prestazioni maggiori nel [!DNL Audience Manager] corso, mantenendo allo stesso tempo lo stesso scopo per il passaggio della frequenza.

>[!MORE_ LIKE_ THIS]
>
>* [Controlli del Generatore di segmenti: Sezione Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintassi codice utilizzata nell&#39;Editor di espressioni segmento](../../features/segments/segment-code-syntax.md)

