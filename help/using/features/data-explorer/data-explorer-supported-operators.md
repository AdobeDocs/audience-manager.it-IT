---
description: Utilizza gli operatori logici per raggruppare coppie chiave-valore e caratteristiche di retrocompilazione.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: Operatori logici supportati
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%

---

# Operatori logici supportati {#supported-logical-operators}

Utilizza gli operatori logici per raggruppare coppie chiave-valore e caratteristiche di retrocompilazione.

## Operatori supportati per la ricerca del segnale {#supported-operators-search}

Utilizza i seguenti operatori logici supportati per cercare coppie chiave-valore:

### Operatori di confronto

| Operatore | Definizione |
|---|---|
| **==** | Uguale |
| **>** | Maggiore di |
| **&lt;** | Minore di |
| **=>** | Maggiore/uguale a |
| **&lt;=** | Minore di/uguale a |

### Operatori denominati

| Operatore | Valuta fino a [!DNL True] quando |
|---|---|
| **[!UICONTROL Contains]** | Il valore in una coppia chiave-valore *contiene* caratteri specificati da questo operatore. |
| **[!UICONTROL Startswith]** | Il valore in una coppia chiave-valore *inizia con* caratteri specificati da questo operatore. |
| **[!UICONTROL Endswith]** | Il valore in una coppia chiave-valore *termina con* i caratteri specificati da questo operatore. |

## Operatori supportati per il backfill e la stima delle caratteristiche {#supported-operators-backfilling}

È possibile retrocompilare caratteristiche che includono espressioni contenenti uno qualsiasi degli operatori supportati da [!UICONTROL Signal Search]. Oltre a questi operatori, la retrocompilazione e la stima delle caratteristiche supportano anche gli operatori logici [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL AND NOT], utilizzati per combinare coppie chiave-valore all&#39;interno delle espressioni delle caratteristiche precompilate.
