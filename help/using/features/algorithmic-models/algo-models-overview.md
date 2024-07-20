---
description: Descrive i modelli algoritmici disponibili in Audience Manager.
keywords: algo modella come funziona i tipi di pubblico predittivi
seo-description: Describes the algorithmic models available in Audience Manager.
seo-title: Algorithmic Models Overview
solution: Audience Manager
title: Panoramica dei modelli algoritmici
feature: Algorithmic Models
exl-id: ee5c3392-2756-45c5-b325-41a51d3c494f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# Panoramica dei modelli algoritmici

## Cos’è la modellazione algoritmica{#what-algo-modeling}

La modellazione algoritmica in Audience Manager si riferisce all’utilizzo della scienza dei dati per espandere i tipi di pubblico esistenti o classificarli in utenti tipo.

Questa operazione viene eseguita tramite due tipi di algoritmi: [!UICONTROL Look-Alike Modeling] e [!UICONTROL Predictive Audiences].

## Modellazione lookalike{#lam}

[!UICONTROL Look-Alike Modeling] consente di individuare nuovi tipi di pubblico univoci tramite l&#39;analisi automatizzata dei dati. Il processo inizia quando selezioni una caratteristica o un segmento, un intervallo di tempo e origini dati di prime e terze parti. Le scelte effettuate forniscono gli input per il modello algoritmico. Durante l’esecuzione del processo di analisi, vengono cercati gli utenti idonei in base alle caratteristiche condivise della popolazione selezionata.

Al termine, questi dati sono disponibili in [Generatore di caratteristiche](../../features/traits/about-trait-builder.md) dove puoi utilizzarli per creare caratteristiche basate sulla [precisione e portata](../../features/traits/trait-accuracy-reach.md). Inoltre, puoi creare segmenti che combinano caratteristiche algoritmiche con caratteristiche basate su regole e aggiungere altri requisiti di qualificazione con espressioni booleane e operatori di confronto.

[!UICONTROL Look-Alike Modeling] offre un modo dinamico per estrarre valore da tutti i dati delle caratteristiche disponibili.

Per ulteriori informazioni su [!UICONTROL Look-Alike Modeling], vedere [Informazioni sulla modellazione lookalike](understanding-models.md).

## Predictive Audiences{#predictive-audiences}

[!UICONTROL Predictive Audiences] ti consente di classificare in tempo reale un pubblico sconosciuto in utenti tipo distinti utilizzando tecniche avanzate di scienza dei dati.

In un contesto di marketing, un utente tipo è un segmento di pubblico definito da visitatori, utenti o potenziali acquirenti che condividono un set specifico di caratteristiche come dati demografici, abitudini di navigazione, cronologia acquisti, ecc.

I modelli di [!UICONTROL Predictive Audiences] sviluppano ulteriormente questo concetto, utilizzando le funzionalità di machine learning di Audience Manager per classificare automaticamente tipi di pubblico sconosciuti in utenti tipo distinti. Audience Manager ottiene questo risultato calcolando la propensione del pubblico sconosciuto per un set di tipi di pubblico noti.

Per ulteriori informazioni su [!UICONTROL Predictive Audiences], consulta [Panoramica delle audience predittive](predictive-audiences.md).
