---
description: Questo articolo descrive gli operatori di confronto utilizzati da Trait Builder.
seo-description: Questo articolo descrive gli operatori di confronto utilizzati da Trait Builder.
seo-title: Utilizzo degli operatori di confronto in Generatore di caratteristiche
solution: Audience Manager
title: Utilizzo degli operatori di confronto in Generatore di caratteristiche
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Utilizzo degli operatori di confronto in Generatore di caratteristiche {#working-with-comparison-operators-in-trait-builder}

Questo articolo descrive gli operatori di confronto utilizzati da [!UICONTROL Trait Builder].

## Scopo degli operatori di confronto

<!-- c_tb_comparison_operators.xml -->

Gli operatori di confronto (o operatori relazionali) vengono utilizzati per confrontare, verificare o valutare la relazione tra valori diversi. In [!UICONTROL Trait Builder]questo caso, quando si creano le regole del segnale, gli operatori di confronto consentono di verificare la relazione tra diverse coppie chiave-valore. Ad esempio, potete creare una regola del segnale per definire un pubblico per i costosi clienti della telecamera. In questo caso, è possibile creare una coppia telecamera/prezzo chiave-valore e qualificare un utente se ha cercato una fotocamera con un prezzo uguale o superiore a una quantità impostata.

## Vantaggi degli operatori di confronto

Gli operatori di confronto sono utili per valutare e creare caratteristiche basate su più valori. La valutazione dei prezzi dei beni e dei servizi può illustrare tale condizione. Ad esempio, l'azienda potrebbe voler identificare i visitatori in base ai prezzi dei prodotti visualizzati. Tuttavia, può risultare inefficiente dal punto di vista amministrativo definire singoli segmenti in base a valori specifici. Gli operatori di confronto contribuiscono a superare questo ostacolo stabilendo attivatori di segmentazione in base a soglie o intervalli di prezzo.

## Operatori di confronto

È possibile creare regole con i seguenti operatori di confronto:

| Operatore | Definizione |
|---|---|
| **==** | Uguale a |
| **!=** | Non uguale a |
| **&gt;** | Maggiore di |
| **&lt;** | Minore di |
| **=&gt;** | Maggiore di/uguale a |
| **&lt;=** | Minore di/uguale a |

## Operatori denominati

È possibile creare regole con i seguenti operatori denominati:

| Operatore | Valuta in [!DNL True] Quando |
|---|---|
| **[!UICONTROL Contains]** | Il valore in una coppia chiave-valore *contiene* i caratteri specificati da questo operatore. |
| **[!UICONTROL Matcheswords]** | Il valore di una coppia chiave-valore *corrisponde* al pattern specificato dall'operatore. |
| **[!UICONTROL Startswith]** | Il valore in una coppia chiave-valore *inizia con* i caratteri specificati da questo operatore. |
| **[!UICONTROL Endswith]** | Il valore in una coppia chiave-valore *termina con* i caratteri specificati da questo operatore. |
| **[!UICONTROL Matchesregex]** | Il valore in una coppia chiave-valore *corrisponde* al pattern specificato da un'espressione regolare. [Ulteriori](../../features/traits/trait-builder-regex.md) informazioni sull'utilizzo delle espressioni regolari in [!UICONTROL Trait Builder]. |

>[!MORE_LIKE_this]
>
>* [Espressioni booleane in Generatore di caratteristiche e segmenti](../../reference/boolean-expressions-tsb.md)
>* [Informazioni sulle espressioni booleane in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Ordine delle operazioni nelle espressioni TraitBuilder](../../features/traits/trait-operator-precedence.md)
>* [Espressioni di esempio con operatori booleani e di confronto](../../features/traits/trait-expression-samples.md)

