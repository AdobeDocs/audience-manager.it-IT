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
ht-degree: 0%

---

# Ricerca di segnali per coppie chiave-valore {#search-signals-by-key-value-pairs}

Cerca uno o più segnali, in base alle rispettive coppie chiave-valore.
Per cercare più segnali, fare clic sul pulsante ![Aggiungi](assets/icon_add.png). Inserisci le coppie chiave-valore da cercare, quindi utilizza i seguenti filtri per limitare i risultati.

* **Stato segnale**: ricerca di segnali inclusi nelle caratteristiche, segnali non utilizzati o entrambi.
* **Visualizza record per**: selezionare l&#39;intervallo di tempo in cui cercare i segnali ricevuti.
* **Conteggi minimi**: visualizza solo i segnali con il conteggio totale minimo specificato nell&#39;intervallo selezionato.

>[!IMPORTANT]
>
>Per un’esperienza utente semplificata, i risultati della ricerca per coppia chiave-valore si basano sul campionamento dei dati. Consulta [Campionamento dati e tassi di errore](/help/using/reporting/report-sampling.md) per informazioni dettagliate su come [!DNL Audience Manager] utilizza il campionamento dei dati e sul motivo per cui possono apparire lievi varianti di risultati quando si confronta la ricerca chiave-valore con le ricerche generali.

Durante la ricerca di segnali utilizzando più coppie chiave-valore, [!DNL Audience Manager] collega le coppie utilizzando l&#39;operatore logico **AND**. Ad esempio, supponiamo che tu stia eseguendo una ricerca con le seguenti coppie chiave-valore:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Questa ricerca restituirà solo i risultati qualificati per tutti e tre i filtri nella stessa chiamata: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Segnali esclusi dalla ricerca del segnale {#excluded-signals}

Le variabili chiave utilizzate da Audience Manager e precedute dai prefissi `d_` e `h_` non vengono visualizzate da [!UICONTROL Signals Search]. Per informazioni dettagliate, vedi [Requisiti di prefisso per le variabili chiave](../../traits/trait-variable-prefixes.md).

## Distinzione tra maiuscole e minuscole e completamento automatico della ricerca {#case-insensitivity}

I campi di ricerca chiave e valore fanno distinzione tra maiuscole e minuscole. Il campo di ricerca chiave include suggerimenti completati automaticamente.

![](assets/signal-search-suggestions.png)

Supponiamo che [!DNL Audience Manager] abbia ricevuto i seguenti segnali:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Quando immetti `product` nel campo di ricerca chiave, ricevi suggerimenti completati automaticamente per `productCategory` e `product`.

Analogamente, quando si cerca `product == PHONE`, [!UICONTROL Data Explorer] restituisce risultati solo per `product == PHONE`.

Anche le realizzazioni delle caratteristiche in background fanno distinzione tra maiuscole e minuscole. Una caratteristica contenente il segnale con la coppia chiave-valore `PRODUCT == SMARTPHONE` non qualifica il segnale con la coppia chiave-valore `product == smartphone`.
