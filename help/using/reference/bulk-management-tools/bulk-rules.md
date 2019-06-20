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


# Creare o aggiornare regole di caratteristica e segmenti{#create-or-update-trait-rules-and-segment-rules}

I fogli di lavoro di creazione e aggiornamento accettano un&#39;intestazione traitrule che consente di applicare più regole in una singola operazione. Seguite queste istruzioni per effettuare richieste di regole in massa.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>Non [!UICONTROL Bulk Management Tools]*sono* supportati da [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. Per modifiche in massa, consigliamo di lavorare con [le API](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell&#39; [!DNL Audience Manager] interfaccia utente vengono rispettate nell&#39; [!UICONTROL Bulk Management Tools]interfaccia.

## Utilizzo delle regole delle caratteristiche {#trait-rules}

Nel vostro foglio di lavoro, la colonna regola caratteristica restituisce e accetta regole che consistono di espressioni booleane, operatori di confronto e espressioni regolari. Puoi creare regole con caratteristiche o segmenti in e [!DNL Audience Manager] copiarle nel tuo foglio di lavoro. Oppure, se avete familiarità con la sintassi delle regole, potete scrivere espressioni direttamente nei fogli di lavoro.

## Esempio di generatore di regole {#rule-builder-example}

Diamo un&#39;occhiata a un esempio che mostra come utilizzare [!UICONTROL Segment Builder] la regola per creare una regola nel foglio di lavoro in massa. Tuttavia, non si tratta di un insieme di istruzioni dettagliate per questi strumenti. Iniziamo con una regola semplice già creata. Per istruzioni su come usare i costruttori di regole, consulta Generatore [di segmenti](../../features/segments/segment-builder.md) e Generatore [di caratteristiche](../../features/traits/about-trait-builder.md).

Con il generatore di regole visivo, abbiamo creato una regola di segmento con 3 caratteristiche e un [!UICONTROL AND] operatore booleano.

![](assets/visualrule.png)

Fate clic su **[!UICONTROL Code View]** per ottenere la versione di testo di questa regola.

>[!TIP]
>
>Fate clic per **[!UICONTROL Validate Expression]** controllare la logica della regola. In questo modo non potrete caricare una regola non valida.

![](assets/coderule.png)

Incolla la regola nel [!UICONTROL Bulk Management Tools] foglio di lavoro e conferma le modifiche per aggiornare le regole dei segmenti in gruppo.

![](assets/segmentrule.png)

## Creazione di regole personalizzate {#create-rules}

Potete scrivere le vostre regole esterne [!UICONTROL Rule Builder]. Prima di iniziare, leggi la documentazione che copre elementi quali operatori, espressioni e variabili richieste. È consigliabile esaminare quanto segue:

* [Utilizzo degli operatori di confronto nel generatore di caratteristiche](../../features/traits/trait-comparison-operators.md)
* [Ordine delle operazioni](../../features/traits/trait-operator-precedence.md)
* [Requisiti di prefisso per variabili chiave](../../features/traits/trait-variable-prefixes.md)
* [Espressioni di esempio con operatori booleani e di confronto](../../features/traits/trait-expression-samples.md)

