---
description: I segnali sono l'unità di informazioni più piccola all'interno di Audience Manager. Rappresentano interazioni degli utenti o attività utente sulle proprietà online e vengono trasmesse ad Audience Manager da utilizzare nelle regole delle caratteristiche.
seo-description: I segnali sono l'unità di informazioni più piccola all'interno di Audience Manager. Rappresentano interazioni degli utenti o attività utente sulle proprietà online e vengono trasmesse ad Audience Manager da utilizzare nelle regole delle caratteristiche.
seo-title: Informazioni sui segnali
title: Informazioni sui segnali
uuid: 04 a 0554 e -954 e -484 a -8838-9161 ef 416872
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Informazioni sui segnali

I segnali sono l&#39;unità di informazioni più piccola all&#39;interno di Audience Manager. Rappresentano interazioni degli utenti o attività dell&#39;utente sulle proprietà online e vengono trasmesse ad Audience Manager da utilizzare nelle regole delle caratteristiche.

[!DNL Audience Manager] utilizza coppie chiave-valore per rappresentare i segnali. Ad esempio, il seguente segnale potrebbe indicare che un visitatore ha raggiunto una pagina Web contenente l&#39;elettronica:

* `page = electronics`

Il [pannello Segnali](../../features/data-explorer/data-explorer-signals-dashboard.md) mostra più tipi di attributi del segnale che potete usare per creare nuove caratteristiche. Di seguito viene riportata una visualizzazione dettagliata delle proprietà del segnale disponibili:

* *La coppia* chiave-valore mostra la coppia chiave-valore del segnale ricevuto da [!DNL Audience Manager].
* *Il tipo di segnale* descrive la categoria di ogni segnale. I segnali rientrano in una delle seguenti categorie:
   * [File di registro fruibili](/help/using/integration/media-data-integration/actionable-log-files.md): segnali in tempo reale ricevuti dai file di registro delle prestazioni multimediali;
   * [!DNL Adobe Analytics]: i segnali in tempo reale ricevuti dall [!DNL Adobe Analytics] &#39;account,
   * Dati generali sulla linea: dati in tempo reale generati dall&#39;attività dell&#39;audience e non inclusi nei file di registro fruibili e [!DNL Adobe Analytics];
   * Record caricati: dati ricevuti tramite trasferimento di dati batch.
* *Origine segnale* dipende dal tipo di segnale:
   * Per i segnali caricati, l&#39;origine del segnale è il nome dell&#39;origine dati.
   * Per i segnali originati [!DNL Adobe Analytics], l&#39;origine dati sarà sempre una suite di rapporti.
   * Per i file di registro fruibili e i dati generali su linea, non vengono visualizzate informazioni sull&#39;origine del segnale.
* *Totale conteggio* mostra il numero totale di volte in cui è stato ricevuto un segnale in tempo reale negli [!DNL Audience Manager] ultimi 7 giorni.
* *Incluso in Caratteristiche* mostra se il segnale fa parte di una caratteristica. Fate clic sulla freccia per visualizzare le caratteristiche che includono il segnale corrispondente. Per i segnali che non fanno parte di alcuna caratteristica, il valore della colonna diventa [!UICONTROL Create Onboarded Trait] o [!UICONTROL Create Rule-Based Trait]meno.

## Frequenza aggiornamento dati segnale

A causa della grande quantità di dati elaborati su base giornaliera da Audience Manager, [!UICONTROL Data Explorer] i dati visualizzati vengono aggiornati a intervalli di tempo fissi a seconda del tipo di segnale:

* I dati del segnale in tempo reale (file di registro fruibili, [!DNL Adobe Analytics] dati e dati generali su linea) vengono aggiornati ogni 4 a 6 ore.
* I dati del segnale caricati vengono aggiornati ogni 24 ore.

## Concetti correlati

[Segnali, caratteristiche e segmenti](/help/using/reference/signal-trait-segment.md)