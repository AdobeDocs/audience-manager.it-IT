---
description: Definisce e descrive coppie chiave-valore standard e serializzate.
keywords: integration code
seo-description: Definisce e descrive coppie chiave-valore standard e serializzate.
seo-title: Coppie chiave-valore spiegate
solution: Audience Manager
title: Coppie chiave-valore spiegate
uuid: f 1435742-81 ca -4964-8370-accf 2 f 1 c 47 a 5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Coppie chiave-valore spiegate{#key-value-pairs-explained}

Definisce e descrive coppie chiave-valore standard e serializzate.

<!-- 

c_key_value_explained.xml

 -->

Una coppia chiave-valore è composta da due elementi dati correlati: Una chiave, ovvero una costante che definisce il set di dati (ad es. genere, colore, prezzo) e un valore, ovvero una variabile che appartiene al set (ad es. uomo/donna, verde, 100). In modo completo, una coppia chiave-valore potrebbe avere l&#39;aspetto seguente:

* `gender = male`
* `color = green`
* `price > 100`

## Standard e coppie chiave-valore serializzate {#standard-serialized-pairs}

Le destinazioni accettano dati chiave-valore in *`standard`* o *`serialized`* formato. La formattazione standard organizza i dati in coppie chiave-valore separate. Ogni chiave viene definita esplicitamente, anche quando viene utilizzata di nuovo per definire un altro valore. Per contro, la formattazione serializzata condensa più valori in un set definito da una singola chiave. Inoltre, in una coppia serializzata, viene utilizzato un indicatore speciale per separare i valori all&#39;interno del set chiave-valore. Infine, i valori chiave standard e serializzati possono contenere valori singoli o multipli. Nella tabella seguente sono riportati alcuni esempi di formati chiave-valore standard e di serie.

| Formattazione | Chiave singola | Coppie chiave-valore |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializzato** | `x=1;2` | `x=1;2&y=3;4` |



## Tasti, delimitatori e separatori {#keys-delimiters-separators}

Quando si utilizzano dati serializzati, è necessario specificare i caratteri che separano i valori *all&#39;interno* e *tra* le coppie chiave-valore. Gli elementi delle coppie chiave-valore sono definiti come segue:

* **Chiave:** Un identificatore univoco nella coppia chiave-valore.
* **Delimitatore valore:** Separa le singole coppie chiave-valore.
* **Separatore chiave chiave:** Separa una chiave dai valori all&#39;interno di una coppia chiave-valore.
* **Separatore di serie:** Separa i singoli valori all&#39;interno delle coppie chiave-valore serializzate.

## Standard e chiavi chiave serializzate-Valore {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type (Tipo) </th> 
   <th colname="col2" class="entry"> Esempio  </th> 
   <th colname="col3" class="entry"> Chiave </th> 
   <th colname="col4" class="entry"> Separatore chiave chiave </th> 
   <th colname="col5" class="entry"> Delimitatore chiave chiave </th> 
   <th colname="col6" class="entry"> Separatore di serie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Singola chiave</b> <p>(Standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/d </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Coppie chiave-valore</b> <p>(Standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Singola chiave</b> <p>(serie seriale) </p> </td> 
   <td colname="col2"> <code> x = 1; 2; 3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/d </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Coppie chiave-valore</b> (serie) </td> 
   <td colname="col2"> <code> x = 1; 2 &amp; y = 3; 4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

