---
description: Cerca uno o più segnali, in base alle rispettive coppie chiave-valore.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Ricerca di segnali per coppie chiave-valore
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# Ricerca di segnali per coppie chiave-valore {#search-signals-by-key-value-pairs}

Cerca uno o più segnali, in base alle rispettive coppie chiave-valore.
Per cercare più segnali, fare clic sul pulsante ![Aggiungi](assets/icon_add.png) pulsante. Inserisci le coppie chiave-valore da cercare, quindi utilizza i seguenti filtri per limitare i risultati.

* **Stato del segnale**: cerca i segnali inclusi nelle caratteristiche, nei segnali non utilizzati o in entrambi.
* **Visualizza record per**: seleziona l’intervallo di tempo in cui cercare i segnali ricevuti.
* **Conteggi minimi**: visualizza solo i segnali con il conteggio totale minimo specificato nell’intervallo selezionato.

>[!IMPORTANT]
>
>Per un’esperienza utente semplificata, i risultati della ricerca per coppia chiave-valore si basano sul campionamento dei dati. Consulta [Campionamento dei dati e tassi di errore](/help/using/reporting/report-sampling.md) per informazioni dettagliate su come [!DNL Audience Manager] utilizza il campionamento dei dati e il motivo per cui possono apparire lievi varianti di risultati quando si confronta la ricerca chiave-valore con le ricerche generali.

Quando si ricercano segnali utilizzando più coppie chiave-valore, [!DNL Audience Manager] collega le coppie utilizzando il **E** operatore. Ad esempio, supponiamo che tu stia eseguendo una ricerca con le seguenti coppie chiave-valore:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Questa ricerca restituirà solo i risultati idonei per tutti e tre i filtri sulla stessa chiamata: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Segnali esclusi dalla ricerca del segnale {#excluded-signals}

Variabili chiave utilizzate da Audience Manager e precedute da `d_` e `h_` i prefissi non vengono visualizzati da [!UICONTROL Signals Search]. Consulta [Requisiti di prefisso delle variabili chiave](../../traits/trait-variable-prefixes.md) per i dettagli.

## Distinzione tra maiuscole e minuscole e completamento automatico della ricerca {#case-insensitivity}

I campi di ricerca chiave e valore fanno distinzione tra maiuscole e minuscole. Il campo di ricerca chiave include suggerimenti completati automaticamente.

![](assets/signal-search-suggestions.png)

Diciamo che [!DNL Audience Manager] ha ricevuto i seguenti segnali:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Quando si immette `product` nel campo di ricerca chiave, ricevi suggerimenti completati automaticamente per `productCategory` e `product`.

Analogamente, quando si cerca `product == PHONE`, [!UICONTROL Data Explorer] restituisce risultati solo per `product == PHONE`.

Anche le realizzazioni delle caratteristiche in background fanno distinzione tra maiuscole e minuscole. Caratteristica contenente il segnale con la coppia chiave-valore `PRODUCT == SMARTPHONE` non qualifica il segnale con la coppia chiave-valore `product == smartphone`.
