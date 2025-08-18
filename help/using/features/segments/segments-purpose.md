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
source-wordcount: '303'
ht-degree: 1%

---

# Segmenti: finalità, composizione e regole {#segments-purpose-composition-and-rules}

Descrive [!UICONTROL segments], le relative parti costitutive e la creazione di regole con [!UICONTROL Segment Builder].

## Scopo di [!UICONTROL Segments]

Un *`segment`* (o un *`audience`*) è un insieme di utenti che condividono attributi comuni. In Audience Manager, puoi creare [!UICONTROL segments] con regole lato server. Queste regole ti consentono di creare gruppi di pubblico in base agli attributi dei visitatori del sito, ad esempio:

* Comportamento
* Caratteristiche demografiche (età, genere, reddito, ecc.);
* Altre caratteristiche definibili nell’interfaccia utente.

## Composizione [!UICONTROL Segment]

Un Audience Manager [!UICONTROL segment] è una regola lato server costituita da singoli o gruppi di caratteristiche. Le caratteristiche sono composte da elementi di dati denominati coppie chiave-valore. Oltre alle regole impostate al livello [!UICONTROL segment], queste coppie chiave-valore contengono i criteri che qualificano i visitatori per la caratteristica e l&#39;iscrizione a [!UICONTROL segment].

## Considerazioni sulla mappatura di [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Quando si mappano le suite di rapporti o Adobe Analytics [!UICONTROL segments] nell&#39;organizzazione Experience Cloud, Audience Manager crea automaticamente [!UICONTROL segments] e caratteristiche nuovi, corrispondenti, di sola lettura. Impossibile modificare o cambiare il percorso di archiviazione di questi [!UICONTROL segments] da Audience Manager. Tuttavia, qualsiasi modifica eseguita sull&#39;Adobe Analytics [!UICONTROL segments] o sulle suite di rapporti mappate si riflette in Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] sono diversi da [!DNL Adobe Analytics] [!UICONTROL segments]. Leggi [Informazioni sui segmenti in Analytics e Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=it) per una descrizione dettagliata delle differenze.

## Crea [!UICONTROL Segments] basato su regole con [!UICONTROL Segment Builder]

A differenza dei pixel tradizionali che si attivano in risposta a condizioni semplici di sì/no, [!UICONTROL Segment Builder] consente di creare requisiti complessi di [!UICONTROL segment]. Come [!UICONTROL traits], [!UICONTROL segments] valuta i dati utilizzando [!DNL Boolean] espressioni ([!DNL AND], [!DNL OR], [!DNL NOT]), operatori di confronto (maggiore di, minore di, uguale a, ecc.) e criteri di recency/frequenza. Queste funzionalità consentono di creare un pubblico mirato [!UICONTROL segments] in base alle esigenze aziendali.

## Vantaggi

[!UICONTROL Segments] migliora i processi standard di creazione/segmentazione del pubblico basati su pixel perché ti consentono di:

* Genera [!UICONTROL segments] pertinenti e utili con caratteristiche di prima e terze parti.
* Crea regole di segmentazione complesse e sofisticate con operatori booleani, espressioni di confronto e criteri di recency/frequenza.
* Invia dati [!UICONTROL segment] a un partner di destinazione.
* Monitora le prestazioni con i rapporti di Audience Manager.

>[!MORELIKETHIS]
>
>* [Segnali, caratteristiche e segmenti](../../reference/signal-trait-segment.md)
