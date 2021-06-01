---
description: Sintesi della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e elenco dei rapporti che restituiscono informazioni basate su dati campionati.
seo-description: Sintesi della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e elenco dei rapporti che restituiscono informazioni basate su dati campionati.
seo-title: Campionamento di dati e tassi di errore nei report selezionati di Audience Manager
solution: Audience Manager
title: Campionamento di dati e tassi di errore nei report selezionati di Audience Manager
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Riferimento per la generazione di rapporti
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 7%

---

# Campionamento di dati e tassi di errore nei report selezionati di Audience Manager{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Sintesi della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e elenco dei rapporti che restituiscono informazioni basate su dati campionati.

## Rapporto di campionamento dei dati {#data-sampling-ratio}

Alcuni report [!DNL Audience Manager] mostrano risultati basati su un set campionato della quantità totale di dati disponibili. Il rapporto dei dati campionati è di 1:54. Per i rapporti che utilizzano dati campionati, ciò significa che i risultati sono basati su 1 record su ogni set di 54 record.

Questi rapporti utilizzano dati statistici campionati perché hanno bisogno di un&#39;enorme quantità di potenza di calcolo per generare risultati. Il campionamento aiuta a trovare un equilibrio tra la riduzione delle richieste di calcolo, il mantenimento delle prestazioni del sistema e la fornitura di risultati precisi.

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

Nei rapporti che generano dati di sovrapposizione possono verificarsi errori. Un errore è definito come la percentuale di record che:

* Non avrebbe dovuto essere incluso in un rapporto ma sarebbe stato comunque aggiunto.
* Avrebbe dovuto essere incluso in un rapporto, ma è stato escluso.

È importante notare che i nostri test e modelli mostrano che il tasso di errore *diminuisce* in proporzione inversa rispetto al numero di record nel set di dati. I set di dati con molti record generano meno errori rispetto ai set con un numero ridotto di record. Guardiamo questa affermazione in modo più quantitativo. Come mostrato nella tabella seguente, per un determinato numero di record, il 95% dei risultati del rapporto sarà inferiore a un tasso di errore specifico.

| Numero di record | Frequenza errori |
|--- |--- |
| 500 - 1.000 | Il 95% è al di sotto di un tasso di errore del 42%. |
| 1.000 - 1.500 | Il 95% è al di sotto di un tasso di errore del 34%. |
| 10.000 - 50.000 | Il 95% è al di sotto di un tasso di errore del 14%. |
| 50.000 | Il 95% è al di sotto di un tasso di errore del 6%. |
| 100.000 | Il 95% è al di sotto di un tasso di errore del 4%. |
| 500.000 (o più) | Il 95% è al di sotto di un tasso di errore del 2%. |

## Utilizzo della metodologia di campionamento dei minhash {#minhash}

Sulla base della metodologia di campionamento [Minhash](https://en.wikipedia.org/wiki/MinHash) , Audience Manager utilizza un nuovo metodo per calcolare le caratteristiche e i calcolatori dei segmenti sopra uno sketch di dati di hash di una permutazione. Questo nuovo metodo produce una varianza inferiore rispetto al calcolatore standard per la somiglianza Jaccard. Vedi la sezione seguente per i rapporti che utilizzano questa metodologia.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Rapporti che utilizzano dati di esempio {#reports-using-sampled-data}

I rapporti [!DNL Audience Manager] che utilizzano dati statistici campionati e la metodologia di campionamento di hash includono:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Campionamento statistico | Metodologia di campionamento del minhash |
|--- |--- |
| [Tipi di ](../features/addressable-audiences.md) pubblico indirizzabili (dati a livello di cliente e segmento). | [Rapporti di sovrapposizione](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)  (da caratteristica a caratteristica, da segmento a caratteristica e da segmento a segmento) |
| La metrica [Dispositivi totali](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) per un elemento [!UICONTROL Profile Merge Rule]. | [Raccomandazioni sulle caratteristiche](/help/using/features/segments/trait-recommendations.md) |
| [Data ](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) Explorer utilizza i dati campionati nella  [!UICONTROL Search] scheda ed eventuali  [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
