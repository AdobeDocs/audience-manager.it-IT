---
description: Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
seo-description: Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
seo-title: Ricerca di segnali per coppie chiave-valore
title: Ricerca di segnali per coppie chiave-valore
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: 'Data Explorer '
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 5%

---

# Ricerca di segnali per coppie chiave-valore {#search-signals-by-key-value-pairs}

Cercare uno o più segnali, in base alle rispettive coppie chiave-valore.
Per cercare più di un segnale, fare clic sul pulsante ![Aggiungi](assets/icon_add.png). Immetti le coppie chiave-valore da cercare, quindi utilizza i seguenti filtri per limitare i risultati.

* **Stato** del segnale: cerca i segnali inclusi nelle caratteristiche, nei segnali inutilizzati o in entrambi.
* **Visualizza record per**: selezionare l&#39;intervallo di tempo in cui cercare i segnali ricevuti.
* **Conteggi** minimi: visualizza solo i segnali con il numero totale minimo specificato nell&#39;intervallo selezionato.

>[!IMPORTANT]
>
>Per semplificare l’esperienza utente, i risultati della ricerca con coppie chiave-valore si basano sul campionamento dei dati. Per informazioni dettagliate su come [!DNL Audience Manager] utilizza il campionamento dei dati e sui motivi per cui possono comparire lievi variazioni dei risultati quando si confronta la ricerca chiave-valore con le ricerche generali, consulta [Campionamento dei dati e tassi di errore](/help/using/reporting/report-sampling.md) .

Durante la ricerca di segnali utilizzando più coppie chiave-valore, [!DNL Audience Manager] collega le coppie utilizzando l&#39;operatore logico **AND**. Ad esempio, supponiamo che tu stia eseguendo una ricerca con le seguenti coppie chiave-valore:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Questa ricerca restituirà solo i risultati idonei per tutti e tre i filtri nella stessa chiamata: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Segnali esclusi dalla ricerca del segnale {#excluded-signals}

Le variabili chiave utilizzate dall&#39;Audience Manager e con prefisso `d_` e `h_` non vengono visualizzate da [!UICONTROL Signals Search]. Per ulteriori informazioni, consulta [Requisiti del prefisso per le variabili chiave](../../traits/trait-variable-prefixes.md) .

## Insensibilità alle maiuscole e minuscole e completamento automatico della ricerca {#case-insensitivity}

I campi di ricerca chiave e valore non fanno distinzione tra maiuscole e minuscole. Il campo di ricerca chiave include suggerimenti completati automaticamente.

![](assets/signal-search-suggestions.png)

Supponiamo che [!DNL Audience Manager] abbia ricevuto i seguenti segnali:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Quando immetti `product` nel campo di ricerca chiave, ricevi suggerimenti completati automaticamente per `productCategory`, `newProduct`, `PRODUCT` e `product`.

Allo stesso modo, quando si cerca `product == phone`, [!UICONTROL Data Explorer] restituisce i risultati sia per `PRODUCT == phone` che per `product == PHONE`.
Le realizzazioni con caratteristiche con backfill non distinguono tra maiuscole e minuscole. Anche una caratteristica contenente il segnale con la coppia chiave-valore `PRODUCT == SMARTPHONE` qualifica il segnale con la coppia chiave-valore `product == smartphone`.
