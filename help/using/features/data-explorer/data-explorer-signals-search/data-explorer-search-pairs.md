---
description: Cercare uno o più segnali in base alle rispettive coppie chiave-valore.
seo-description: Cercare uno o più segnali in base alle rispettive coppie chiave-valore.
seo-title: Segnali di ricerca per coppie chiave-valore
title: Segnali di ricerca per coppie chiave-valore
uuid: 2 a 38 d 0 d 4-4 a 2 e -4 ca 5-b 9 ec-af 9 d 4963 d 876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Search Signals by Key-Value Pairs {#search-signals-by-key-value-pairs}

Cercare uno o più segnali in base alle rispettive coppie chiave-valore.
To search for more than one signal, click the ![Add](assets/icon_add.png) button. Inserite le coppie chiave-valore che desiderate cercare, quindi utilizzate i seguenti filtri per limitare i risultati.

* **Stato del segnale**: cercare segnali inclusi in caratteristiche, segnali inutilizzati o entrambi.
* **Visualizzare i record per**: selezionare l'intervallo di tempo in cui cercare i segnali ricevuti.
* **Conteggio minimo**: visualizzare solo i segnali con il conteggio totale minimo specificato nell'intervallo selezionato.

>[!IMPORTANT]
>
>Per un'esperienza utente ottimizzata, i risultati delle ricerche chiave-valore sono basati sul campionamento dei dati. See [Data Sampling and Error Rates](/help/using/reporting/report-sampling.md) for details on how [!DNL Audience Manager] uses data sampling and why slight result variations may appear when comparing key-value search to general searches.

When searching for signals using multiple key-value pairs, [!DNL Audience Manager] links the pairs using the logical **AND** operator. Ad esempio, supponiamo che tu stia eseguendo una ricerca con le seguenti coppie chiave-valore:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

This search will return only results that qualify for all three filters on the same call: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Case Insensitivity and Search Auto-Completion {#case-insensitivity}

I campi di ricerca chiave e valore non sono sensibili alle maiuscole/minuscole. Il campo di ricerca chiave include suggerimenti completati automaticamente.

![](assets/signal-search-suggestions.png)

Let's say [!DNL Audience Manager] received the following signals:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

When you enter `product` in the key search field, you receive auto-completed suggestions for `productCategory`, `newProduct`, `PRODUCT`, and `product`.

Similarly, when you search for `product == phone`, [!UICONTROL Data Explorer] returns results for both `PRODUCT == phone` and `product == PHONE`.
Le caratteristiche con caratteristiche ridotte sono insensibili. A trait containing the signal with the key-value pair `PRODUCT == SMARTPHONE` also qualifies the signal with the key-value pair `product == smartphone`.