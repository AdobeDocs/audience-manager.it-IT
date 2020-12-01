---
description: Descrive i segmenti, le loro parti costitutive e la creazione di regole con Segment Builder (Generatore di segmenti).
seo-description: Descrive i segmenti, le loro parti costitutive e la creazione di regole con Segment Builder (Generatore di segmenti).
seo-title: Finalità, composizione e regole dei segmenti
solution: Audience Manager
title: Finalità, composizione e regole dei segmenti
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# Segmenti: finalità, composizione e regole {#segments-purpose-composition-and-rules}

Descrive [!UICONTROL segments], le relative parti costitutive e la creazione di regole con [!UICONTROL Segment Builder].

## Finalità di [!UICONTROL Segments]

Un *`segment`* (o un *`audience`*) è un insieme di utenti che condividono attributi comuni. In  Audience Manager, si crea [!UICONTROL segments] con regole lato server. Queste regole consentono di creare gruppi di audience in base agli attributi del visitatore del sito, come:

* Comportamento;
* Demografia (età, genere, reddito, ecc.);
* Altre caratteristiche definite nell’interfaccia utente.

## [!UICONTROL Segment] Composizione

Un Audience Manager  [!UICONTROL segment] è una regola lato server che consiste di singoli o gruppi di caratteristiche. Le caratteristiche sono composte da elementi di dati denominati coppie chiave-valore. Insieme alle regole impostate a livello [!UICONTROL segment], queste coppie chiave-valore contengono i criteri che qualificano i visitatori per le caratteristiche e l&#39;appartenenza a [!UICONTROL segment].

## Considerazioni sulla mappatura [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Quando si esegue la mappatura  suite di rapporti Adobe Analytics [!UICONTROL segments] nell&#39;organizzazione del Experience Cloud ,  Audience Manager crea automaticamente caratteristiche e caratteristiche nuove, corrispondenti e di sola lettura. [!UICONTROL segments] Non è possibile modificare o modificare il percorso di memorizzazione di questi [!UICONTROL segments] dal Audience Manager . Tuttavia, qualsiasi modifica eseguita sulle  Adobe Analytics [!UICONTROL segments] o sulle suite di rapporti mappate viene visualizzata in  Audience Manager.

>[!TIP]
>
> Audience Manager [!UICONTROL segments] è diverso da [!DNL Adobe Analytics] [!UICONTROL segments]. Leggi [I segmenti in Analytics e  Audience Manager](https://docs.adobe.com/content/help/it-IT/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) per una descrizione dettagliata delle differenze.

## Crea regole basate su [!UICONTROL Segments] con [!UICONTROL Segment Builder]

A differenza dei pixel tradizionali attivati in risposta a semplici condizioni sì/no, [!UICONTROL Segment Builder] consente di creare requisiti [!UICONTROL segment] complessi. Come [!UICONTROL traits], [!UICONTROL segments] valutare i dati utilizzando espressioni [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]), operatori di confronto (maggiore di, minore, uguale a, ecc.) e criteri di aggiornamento/frequenza. Queste funzioni aiutano a creare audience mirate [!UICONTROL segments] in base alle esigenze aziendali.

## Vantaggi

[!UICONTROL Segments] ottimizza i processi standard di creazione/segmentazione dei tipi di pubblico basati su pixel, in quanto consentono di:

* Create elementi [!UICONTROL segments] pertinenti e utili con caratteristiche di prime e terze parti.
* Create regole di segmentazione sofisticate e complesse con operatori booleani, espressioni di confronto e criteri di recency/frequenza.
* Inviare [!UICONTROL segment] dati a un partner di destinazione.
* Monitorare le prestazioni con  report di Audience Manager.

>[!MORELIKETHIS]
>
>* [Segnali, caratteristiche e segmenti](../../reference/signal-trait-segment.md)

