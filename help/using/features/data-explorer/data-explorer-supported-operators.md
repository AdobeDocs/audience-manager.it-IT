---
description: Utilizzate operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.
seo-description: Utilizzate operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.
seo-title: Operatori logici supportati
title: Operatori logici supportati
uuid: 645 fcb 6 f -50 ac -49 bc -8 df 9-c 699 c 749 cf 8 f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Operatori logici supportati {#supported-logical-operators}

Utilizzate operatori logici per raggruppare coppie chiave-valore e caratteristiche di backfill.

## Operatori supportati per la ricerca del segnale {#supported-operators-search}

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

| Operatore | Restituisce [!DNL True] quando |
|---|---|
| **[!UICONTROL Contains]** | Il valore in una coppia chiave-valore *contiene* caratteri specificati da questo operatore. |
| **[!UICONTROL Startswith]** | Il valore in una coppia chiave-valore *inizia con* caratteri specificati da questo operatore. |
| **[!UICONTROL Endswith]** | Il valore in una coppia chiave-valore *termina con* i caratteri specificati dall&#39;operatore. |

## Operatori supportati per Backfill e stima delle caratteristiche {#supported-operators-backfilling}

Potete riempire le caratteristiche contenenti espressioni contenenti qualsiasi degli operatori supportati da [!UICONTROL Signal Search]. Oltre a tali operatori, la funzione di backfill e la stima delle caratteristiche supportano anche gli operatori logici [!UICONTROL AND], [!UICONTROL OR][!UICONTROL AND NOT] utilizzati per combinare coppie chiave-valore nelle espressioni di caratteristica backriempita.