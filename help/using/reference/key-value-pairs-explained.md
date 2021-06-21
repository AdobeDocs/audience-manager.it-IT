---
description: Definisce e descrive coppie chiave-valore standard e serializzati.
keywords: integration code
seo-description: Definisce e descrive coppie chiave-valore standard e serializzati.
seo-title: Spiegazione delle coppie chiave-valore
solution: Audience Manager
title: Spiegazione delle coppie chiave-valore
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: 'Riferimenti '
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 5%

---

# Spiegazione delle coppie chiave-valore{#key-value-pairs-explained}

Definisce e descrive coppie chiave-valore standard e serializzati.

<!-- 

c_key_value_explained.xml

 -->

Una coppia chiave-valore è costituita da due elementi dati correlati: Una chiave, che è una costante che definisce il set di dati (ad esempio, genere, colore, prezzo) e un valore, che è una variabile che appartiene al set (ad esempio, maschio/femmina, verde, 100). Completamente formata, una coppia chiave-valore potrebbe avere un aspetto simile al seguente:

* `gender = male`
* `color = green`
* `price > 100`

## Coppie chiave-valore standard e serializzate {#standard-serialized-pairs}

Le destinazioni accettano dati chiave-valore in formato *`standard`* o *`serialized`* . La formattazione standard organizza i dati in coppie chiave-valore separate. Ogni chiave è indicata esplicitamente, anche quando viene utilizzata di nuovo per definire un valore diverso. Al contrario, la formattazione serializzata condensa più valori in un set definito da un singolo tasto. Inoltre, in una coppia serializzata, viene utilizzato un indicatore speciale per separare i valori all&#39;interno dell&#39;insieme chiave-valore. Infine, i valori chiave standard e serializzati possono contenere uno o più valori. Nella tabella seguente sono riportati alcuni esempi di formati chiave standard e seriali.

| Formattazione | Chiave singola | Coppie chiave-valore |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializzato** | `x=1;2` | `x=1;2&y=3;4` |



## Tasti, delimitatori e separatori {#keys-delimiters-separators}

Quando lavori con dati serializzati, devi specificare i caratteri che separano i valori *all&#39;interno di* e *tra* le coppie chiave-valore. Gli elementi nelle coppie chiave-valore sono definiti come segue:

* **Chiave:** un identificatore univoco nella coppia chiave-valore.
* **delimitatore di valori:** separa le singole coppie chiave-valore.
* **Separatore chiave-valore:** separa una chiave dai valori all’interno di una coppia chiave-valore.
* **Separatore seriale:** separa i singoli valori all’interno di coppie chiave-valore serializzate.

## Elementi chiave-valore standard e serializzati {#standard-serialized-key-value-elements}


| Type (Tipo) | Esempio | Chiave | Separatore chiave-valore | Delimitatore chiave-valore | Separatore seriale |
|---------|----------|---------|---------|----------|---------|
| **Chiave**  singola (standard) | `x=1&x=2` | `x` | `=` | `&` | n/d |
| **Coppie chiave-valore**  (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/d |
| **Chiave**  singola (seriale) | `x=1;2;3` | `x` | `=` | n/d | `;` |
| **Coppie chiave-valore**  (seriali) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
