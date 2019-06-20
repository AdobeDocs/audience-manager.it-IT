---
description: Cercare uno o più segnali in base alle rispettive coppie chiave-valore.
seo-description: Cercare uno o più segnali in base alle rispettive coppie chiave-valore.
seo-title: Segnali di ricerca per coppie chiave-valore
title: Segnali di ricerca per coppie chiave-valore
uuid: 2 a 38 d 0 d 4-4 a 2 e -4 ca 5-b 9 ec-af 9 d 4963 d 876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Segnali di ricerca per coppie chiave-valore {#search-signals-by-key-value-pairs}

Cercare uno o più segnali in base alle rispettive coppie chiave-valore.
Per cercare più di un segnale, fate clic sul pulsante ![Aggiungi](assets/icon_add.png) . Inserite le coppie chiave-valore che desiderate cercare, quindi utilizzate i seguenti filtri per limitare i risultati.

* **Stato del segnale**: cercare segnali inclusi in caratteristiche, segnali inutilizzati o entrambi.
* **Visualizzare i record per**: selezionare l&#39;intervallo di tempo in cui cercare i segnali ricevuti.
* **Conteggio minimo**: visualizzare solo i segnali con il conteggio totale minimo specificato nell&#39;intervallo selezionato.

>[!IMPORTANT]
>
>Per un&#39;esperienza utente ottimizzata, i risultati delle ricerche chiave-valore sono basati sul campionamento dei dati. Consultate [Campionamento dei dati e percentuali](/help/using/reporting/report-sampling.md) di errore per informazioni su come [!DNL Audience Manager] utilizzare il campionamento dei dati e perché le variazioni lievi dei risultati possono essere visualizzate confrontando la ricerca chiave-valore con ricerche generiche.

Durante la ricerca di segnali utilizzando più coppie chiave-valore, [!DNL Audience Manager] collega le coppie utilizzando l&#39;operatore **logico AND** . Ad esempio, supponiamo che tu stia eseguendo una ricerca con le seguenti coppie chiave-valore:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Questa ricerca restituirà solo i risultati idonei per tutti e tre i filtri nella stessa chiamata: `c_creative == "12345"``AND``c_product == "smartphone"``AND``c_location == "europe"`.

![](assets/signals-search.png)

## Insensibilità tra maiuscole e minuscole e Ricerca automatica {#case-insensitivity}

I campi di ricerca chiave e valore non sono sensibili alle maiuscole/minuscole. Il campo di ricerca chiave include suggerimenti completati automaticamente.

![](assets/signal-search-suggestions.png)

Diciamo [!DNL Audience Manager] ricevuti i segnali seguenti:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Quando immetti `product` il campo di ricerca chiave, riceverai suggerimenti automatici per `productCategory``newProduct`, `PRODUCT`e `product`.

Similarly, when you search for `product == phone`, [!UICONTROL Data Explorer] returns results for both `PRODUCT == phone` and `product == PHONE`.
Le caratteristiche con caratteristiche ridotte sono insensibili. Anche una caratteristica contenente il segnale con la coppia `PRODUCT == SMARTPHONE` chiave-valore qualifica il segnale con la coppia `product == smartphone`chiave-valore.