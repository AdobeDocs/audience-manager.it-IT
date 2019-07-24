---
description: Audience Lab consente diversi casi d'uso consentendo di utilizzare segmenti linea di base per creare gruppi di test. Potete suddividere i gruppi di test in diversi segmenti di test mutualmente esclusivi, mappare questi in destinazioni diverse e quindi determinare quale dei segmenti più efficace per guidare le conversioni.
seo-description: Audience Lab consente diversi casi d'uso consentendo di utilizzare segmenti linea di base per creare gruppi di test. Potete suddividere i gruppi di test in diversi segmenti di test mutualmente esclusivi, mappare questi in destinazioni diverse e quindi determinare quale dei segmenti più efficace per guidare le conversioni.
seo-title: Casi d'uso di Audience Lab
solution: Audience Manager
title: Casi d'uso di Audience Lab
topic: API DIL
uuid: 727 bec 8 a-df 9 a -40 cc-b 8 a 7-e 1980 d 146 a 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] abilita diversi casi d'uso consentendo di utilizzare segmenti linea di base per la creazione di gruppi di test. Potete suddividere i gruppi di test in diversi segmenti di test mutualmente esclusivi, mappare questi in destinazioni diverse e quindi determinare quale dei segmenti più efficace per guidare le conversioni.

## Compare Models in Audience Lab {#compare-models}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] offre un modo semplice per confrontare i tassi di conversione dei clienti tra i tuoi modelli attivi.

<!-- audience-lab-compare-models.xml -->

In questo caso d'uso, confronterete modelli diversi. You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) feature in [!DNL Audience Manager].

1. Create two models, either in the [Model Builder](../../features/algorithmic-models/create-model.md), or via an outside platform.
1. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
1. Crea segmenti mutualmente esclusivi in modo che gli utenti in entrambi i modelli non si sovrappongano:

   * Create a *Model 1 Segment* and a *Model 2 Segment*.
   * Have the segment rule for *Model 1 Segment* be model 1 trait [!DNL AND NOT] model 2 trait, and vice-versa for *Model 2 Segment*.

1. [Crea due gruppi di test di segmenti](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], uno con *Segmento Modello 1* come linea di base, l'altro con *Segmento Modello 2* come linea di base.

   * Mantenete le variabili uguali per entrambi i gruppi di test: stesse destinazioni, caratteristiche creative e di conversione.
   * Assicuratevi che i segmenti di test abbiano un numero di utenti simile (ad es. 1.6 milioni e 1.8 milioni di utenti, 1.6 milioni e 16 milioni di utenti).
   * Riserva un segmento di controllo in ciascun gruppo di test del segmento di prova. In tal modo, puoi impostare una piccola parte di ogni segmento e non eseguirne il targeting esplicito nel test.

1. Esaminate i risultati:

   * The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions each model is driving. Per le campagne basate su conversione, il segmento di test che genera il maggior numero di conversioni indicherà il modello che funziona meglio.
   * Dato che disponete di segmenti di controllo, potete valutare anche il comportamento del modello rispetto al targeting standard. Non solo state testando un modello rispetto all'altro, ma testare la domanda di «Provare questo modello meglio delle normali prassi?»

## Testing Creatives Across Destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. Questo caso d'uso consente anche di misurare le conversioni dei creativi rispetto alle conversioni naturali.

1. [Crea un gruppo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)di test segmenti, selezionando il segmento a cui vuoi associare i dati creativi come segmento della linea di base.
1. Suddivide il segmento della linea di base in segmenti di test e di controllo.
1. Mappate i segmenti di prova sulle diverse destinazioni da sottoporre a test.
1. Il segmento di controllo può essere tenuto premuto e non mappato su alcuna destinazione. Il segmento di controllo non deve essere mirato dal test creativo per impostare una linea di base dei risultati per le conversioni in modo naturale.
1. Specificate una data di inizio e una data di fine per il test.
1. Configurare il segmento e le credenziali nelle destinazioni.
1. The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions the creative is driving across the destinations.
1. Poiché avete creato un segmento di controllo, potete anche valutare il livello di creatività rispetto alle conversioni in corso. Stai sottoponendo a test la domanda: " Questa creatività genera un tasso di conversione più elevato rispetto alle normali pratiche? "
