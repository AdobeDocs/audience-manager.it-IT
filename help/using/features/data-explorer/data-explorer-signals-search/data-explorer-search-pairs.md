---
description: Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
seo-description: Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
seo-title: Ricerca di segnali per coppie chiave-valore
title: Ricerca di segnali per coppie chiave-valore
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 4%

---


# Ricerca di segnali per coppie chiave-valore {#search-signals-by-key-value-pairs}

Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
Per cercare più di un segnale, fare clic sul pulsante ![Aggiungi](assets/icon_add.png). Inserite le coppie chiave-valore da cercare, quindi utilizzate i seguenti filtri per restringere i risultati.

* **Stato** del segnale: cercare i segnali inclusi nelle caratteristiche, nei segnali non utilizzati o in entrambi.
* **Visualizza record per**: selezionare l&#39;intervallo di tempo in cui cercare i segnali ricevuti.
* **Conteggio** minimo: visualizza solo i segnali con il conteggio totale minimo specificato nell&#39;intervallo selezionato.

>[!IMPORTANT]
>
>Per un&#39;esperienza utente semplificata, i risultati della ricerca con coppie chiave-valore si basano sul campionamento dei dati. Per informazioni dettagliate sull&#39;utilizzo del campionamento dei dati da parte di [Campionamento dei dati e tassi di errore](/help/using/reporting/report-sampling.md), vedere [!DNL Audience Manager] e sulle ragioni per cui possono comparire lievi variazioni di risultati quando si confronta la ricerca chiave-valore con le ricerche generali.

Durante la ricerca di segnali che utilizzano più coppie chiave-valore, [!DNL Audience Manager] collega le coppie utilizzando l&#39;operatore logico **AND**. Ad esempio, supponiamo che si stia eseguendo una ricerca con le seguenti coppie chiave-valore:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Questa ricerca restituisce solo i risultati idonei per tutti e tre i filtri nella stessa chiamata: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Segnali esclusi dalla ricerca del segnale {#excluded-signals}

Le variabili chiave utilizzate dal Audience Manager  e con il prefisso `d_` e `h_` non vengono visualizzate da [!UICONTROL Signals Search]. Per ulteriori informazioni, vedere [Requisiti del prefisso per le variabili chiave](../../traits/trait-variable-prefixes.md).

## Insensibilità alle maiuscole e ricerca Completamento automatico {#case-insensitivity}

I campi di ricerca chiave e valore non fanno distinzione tra maiuscole e minuscole. Il campo di ricerca delle chiavi include suggerimenti con completamento automatico.

![](assets/signal-search-suggestions.png)

Supponiamo che [!DNL Audience Manager] abbia ricevuto i seguenti segnali:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Quando si immette `product` nel campo di ricerca chiave, si ricevono suggerimenti automaticamente completati per `productCategory`, `newProduct`, `PRODUCT` e `product`.

Allo stesso modo, quando si cerca `product == phone`, [!UICONTROL Data Explorer] restituisce i risultati sia per `PRODUCT == phone` che per `product == PHONE`.
Le realizzazioni con tratti con backfill non fanno distinzione tra maiuscole e minuscole. Una caratteristica contenente il segnale con la coppia chiave-valore `PRODUCT == SMARTPHONE` qualifica anche il segnale con la coppia chiave-valore `product == smartphone`.