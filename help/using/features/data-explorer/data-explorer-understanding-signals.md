---
description: I segnali sono l’unità di informazioni più piccola all’interno di Audience Manager. Rappresentano le interazioni degli utenti o l’attività degli utenti sulle proprietà online e vengono trasmessi ad Audience Manager per essere utilizzati nelle regole delle caratteristiche.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Informazioni sui segnali
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Informazioni sui segnali

I segnali sono l’unità di informazioni più piccola all’interno di Audience Manager. Rappresentano le interazioni degli utenti o l’attività degli utenti sulle proprietà online e vengono trasmessi ad Audience Manager per essere utilizzati nelle regole delle caratteristiche.

[!DNL Audience Manager] utilizza coppie chiave-valore per rappresentare i segnali. Ad esempio, il seguente segnale potrebbe indicare che un visitatore ha raggiunto una pagina web contenente componenti elettronici:

* `page = electronics`

Il [Dashboard segnali](../../features/data-explorer/data-explorer-signals-dashboard.md) mostra più tipi di attributi di segnale che è possibile utilizzare per creare nuove caratteristiche. Ecco una vista dettagliata delle proprietà del segnale disponibili:

* *Coppia chiave-valore* mostra la coppia chiave-valore del segnale ricevuto da [!DNL Audience Manager].
* *Tipo di segnale* descrive la categoria di ciascun segnale. I segnali rientrano in una delle seguenti categorie:
   * [File di registro fruibili](/help/using/integration/media-data-integration/actionable-log-files.md): segnali in tempo reale ricevuti dai file di registro delle prestazioni multimediali;
   * [!DNL Adobe Analytics]: segnali in tempo reale ricevuti dal tuo account [!DNL Adobe Analytics];
   * Dati generali online: dati in tempo reale generati dall&#39;attività del pubblico e non inclusi nei file di registro fruibili e [!DNL Adobe Analytics];
   * Record onboarded: dati ricevuti tramite trasferimenti di dati in batch.
* *Segnale Source* dipende dal tipo di segnale:
   * Per i segnali onboarded, la sorgente di segnale è il nome della sorgente di dati.
   * Per i segnali provenienti da [!DNL Adobe Analytics], l&#39;origine dati sarà sempre una suite di rapporti.
   * Per i file di registro utilizzabili e i dati generali in linea, non vengono visualizzate informazioni sull’origine del segnale.
* *Conteggi totali* mostra il numero totale di volte in cui è stato ricevuto un segnale in tempo reale da [!DNL Audience Manager] negli ultimi 7 giorni.
* *Incluso nelle caratteristiche* indica se il segnale fa parte di una caratteristica. Fai clic sulla freccia per visualizzare le caratteristiche che includono il segnale corrispondente. Per i segnali che non fanno parte di alcuna caratteristica, il valore della colonna cambia in [!UICONTROL Create Onboarded Trait] o [!UICONTROL Create Rule-Based Trait].

## Frequenza aggiornamento dati segnale

A causa della grande quantità di dati elaborati quotidianamente da Audience Manager, [!UICONTROL Data Explorer] aggiorna i dati del segnale visualizzati a intervalli di tempo fissi, a seconda del tipo di segnale:

* I dati dei segnali in tempo reale (file di registro utilizzabili, dati [!DNL Adobe Analytics] e dati generali in linea) vengono aggiornati ogni 4-6 ore.
* I dati del segnale onboarded vengono aggiornati ogni 24 ore.

## Concetti correlati

[Segnali, caratteristiche e segmenti](/help/using/reference/signal-trait-segment.md)
