---
description: Questo articolo descrive gli operatori di confronto utilizzati dal Generatore di caratteristiche.
seo-description: Questo articolo descrive gli operatori di confronto utilizzati dal Generatore di caratteristiche.
seo-title: Utilizzo degli operatori di confronto nel Generatore di caratteristiche
solution: Audience Manager
title: Utilizzo degli operatori di confronto nel Generatore di caratteristiche
uuid: 41 bec 3 b 3-e 5 df -4 a 6 f-abb 0-80 ce 4 c 75 f 5 e 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## Scopo degli operatori di confronto

<!-- c_tb_comparison_operators.xml -->

Operatori di confronto (o operatori relazionali) vengono utilizzati per confrontare, verificare o valutare la relazione tra valori diversi. In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. Ad esempio, potete creare una regola di segnale per definire un pubblico per acquirenti da fotocamera costosi. In questo caso, è possibile creare una coppia di valori chiave/prezzo e qualificare un utente se ha cercato una videocamera con un prezzo pari o superiore a un importo impostato.

## Vantaggi degli operatori di confronto

Gli operatori di confronto sono utili quando è necessario valutare e creare caratteristiche basate su più valori. L'aspetto dei prezzi su beni e servizi può illustrare questa condizione. Ad esempio, la tua attività potrebbe voler identificare i visitatori in base ai prezzi dei prodotti visualizzati. Tuttavia, può essere amministrativamente inefficiente per definire singoli segmenti basati su valori specifici. Gli operatori di confronto contribuiscono a superare questo ostacolo stabilendo attivatori di segmentazione basati su soglie di prezzo o intervalli.

## Operatori di confronto

Puoi creare regole con i seguenti operatori di confronto:

| Operatore | Definizione |
|---|---|
| **==** | Uguale a |
| **!=** | Non uguale a |
| **&gt;** | Maggiore di |
| **&lt;** | Minore di |
| **=&gt;** | Maggiore di/uguale a |
| **&lt;=** | Minore di/uguale a |

## Operatori denominati

Potete creare regole con i seguenti operatori denominati:

| Operatore | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Matcheswords]** | The value in a key-value pair *matches* the pattern specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |
| **[!UICONTROL Matchesregex]** | The value in a key-value pair *matches* the pattern specified by a regular expression. [Scopri come](../../features/traits/trait-builder-regex.md) usare espressioni regolari in [!UICONTROL Trait Builder]. |

>[!MORE_ LIKE_ THIS]
>
>* [Espressioni booleane in Caratteristiche e Generatore segmenti](../../reference/boolean-expressions-tsb.md)
>* [Informazioni sulle espressioni booleane in traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Ordine delle operazioni nelle espressioni traitbuilder](../../features/traits/trait-operator-precedence.md)
>* [Espressioni di esempio con operatori booleani e di confronto](../../features/traits/trait-expression-samples.md)

