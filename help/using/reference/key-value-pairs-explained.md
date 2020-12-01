---
description: Definisce e descrive coppie chiave-valore standard e serializzati.
keywords: integration code
seo-description: Definisce e descrive coppie chiave-valore standard e serializzati.
seo-title: Spiegazione delle coppie chiave-valore
solution: Audience Manager
title: Spiegazione delle coppie chiave-valore
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: reference
translation-type: tm+mt
source-git-commit: 5d6983f5308f1dfd4560ee1b38bcaee3ca6e422f
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 4%

---


# Spiegazione delle coppie chiave-valore{#key-value-pairs-explained}

Definisce e descrive coppie chiave-valore standard e serializzati.

<!-- 

c_key_value_explained.xml

 -->

Una coppia chiave-valore è costituita da due elementi dati correlati: Una chiave, che è una costante che definisce il set di dati (ad esempio, genere, colore, prezzo) e un valore, che è una variabile che appartiene al set (ad esempio, maschio/femmina, verde, 100). Completamente formata, una coppia chiave-valore potrebbe essere simile alla seguente:

* `gender = male`
* `color = green`
* `price > 100`

## Coppie chiave standard e serializzate {#standard-serialized-pairs}

Le destinazioni accettano i dati chiave-valore in formato *`standard`* o *`serialized`*. La formattazione standard organizza i dati in coppie chiave-valore separate. Ogni chiave è specificata in modo esplicito, anche se utilizzata di nuovo per definire un valore diverso. Per contro, la formattazione serializzata condensa più valori in un unico set definito da un singolo tasto. Inoltre, in una coppia serializzata, viene utilizzato un indicatore speciale per separare i valori all&#39;interno dell&#39;insieme chiave-valore. Infine, i valori chiave standard e serializzati possono contenere uno o più valori. Nella tabella seguente sono riportati alcuni esempi di formati chiave standard e seriali.

| Formattazione | Chiave singola | Coppie chiave-valore |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializzato** | `x=1;2` | `x=1;2&y=3;4` |



## Tasti, delimitatori e separatori {#keys-delimiters-separators}

Quando si utilizzano dati serializzati, è necessario specificare i caratteri che separano i valori *all&#39;interno di* e *tra* le coppie chiave-valore. Gli elementi nelle coppie chiave-valore sono definiti come segue:

* **Chiave:** un identificatore univoco nella coppia chiave-valore.
* **delimitatore di valori:** separa singole coppie chiave-valore.
* **Separatore chiave-valore:** separa una chiave dai valori all’interno di una coppia chiave-valore.
* **Separatore seriale:** separa i singoli valori all&#39;interno delle coppie chiave-valore serializzate.

## Elementi chiave standard e serializzati {#standard-serialized-key-value-elements}


| Type (Tipo) | Esempio | Chiave | Separatore chiave-valore | Delimitatore chiave-valore | Separatore seriale |
---------|----------|---------|---------|----------|---------
| **Chiave**  singola (standard) | `x=1&x=2` | `x` | `=` | `&` | n/d |
| **Coppie**  chiave-valore (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/d |
| **Tasto**  singolo (seriale) | `x=1;2;3` | `x` | `=` | n/d | `;` |
| **Coppie**  chiave-valore (serie) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
