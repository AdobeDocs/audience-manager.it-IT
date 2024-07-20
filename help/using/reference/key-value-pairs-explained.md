---
description: Definisce e descrive coppie chiave-valore standard e serializzate.
keywords: codice di integrazione
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Spiegazione delle coppie chiave-valore
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Spiegazione delle coppie chiave-valore{#key-value-pairs-explained}

Definisce e descrive coppie chiave-valore standard e serializzate.

<!-- 

c_key_value_explained.xml

 -->

Una coppia chiave-valore è costituita da due elementi dati correlati: una chiave, che è una costante che definisce il set di dati (ad esempio, genere, colore, prezzo) e un valore, che è una variabile che appartiene al set (ad esempio, maschio/femmina, verde, 100). Completamente formato, una coppia chiave-valore potrebbe essere simile alla seguente:

* `gender = male`
* `color = green`
* `price > 100`

## Coppie chiave-valore standard e serializzate {#standard-serialized-pairs}

Le destinazioni accettano dati chiave-valore in formato *`standard`* o *`serialized`*. La formattazione standard organizza i dati in coppie chiave-valore separate. Ogni chiave viene dichiarata esplicitamente, anche se utilizzata di nuovo per definire un valore diverso. Al contrario, la formattazione serializzata condensa più valori in un unico insieme definito da una singola chiave. Inoltre, in una coppia serializzata, viene utilizzato un indicatore speciale per separare i valori all’interno dell’insieme chiave-valore. Infine, i valori chiave standard e serializzati possono contenere uno o più valori. Nella tabella seguente vengono forniti esempi di formati chiave-valore standard e seriali.

| Formattazione | Chiave singola | Coppie chiave-valore |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializzato** | `x=1;2` | `x=1;2&y=3;4` |



## Chiavi, delimitatori e separatori {#keys-delimiters-separators}

Quando si lavora con dati serializzati, è necessario specificare i caratteri che separano i valori *entro* e *tra* le coppie chiave-valore. Gli elementi nelle coppie chiave-valore sono definiti come segue:

* **Chiave:** Identificatore univoco nella coppia chiave-valore.
* **Delimitatore valore:** Separa singole coppie chiave-valore.
* **Separatore chiave-valore:** Separa una chiave dai valori all&#39;interno di una coppia chiave-valore.
* **Separatore seriale:** separa i singoli valori all&#39;interno di coppie chiave-valore serializzate.

## Elementi chiave-valore standard e serializzati {#standard-serialized-key-value-elements}


| Type (Tipo) | Esempio | Chiave | Separatore chiave-valore | Delimitatore chiave-valore | Separatore seriale |
|---------|----------|---------|---------|----------|---------|
| **Chiave singola** (standard) | `x=1&x=2` | `x` | `=` | `&` | n/d |
| **Coppie chiave-valore** (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/d |
| **Chiave singola** (seriale) | `x=1;2;3` | `x` | `=` | n/d | `;` |
| **Coppie chiave-valore** (seriale) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
