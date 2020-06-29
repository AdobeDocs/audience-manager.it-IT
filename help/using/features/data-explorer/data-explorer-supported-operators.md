---
description: Utilizzare operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.
seo-description: Utilizzare operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.
seo-title: Operatori logici supportati
title: Operatori logici supportati
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 1%

---


# Operatori logici supportati {#supported-logical-operators}

Utilizzare operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.

## Operatori supportati per la ricerca del segnale {#supported-operators-search}

Utilizzate i seguenti operatori logici supportati per cercare coppie chiave-valore:

### Operatori di confronto

| Operatore | Definizione |
|---|---|
| **==** | Uguale a |
| **>** | Maggiore di |
| **&lt;** | Minore di |
| **=>** | Maggiore di/uguale a |
| **&lt;=** | Minore di/uguale a |

### Operatori denominati

| Operatore | Valuta in [!DNL True] Quando |
|---|---|
| **[!UICONTROL Contains]** | Il valore in una coppia chiave-valore *contiene* i caratteri specificati da questo operatore. |
| **[!UICONTROL Startswith]** | Il valore in una coppia chiave-valore *inizia con* i caratteri specificati da questo operatore. |
| **[!UICONTROL Endswith]** | Il valore in una coppia chiave-valore *termina con* i caratteri specificati da questo operatore. |

## Operatori supportati per il recupero e la stima delle caratteristiche {#supported-operators-backfilling}

Potete eseguire il backfill delle caratteristiche che includono espressioni contenenti uno degli operatori supportati da [!UICONTROL Signal Search]. Oltre a questi operatori, il backfill e la stima delle caratteristiche supportano anche gli operatori [!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL AND NOT] logici, utilizzati per combinare coppie chiave-valore all&#39;interno delle espressioni di caratteristica con backfill.