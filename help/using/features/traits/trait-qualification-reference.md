---
description: La qualifica o la realizzazione delle caratteristiche viene trattata in modo diverso in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualificazione delle caratteristiche, vedere la tabella seguente.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: La qualifica o la realizzazione delle caratteristiche viene trattata in modo diverso in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualificazione delle caratteristiche, vedere la tabella seguente.
seo-title: Riferimento per la qualifica delle caratteristiche
solution: Audience Manager
title: Riferimento per la qualifica delle caratteristiche
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: bd0ebcddc89c2141e9ce55d7fa2e68b5ca1cbb22

---


# Riferimento per la qualifica delle caratteristiche {#trait-qualification-reference}

La qualifica o la realizzazione delle caratteristiche viene trattata in modo diverso in Audience Manager, a seconda del tipo di caratteristica. Per informazioni dettagliate sulla qualificazione delle caratteristiche, vedere la tabella seguente.

## Qualificazione caratteristica per tipo di caratteristica {#trait-type}

| Tipo di caratteristica | Criteri di qualifica |
|---|---|
| Caratteristiche basate su regole | La qualifica di caratteristica avviene in tempo reale, in quanto gli utenti hanno diritto a una caratteristica nel browser. Gli utenti inizieranno a qualificarsi per una caratteristica basata su regola circa 4 ore dopo la [creazione della caratteristica](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) nell&#39;interfaccia utente. Le caratteristiche basate su regole consentono di utilizzare i controlli di [aggiornamento e frequenza](../segments/recency-and-frequency.md) per i limiti di frequenza degli annunci e altri casi di utilizzo. |
| Caratteristiche di bordo | La qualifica di caratteristica avviene dopo l&#39;elaborazione di un file in ingresso, ovvero il file in ingresso viene [importato in Audience Manager](../../faq/faq-inbound-data-ingestion.md) , ovvero quando si verifica la qualifica di caratteristica. Prima di caricare un file in entrata per l’elaborazione, è necessario attendere circa 4 ore dopo aver creato una caratteristica caricata. Per le caratteristiche registrate, il numero massimo di qualifiche per un profilo utente è 1. |
| Caratteristiche algoritmiche | Per le caratteristiche algoritmiche, il numero massimo di qualifiche per un profilo utente è 1. |
| Caratteristiche delle cartelle | Una caratteristica della cartella riassume le caratteristiche delle caratteristiche che contiene. Leggi caratteristiche [cartella: Informazioni](about-folder-traits.md) per ulteriori informazioni. |
| Caratteristiche di pubblico attive e caratteristiche sincronizzate dell&#39;origine dati | Una [!UICONTROL Active Audience] caratteristica contiene tutti i dispositivi in gestione nel tuo account Audience Manager. [!UICONTROL Data Source Synced Traits] tenere traccia di tutti gli utenti associati a un&#39;origine dati. Ulteriori informazioni sulle caratteristiche [Active Audience e sulle caratteristiche](client-activity-synced-audience-traits.md)sincronizzate dell&#39;origine dati. |

## Realizzazioni di caratteristiche univoche e popolazione di caratteristiche totali {#unique-trait-realizations}

![realizzazione unica-caratteristica](assets/trait-graph.png)

A seconda del tipo di risultati che si desidera visualizzare nel grafico (filtrato per [!UICONTROL Device ID] o ID [!UICONTORL ]multi-dispositivo), le metriche hanno significati diversi:

Quando filtrate i risultati tramite [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori anonimi del dispositivo che hanno aggiunto la caratteristica al proprio profilo entro intervalli di tempo diversi.
* [!UICONTROL Total Trait Population] è il numero di visitatori anonimi del dispositivo che hanno questa caratteristica sul loro profilo.

Quando filtrate i risultati tramite [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori autenticati che hanno aggiunto la caratteristica al proprio profilo, entro intervalli di tempo diversi.
* [!UICONTROL Total Trait Population] è il numero di visitatori autenticati che hanno questa caratteristica sul loro profilo.

Pensate ai numeri in questo modo. Nell&#39;immagine qui sopra, dalla vista Dettagli [](../../features/traits/trait-details-page.md) caratteristica, 90.173 rappresenta il numero di dispositivi attivi che hanno visitato le vostre proprietà ieri. Il valore [!UICONTROL Total Trait Population] di 55.757 rappresenta la quantità di utenti attualmente qualificati per questa caratteristica. La [!UICONTROL Total Trait Population] figura mostra la quantità totale di utenti che potrebbero essere utilizzati per la segmentazione/il targeting. In genere, gli utenti restano parte di una caratteristica per 120 giorni.

Perché facciamo due diversi processi computazionali per calcolare le due popolazioni, il [!UICONTROL Total Trait Population] ritardo è sempre [!UICONTROL Unique Trait Realizations] di 24 ore. Nel grafico qui sopra, potete vedere circa 90.400 [!UICONTROL Unique Trait Realizations] e un [!UICONTROL Total Trait Population] di circa 90.300 per il 5 febbraio. I 90.400 profili vengono aggiunti al [!UICONTROL Total Trait Population] giorno successivo.

Per portare ulteriormente a casa il punto, se avete sperimentato un picco di 10.000 visitatori in questo momento, si presentavano in quella di domani [!UICONTROL Unique Trait Realizations], ma si presentavano solo 24 ore dopo nella [!UICONTROL Total Trait Population].

Qualsiasi modifica nelle realizzazioni delle caratteristiche riflette le popolazioni dei segmenti.

## Popolazione segmento in tempo reale e popolazione segmento totale {#real-time-segment}

![realizzazione unica-caratteristica](assets/segment-graph.png)

Consente di [!UICONTROL Real-time Segment Population] conteggiare il numero di dispositivi idonei per il segmento selezionato e che hanno raggiunto le proprietà nell&#39;intervallo di tempo selezionato.

Consente di [!UICONTROL Total Segment Population] conteggiare il numero di dispositivi idonei per il segmento selezionato nell&#39;intervallo di tempo selezionato. Il [!UICONTROL 1 Day] rapporto rappresenta il conteggio di popolazione del segmento più aggiornato.

Pensate ai numeri in questo modo. Nell&#39;immagine precedente, dalla visualizzazione Dettagli [](../../features/segments/segment-summary-view.md) segmento, 9.993 rappresenta il numero di dispositivi attivi che hanno visitato ieri le vostre proprietà e che hanno acquisito le qualifiche per il segmento. Il numero [!UICONTROL Total Segment Population] di 699.532 rappresenta il numero totale di dispositivi attualmente idonei per questo segmento. La [!UICONTROL Total Segment Population] figura mostra il numero totale di dispositivi che possono essere utilizzati per segmentazione/targeting.

Perché facciamo due diversi processi computazionali per calcolare le due popolazioni, il [!UICONTROL Total Segment Population] ritardo è sempre [!UICONTROL Real-time Segment Population] di 24 ore. Nel grafico qui sopra, potete vedere un 8.116 [!UICONTROL Real-time Segment Population] e un [!UICONTROL Total Segment Population] di 742.000 per il 2 febbraio. I profili 8.116 vengono aggiunti al [!UICONTROL Total Segment Population] giorno successivo.

Per portare ulteriormente a casa il punto, se avete sperimentato un picco di 10.000 visitatori in questo momento, si presentavano in quella di domani [!UICONTROL Real-time Segment Population], ma si presentavano solo 24 ore dopo nella [!UICONTROL Total Segment Population].

## Limite di qualifica caratteristica {#trait-qualification-limit}

Per ciascun profilo utente viene applicato un limite di 150.000 qualifiche di caratteristica, che si tratti di un profilo autenticato ([DPUUID](../../reference/ids-in-aam.md)) o di un ID dispositivo ([UUID](../../reference/ids-in-aam.md)). Sebbene i DPUUID siano univoci per un’istanza specifica di [!DNL Audience Manager], gli UUID vengono condivisi tra le diverse [!DNL Audience Manager] piattaforme. Per [!UICONTROL UUID]esempio, imponiamo una politica di equità quando si memorizzano le qualifiche di caratteristiche. Un algoritmo garantisce che una quota uguale del [!UICONTROL UUID] profilo sia disponibile per ogni istanza di [!DNL Audience Manager].
