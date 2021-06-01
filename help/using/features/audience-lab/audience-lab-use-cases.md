---
description: Audience Lab abilita diversi casi d’uso consentendo di utilizzare segmenti di base per la creazione di gruppi di test. Puoi dividere i gruppi di test in diversi segmenti di test reciprocamente esclusivi, mapparli su destinazioni diverse e quindi determinare quali dei segmenti sono più efficaci nel promuovere le conversioni.
seo-description: Audience Lab abilita diversi casi d’uso consentendo di utilizzare segmenti di base per la creazione di gruppi di test. Puoi dividere i gruppi di test in diversi segmenti di test reciprocamente esclusivi, mapparli su destinazioni diverse e quindi determinare quali dei segmenti sono più efficaci nel promuovere le conversioni.
seo-title: Casi di utilizzo di Audience Lab
solution: Audience Manager
title: Casi di utilizzo di Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: 'Audience Lab '
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Casi di utilizzo di Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] abilita diversi casi d’uso consentendo di utilizzare segmenti della linea di base per la creazione di gruppi di test. Puoi dividere i gruppi di test in diversi segmenti di test reciprocamente esclusivi, mapparli su destinazioni diverse e quindi determinare quali dei segmenti sono più efficaci nel promuovere le conversioni.

## Confrontare i modelli in Audience Lab {#compare-models}

Puoi utilizzare diversi tipi e origini di modelli in [!DNL Audience Manager]. [!UICONTROL Audience Lab] offre un modo semplice per confrontare i tassi di conversione dei clienti, tra i modelli attivi.

<!-- audience-lab-compare-models.xml -->

In questo caso d’uso, stai confrontando diversi modelli. Puoi utilizzare i modelli creati tramite un data warehouse interno e importarli in [!DNL Audience Manager] come [Caratteristiche onboarded](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) oppure utilizzare la funzione [Modelli algoritmici](../../features/algorithmic-models/understanding-models.md) in [!DNL Audience Manager].

1. Crea due modelli, nel [Generatore di modelli](../../features/algorithmic-models/create-model.md) o tramite una piattaforma esterna.
1. Crea [caratteristiche algoritmiche](../../features/traits/create-algorithmic-traits.md) dal modello algoritmico o importa i tuoi modelli come caratteristiche onboarded.
1. Crea segmenti reciprocamente esclusivi in modo che gli utenti di entrambi i modelli non si sovrappongano:

   * Crea un *segmento modello 1* e un *segmento modello 2*.
   * Avere la regola del segmento per *Segmento modello 1* come caratteristica del modello 1 [!DNL AND NOT] modello 2 e viceversa per *Segmento modello 2*.

1. [Crea due ](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) raggruppamenti di test di segmento  [!UICONTROL Audience Lab], uno con  *Segmenti modello 1 come linea di base, l&#39;altro con* Segmenti modello 2  ** come linea di base.

   * Mantieni le variabili uguali per entrambi i gruppi di test: stesse destinazioni, caratteristiche creative, di conversione.
   * Assicurati che i segmenti di test abbiano un numero simile di utenti (ad es. 1,6 milioni e 1,8 milioni va bene, 1,6 milioni e 16 milioni no).
   * Riserva un segmento di controllo in ciascun gruppo di test del segmento di test. In questo modo, puoi mettere da parte una piccola parte di ciascun segmento e non eseguirne esplicitamente il targeting nel test.

1. Esamina i risultati:

   * La [visualizzazione di reporting di Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrerà il numero di conversioni che ogni modello sta guidando. Per le campagne basate su conversione, il segmento di test che genera il maggior numero di conversioni indica il modello che offre le prestazioni migliori.
   * Poiché hai dei segmenti di controllo, puoi anche valutare come ha fatto il modello rispetto al targeting standard. Non solo state testando un modello rispetto all&#39;altro, ma testando la domanda &quot;questo modello ha fatto meglio delle normali pratiche?&quot;

## Verifica dei creativi tra le destinazioni {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilizza [!UICONTROL Audience Lab] per misurare il numero di conversioni che un creativo sta generando tra destinazioni diverse. Questo caso d’uso consente inoltre di misurare le conversioni del creativo rispetto alle conversioni presenti in modo naturale.

1. [Crea un gruppo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) di test dei segmenti, selezionando il segmento su cui si desidera eseguire il test della creatività come segmento della linea di base.
1. Dividi il segmento della linea di base in segmenti di test e segmenti di controllo.
1. Mappa i segmenti di test sulle diverse destinazioni da sottoporre a test.
1. Il segmento di controllo può essere rifiutato e non mappato su alcuna destinazione. Il segmento di controllo non deve essere oggetto di targeting da parte del creativo del test per impostare una linea di base dei risultati per le conversioni presenti in modo naturale.
1. Specifica una data di inizio e una data di fine per il test.
1. Imposta il segmento e il contenuto creativo nelle destinazioni.
1. La [visualizzazione di reporting di Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrerà il numero di conversioni che il creativo sta generando tra le destinazioni.
1. Poiché hai creato un segmento di controllo, puoi anche valutare il comportamento creativo rispetto alle conversioni presenti in modo naturale. Stai testando la domanda: &quot;Questo creativo ha generato un tasso di conversione più alto rispetto alle pratiche normali?&quot;
