---
description: I fogli di lavoro di creazione e aggiornamento accettano un'intestazione traitRule che consente di applicare più regole in un'unica operazione. Segui queste istruzioni per effettuare richieste di regole in blocco.
seo-description: I fogli di lavoro di creazione e aggiornamento accettano un'intestazione traitRule che consente di applicare più regole in un'unica operazione. Segui queste istruzioni per effettuare richieste di regole in blocco.
seo-title: Creare o aggiornare regole di caratteristiche e di segmenti
solution: Audience Manager
title: Creare o aggiornare regole di caratteristiche e di segmenti
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 10%

---

# Creare o aggiornare regole di caratteristiche e di segmenti{#create-or-update-trait-rules-and-segment-rules}

I fogli di lavoro di creazione e aggiornamento accettano un&#39;intestazione traitRule che consente di applicare più regole in un&#39;unica operazione. Segui queste istruzioni per effettuare richieste di regole in blocco.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate in  [!UICONTROL Bulk Management Tools].

## Utilizzo delle regole delle caratteristiche {#trait-rules}

Nel tuo foglio di lavoro, la colonna della regola delle caratteristiche restituisce e accetta regole costituite da espressioni booleane, operatori di confronto ed espressioni regolari. Puoi creare regole con il generatore di caratteristiche o segmenti in [!DNL Audience Manager] e copiarle nel tuo foglio di lavoro. Oppure, se hai familiarità con la sintassi delle regole, puoi scrivere espressioni direttamente nei fogli di lavoro.

## Esempio di generatore di regole {#rule-builder-example}

Diamo un&#39;occhiata a un esempio che dimostra come utilizzare [!UICONTROL Segment Builder] per creare una regola che è possibile per il foglio di lavoro di massa. Tuttavia, questo non è un insieme di istruzioni dettagliate per questi strumenti. Invece, cominceremo con una semplice regola che è già stata creata. Per istruzioni su come utilizzare i generatore di regole, consulta [Generatore di segmenti](../../features/segments/segment-builder.md) e [Generatore di caratteristiche](../../features/traits/about-trait-builder.md).

Con il generatore di regole visive, abbiamo creato una regola di segmento con 3 caratteristiche e un operatore booleano [!UICONTROL AND].

![](assets/visualrule.png)

Fai clic su **[!UICONTROL Code View]** per ottenere la versione testuale di questa regola.

>[!TIP]
>
>Fai clic su **[!UICONTROL Validate Expression]** per controllare la logica della regola. Questo ti aiuterà a impedire il caricamento di una regola non valida.

![](assets/coderule.png)

Incolla la regola nel foglio di lavoro [!UICONTROL Bulk Management Tools] e conferma le modifiche per aggiornare le regole del segmento in blocco.

![](assets/segmentrule.png)

## Creazione di regole personalizzate {#create-rules}

Puoi scrivere le tue regole al di fuori di [!UICONTROL Rule Builder]. Prima di iniziare, leggi la documentazione che tratta argomenti come gli operatori, l’espressione e le variabili richieste. Si consiglia di rivedere quanto segue:

* [Utilizzo Degli Operatori Di Confronto Nel Generatore Di Caratteristiche](../../features/traits/trait-comparison-operators.md)
* [Ordine delle operazioni](../../features/traits/trait-operator-precedence.md)
* [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md)
* [Espressioni di esempio con operatori booleani e di confronto](../../features/traits/trait-expression-samples.md)
