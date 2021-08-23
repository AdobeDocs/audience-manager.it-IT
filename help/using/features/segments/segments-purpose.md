---
description: Descrive i segmenti, le loro parti costitutive e la creazione di regole con il Generatore di segmenti.
seo-description: Descrive i segmenti, le loro parti costitutive e la creazione di regole con il Generatore di segmenti.
seo-title: Finalità, composizione e regole dei segmenti
solution: Audience Manager
title: Finalità, composizione e regole dei segmenti
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 'Segmenti '
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Segmenti: finalità, composizione e regole {#segments-purpose-composition-and-rules}

Descrive [!UICONTROL segments], le relative parti costituenti e la creazione di regole con [!UICONTROL Segment Builder].

## Scopo di [!UICONTROL Segments]

Un *`segment`* (o un *`audience`*) è un insieme di utenti che condividono attributi comuni. Ad Audience Manager, puoi creare [!UICONTROL segments] con regole lato server. Queste regole consentono di creare gruppi di pubblico in base agli attributi dei visitatori del sito, ad esempio:

* Comportamento;
* Dati demografici (età, genere, reddito, ecc.);
* Altre caratteristiche definite nell’interfaccia utente.

## [!UICONTROL Segment] Composizione

Un Audience Manager [!UICONTROL segment] è una regola lato server costituita da singoli o gruppi di caratteristiche. Le caratteristiche sono composte da elementi dati chiamati coppie chiave-valore. Oltre alle regole impostate a livello di [!UICONTROL segment], queste coppie chiave-valore contengono i criteri che qualificano i visitatori per le caratteristiche e l&#39;appartenenza a [!UICONTROL segment].

## Considerazioni sulla mappatura [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Quando si mappano le suite di rapporti Adobe Analytics [!UICONTROL segments] o le suite di rapporti nell’organizzazione Experience Cloud, in Audience Manager vengono create automaticamente nuove caratteristiche [!UICONTROL segments] e di sola lettura corrispondenti. Non è possibile modificare o modificare il percorso di archiviazione di questi [!UICONTROL segments] dall&#39;Audience Manager. Tuttavia, qualsiasi modifica apportata alle suite di rapporti o Adobe Analytics mappate [!UICONTROL segments] viene riportata in Audience Manager.

>[!TIP]
>
>Gli Audienci Manager [!UICONTROL segments] sono diversi da [!DNL Adobe Analytics] [!UICONTROL segments]. Per una descrizione dettagliata delle differenze, leggi [Informazioni sui segmenti in Analytics e Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) .

## Crea regole basate su [!UICONTROL Segments] con [!UICONTROL Segment Builder]

A differenza dei pixel tradizionali che si attivano in risposta a semplici condizioni sì/no, [!UICONTROL Segment Builder] consente di creare requisiti [!UICONTROL segment] complessi. Come [!UICONTROL traits], [!UICONTROL segments] valuta i dati utilizzando le espressioni [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]), gli operatori di confronto (maggiore di, minore, uguale a, ecc.) e i criteri di aggiornamento/frequenza. Queste funzioni consentono di creare un pubblico mirato [!UICONTROL segments] in base alle esigenze aziendali.

## Vantaggi

[!UICONTROL Segments] migliora i processi standard di creazione/segmentazione del pubblico basati su pixel, perché consentono di:

* Crea caratteristiche pertinenti e utili [!UICONTROL segments] con caratteristiche di prima e terze parti.
* Crea regole di segmentazione sofisticate e complesse con operatori booleani, espressioni di confronto e criteri di recency/frequenza.
* Invia dati [!UICONTROL segment] a un partner di destinazione.
* Monitora le prestazioni con i report di Audience Manager.

>[!MORELIKETHIS]
>
>* [Segnali, caratteristiche e segmenti](../../reference/signal-trait-segment.md)

