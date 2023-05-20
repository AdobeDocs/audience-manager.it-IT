---
description: Descrive la relazione tra precisione e portata nelle caratteristiche algoritmiche.
seo-description: Describes the relationship between accuracy and reach in algorithmic traits.
seo-title: Accuracy and Reach
solution: Audience Manager
title: Precisione e portata
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 2%

---

# Precisione e portata {#accuracy-and-reach}

Descrive la relazione tra precisione e portata nelle caratteristiche algoritmiche.

<!-- c_accuracy_reach.xml -->

## Precisione e portata: informazioni

È importante comprendere la relazione tra precisione e portata quando si lavora con caratteristiche algoritmiche. L’accuratezza è rappresentata da un valore con punteggio che riflette la somiglianza degli utenti alla linea di base. La scala di precisione va da 0 (precisione minima) a 1 (precisione massima). Raggiungi è semplicemente un valore che rappresenta il numero di utenti univoci che desideri includere in una caratteristica. La portata e l&#39;accuratezza sono inversamente correlate. Le caratteristiche precise raggiungono meno utenti e le caratteristiche con una portata maggiore sono meno precise. L’immagine seguente illustra questo concetto.

![](assets/Reach_v_Accuracy.png)

## Accuratezza e portata degli effetti sulla dimensione del pubblico

Gli obiettivi aziendali dovrebbero aiutarti a prendere le decisioni giuste in merito a precisione e portata quando lavori con le caratteristiche algoritmiche. Se l’obiettivo è la precisione, tieni presente che la popolazione di una caratteristica può aumentare o diminuire tra le esecuzioni dei modelli. Le modifiche della popolazione sono il risultato delle decisioni prese dall’algoritmo durante ciascun periodo di valutazione. A volte, l’algoritmo trova utenti più qualificati durante un ciclo di elaborazione e, durante altri, può trovarne meno. I risultati sono determinati dai dati della linea di base utilizzati per creare il modello e dai nuovi visitatori e dalle qualifiche delle caratteristiche acquisite dall’esecuzione del modello precedente. Al contrario, quando si lavora con la portata, il conteggio della popolazione utente rimane costante. Ad esempio, se desideri raggiungere 10.000 utenti, l’algoritmo si assicurerà che raggiunga sempre quel numero per ogni esecuzione del modello.

## Casi d’uso generali per Accuratezza e portata

L’attenzione sulla precisione o sulla portata dipende da cosa desideri ottenere con un particolare segmento. La tabella seguente può aiutarti a valutare la precisione rispetto alla portata durante la creazione di una caratteristica.

| Preferenze per le decisioni sulle caratteristiche | Aiuta a trovare |
|---|---|
| **Precisione** | Utenti simili ai clienti di base nel modello. Utile per campagne mirate quando desideri raggiungere un pubblico specifico. |
| **Raggiungi** | Un numero specifico di utenti per ogni esecuzione di dati. Utile per le campagne sui marchi quando sei interessato a raggiungere un pubblico di una dimensione specifica. |
