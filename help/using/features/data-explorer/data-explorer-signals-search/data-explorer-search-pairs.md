---
description: Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
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

Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
Per cercare più di un segnale, fai clic sul pulsante ![Aggiungi](assets/icon_add.png) pulsante . Immetti le coppie chiave-valore da cercare, quindi utilizza i seguenti filtri per limitare i risultati.

* **Stato del segnale**: cerca i segnali inclusi nelle caratteristiche, nei segnali inutilizzati o in entrambi.
* **Visualizza record per**: selezionare l&#39;intervallo di tempo in cui cercare i segnali ricevuti.
* **Conteggi minimi**: visualizza solo i segnali con il numero totale minimo specificato nell&#39;intervallo selezionato.

>[!IMPORTANT]
>
>Per semplificare l’esperienza utente, i risultati della ricerca con coppie chiave-valore si basano sul campionamento dei dati. Vedi [Campionamento di dati e tassi di errore](/help/using/reporting/report-sampling.md) per informazioni dettagliate su come [!DNL Audience Manager] utilizza il campionamento dei dati e il motivo per cui possono comparire lievi variazioni di risultati quando si confronta la ricerca chiave-valore con le ricerche generali.

Quando si cercano segnali utilizzando più coppie chiave-valore, [!DNL Audience Manager] collega le coppie utilizzando la logica **E** operatore. Ad esempio, supponiamo che tu stia eseguendo una ricerca con le seguenti coppie chiave-valore:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Questa ricerca restituirà solo i risultati idonei per tutti e tre i filtri nella stessa chiamata: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Segnali esclusi dalla ricerca del segnale {#excluded-signals}

Variabili chiave utilizzate dall&#39;Audience Manager e precedute dal `d_` e `h_` i prefissi non vengono visualizzati da [!UICONTROL Signals Search]. Vedi [Requisiti di prefisso delle variabili chiave](../../traits/trait-variable-prefixes.md) per i dettagli.

## Sensibilità delle maiuscole e delle minuscole e completamento automatico della ricerca {#case-insensitivity}

I campi di ricerca chiave e valore sono sensibili all’uso di maiuscole e minuscole. Il campo di ricerca chiave include suggerimenti completati automaticamente.

![](assets/signal-search-suggestions.png)

Diciamo [!DNL Audience Manager] ha ricevuto i seguenti segnali:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Quando immetti `product` nel campo di ricerca chiave ricevi suggerimenti completati automaticamente per `productCategory` e `product`.

Allo stesso modo, quando cerchi `product == PHONE`, [!UICONTROL Data Explorer] restituisce solo i risultati per `product == PHONE`.

Anche le realizzazioni con caratteristiche con backfill distinguono tra maiuscole e minuscole. Caratteristica contenente il segnale con la coppia chiave-valore `PRODUCT == SMARTPHONE` non qualifica il segnale con la coppia chiave-valore `product == smartphone`.
