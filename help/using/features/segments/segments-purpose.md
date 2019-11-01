---
description: Descrive i segmenti, le loro parti costitutive e la creazione di regole con Segment Builder (Generatore di segmenti).
seo-description: Descrive i segmenti, le loro parti costitutive e la creazione di regole con Segment Builder (Generatore di segmenti).
seo-title: Finalità, composizione e regole dei segmenti
solution: Audience Manager
title: Finalità, composizione e regole dei segmenti
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Segmenti: Finalità, composizione e regole {#segments-purpose-composition-and-rules}

Descrive i segmenti, le relative parti costitutive e la creazione di regole con [!UICONTROL Segment Builder].

## Scopo dei segmenti

Un *`segment`* (o *`audience`*) è un insieme di utenti che condividono attributi comuni. In Audience Manager, puoi creare segmenti con regole lato server. Queste regole consentono di creare gruppi di audience in base agli attributi del visitatore del sito, come:

* Comportamento;
* Demografia (età, genere, reddito, ecc.);
* Altre caratteristiche definite nell’interfaccia utente.

## Composizione segmento

Un segmento di Audience Manager è una regola lato server che consiste di singole caratteristiche o gruppi di caratteristiche. Le caratteristiche sono composte da elementi di dati denominati coppie chiave-valore. Insieme alle regole impostate a livello di segmento, queste coppie chiave-valore contengono i criteri che qualificano i visitatori per la caratteristica e l'appartenenza al segmento.

## Considerazioni sulla mappatura dei segmenti di Adobe Analytics

Quando mappate segmenti o suite di rapporti di Adobe Analytics alla vostra organizzazione Experience Cloud, Audience Manager crea automaticamente nuovi segmenti e caratteristiche di sola lettura corrispondenti. Non puoi modificare o modificare la posizione di archiviazione di questi segmenti da Audience Manager. Tuttavia, qualsiasi modifica eseguita sui segmenti Adobe Analytics o sulle suite di rapporti mappati viene visualizzata in Audience Manager.

>[!TIP]
>
>I segmenti di Audience Manager sono diversi dai [!DNL Adobe Analytics] segmenti. Leggi [Informazioni sui segmenti in Analytics e Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) per una descrizione dettagliata delle differenze.

## Creazione di segmenti basati su regole con Segment Builder

A differenza dei pixel tradizionali attivati in risposta a semplici condizioni sì/no, Generatore di segmenti consente di creare requisiti di segmento complessi. Caratteristiche simili, i segmenti valutano i dati utilizzando [!DNL Boolean] espressioni ([!DNL AND], [!DNL OR], [!DNL NOT]), operatori di confronto (maggiore di, minore, uguale a, ecc.) e criteri di recency/frequenza. Queste funzioni aiutano a creare segmenti di pubblico mirati in base alle esigenze aziendali.

## Vantaggi

I segmenti migliorano i processi standard di creazione/segmentazione dell'audience basati su pixel, perché consentono di:

* Crea segmenti utili e pertinenti con caratteristiche di prime e terze parti.
* Create regole di segmentazione sofisticate e complesse con operatori booleani, espressioni di confronto e criteri di aggiornamento/frequenza.
* Invia i dati del segmento a un partner di destinazione.
* Monitorate le prestazioni con i rapporti di Audience Manager.

>[!MORELIKETHIS]
>
>* [Segnali, caratteristiche e segmenti](../../reference/signal-trait-segment.md)

