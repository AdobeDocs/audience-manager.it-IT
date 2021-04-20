---
description: La qualificazione delle caratteristiche, o realizzazione delle caratteristiche, viene trattata in modo diverso nell’Audience Manager, a seconda del tipo di caratteristica. Vedi la tabella seguente per informazioni dettagliate sulla qualifica delle caratteristiche.
keywords: Qualificazione delle caratteristiche, Realizzazione delle caratteristiche, Realizzazioni delle caratteristiche univoche, UTR, Popolazione totale delle caratteristiche, TTP
seo-description: La qualificazione delle caratteristiche, o realizzazione delle caratteristiche, viene trattata in modo diverso nell’Audience Manager, a seconda del tipo di caratteristica. Vedi la tabella seguente per informazioni dettagliate sulla qualifica delle caratteristiche.
seo-title: Riferimento per la qualifica delle caratteristiche
solution: Audience Manager
title: Riferimento per la qualifica delle caratteristiche
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,223f5fc6-c939-4bc6-94a3-5d953abc601a
translation-type: tm+mt
source-git-commit: e13f81df9b0d59cd958f4c2a615c31df00ce2cc5
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# Riferimenti per la qualifica di caratteristiche e segmenti {#trait-qualification-reference}

La qualificazione delle caratteristiche, o realizzazione delle caratteristiche, viene trattata in modo diverso nell’Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualifica del tipo di caratteristica, consulta [Qualificazione delle caratteristiche per tipo di caratteristica](#trait-type) .

Inoltre, per informazioni sulla qualifica dei segmenti, consulta [Popolazione di segmenti in tempo reale e Popolazione di segmenti totale](#real-time-segment) .



## Qualificazione delle caratteristiche per tipo di caratteristica {#trait-type}

| Tipo di caratteristica | Criteri di qualifica |
|---|---|
| Caratteristiche basate su regole | La qualificazione delle caratteristiche avviene in tempo reale, in quanto gli utenti si qualificano per una caratteristica nel proprio browser. Gli utenti inizieranno a qualificarsi per una caratteristica basata su regole circa 4 ore dopo la [creazione della caratteristica](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) nell&#39;interfaccia utente. Le caratteristiche basate su regole consentono di utilizzare i controlli [recency e frequenza](../segments/recency-and-frequency.md) per il limite di frequenza degli annunci e altri casi d’uso. |
| Caratteristiche onboarded | La qualifica delle caratteristiche avviene dopo l’elaborazione di un file in entrata, ovvero il file in entrata [viene importato in Audience Manager](../../faq/faq-inbound-data-ingestion.md) e cioè quando si verifica la qualifica delle caratteristiche. È necessario attendere circa 4 ore dalla creazione di una caratteristica onboarded prima di caricare un file in entrata per l’elaborazione. Per le caratteristiche onboarded, il numero massimo di qualifiche per un profilo utente è 1. |
| Caratteristiche algoritmiche | Per le caratteristiche algoritmiche, il numero massimo di qualifiche per un profilo utente è 1. |
| Caratteristiche cartella | Una caratteristica della cartella riassume le qualifiche delle caratteristiche delle caratteristiche che contiene. Leggi [Caratteristiche cartella: Informazioni su](about-folder-traits.md) per ulteriori informazioni. |
| Caratteristiche di pubblici attivi e caratteristiche sincronizzate con la sorgente dei dati | Una caratteristica [!UICONTROL Active Audience] contiene tutti i dispositivi in gestione nel tuo account di Audience Manager. [!UICONTROL Data Source Synced Traits] tenere traccia di tutti gli utenti associati a un’origine dati. Ulteriori informazioni su [Caratteristiche di pubblico attivo e caratteristiche sincronizzate con origine dati](client-activity-synced-audience-traits.md). |

## Realizzazioni di caratteristiche univoche e popolazione totale di caratteristiche {#unique-trait-realizations}

![realizzazione di caratteristiche uniche](assets/trait-graph.png)

A seconda del tipo di risultati che si desidera visualizzare nel grafico (filtrato da [!UICONTROL Device ID] o [!UICONTROL Cross-Device ID]), le metriche hanno significati diversi:

Durante il filtraggio dei risultati per [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori anonimi del dispositivo che hanno aggiunto la caratteristica al profilo entro intervalli di tempo diversi.
* [!UICONTROL Total Trait Population] è il numero di visitatori del tuo dispositivo anonimi che hanno questa caratteristica sul loro profilo.

Durante il filtraggio dei risultati per [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori autenticati che hanno aggiunto la caratteristica al profilo entro intervalli di tempo diversi.
* [!UICONTROL Total Trait Population] è il numero di visitatori autenticati che hanno questa caratteristica sul loro profilo.

Pensate ai numeri in questo modo. Nell&#39;immagine precedente, dalla vista [Dettagli caratteristica](../../features/traits/trait-details-page.md), 90.173 rappresenta il numero di dispositivi attivi che hanno visitato le tue proprietà ieri. Il valore [!UICONTROL Total Trait Population] di 55.757 rappresenta la quantità di utenti attualmente qualificati per questa caratteristica. La figura [!UICONTROL Total Trait Population] mostra la quantità totale di utenti che possono essere utilizzati per la segmentazione/il targeting. In genere, gli utenti rimangono parte di una caratteristica per 120 giorni.

Poiché eseguiamo due diversi processi di calcolo per calcolare le due popolazioni, il [!UICONTROL Total Trait Population] rimane sempre indietro di 24 ore rispetto al [!UICONTROL Unique Trait Realizations]. Nel grafico qui sopra, puoi vedere circa 90.400 [!UICONTROL Unique Trait Realizations] e un [!UICONTROL Total Trait Population] di circa 90.300 per il 5 febbraio. I 90.400 profili vengono aggiunti al [!UICONTROL Total Trait Population] il giorno successivo.

Per portare ulteriormente il punto a casa, se avete sperimentato un picco di 10.000 visitatori in questo momento, apparirebbero nel [!UICONTROL Unique Trait Realizations] di domani, ma apparirebbero solo 24 ore dopo nel [!UICONTROL Total Trait Population].

Qualsiasi cambiamento nelle realizzazioni delle caratteristiche riflette le popolazioni dei segmenti.

## Popolazione di segmenti in tempo reale e popolazione totale di segmenti {#real-time-segment}

![realizzazione di caratteristiche uniche](assets/segment-graph.png)

Il [!UICONTROL Real-time Segment Population] conta il numero di dispositivi che si sono qualificati per il segmento selezionato e hanno raggiunto le proprietà, entro l’intervallo di tempo selezionato.

Il [!UICONTROL Total Segment Population] conta il numero di dispositivi qualificati per il segmento selezionato nell’intervallo di tempo selezionato. Il rapporto [!UICONTROL 1 Day] rappresenta il conteggio di popolazione del segmento più aggiornato.

Pensate ai numeri in questo modo. Nell&#39;immagine precedente, dalla visualizzazione [Dettagli segmento](../../features/segments/segment-summary-view.md), 9.993 rappresenta il numero di dispositivi attivi che hanno visitato le tue proprietà ieri e che si sono qualificati per il segmento. Il numero [!UICONTROL Total Segment Population] di 699.532 rappresenta il numero totale di dispositivi attualmente qualificati per questo segmento. La figura [!UICONTROL Total Segment Population] mostra il numero totale di dispositivi che possono essere utilizzati per la segmentazione/il targeting.

Poiché eseguiamo due diversi processi di calcolo per calcolare le due popolazioni, il [!UICONTROL Total Segment Population] rimane sempre indietro di 24 ore rispetto al [!UICONTROL Real-time Segment Population]. Nel grafico qui sopra, puoi vedere un 8.116 [!UICONTROL Real-time Segment Population] e un [!UICONTROL Total Segment Population] di 742.000 per il 2 febbraio. I profili 8.116 vengono aggiunti al [!UICONTROL Total Segment Population] il giorno successivo.

Per portare ulteriormente il punto a casa, se avete sperimentato un picco di 10.000 visitatori in questo momento, apparirebbero nel [!UICONTROL Real-time Segment Population] di domani, ma apparirebbero solo 24 ore dopo nel [!UICONTROL Total Segment Population].

## Limite di qualifica delle caratteristiche {#trait-qualification-limit}

Per ciascun profilo utente viene applicato un limite di 150.000 qualifiche di caratteristiche, sia che si tratti di un profilo autenticato ([DPUUID](../../reference/ids-in-aam.md)) o di un ID dispositivo ([UUID](../../reference/ids-in-aam.md)). Sebbene i DPUUID siano univoci per un&#39;istanza specifica di [!DNL Audience Manager], gli UUID sono condivisi tra le diverse piattaforme [!DNL Audience Manager]. Per [!UICONTROL UUID]s, imponiamo una policy di equità quando memorizziamo le qualifiche delle caratteristiche. Un algoritmo assicura che una condivisione uguale del profilo [!UICONTROL UUID] sia disponibile per ogni istanza di [!DNL Audience Manager].
