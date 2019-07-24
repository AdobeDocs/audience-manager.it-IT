---
description: Utilizzate operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.
seo-description: Utilizzate operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.
seo-title: Operatori logici supportati
title: Operatori logici supportati
uuid: 645 fcb 6 f -50 ac -49 bc -8 df 9-c 699 c 749 cf 8 f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Supported Logical Operators {#supported-logical-operators}

Utilizzate operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.

## Supported Operators for Signal Search {#supported-operators-search}

Usate i seguenti operatori logici supportati per cercare coppie chiave-valore:

### Operatori di confronto

| Operatore | Definizione |
|---|---|
| **==** | Uguale a |
| **&gt;** | Maggiore di |
| **&lt;** | Minore di |
| **=&gt;** | Maggiore di/uguale a |
| **&lt;=** | Minore di/uguale a |

### Operatori denominati

| Operatore | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |

## Supported Operators for Trait Backfilling and Estimation {#supported-operators-backfilling}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.