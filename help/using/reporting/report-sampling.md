---
description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: Data Sampling and Error Rates in Selected Audience Manager Reports
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
TQID: https://experienceleague.adobe.com/VGqto9hCroCmKygXvwZNOiAYnsV9CmdPzAoEvKnkV90
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
subfeature_v2:
  - id: a2c6d65b-635d-4454-a9cc-9771ed501bb4
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: f2fdbb191013b0bcb9bdab0529e3b7f3c872fd54
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 1%

---

# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.

## Data Sampling Ratio {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. The sampled data ratio is 1:54. For reports that use sampled data, this means your results are based on 1 record out of every set of 54 records.

These reports use statistical sampled data because they need a tremendous amount of computing power to generate results. Sampling helps strike a balance between reduced computational demands, maintaining system performance, and providing accurate results.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Error Rates {#error-rates}

Errors can occur in reports that generate overlap data. An error is defined as the percentage of records that:

* Should not have been included in a report but were added anyway.
* Should have been included in a report but were left out.

It&#39;s important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. Data sets that have a lot of records generate fewer errors than sets with a small number of records. Let&#39;s look at this assertion in a more quantitative manner. As shown in the following table, for a set number of records, 95% of your report results will be below a specific error rate.

| Number of Records | Error Rate |
|--- |--- |
| 500 - 1,000 | 95% are under a 42% error rate. |
| 1,000 - 1,500 | 95% are under a 34% error rate. |
| 10,000 - 50,000 | 95% are under a 14% error rate. |
| 50.000 | Il 95% è al di sotto di un tasso di errore del 6%. |
| 100.000 | Il 95% è al di sotto di un tasso di errore del 4%. |
| 500.000 (o più) | Il 95% è al di sotto di un tasso di errore del 2%. |

## Utilizzo della metodologia di campionamento Minhash {#minhash}

In base alla metodologia di campionamento [Minhash](https://en.wikipedia.org/wiki/MinHash), Audience Manager utilizza un nuovo metodo per calcolare i stimatori di caratteristiche e segmenti sopra uno schizzo di dati con hash a una permutazione. Questo nuovo metodo produce una varianza inferiore rispetto allo stimatore standard per la somiglianza Jaccard. Consulta la sezione seguente per i rapporti che utilizzano questa metodologia.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Rapporti Che Utilizzano Dati Campionati {#reports-using-sampled-data}

I report [!DNL Audience Manager] che utilizzano i dati statistici campionati e la metodologia di campionamento Minhash includono:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Campionamento statistico | Metodologia di campionamento Minhash |
|--- |--- |
| [Dati del pubblico indirizzabile](../features/addressable-audiences.md) (dati a livello di cliente e segmento). | [Rapporti di sovrapposizione](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (da caratteristica a caratteristica, da segmento a caratteristica e da segmento a segmento) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) utilizza i dati campionati nella scheda [!UICONTROL Search] e in qualsiasi [!UICONTROL Saved Searches] | [Consigli di Audience Marketplace](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
