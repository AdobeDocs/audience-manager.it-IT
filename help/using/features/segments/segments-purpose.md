---
description: Descrive i segmenti, le loro parti costitutive e la creazione di regole con Segment Builder.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Scopo, composizione e regole dei segmenti
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 3%

---

# Segmenti: finalità, composizione e regole {#segments-purpose-composition-and-rules}

Descrive [!UICONTROL segments], le loro parti costitutive e la creazione di regole con [!UICONTROL Segment Builder].

## Scopo di [!UICONTROL Segments]

A *`segment`* (o un *`audience`*) è un insieme di utenti che condividono attributi comuni. Ad Audience Manager, puoi creare [!UICONTROL segments] con regole lato server. Queste regole ti consentono di creare gruppi di pubblico in base agli attributi dei visitatori del sito, ad esempio:

* Comportamento;
* Caratteristiche demografiche (età, genere, reddito, ecc.);
* Altre caratteristiche definibili nell’interfaccia utente.

## [!UICONTROL Segment] Composizione

Un Audience Manager [!UICONTROL segment] è una regola lato server costituita da singoli o gruppi di caratteristiche. Le caratteristiche sono composte da elementi di dati denominati coppie chiave-valore. Insieme alle regole impostate in [!UICONTROL segment] livello, queste coppie chiave-valore contengono i criteri che qualificano i visitatori per le caratteristiche e [!UICONTROL segment] iscrizione.

## Considerazioni su [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Mappatura

Durante la mappatura di Adobe Analytics [!UICONTROL segments] o suite di rapporti per l’organizzazione Experience Cloud, Audience Manager crea automaticamente nuove suite di rapporti di sola lettura corrispondenti [!UICONTROL segments] e caratteristiche. Non è possibile modificare o modificare il percorso di archiviazione di questi [!UICONTROL segments] dall&#39;Audience Manager. Tuttavia, qualsiasi modifica eseguita sull’Adobe Analytics mappato [!UICONTROL segments] o nelle suite di rapporti si riflette in Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] sono diversi da [!DNL Adobe Analytics] [!UICONTROL segments]. Letto [Segmenti in Analytics e Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) per una descrizione dettagliata delle differenze.

## Crea basato su regole [!UICONTROL Segments] Con [!UICONTROL Segment Builder]

A differenza dei pixel tradizionali che si attivano in risposta a semplici condizioni sì/no, [!UICONTROL Segment Builder] consente di creare elementi complessi [!UICONTROL segment] requisiti. Mi piace [!UICONTROL traits], [!UICONTROL segments] valutare i dati tramite [!DNL Boolean] espressioni ([!DNL AND], [!DNL OR], [!DNL NOT]), operatori di confronto (maggiore di, minore di, uguale a, ecc.) e criteri di recency/frequenza. Queste funzioni aiutano a creare un pubblico mirato [!UICONTROL segments] in base alle esigenze aziendali.

## Vantaggi

[!UICONTROL Segments] migliora i processi standard di creazione/segmentazione del pubblico basati su pixel perché ti consentono di:

* Genera informazioni utili e pertinenti [!UICONTROL segments] con caratteristiche di prima parte e terze parti.
* Crea regole di segmentazione complesse e sofisticate con operatori booleani, espressioni di confronto e criteri di recency/frequenza.
* Invia [!UICONTROL segment] dati a un partner di destinazione.
* Monitora le prestazioni con i rapporti Audience Manager.

>[!MORELIKETHIS]
>
>* [Segnali, caratteristiche e segmenti](../../reference/signal-trait-segment.md)

