---
description: Audience Lab consente diversi casi di utilizzo consentendo di utilizzare segmenti di base per la creazione di gruppi di test. Potete dividere i gruppi di test in diversi segmenti di test che si escludono a vicenda, mapparli su destinazioni diverse e quindi determinare quali dei segmenti sono più efficaci nel promuovere le conversioni.
seo-description: Audience Lab consente diversi casi di utilizzo consentendo di utilizzare segmenti di base per la creazione di gruppi di test. Potete dividere i gruppi di test in diversi segmenti di test che si escludono a vicenda, mapparli su destinazioni diverse e quindi determinare quali dei segmenti sono più efficaci nel promuovere le conversioni.
seo-title: Casi di utilizzo di Audience Lab
solution: Audience Manager
title: Casi di utilizzo di Audience Lab
topic: API DIL
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Casi di utilizzo di Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] consente diversi casi di utilizzo consentendo di utilizzare segmenti di base per la creazione di gruppi di test. Potete dividere i gruppi di test in diversi segmenti di test che si escludono a vicenda, mapparli su destinazioni diverse e quindi determinare quali dei segmenti sono più efficaci nel promuovere le conversioni.

## Confronto di modelli in Audience Lab {#compare-models}

È possibile utilizzare diversi tipi e origini di modelli in [!DNL Audience Manager]. [!UICONTROL Audience Lab] offre un modo semplice per confrontare i tassi di conversione dei clienti tra i modelli attivi.

<!-- audience-lab-compare-models.xml -->

In questo caso di utilizzo, si stanno confrontando diversi modelli. È possibile utilizzare modelli creati tramite un data warehouse interno e importarli [!DNL Audience Manager] come caratteristiche [](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) integrate oppure utilizzare la funzione Modelli [](../../features/algorithmic-models/understanding-models.md) algoritmici di [!DNL Audience Manager].

1. Create due modelli, nel [Model Builder](../../features/algorithmic-models/create-model.md)o tramite una piattaforma esterna.
1. Create caratteristiche [](../../features/traits/create-algorithmic-traits.md) algoritmiche dal modello algoritmico o importate modelli personalizzati come caratteristiche integrate.
1. Crea segmenti che si escludono a vicenda in modo che gli utenti di entrambi i modelli non si sovrappongano:

   * Crea un segmento ** modello 1 e un segmento ** modello 2.
   * Far sì che la regola del segmento per il segmento *del modello 1 Segmento* sia un tratto del modello 1 [!DNL AND NOT] modello 2 e viceversa per il segmento *del* modello 2.

1. [Create due gruppi](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) di test dei segmenti in [!UICONTROL Audience Lab], uno con il segmento ** Modello 1 come linea di base, l'altro con il segmento ** Modello 2 come linea di base.

   * Mantenete le variabili invariate per entrambi i gruppi di test: stesse destinazioni, caratteristiche creative, di conversione.
   * Assicuratevi che i segmenti di test abbiano un numero di utenti simile (ad es. 1,6 milioni e 1,8 milioni è ok, 1,6 milioni e 16 milioni no).
   * Riservare un segmento di controllo in ciascun gruppo di test del segmento di test. In questo modo, potete mettere da parte una piccola parte di ciascun segmento e non eseguire il targeting esplicito per tali segmenti nel test.

1. Esaminate i risultati:

   * La visualizzazione [di reporting di](../../features/audience-lab/audience-lab-reporting-view.md) Audience Lab mostra il numero di conversioni generate da ogni modello. Per le campagne basate sulla conversione, il segmento di test che genera il maggior numero di conversioni sarà il modello che esegue meglio.
   * Poiché avete segmenti di controllo, potete anche valutare come il modello ha agito rispetto al targeting standard. Non state solo testando un modello contro l'altro, ma testando la domanda "questo modello ha funzionato meglio delle normali pratiche?"

## Verifica dei creativi tra le destinazioni {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilizzate questa opzione [!UICONTROL Audience Lab] per misurare il numero di conversioni che un creativo sta generando tra diverse destinazioni. Questo caso d’uso consente inoltre di misurare le conversioni dei creativi rispetto alle conversioni che si verificano naturalmente.

1. [Create un gruppo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)di test dei segmenti, selezionando il segmento con cui eseguire il test della creatività come segmento della linea di base.
1. Dividi il segmento della linea di base in segmenti di test e segmenti di controllo.
1. Mappate i segmenti di test sulle diverse destinazioni da sottoporre a test.
1. Il segmento di controllo può essere bloccato e non mappato ad alcuna destinazione. Il segmento di controllo non deve essere mirato dal creativo del test per impostare una baseline dei risultati per le conversioni che si verificano naturalmente.
1. Specificate una data di inizio e una data di fine per il test.
1. Imposta il segmento e il creativo nelle destinazioni.
1. La visualizzazione [di reporting di](../../features/audience-lab/audience-lab-reporting-view.md) Audience Lab mostrerà il numero di conversioni che il creativo sta guidando tra le destinazioni.
1. Poiché hai creato un segmento di controllo, puoi anche valutare come il creativo ha agito rispetto alle conversioni che si verificano naturalmente. Stai verificando la domanda: "Questo creativo ha generato un tasso di conversione più alto rispetto alle normali pratiche?"
