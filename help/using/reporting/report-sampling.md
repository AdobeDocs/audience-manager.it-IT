---
description: Riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e un elenco di rapporti che restituiscono informazioni basate su dati campionati.
seo-description: Riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e un elenco di rapporti che restituiscono informazioni basate su dati campionati.
seo-title: Campionamento dei dati e tassi di errore nei report Audience Manager selezionati
solution: Audience Manager
title: Campionamento dei dati e tassi di errore nei report Audience Manager selezionati
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
translation-type: tm+mt
source-git-commit: 6dca5c8bc338a670050123a94808795705450c3a

---


# Campionamento dei dati e tassi di errore nei report Audience Manager selezionati{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Riepilogo della metodologia di campionamento utilizzata per alcuni rapporti, tassi di errore di campionamento e un elenco di rapporti che restituiscono informazioni basate su dati campionati.

## Rapporto di campionamento dei dati e requisiti minimi {#data-sampling-ratio}

Alcuni [!DNL Audience Manager] rapporti visualizzano i risultati in base a un set campionato della quantità totale di dati disponibili. Il rapporto dei dati campionati è di 1:54. Per i report che utilizzano dati campionati, i risultati sono basati su 1 record su ogni set di 54 record.

Questi report utilizzano dati campionati perché necessitano di una notevole quantità di potenza di elaborazione per generare risultati. Il campionamento aiuta a trovare un equilibrio tra la riduzione delle richieste di calcolo, il mantenimento delle prestazioni del sistema e la fornitura di risultati accurati.

I report che utilizzano il campionamento escludono caratteristiche e segmenti quando non soddisfano i requisiti minimi di visitatore univoco. Tali requisiti minimi sono i seguenti:

* Caratteristiche: 28.000 realizzazioni [di caratteristiche](/help/using/features/traits/trait-and-segment-qualification-reference.md#unique-trait-realizations) univoche per un periodo di 14 giorni.
* Segmenti: 70.000 utenti in tempo reale per un periodo di 14 giorni.

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

## Report che utilizzano dati di esempio {#reports-using-sampled-data}

I [!DNL Audience Manager] rapporti che utilizzano i dati campionati includono:

* [Report](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) di sovrapposizione (caratteristiche, caratteristiche, caratteristiche e segmento per segmento).
* [Dati Pubblico](../features/addressable-audiences.md) indirizzabili (dati a livello di cliente e segmento).
* La metrica Dispositivi [](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) totali per un [!UICONTROL Profile Merge Rule].
* [Esplora](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) dati utilizza i dati campionati nella [!UICONTROL Search] scheda ed eventuali [!UICONTROL Saved Searches].