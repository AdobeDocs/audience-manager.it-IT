---
description: I fogli di lavoro di creazione e aggiornamento accettano un'intestazione traitrule che consente di applicare più regole in una singola operazione. Seguite queste istruzioni per effettuare richieste di regole in massa.
seo-description: I fogli di lavoro di creazione e aggiornamento accettano un'intestazione traitrule che consente di applicare più regole in una singola operazione. Seguite queste istruzioni per effettuare richieste di regole in massa.
seo-title: Creare o aggiornare regole di caratteristica e segmenti
solution: Audience Manager
title: Creare o aggiornare regole di caratteristica e segmenti
uuid: bdd 5 f 8 f 1-bb 83-4844-b 681-654 e 45 ace 3 e 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

I fogli di lavoro di creazione e aggiornamento accettano un'intestazione traitrule che consente di applicare più regole in una singola operazione. Seguite queste istruzioni per effettuare richieste di regole in massa.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

## Working with trait rules {#trait-rules}

Nel vostro foglio di lavoro, la colonna regola caratteristica restituisce e accetta regole che consistono di espressioni booleane, operatori di confronto e espressioni regolari. You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. Oppure, se avete familiarità con la sintassi delle regole, potete scrivere espressioni direttamente nei fogli di lavoro.

## Rule builder example {#rule-builder-example}

Let's take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. Tuttavia, non si tratta di un insieme di istruzioni dettagliate per questi strumenti. Iniziamo con una regola semplice già creata. For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md) and [Trait Builder](../../features/traits/about-trait-builder.md).

With the visual rule builder, we've created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule.

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. In questo modo non potrete caricare una regola non valida.

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. Prima di iniziare, leggi la documentazione che copre elementi quali operatori, espressioni e variabili richieste. È consigliabile esaminare quanto segue:

* [Utilizzo degli operatori di confronto nel generatore di caratteristiche](../../features/traits/trait-comparison-operators.md)
* [Ordine delle operazioni](../../features/traits/trait-operator-precedence.md)
* [Requisiti di prefisso per variabili chiave](../../features/traits/trait-variable-prefixes.md)
* [Espressioni di esempio con operatori booleani e di confronto](../../features/traits/trait-expression-samples.md)

