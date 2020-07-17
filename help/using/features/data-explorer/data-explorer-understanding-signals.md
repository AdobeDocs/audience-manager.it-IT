---
description: I segnali sono l'unità di informazione più piccola  Audience Manager. Rappresentano le interazioni degli utenti o le attività degli utenti sulle proprietà online e passano a  Audience Manager da utilizzare nelle regole sulle caratteristiche.
seo-description: I segnali sono l'unità di informazione più piccola  Audience Manager. Rappresentano le interazioni degli utenti o le attività degli utenti sulle proprietà online e passano a  Audience Manager da utilizzare nelle regole sulle caratteristiche.
seo-title: Informazioni sui segnali
title: Informazioni sui segnali
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 2%

---


# Informazioni sui segnali

I segnali sono l&#39;unità di informazione più piccola  Audience Manager. Rappresentano le interazioni degli utenti o l&#39;attività degli utenti sulle proprietà online e passano a  Audience Manager da utilizzare nelle regole sulle caratteristiche.

[!DNL Audience Manager] utilizza coppie chiave-valore per rappresentare i segnali. Ad esempio, il segnale seguente potrebbe indicare che un visitatore ha raggiunto una pagina Web contenente elementi elettronici:

* `page = electronics`

Il Pannello [](../../features/data-explorer/data-explorer-signals-dashboard.md) Segnali mostra diversi tipi di attributi di segnale che potete usare per creare nuove caratteristiche. Di seguito viene fornita una visualizzazione dettagliata delle proprietà del segnale disponibili:

* *Coppia* chiave-valore indica la coppia chiave-valore del segnale ricevuto da [!DNL Audience Manager].
* *Il tipo* di segnale descrive la categoria di ciascun segnale. I segnali rientrano in una delle seguenti categorie:
   * [File](/help/using/integration/media-data-integration/actionable-log-files.md)di registro fruibili: segnali in tempo reale ricevuti dai file di registro delle prestazioni dei supporti;
   * [!DNL Adobe Analytics]: segnali in tempo reale ricevuti dal vostro [!DNL Adobe Analytics] account;
   * Dati generali in linea: dati in tempo reale generati dall&#39;attività dell&#39;audience e non inclusi nei file di registro fruibili e [!DNL Adobe Analytics];
   * Record a bordo: i dati ricevuti tramite trasferimenti di dati batch.
* *Sorgente* segnale dipende dal tipo di segnale:
   * Per i segnali caricati, l&#39;origine del segnale è il nome dell&#39;origine dati.
   * Per i segnali provenienti da [!DNL Adobe Analytics], l&#39;origine dati sarà sempre una suite di rapporti.
   * Per i file di registro fruibili e i dati generali in linea, non vengono visualizzate informazioni sulle sorgenti del segnale.
* *Conteggi* totali mostra il numero totale di volte in cui un segnale in tempo reale è stato ricevuto [!DNL Audience Manager] negli ultimi 7 giorni.
* *Incluso in Caratteristiche* mostra se il segnale fa parte di una caratteristica. Fare clic sulla freccia per visualizzare le caratteristiche che includono il segnale corrispondente. Per i segnali che non fanno parte di alcuna caratteristica, il valore della colonna diventa [!UICONTROL Create Onboarded Trait] o [!UICONTROL Create Rule-Based Trait].

## Frequenza di aggiornamento dei dati del segnale

A causa della grande quantità di dati che  Audience Manager elabora quotidianamente, [!UICONTROL Data Explorer] aggiorna i dati del segnale visualizzati a intervalli di tempo fissi, a seconda del tipo di segnale:

* I dati del segnale in tempo reale (file di registro fruibili, [!DNL Adobe Analytics] dati e dati generali in linea) vengono aggiornati ogni 4-6 ore.
* I dati del segnale a bordo vengono aggiornati ogni 24 ore.

## Concetti correlati

[Segnali, caratteristiche e segmenti](/help/using/reference/signal-trait-segment.md)