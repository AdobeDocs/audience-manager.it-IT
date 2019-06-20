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


# Casi d&#39;uso di Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] abilita diversi casi d&#39;uso consentendo di utilizzare segmenti linea di base per la creazione di gruppi di test. Potete suddividere i gruppi di test in diversi segmenti di test mutualmente esclusivi, mappare questi in destinazioni diverse e quindi determinare quale dei segmenti più efficace per guidare le conversioni.

## Confronta modelli in Audience Lab {#compare-models}

È [!DNL Audience Manager]possibile utilizzare più tipi e origini di modelli diversi. [!UICONTROL Audience Lab] offre un modo semplice per confrontare i tassi di conversione dei clienti tra i tuoi modelli attivi.

<!-- audience-lab-compare-models.xml -->

In questo caso d&#39;uso, confronterete modelli diversi. Potete utilizzare modelli creati tramite un archivio dati interno e importarli come [!DNL Audience Manager] Caratteristiche [caricate](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) oppure potete utilizzare la [funzione Modelli](../../features/algorithmic-models/understanding-models.md) algoritmici in [!DNL Audience Manager].

1. Create due modelli, nel Generatore [](../../features/algorithmic-models/create-model.md)modelli o tramite una piattaforma esterna.
1. Create [tratti algoritmici](../../features/traits/create-algorithmic-traits.md) dal modello algoritmico o importate modelli personalizzati come caratteristiche registrate.
1. Crea segmenti mutualmente esclusivi in modo che gli utenti in entrambi i modelli non si sovrappongano:

   * Crea un *segmento Modello 1* e un *segmento Modello 2*.
   * La regola del segmento per *Segmento modello 1* deve essere trait [!DNL AND NOT] model 1 trait, e viceversa per *Segmento Modello 2*.

1. [Crea due gruppi di test di segmenti](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) in [!UICONTROL Audience Lab], uno con *Segmento Modello 1* come linea di base, l&#39;altro con *Segmento Modello 2* come linea di base.

   * Mantenete le variabili uguali per entrambi i gruppi di test: stesse destinazioni, caratteristiche creative e di conversione.
   * Assicuratevi che i segmenti di test abbiano un numero di utenti simile (ad es. 1.6 milioni e 1.8 milioni di utenti, 1.6 milioni e 16 milioni di utenti).
   * Riserva un segmento di controllo in ciascun gruppo di test del segmento di prova. In tal modo, puoi impostare una piccola parte di ogni segmento e non eseguirne il targeting esplicito nel test.

1. Esaminate i risultati:

   * La [vista di reporting di Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrerà il numero di conversioni che ogni modello sta guidando. Per le campagne basate su conversione, il segmento di test che genera il maggior numero di conversioni indicherà il modello che funziona meglio.
   * Dato che disponete di segmenti di controllo, potete valutare anche il comportamento del modello rispetto al targeting standard. Non solo state testando un modello rispetto all&#39;altro, ma testare la domanda di «Provare questo modello meglio delle normali prassi?»

## Test creativi tra destinazioni {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilizzate per [!UICONTROL Audience Lab] misurare il numero di conversioni che un creativo sta guidando su diverse destinazioni. Questo caso d&#39;uso consente anche di misurare le conversioni dei creativi rispetto alle conversioni naturali.

1. [Crea un gruppo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)di test segmenti, selezionando il segmento a cui vuoi associare i dati creativi come segmento della linea di base.
1. Suddivide il segmento della linea di base in segmenti di test e di controllo.
1. Mappate i segmenti di prova sulle diverse destinazioni da sottoporre a test.
1. Il segmento di controllo può essere tenuto premuto e non mappato su alcuna destinazione. Il segmento di controllo non deve essere mirato dal test creativo per impostare una linea di base dei risultati per le conversioni in modo naturale.
1. Specificate una data di inizio e una data di fine per il test.
1. Configurare il segmento e le credenziali nelle destinazioni.
1. La [vista di reporting di Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) mostrerà il numero di conversioni che la creatività sta guidando tra le destinazioni.
1. Poiché avete creato un segmento di controllo, potete anche valutare il livello di creatività rispetto alle conversioni in corso. Stai sottoponendo a test la domanda: &quot; Questa creatività genera un tasso di conversione più elevato rispetto alle normali pratiche? &quot;
