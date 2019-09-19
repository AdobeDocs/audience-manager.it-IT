---
description: In Segment Builder (Generatore di segmenti), la frequenza e la frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.
seo-description: In Segment Builder (Generatore di segmenti), la frequenza e la frequenza consentono di segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.
seo-title: Recency e frequenza
solution: Audience Manager
title: Recency e frequenza
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency e frequenza {#recency-and-frequency}

In [!UICONTROL Segment Builder]recency e frequenza potete segmentare i visitatori in base alle azioni che si verificano o si ripetono in un determinato intervallo giornaliero.

Audience Manager definisce [!DNL recency] e [!DNL frequency] come segue:

* **[!UICONTROL Recency]** : Il numero di giorni durante i quali un utente ha visualizzato o qualificato una o più caratteristiche.
* **[!UICONTROL Frequency]** : Frequenza con cui un utente ha visualizzato o qualificato una o più caratteristiche.

[!UICONTROL Recency] e [!UICONTROL Frequency] le impostazioni consentono di segmentare i visitatori in base al loro livello di interesse reale (o percepito) in un sito, una sezione o un particolare contenuto creativo. Ad esempio, gli utenti idonei per un segmento con requisiti di recency/frequenza elevati possono essere più interessati a un sito o a un prodotto rispetto agli utenti che visitano meno spesso o meno frequentemente.

## Posizione delle impostazioni di aggiornamento e frequenza {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] e [!UICONTROL Frequency] le impostazioni si trovano nella [!UICONTROL Basic View] sezione del [!UICONTROL Traits] pannello. Fate clic sull'icona dell'orologio per visualizzare questi controlli.

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
   <td colname="col1"> <p> <b>Caratteristiche di terze parti</b> </p> </td> 
   <td colname="col2"> <p>Non è possibile impostare regole di frequenza sulle caratteristiche individuali di terze parti o sui gruppi di caratteristiche che contengono caratteristiche di terze parti. Recency e frequenza si applicano solo alle proprie caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisiti di aggiornamento</b> </p> </td> 
   <td colname="col2"> <p>Puoi configurare i requisiti di frequenza <i>senza</i> configurare i requisiti di aggiornamento. È sufficiente impostare un valore di frequenza e lasciare vuoto il campo Recency. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regole di unione profilo</b> </p> </td> 
   <td colname="col2"> <p>Consulta <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frequenza caratteristiche, Grafici per dispositivi esterni e Regole</a>di unione profili. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di maschiatura delle frequenze {#frequency-capping}

Le espressioni di capping delle frequenze includono tutti gli utenti il cui numero di realizzazioni delle caratteristiche è inferiore al valore desiderato. Di seguito sono riportati alcuni esempi:

* L'espressione `frequency([1000T]) <= 5` include tutti gli utenti che hanno realizzato la caratteristica con l'ID "1000" al massimo cinque volte, inclusi gli utenti che non hanno realizzato la caratteristica.
* Se è necessario che i requisiti di aggiornamento/frequenza siano inferiori a un numero specifico di volte o di giorni, unire tale caratteristica a un altro con un `AND` operatore. Utilizzando l'esempio riportato sopra, questa espressione diventa valida quando vi si unisce un altro tratto come illustrato di seguito: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Per i casi d’uso di limite di frequenza per la pubblicità, potete creare una regola di segmento simile alla seguente: `(frequency([1000T] <= 2D) >= 5)`. Questa espressione include tutti gli utenti che hanno realizzato la caratteristica con l'ID "1000" negli ultimi 2 giorni almeno cinque volte. Impostare il limite di frequenza inviando questo segmento al server di annunci con un `NOT` set sul segmento nel server di annunci. Questo approccio consente di ottenere prestazioni migliori [!DNL Audience Manager] pur continuando a servire lo stesso scopo per i limiti di frequenza.

>[!MORE_LIKE_this]
>
>* [Controlli Generatore di segmenti: Sezione Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintassi del codice utilizzata nell'Editor di espressioni di segmento](../../features/segments/segment-code-syntax.md)

