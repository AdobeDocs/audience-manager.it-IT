---
description: Audience Lab consente diversi casi d’uso consentendoti di utilizzare i segmenti di base per la creazione di gruppi di test. Puoi suddividere i gruppi di test in diversi segmenti di test reciprocamente esclusivi, mapparli su destinazioni diverse e quindi determinare quale dei segmenti è più efficace per stimolare le conversioni.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Casi di utilizzo di Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 1%

---

# Casi di utilizzo di Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] abilita diversi casi d’uso consentendo di utilizzare i segmenti della linea di base per la creazione di gruppi di test. Puoi suddividere i gruppi di test in diversi segmenti di test reciprocamente esclusivi, mapparli su destinazioni diverse e quindi determinare quale dei segmenti è più efficace per stimolare le conversioni.

## Confrontare modelli in Audience Lab {#compare-models}

È possibile utilizzare diversi tipi e origini di modelli in [!DNL Audience Manager]. [!UICONTROL Audience Lab] offre un modo semplice per confrontare i tassi di conversione dei clienti, tra i diversi modelli attivi.

<!-- audience-lab-compare-models.xml -->

In questo caso d’uso, stai confrontando diversi modelli. Puoi utilizzare i modelli creati tramite un data warehouse interno e importarli in [!DNL Audience Manager] as [Caratteristiche onboarded](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) oppure puoi utilizzare il [Modelli algoritmici](../../features/algorithmic-models/understanding-models.md) funzionalità in [!DNL Audience Manager].

1. Creare due modelli, in [Generatore di modelli](../../features/algorithmic-models/create-model.md)o tramite una piattaforma esterna.
1. Crea [caratteristiche algoritmiche](../../features/traits/create-algorithmic-traits.md) dal modello algoritmico o importa i tuoi modelli come caratteristiche onboarded.
1. Crea segmenti reciprocamente esclusivi in modo che gli utenti di entrambi i modelli non si sovrappongano:

   * Creare un *Segmento modello 1* e un *Segmento modello 2*.
   * Assicurati che la regola del segmento per *Segmento modello 1* essere caratteristica modello 1 [!DNL AND NOT] caratteristica modello 2 e viceversa per *Segmento modello 2*.

1. [Creare due gruppi di test dei segmenti](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], uno con *Segmento modello 1* come linea di base, l&#39;altra con *Segmento modello 2* come linea di base.

   * Mantieni le variabili uguali per entrambi i gruppi di test: stesse destinazioni, creatività, caratteristiche di conversione.
   * Assicurati che i segmenti di test abbiano un numero di utenti simile (ad esempio, 1,6 milioni e 1,8 milioni vanno bene, 1,6 milioni e 16 milioni no).
   * Prenotare un segmento di controllo in ciascun gruppo di test dei segmenti di test. In questo modo, puoi mettere da parte una piccola parte di ciascun segmento e non indirizzarli esplicitamente nel test.

1. Esamina i risultati:

   * Il [Visualizzazione di reporting di Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrerà il numero di conversioni guidate da ciascun modello. Per le campagne basate sulla conversione, il segmento di test che guida il maggior numero di conversioni indica il modello che offre le prestazioni migliori.
   * Poiché disponi di segmenti di controllo, puoi anche valutare il comportamento del modello rispetto al &quot;targeting standard&quot;. Non si sta solo testando un modello rispetto all&#39;altro, ma si sta anche testando la domanda &quot;questo modello ha funzionato meglio delle normali pratiche?&quot;

## Verifica di creativi tra le destinazioni {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilizzare [!UICONTROL Audience Lab] per misurare il numero di conversioni che un creativo sta guidando tra diverse destinazioni. Questo caso d’uso consente inoltre di misurare le conversioni del contenuto creativo rispetto alle conversioni naturali.

1. [Creare un gruppo di test dei segmenti](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), selezionando il segmento su cui desideri testare il contenuto creativo come segmento della linea di base.
1. Dividi il segmento della linea di base in segmenti di test e segmenti di controllo.
1. Mappa i segmenti di test sulle diverse destinazioni che desideri testare.
1. Il segmento di controllo può essere trattenuto e non mappato su alcuna destinazione. Il segmento di controllo non deve essere preso in considerazione dalla creatività del test per impostare una linea di base di risultati per le conversioni naturali.
1. Specifica una data di inizio e una data di fine per il test.
1. Configura il segmento e il contenuto creativo nelle destinazioni.
1. Il [Visualizzazione di reporting di Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrerà il numero di conversioni che il contenuto creativo sta causando tra le destinazioni.
1. Poiché hai creato un segmento di controllo, puoi anche valutare il comportamento della creatività rispetto alle conversioni naturali. Stai testando la domanda: &quot;Questo elemento creativo ha generato un tasso di conversione più elevato rispetto alle normali procedure?&quot;
