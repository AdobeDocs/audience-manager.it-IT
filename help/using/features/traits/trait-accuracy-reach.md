---
description: Descrive la relazione tra precisione e portata nelle caratteristiche algoritmiche.
seo-description: Descrive la relazione tra precisione e portata nelle caratteristiche algoritmiche.
seo-title: Precisione e portata
solution: Audience Manager
title: Precisione e portata
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: 'Caratteristiche '
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 3%

---

# Precisione e portata {#accuracy-and-reach}

Descrive la relazione tra precisione e portata nelle caratteristiche algoritmiche.

<!-- c_accuracy_reach.xml -->

## Precisione rispetto a portata: Informazioni

È importante comprendere la relazione tra precisione e portata quando si lavora con caratteristiche algoritmiche. L’accuratezza è rappresentata da un valore con punteggio che riflette la similarità degli utenti rispetto alla linea di base. La scala di precisione va da 0 (precisione minore) a 1 (precisione maggiore). Reach è semplicemente un valore che rappresenta il numero di utenti univoci che desideri includere in una caratteristica. Raggiungimento e precisione sono inversamente correlati. Le caratteristiche precise raggiungono meno utenti e le caratteristiche con una portata maggiore sono meno precise. L&#39;immagine seguente illustra questo concetto.

![](assets/Reach_v_Accuracy.png)

## Precisione e portata influiscono sulle dimensioni del pubblico

I tuoi obiettivi aziendali dovrebbero aiutarti a prendere le decisioni giuste su precisione e portata quando lavori con caratteristiche algoritmiche. Se l’obiettivo è la precisione, noterai che la popolazione di una caratteristica può aumentare o diminuire tra le esecuzioni dei modelli. I cambiamenti di popolazione sono i risultati dell&#39;algoritmo che prende decisioni durante ogni periodo di valutazione. A volte, l’algoritmo trova utenti più qualificati durante un ciclo di elaborazione e, in altri, potrebbe trovarne di meno. I risultati sono determinati dai dati della linea di base utilizzati per creare il modello e i nuovi visitatori e le qualifiche delle caratteristiche derivanti dall&#39;esecuzione del modello precedente. Al contrario, quando si lavora con REACH, il conteggio della popolazione degli utenti rimane costante. Ad esempio, se desideri raggiungere 10.000 utenti, l&#39;algoritmo si accerterà che abbia sempre raggiunto quel numero per ogni esecuzione del modello.

## Casi d’uso generali per precisione e portata

L’attenzione per la precisione o la portata dipende da cosa si desidera ottenere con un particolare segmento. La tabella seguente può essere utile per valutare precisione e portata durante la creazione di una caratteristica.

| Vantaggi della decisione sulle caratteristiche | Aiuta a trovare |
|---|---|
| **Precisione** | Utenti simili ai clienti della linea di base nel modello. Utile per campagne mirate quando desideri raggiungere un pubblico specifico. |
| **Raggiungimento** | Un numero specifico di utenti per ogni esecuzione di dati. Utile per le campagne sul marchio quando sei interessato a raggiungere un pubblico di dimensioni specifiche. |
