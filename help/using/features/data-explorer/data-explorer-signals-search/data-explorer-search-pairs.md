---
description: Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
seo-description: Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
seo-title: Ricerca segnali per coppie chiave-valore
title: Ricerca segnali per coppie chiave-valore
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Ricerca segnali per coppie chiave-valore {#search-signals-by-key-value-pairs}

Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
Per cercare più di un segnale, fare clic sul pulsante ![Aggiungi](assets/icon_add.png) . Inserite le coppie chiave-valore da cercare, quindi utilizzate i seguenti filtri per restringere i risultati.

* **Stato** del segnale: cercare i segnali inclusi nelle caratteristiche, nei segnali non utilizzati o in entrambi.
* **Visualizza record per**: selezionare l'intervallo di tempo in cui cercare i segnali ricevuti.
* **Conteggio** minimo: visualizza solo i segnali con il conteggio totale minimo specificato nell'intervallo selezionato.

>[!IMPORTANT]
>
>Per un'esperienza utente semplificata, i risultati della ricerca con coppie chiave-valore si basano sul campionamento dei dati. Per informazioni dettagliate sull’ [utilizzo del campionamento dei dati, consultate Campionamento dei](/help/using/reporting/report-sampling.md) dati e Frequenza [!DNL Audience Manager] di errore e il motivo per cui possono comparire lievi variazioni di risultati quando si confronta la ricerca chiave-valore con le ricerche generali.

Durante la ricerca di segnali utilizzando più coppie chiave-valore, [!DNL Audience Manager] collega le coppie utilizzando l'operatore logico **AND** . Ad esempio, supponiamo che si stia eseguendo una ricerca con le seguenti coppie chiave-valore:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Questa ricerca restituisce solo i risultati idonei per tutti e tre i filtri nella stessa chiamata: `c_creative == "12345"``AND` `c_product == "smartphone"``AND``c_location == "europe"`.

![](assets/signals-search.png)

## Insensibilità alle maiuscole e ricerca Completamento automatico {#case-insensitivity}

I campi di ricerca chiave e valore non fanno distinzione tra maiuscole e minuscole. Il campo di ricerca delle chiavi include suggerimenti con completamento automatico.

![](assets/signal-search-suggestions.png)

Supponiamo di aver [!DNL Audience Manager] ricevuto i seguenti segnali:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Quando immettete `product` nel campo di ricerca delle chiavi, riceverete suggerimenti `productCategory`, `newProduct`, `PRODUCT`e `product`suggerimenti completati automaticamente.

Allo stesso modo, quando eseguite una ricerca `product == phone`, [!UICONTROL Data Explorer] restituisce i risultati sia per `PRODUCT == phone` che per `product == PHONE`.
Le realizzazioni con tratti con backfill non fanno distinzione tra maiuscole e minuscole. Una caratteristica contenente il segnale con la coppia chiave-valore `PRODUCT == SMARTPHONE` qualifica anche il segnale con la coppia chiave-valore `product == smartphone`.