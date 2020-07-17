---
description: I fogli di lavoro per la creazione e l'aggiornamento accettano un'intestazione traitRule che consente di applicare più regole in un'unica operazione. Seguite queste istruzioni per eseguire richieste di regole in blocco.
seo-description: I fogli di lavoro per la creazione e l'aggiornamento accettano un'intestazione traitRule che consente di applicare più regole in un'unica operazione. Seguite queste istruzioni per eseguire richieste di regole in blocco.
seo-title: Creare o aggiornare regole di caratteristiche e di segmenti
solution: Audience Manager
title: Creare o aggiornare regole di caratteristiche e di segmenti
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 10%

---


# Creare o aggiornare regole di caratteristiche e di segmenti{#create-or-update-trait-rules-and-segment-rules}

I fogli di lavoro per la creazione e l&#39;aggiornamento accettano un&#39;intestazione traitRule che consente di applicare più regole in un&#39;unica operazione. Seguite queste istruzioni per eseguire richieste di regole in blocco.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

## Utilizzo delle regole sulle caratteristiche {#trait-rules}

Nel foglio di lavoro, la colonna regola caratteristica restituisce e accetta regole che consistono in espressioni booleane, operatori di confronto ed espressioni regolari. È possibile creare regole con il generatore di caratteristiche o segmenti [!DNL Audience Manager] e copiarle nel foglio di lavoro. Oppure, se avete familiarità con la sintassi delle regole, potete scrivere espressioni direttamente nei fogli di lavoro.

## Esempio di generatore di regole {#rule-builder-example}

Esaminiamo un esempio che illustra come utilizzare [!UICONTROL Segment Builder] per creare una regola per il foglio di lavoro di massa. Tuttavia, non si tratta di una serie di istruzioni dettagliate per tali strumenti. Cominceremo con una semplice regola già creata. Per istruzioni sull&#39;utilizzo dei generatore di regole, consultate Generatore [di](../../features/segments/segment-builder.md) segmenti e Generatore [di](../../features/traits/about-trait-builder.md)caratteristiche.

Con il generatore di regole visive, abbiamo creato una regola di segmento con 3 caratteristiche e un [!UICONTROL AND] operatore booleano.

![](assets/visualrule.png)

Fate clic **[!UICONTROL Code View]** per ottenere la versione testuale della regola.

>[!TIP]
>
>Fare clic **[!UICONTROL Validate Expression]** per controllare la logica della regola. In questo modo si evita di caricare una regola non valida.

![](assets/coderule.png)

Incolla la regola nel [!UICONTROL Bulk Management Tools] foglio di lavoro e conferma le modifiche per aggiornare le regole del segmento in blocco.

![](assets/segmentrule.png)

## Creazione di regole personalizzate {#create-rules}

Puoi scrivere le tue regole al di fuori di [!UICONTROL Rule Builder]. Prima di iniziare, leggete la documentazione che tratta argomenti quali operatori, espressioni e variabili obbligatorie. È consigliabile rivedere quanto segue:

* [Utilizzo Degli Operatori Di Confronto Nel Generatore Di Caratteristiche](../../features/traits/trait-comparison-operators.md)
* [Ordine delle operazioni](../../features/traits/trait-operator-precedence.md)
* [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md)
* [Espressioni di esempio con operatori booleani e di confronto](../../features/traits/trait-expression-samples.md)

