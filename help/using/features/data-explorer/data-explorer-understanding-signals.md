---
description: I segnali sono l'unità di informazione più piccola all'interno dell'Audience Manager. Rappresentano le interazioni dell’utente o l’attività dell’utente sulle proprietà online e vengono passati all’Audience Manager da utilizzare nelle regole delle caratteristiche.
seo-description: I segnali sono l'unità di informazione più piccola all'interno dell'Audience Manager. Rappresentano le interazioni dell’utente o l’attività dell’utente sulle proprietà online e vengono passati all’Audience Manager da utilizzare nelle regole delle caratteristiche.
seo-title: Informazioni sui segnali
title: Informazioni sui segnali
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: 'Data Explorer '
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Informazioni sui segnali

I segnali sono l&#39;unità di informazione più piccola all&#39;interno dell&#39;Audience Manager. Rappresentano le interazioni dell’utente o l’attività dell’utente sulle proprietà on-line e vengono passati all’Audience Manager da utilizzare nelle regole delle caratteristiche.

[!DNL Audience Manager] utilizza coppie chiave-valore per rappresentare i segnali. Ad esempio, il segnale seguente potrebbe indicare che un visitatore ha raggiunto una pagina web contenente elementi elettronici:

* `page = electronics`

Il [Dashboard dei segnali](../../features/data-explorer/data-explorer-signals-dashboard.md) mostra diversi tipi di attributi di segnale che è possibile utilizzare per creare nuove caratteristiche. Ecco una visualizzazione dettagliata delle proprietà del segnale disponibili:

* *Le coppie chiave-valore* mostrano la coppia chiave-valore del segnale ricevuto da  [!DNL Audience Manager].
* *Il* tipo di segnale descrive la categoria di ciascun segnale. I segnali rientrano in una delle seguenti categorie:
   * [File](/help/using/integration/media-data-integration/actionable-log-files.md) di registro fruibili: segnali in tempo reale ricevuti dai file di log delle prestazioni dei supporti;
   * [!DNL Adobe Analytics]: segnali in tempo reale ricevuti dal tuo  [!DNL Adobe Analytics] account;
   * Dati generali in linea: dati in tempo reale generati dalla tua attività di pubblico e non inclusi nei file di registro actionable e [!DNL Adobe Analytics];
   * Registri di bordo: dati ricevuti tramite trasferimenti di dati in batch.
* *La* sorgente del segnale dipende dal tipo di segnale:
   * Per i segnali onboarded, l&#39;origine del segnale è il nome dell&#39;origine dati.
   * Per i segnali provenienti da [!DNL Adobe Analytics], l&#39;origine dati sarà sempre una suite di rapporti.
   * Per i file di registro utilizzabili e i dati generali in linea, non vengono visualizzate informazioni sulle sorgenti del segnale.
* *Totale* mostra il numero totale di volte in cui un segnale in tempo reale è stato ricevuto da  [!DNL Audience Manager] negli ultimi 7 giorni.
* *Incluso nelle* caratteristiche, mostra se il segnale fa parte di qualsiasi caratteristica. Fai clic sulla freccia per visualizzare le caratteristiche che includono il segnale corrispondente. Per i segnali che non fanno parte di alcuna caratteristica, il valore della colonna diventa [!UICONTROL Create Onboarded Trait] o [!UICONTROL Create Rule-Based Trait].

## Frequenza di aggiornamento dei dati del segnale

A causa della grande quantità di dati che Audience Manager elabora quotidianamente, [!UICONTROL Data Explorer] aggiorna i dati del segnale visualizzato a intervalli di tempo fissi, a seconda del tipo di segnale:

* I dati del segnale in tempo reale (file di registro fruibili, dati [!DNL Adobe Analytics] e dati online generali) vengono aggiornati ogni 4-6 ore.
* I dati del segnale di bordo vengono aggiornati ogni 24 ore.

## Concetti correlati

[Segnali, caratteristiche e segmenti](/help/using/reference/signal-trait-segment.md)
