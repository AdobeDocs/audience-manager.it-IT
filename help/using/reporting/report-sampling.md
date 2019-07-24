---
description: Un riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, percentuali di errore campione e un elenco di rapporti che restituiscono informazioni sulla base dei dati campionati.
seo-description: Un riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, percentuali di errore campione e un elenco di rapporti che restituiscono informazioni sulla base dei dati campionati.
seo-title: Campionamento dei dati ed errori in Report Audience Manager selezionati
solution: Audience Manager
title: Campionamento dei dati ed errori in Report Audience Manager selezionati
uuid: 3 d 8 bd 764-a 9 da -40 f 1-8794-54304457 bb 9 a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Un riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, percentuali di errore campione e un elenco di rapporti che restituiscono informazioni sulla base dei dati campionati.

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. Il rapporto dati campionato è 1:54. Per rapporti che utilizzano dati campionati, ciò significa che i risultati sono basati su 1 record per ogni set di 54 record.

Questi report utilizzano dati campionati perché richiedono un'enorme quantità di potenza di calcolo per generare risultati. Il campionamento consente di individuare un compromesso tra le ridotte esigenze computazionali, mantenere le prestazioni del sistema e fornire risultati precisi.

I report che utilizzano il campionamento escludono caratteristiche e segmenti quando non soddisfano i requisiti minimi di visitatori minimi. I seguenti requisiti minimi sono:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) over a 14-day period.
* Segmenti: 70,000 utenti in tempo reale per un periodo di 14 giorni.

## Error Rates {#error-rates}

Si possono verificare errori nei rapporti che generano dati di sovrapposizione. Un errore è definito come percentuale di record:

* Non deve essere stato incluso in un rapporto ma aggiunto comunque.
* Should have been included in a report but were left out.

It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. I set di dati con molti record generano meno errori rispetto a quelli con un numero limitato di record. Diamo un'occhiata a questa asserzione in modo più quantitativo. Come mostrato nella tabella seguente, per un numero impostato di record, il 95% dei risultati del report sarà inferiore a una frequenza di errore specifica.

| Numero di record | Tasso di errore |
|--- |--- |
| 500 - 1,000 | 95% ha una frequenza di errore 42%. |
| 1,000 - 1,500 | 95% ha una frequenza di errore 34%. |
| 10,000 - 50,000 | 95% ha una frequenza di errore 14%. |
| 50,000 | 95% ha una frequenza di errore 6%. |
| 100,000 | 95% ha una frequenza di errore 4%. |
| 500,000 (o più) | 95% ha una frequenza di errore 2%. |

## Reports That Use Sampled Data {#reports-using-sampled-data}

[!DNL Audience Manager] I rapporti che utilizzano i dati campionati includono:

* [Rapporti di sovrapposizione](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (caratteristica a caratteristica, segmento a caratteristica e segmento a segmento).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data).
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
