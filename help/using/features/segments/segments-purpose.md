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
ht-degree: 0%

---


# Segmenti: Finalità, composizione e regole {#segments-purpose-composition-and-rules}

Descrive [!UICONTROL segments]le parti che li compongono e la creazione di regole con [!UICONTROL Segment Builder].

## Finalità [!UICONTROL Segments]

Un *`segment`* (o *`audience`*) è un insieme di utenti che condividono attributi comuni. In  Audience Manager, potete creare [!UICONTROL segments] con regole sul lato server. Queste regole consentono di creare gruppi di audience in base agli attributi del visitatore del sito, come:

* Comportamento;
* Demografia (età, genere, reddito, ecc.);
* Altre caratteristiche definite nell’interfaccia utente.

## [!UICONTROL Segment] Composizione

Un Audience Manager  [!UICONTROL segment] è una regola lato server che consiste di singoli o gruppi di caratteristiche. Le caratteristiche sono composte da elementi di dati denominati coppie chiave-valore. Insieme alle regole impostate a [!UICONTROL segment] livello, queste coppie chiave-valore contengono i criteri che qualificano i visitatori per le caratteristiche e [!UICONTROL segment] l&#39;appartenenza.

## Considerazioni sulla [!UICONTROL Adobe Analytics][!UICONTROL Segment] mappatura

Quando mappate Adobe  Analytics [!UICONTROL segments] o suite di rapporti sulla vostra organizzazione Experience Cloud ,  Audience Manager crea automaticamente nuove caratteristiche [!UICONTROL segments] e caratteristiche corrispondenti e di sola lettura. Non è possibile modificare o modificare il percorso di memorizzazione di questi [!UICONTROL segments] da  Audience Manager. Tuttavia, qualsiasi modifica eseguita su Adobe  Analytics o suite di rapporti mappate viene visualizzata in  Audience Manager. [!UICONTROL segments]

>[!TIP]
>
> Audience Manager [!UICONTROL segments] è diverso da [!DNL Adobe Analytics] [!UICONTROL segments]. Leggi [Comprensione dei segmenti in  Analytics e  Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) per una descrizione dettagliata delle differenze.

## Crea regole [!UICONTROL Segments] con [!UICONTROL Segment Builder]

A differenza dei pixel tradizionali attivati in risposta a semplici condizioni sì/no, [!UICONTROL Segment Builder] potete creare [!UICONTROL segment] requisiti complessi. Come [!UICONTROL traits], [!UICONTROL segments] valuta i dati utilizzando [!DNL Boolean] espressioni ([!DNL AND], [!DNL OR], [!DNL NOT]), operatori di confronto (maggiore di, minore, uguale a, ecc.) e criteri di recency/frequenza. Queste funzioni aiutano a creare un pubblico mirato [!UICONTROL segments] in base alle esigenze aziendali.

## Vantaggi

[!UICONTROL Segments] ottimizza i processi standard di creazione/segmentazione dei tipi di pubblico basati su pixel, in quanto consentono di:

* Crea caratteristiche pertinenti e utili [!UICONTROL segments] con caratteristiche di prime e terze parti.
* Create regole di segmentazione sofisticate e complesse con operatori booleani, espressioni di confronto e criteri di recency/frequenza.
* Invia [!UICONTROL segment] dati a un partner di destinazione.
* Monitorare le prestazioni con  report Audience Manager.

>[!MORELIKETHIS]
>
>* [Segnali, caratteristiche e segmenti](../../reference/signal-trait-segment.md)

