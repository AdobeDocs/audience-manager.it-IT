---
description: Riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e un elenco di rapporti che restituiscono informazioni basate su dati campionati.
seo-description: Riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e un elenco di rapporti che restituiscono informazioni basate su dati campionati.
seo-title: Campionamento di dati e tassi di errore nei report selezionati di Audience Manager
solution: Audience Manager
title: Campionamento di dati e tassi di errore nei report selezionati di Audience Manager
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 33d844578c5cd620f9d4c33ec931ae0778aabb07
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 7%

---


# Campionamento di dati e tassi di errore nei report selezionati di Audience Manager{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e un elenco di rapporti che restituiscono informazioni basate su dati campionati.

## Rapporto di campionamento dei dati {#data-sampling-ratio}

Alcuni [!DNL Audience Manager] rapporti visualizzano i risultati in base a un set campionato della quantità totale di dati disponibili. Il rapporto dei dati campionati è di 1:54. Per i report che utilizzano dati campionati, i risultati sono basati su 1 record su ogni set di 54 record.

Questi report utilizzano dati statistici campionati perché necessitano di una quantità enorme di potenza di calcolo per generare risultati. Il campionamento aiuta a trovare un equilibrio tra la riduzione delle richieste di calcolo, il mantenimento delle prestazioni del sistema e la fornitura di risultati accurati.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Tassi di errore {#error-rates}

Gli errori possono verificarsi nei report che generano dati di sovrapposizione. Un errore è definito come la percentuale di record che:

* Non avrebbe dovuto essere incluso in un rapporto ma sarebbe stato comunque aggiunto.
* Avrebbe dovuto essere incluso in una relazione, ma sono stati esclusi.

È importante notare che i nostri test e modelli mostrano che il tasso di errore *diminuisce* in proporzione inversa rispetto al numero di record nel set di dati. I set di dati con molti record generano meno errori rispetto ai set con un numero limitato di record. Guardiamo a questa affermazione in modo più quantitativo. Come mostrato nella tabella seguente, per un numero impostato di record, il 95% dei risultati del rapporto sarà inferiore a un tasso di errore specifico.

| Numero di record | Frequenza errori |
|--- |--- |
| 500 - 1,000 | Il 95% è inferiore a un tasso di errore del 42%. |
| 1,000 - 1,500 | Il 95% è inferiore a un tasso di errore del 34%. |
| 10,000 - 50,000 | Il 95% è inferiore a un tasso di errore del 14%. |
| 50,000 | Il 95% è inferiore a un tasso di errore del 6%. |
| 100,000 | Il 95% è inferiore a un tasso di errore del 4%. |
| 500.000 (o più) | Il 95% è inferiore a un tasso di errore del 2%. |

## Utilizzo della metodologia Minhash Sampling {#minhash}

Sulla base della metodologia di campionamento [Minhash](https://en.wikipedia.org/wiki/MinHash) ,  Audience Manager utilizza un nuovo metodo per calcolare le caratteristiche e gli stimatori del segmento sopra uno sketch di dati One Permutation Hashing. Questo nuovo metodo produce una varianza inferiore rispetto allo stimatore standard per lo stimatore della similarità Jaccard. Consulta la sezione seguente per i report che utilizzano questa metodologia.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Report che utilizzano dati di esempio {#reports-using-sampled-data}

I [!DNL Audience Manager] rapporti che utilizzano i dati statistici campionati e la metodologia di campionamento Minhash includono:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Campionamento statistico | Metodologia di campionamento del minhash |
|--- |--- |
| [Dati Pubblico](../features/addressable-audiences.md) indirizzabili (dati a livello di cliente e segmento). | [Report](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) di sovrapposizione (caratteristiche, caratteristiche e caratteristiche e segmento a segmento) |
| La metrica Dispositivi [](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) totali per un [!UICONTROL Profile Merge Rule]. | [Raccomandazioni sulle caratteristiche](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) utilizza i dati campionati nella [!UICONTROL Search] scheda ed eventuali [!UICONTROL Saved Searches] | [Recommendations Audience Marketplace](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
