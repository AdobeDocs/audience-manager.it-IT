---
description: La qualificazione delle caratteristiche, o realizzazione delle caratteristiche, viene trattata in modo diverso in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualifica delle caratteristiche, consulta la tabella seguente.
keywords: Qualificazione delle caratteristiche,Realizzazione delle caratteristiche,Realizzazioni di caratteristiche univoche,UTR,Popolazione di caratteristiche totale,TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Riferimento per la qualifica delle caratteristiche
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Riferimenti per la qualifica di caratteristiche e segmenti {#trait-qualification-reference}

La qualificazione delle caratteristiche, o realizzazione delle caratteristiche, viene trattata in modo diverso in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualifica del tipo di caratteristica, consulta [Qualificazione della caratteristica per tipo di caratteristica](#trait-type).

Inoltre, per informazioni dettagliate sulla qualifica del segmento, consulta [Popolazione del segmento in tempo reale e popolazione totale del segmento](#real-time-segment).



## Qualificazione delle caratteristiche per tipo di caratteristica {#trait-type}

| Tipo di caratteristica | Criteri di qualificazione |
|---|---|
| Caratteristiche basate su regole | La qualifica delle caratteristiche avviene in tempo reale, in quanto gli utenti si qualificano per una caratteristica nel browser. Gli utenti inizieranno a qualificarsi per una caratteristica basata su regole circa 4 ore dopo che [avrai creato la caratteristica](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) nell&#39;interfaccia utente. Le caratteristiche basate su regole ti consentono di utilizzare i controlli [recency e frequenza](../segments/recency-and-frequency.md) per il limite di frequenza degli annunci e altri casi d&#39;uso. |
| Caratteristiche onboarded | La qualifica delle caratteristiche si verifica dopo l&#39;elaborazione di un file in entrata, ovvero quando il file in entrata viene [importato in Audience Manager](../../faq/faq-inbound-data-ingestion.md), ovvero quando si verifica la qualifica delle caratteristiche. Attendi circa 4 ore dalla creazione di una caratteristica onboarded prima di caricare un file in entrata per l’elaborazione. Per le caratteristiche onboarded, il numero massimo di qualifiche per un profilo utente è 1. |
| Caratteristiche algoritmiche | Per le caratteristiche algoritmiche, il numero massimo di qualifiche per un profilo utente è 1. |
| Caratteristiche cartella | Una caratteristica cartella riassume le qualifiche delle caratteristiche che contiene. Leggi [Caratteristiche cartella: Informazioni su](about-folder-traits.md) per ulteriori informazioni. |
| Caratteristiche di pubblici attivi e caratteristiche sincronizzate con Data Source | Una caratteristica [!UICONTROL Active Audience] contiene tutti i dispositivi gestiti nel tuo account Audience Manager. [!UICONTROL Data Source Synced Traits] tiene traccia di tutti gli utenti associati a un&#39;origine dati. Ulteriori informazioni su [Caratteristiche di pubblico attivo e caratteristiche sincronizzate con Data Source](client-activity-synced-audience-traits.md). |

## Realizzazioni di caratteristiche univoche e popolazione di caratteristiche totale {#unique-trait-realizations}

![realizzazione-caratteristiche-univoche](assets/trait-graph.png)

A seconda del tipo di risultati che si desidera visualizzare nel grafico (filtrati da [!UICONTROL Device ID] o [!UICONTROL Cross-Device ID]), le metriche hanno significati diversi:

Quando si filtrano i risultati per [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori anonimi del tuo dispositivo che hanno aggiunto la caratteristica al loro profilo in diversi intervalli di tempo.
* [!UICONTROL Total Trait Population] è il numero di visitatori anonimi del tuo dispositivo che hanno questa caratteristica sul loro profilo.

Quando si filtrano i risultati per [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori autenticati che hanno aggiunto la caratteristica al loro profilo, entro intervalli di tempo diversi.
* [!UICONTROL Total Trait Population] è il numero di visitatori autenticati che hanno questa caratteristica sul loro profilo.

Pensate ai numeri in questo modo. Nell&#39;immagine qui sopra, nella visualizzazione [Dettagli caratteristica](../../features/traits/trait-details-page.md), 90.173 rappresenta il numero di dispositivi attivi che hanno visitato le tue proprietà ieri. Il [!UICONTROL Total Trait Population] di 55.757 rappresenta la quantità di utenti attualmente qualificati per questa caratteristica. La cifra [!UICONTROL Total Trait Population] ha lo scopo di mostrare la quantità totale di utenti che possono essere utilizzati per segmentazione/targeting. In genere, gli utenti rimangono parte di una caratteristica per 120 giorni.

Poiché vengono eseguiti due processi di calcolo diversi per calcolare le due popolazioni, [!UICONTROL Total Trait Population] è sempre in ritardo rispetto a [!UICONTROL Unique Trait Realizations] per 24 ore. Nel grafico precedente, puoi vedere circa 90.400 [!UICONTROL Unique Trait Realizations] e un [!UICONTROL Total Trait Population] di circa 90.300 per il 5 febbraio. I 90.400 profili vengono aggiunti a [!UICONTROL Total Trait Population] il giorno successivo.

Per dare ulteriore impulso al punto, se al momento si verifica un picco di 10.000 visitatori, questi verranno visualizzati nel [!UICONTROL Unique Trait Realizations] di domani, ma solo 24 ore dopo nel [!UICONTROL Total Trait Population].

Qualsiasi modifica nelle realizzazioni delle caratteristiche si riflette nelle popolazioni dei segmenti.

## Popolazione del segmento in tempo reale e popolazione totale del segmento {#real-time-segment}

![realizzazione-caratteristiche-univoche](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population] conta il numero di dispositivi qualificati per il segmento selezionato e che hanno raggiunto le proprietà, entro l&#39;intervallo di tempo selezionato.

[!UICONTROL Total Segment Population] conta il numero di dispositivi qualificati per il segmento selezionato all&#39;interno dell&#39;intervallo di tempo selezionato. Il rapporto [!UICONTROL 1 Day] rappresenta il conteggio di popolazione del segmento più aggiornato.

Pensate ai numeri in questo modo. Nell&#39;immagine precedente, nella visualizzazione [Dettagli segmento](../../features/segments/segment-summary-view.md), 9.993 rappresenta il numero di dispositivi attivi che hanno visitato le proprietà ieri e si sono qualificati per il segmento. Il [!UICONTROL Total Segment Population] di 699.532 rappresenta il numero totale di dispositivi attualmente qualificati per questo segmento. La figura [!UICONTROL Total Segment Population] ha lo scopo di mostrare il numero totale di dispositivi che possono essere utilizzati per la segmentazione/il targeting.

Poiché vengono eseguiti due processi di calcolo diversi per calcolare le due popolazioni, [!UICONTROL Total Segment Population] è sempre in ritardo rispetto a [!UICONTROL Real-time Segment Population] per 24 ore. Nel grafico qui sopra, puoi vedere un 8.116 [!UICONTROL Real-time Segment Population] e un [!UICONTROL Total Segment Population] di 742.000 per il 2 febbraio. Gli 8.116 profili vengono aggiunti a [!UICONTROL Total Segment Population] il giorno successivo.

Per dare ulteriore impulso al punto, se al momento si verifica un picco di 10.000 visitatori, questi verranno visualizzati nel [!UICONTROL Real-time Segment Population] di domani, ma solo 24 ore dopo nel [!UICONTROL Total Segment Population].

## Limite di qualificazione delle caratteristiche {#trait-qualification-limit}

Imponiamo un limite di 150.000 qualifiche di caratteristiche per ciascun profilo utente, sia che si tratti di un profilo autenticato ([DPUUID](../../reference/ids-in-aam.md)) o di un ID dispositivo ([UUID](../../reference/ids-in-aam.md)). Si noti che mentre gli identificatori DPUUID sono univoci per un&#39;istanza specifica di [!DNL Audience Manager], gli identificatori UUID sono condivisi nella piattaforma [!DNL Audience Manager]. Per [!UICONTROL UUID] s, viene imposta una policy di correttezza durante la memorizzazione delle qualifiche delle caratteristiche. Un algoritmo garantisce che una condivisione uguale del profilo [!UICONTROL UUID] sia disponibile per ogni istanza di [!DNL Audience Manager].
