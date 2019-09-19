---
description: Definisce e descrive coppie chiave-valore standard e serializzati.
keywords: integration code
seo-description: Definisce e descrive coppie chiave-valore standard e serializzati.
seo-title: Spiegazione delle coppie chiave-valore
solution: Audience Manager
title: Spiegazione delle coppie chiave-valore
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

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

## Coppie chiave e valore serializzato {#standard-serialized-pairs}

Le destinazioni accettano i dati chiave-valore in *`standard`* o in *`serialized`* formato. La formattazione standard organizza i dati in coppie chiave-valore separate. Ogni chiave è specificata in modo esplicito, anche se utilizzata di nuovo per definire un valore diverso. Per contro, la formattazione serializzata condensa più valori in un unico set definito da un singolo tasto. Inoltre, in una coppia serializzata, viene utilizzato un indicatore speciale per separare i valori all'interno del set di valori chiave. Infine, i valori chiave standard e serializzati possono contenere uno o più valori. Nella tabella seguente sono riportati alcuni esempi di formati chiave standard e seriali.

| Formattazione | Chiave singola | Coppie chiave-valore |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializzato** | `x=1;2` | `x=1;2&y=3;4` |



## Tasti, delimitatori e separatori {#keys-delimiters-separators}

Quando si utilizzano dati serializzati, è necessario specificare i caratteri che separano i valori *all'interno* e *tra* le coppie chiave-valore. Gli elementi nelle coppie chiave-valore sono definiti come segue:

* **** Chiave:Identificatore univoco nella coppia chiave-valore.
* **** Delimitatore di valori: Separa singole coppie chiave-valore.
* **** Separatore chiave-valore: Separa una chiave dai valori all'interno di una coppia chiave-valore.
* **** Separatore seriale: Separa i singoli valori all'interno delle coppie chiave-valore serializzate.

## Elementi chiave e valore serializzati standard {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type (Tipo) </th> 
   <th colname="col2" class="entry"> Esempio  </th> 
   <th colname="col3" class="entry"> Chiave </th> 
   <th colname="col4" class="entry"> Separatore chiave-valore </th> 
   <th colname="col5" class="entry"> Delimitatore chiave-valore </th> 
   <th colname="col6" class="entry"> Separatore seriale </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Tasto singolo</b> <p>(Standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/d </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Coppie chiave-valore</b> <p>(Standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tasto singolo</b> <p>(seriale) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/d </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Coppie</b> chiave-valore (serie) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

