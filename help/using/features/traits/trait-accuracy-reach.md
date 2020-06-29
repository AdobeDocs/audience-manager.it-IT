---
description: Descrive la relazione tra precisione e portata nelle caratteristiche algoritmiche.
seo-description: Descrive la relazione tra precisione e portata nelle caratteristiche algoritmiche.
seo-title: Precisione e raggiungimento
solution: Audience Manager
title: Precisione e raggiungimento
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Precisione e raggiungimento {#accuracy-and-reach}

Descrive la relazione tra precisione e portata nelle caratteristiche algoritmiche.

<!-- c_accuracy_reach.xml -->

## Precisione e raggiungimento: Informazioni

È importante comprendere la relazione tra precisione e portata quando si utilizzano caratteristiche algoritmiche. Precisione è rappresentata da un valore con un punteggio che riflette la somiglianza degli utenti rispetto alla linea di base. La scala di precisione va da 0 (minimo accurato) a 1 (più preciso). Reach è semplicemente un valore che rappresenta il numero di utenti univoci che desiderate includere in una caratteristica. Raggiungere e la precisione sono inversamente correlati. Le caratteristiche precise raggiungono un numero inferiore di utenti e le caratteristiche con una maggiore portata sono meno precise. L&#39;immagine seguente illustra questo concetto.

![](assets/Reach_v_Accuracy.png)

## Precisione e raggiungimento dell&#39;obiettivo influiscono sulle dimensioni del pubblico

I tuoi obiettivi aziendali dovrebbero aiutarti a prendere le decisioni giuste sull&#39;accuratezza e a raggiungere quando lavori con caratteristiche algoritmiche. Se l&#39;obiettivo è la precisione, notare che la popolazione di una caratteristica può aumentare o diminuire in più esecuzioni di modelli. I cambiamenti di popolazione sono i risultati dell&#39;algoritmo che prende decisioni durante ciascun periodo di valutazione. Talvolta, l&#39;algoritmo rileva più utenti qualificati durante un ciclo di elaborazione e, durante gli altri, ne rileva meno. I risultati sono determinati dai dati di base utilizzati per creare il modello, i nuovi visitatori e le qualifiche di caratteristiche emerse dall&#39;esecuzione del modello precedente. Per contro, quando si lavora con REACH, il conteggio della popolazione dell&#39;utente rimane costante. Ad esempio, se desiderate raggiungere 10.000 utenti, l&#39;algoritmo si accerterà che raggiunga sempre quel numero per ogni esecuzione del modello.

## Casi di utilizzo generali per Precisione e Raggiungimento

L’attenzione sulla precisione o la portata dipende da cosa si desidera ottenere con un particolare segmento. La tabella seguente può essere utile per valutare l’accuratezza rispetto alla portata durante la creazione di una caratteristica.

| Vantaggi della decisione sulle caratteristiche | Aiuta a trovare |
|---|---|
| **Precisione** | Utenti simili ai clienti previsti nel modello. Utile per campagne mirate quando si desidera raggiungere un pubblico specifico. |
| **Raggiungi** | Un numero specifico di utenti per ogni esecuzione di dati. Utile per le campagne sul marchio quando sei interessato a raggiungere un pubblico di dimensioni specifiche. |