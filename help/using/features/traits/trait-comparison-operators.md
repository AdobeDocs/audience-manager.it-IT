---
description: Questo articolo descrive gli operatori di confronto utilizzati dal Generatore di caratteristiche.
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: Utilizzo degli operatori di confronto nel Generatore di caratteristiche
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 5%

---

# Utilizzo degli operatori di confronto nel Generatore di caratteristiche {#working-with-comparison-operators-in-trait-builder}

Questo articolo descrive gli operatori di confronto utilizzati da [!UICONTROL Trait Builder].

## Scopo degli operatori di confronto

<!-- c_tb_comparison_operators.xml -->

Gli operatori di confronto (o operatori relazionali) vengono utilizzati per confrontare, testare o valutare la relazione tra valori diversi. In [!UICONTROL Trait Builder], quando si creano le regole del segnale, gli operatori di confronto consentono di verificare la relazione tra coppie chiave-valore diverse. Ad esempio, si potrebbe creare una regola del segnale per definire un pubblico per i costosi acquirenti di telecamere. In questo caso, è possibile creare una coppia fotocamera/prezzo-valore chiave e qualificare un utente se ha cercato una fotocamera con un prezzo uguale o superiore a una quantità impostata.

## Vantaggi degli operatori di confronto

Gli operatori di confronto sono utili quando devi valutare e creare caratteristiche basate su più valori. Esaminare i prezzi di beni e servizi può illustrare questa condizione. Ad esempio, la tua azienda potrebbe voler identificare i visitatori in base ai prezzi dei prodotti che visualizzano. Tuttavia, definire singoli segmenti in base a valori specifici può risultare non efficiente dal punto di vista amministrativo. Gli operatori di confronto aiutano a superare questo ostacolo stabilendo trigger di segmentazione basati su soglie o intervalli di prezzi.

## Operatori di confronto

Puoi creare regole con i seguenti operatori di confronto:

| Operatore | Definizione |
|---|---|
| **==** | Uguale |
| **!=** | Diverso da |
| **>** | Maggiore di |
| **&lt;** | Minore di |
| **=>** | Maggiore/uguale a |
| **&lt;=** | Minore di/uguale a |

## Operatori denominati

Puoi creare regole con i seguenti operatori denominati:

| Operatore | Valuta fino a [!DNL True] quando |
|---|---|
| **[!UICONTROL Contains]** | Il valore in una coppia chiave-valore *contiene* caratteri specificati da questo operatore. |
| **[!UICONTROL Matcheswords]** | Il valore in una coppia chiave-valore *corrisponde* al pattern specificato da questo operatore. |
| **[!UICONTROL Startswith]** | Il valore in una coppia chiave-valore *inizia con* caratteri specificati da questo operatore. |
| **[!UICONTROL Endswith]** | Il valore in una coppia chiave-valore *termina con* i caratteri specificati da questo operatore. |
| **[!UICONTROL Matchesregex]** | Il valore in una coppia chiave-valore *corrisponde* al pattern specificato da un&#39;espressione regolare. [Ulteriori informazioni](../../features/traits/trait-builder-regex.md) sull&#39;utilizzo delle espressioni regolari in [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Espressioni booleane nel Generatore di caratteristiche e segmenti](../../reference/boolean-expressions-tsb.md)
>* [Informazioni sulle espressioni booleane in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Ordine delle operazioni nelle espressioni TraitBuilder](../../features/traits/trait-operator-precedence.md)
>* [Espressioni di esempio con operatori booleani e di confronto](../../features/traits/trait-expression-samples.md)
