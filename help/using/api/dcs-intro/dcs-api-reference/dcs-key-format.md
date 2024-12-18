---
description: Quando effettua una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Consulta questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: Formattazione delle coppie chiave-valore nelle chiamate DCS
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Formattazione delle coppie chiave-valore nelle chiamate DCS {#formatting-key-value-pairs-in-dcs-calls}

Durante una chiamata, [!DNL DCS] accetta dati chiave-valore in formato standard o serializzato. Consulta questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.

## Coppie chiave-valore standard e serializzate {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo chiave-valore </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Esempio </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Una coppia chiave-valore standard è costituita da una singola chiave e da un singolo valore. Questa struttura organizza i dati in coppie chiave-valore separate. Ogni chiave viene dichiarata esplicitamente, anche quando viene utilizzata di nuovo per definire un valore diverso. Questo è il modo più comune per inviare dati al DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serializzato</b> </td> 
   <td colname="col2"> <p>Una coppia chiave-valore serializzata è costituita da una singola chiave e da più valori. Questo può essere un modo efficiente per organizzare i dati, ma le coppie chiave-valore serializzate richiedono simboli specifici per separare ogni chiave e ogni set chiave-valore. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimitatori e separatori per coppie chiave-valore serializzate {#delimiters-separators}

Con le coppie chiave-valore serializzate, devi specificare gli indicatori che separano i valori all&#39;interno e tra queste variabili. L&#39;Audience Manager richiede i delimitatori e i separatori seguenti:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requisiti per </th> 
   <th colname="col2" class="entry"> Simbolo </th> 
   <th colname="col3" class="entry"> Separa singoli </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimitatori</b> </td> 
   <td colname="col2"> E commerciale e </td> 
   <td colname="col3"> <p>Coppie chiave-valore: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separatori</b> </td> 
   <td colname="col2"> Virgola , </td> 
   <td colname="col3"> <p>Valori all’interno di coppie chiave-valore: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Inviare dati al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Prefissi chiave-valore e variabili supportati dal DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Spiegazione delle coppie chiave-valore](../../../reference/key-value-pairs-explained.md)
