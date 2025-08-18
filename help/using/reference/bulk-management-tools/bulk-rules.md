---
description: I fogli di lavoro di creazione e aggiornamento accettano un'intestazione traitRule che consente di applicare più regole in una singola operazione. Segui queste istruzioni per effettuare richieste in blocco di regole.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Creare o aggiornare regole di caratteristiche e di segmenti
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Creare o aggiornare regole di caratteristiche e di segmenti{#create-or-update-trait-rules-and-segment-rules}

I fogli di lavoro di creazione e aggiornamento accettano un&#39;intestazione traitRule che consente di applicare più regole in una singola operazione. Segui queste istruzioni per effettuare richieste in blocco di regole.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta ufficialmente supportata da Adobe. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Le autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnate nell&#39;interfaccia utente [!DNL Audience Manager] vengono rispettate in [!UICONTROL Bulk Management Tools].

## Utilizzo delle regole per le caratteristiche {#trait-rules}

Nel foglio di lavoro, la colonna delle regole delle caratteristiche restituisce e accetta regole costituite da espressioni booleane, operatori di confronto ed espressioni regolari. È possibile creare regole con Generatore di caratteristiche o segmenti in [!DNL Audience Manager] e copiarle nel foglio di lavoro. In alternativa, se si ha familiarità con la sintassi delle regole, è possibile scrivere espressioni direttamente nei fogli di lavoro.

## Esempio di generatore di regole {#rule-builder-example}

Ecco un esempio che illustra come utilizzare [!UICONTROL Segment Builder] per creare una regola che è possibile utilizzare per il foglio di lavoro in blocco. Tuttavia, non si tratta di un insieme di istruzioni dettagliate per questi strumenti. Inizieremo con una semplice regola già creata. Per istruzioni su come utilizzare i generatori di regole, vedi [Generatore di segmenti](../../features/segments/segment-builder.md) e [Generatore di caratteristiche](../../features/traits/about-trait-builder.md).

Con il generatore di regole visive, è stata creata una regola di segmento con 3 caratteristiche e un operatore [!UICONTROL AND] booleano.

![](assets/visualrule.png)

Fare clic su **[!UICONTROL Code View]** per ottenere la versione testuale della regola.

>[!TIP]
>
>Fai clic su **[!UICONTROL Validate Expression]** per controllare la logica della regola. Questo ti aiuterà a impedire il caricamento di una regola non valida.

![](assets/coderule.png)

Incolla la regola nel foglio di lavoro [!UICONTROL Bulk Management Tools] e conferma le modifiche per aggiornare le regole del segmento in blocco.

![](assets/segmentrule.png)

## Creazione di regole personalizzate {#create-rules}

È possibile scrivere regole personalizzate all&#39;esterno di [!UICONTROL Rule Builder]. Prima di iniziare, assicurati di leggere la documentazione che tratta elementi come operatori, espressioni e variabili richieste. Si consiglia di esaminare quanto segue:

* [Utilizzo Degli Operatori Di Confronto Nel Generatore Di Caratteristiche](../../features/traits/trait-comparison-operators.md)
* [Ordine delle operazioni](../../features/traits/trait-operator-precedence.md)
* [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md)
* [Espressioni di esempio con operatori booleani e di confronto](../../features/traits/trait-expression-samples.md)
