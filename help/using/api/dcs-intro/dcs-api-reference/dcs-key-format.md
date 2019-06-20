---
description: Quando effettuano una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Consultate questa sezione per informazioni su come formattare i dati chiave-valore standard e serializzati.
seo-description: Quando effettuano una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Consultate questa sezione per informazioni su come formattare i dati chiave-valore standard e serializzati.
seo-title: Formattazione delle coppie chiave-valore in DCS Chiamate
solution: Audience Manager
title: Formattazione delle coppie chiave-valore in DCS Chiamate
uuid: af 02 f 2 a 1-4388-4074-ab 4 e -66 ee 82023 f 1 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formattazione delle coppie chiave-valore in DCS Chiamate {#formatting-key-value-pairs-in-dcs-calls}

Durante una chiamata, i [!UICONTROL DCS] dati chiave-valore accettano in formato standard o serializzato. Consultate questa sezione per informazioni su come formattare i dati chiave-valore standard e serializzati.

## Standard e coppie chiave-valore serializzate {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo chiave chiave </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Esempio  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Una coppia chiave-valore standard è composta da una singola chiave e un singolo valore. Questa struttura organizza i dati in coppie chiave-valore separate. Ogni chiave viene definita esplicitamente, anche quando viene utilizzata di nuovo per definire un altro valore. Questo è il modo più comune per inviare dati al DCS. </p> </td>
   <td colname="col3"> <code> key 1 = val 1 &amp; key 2 = val 2 &amp; key 3 = val 3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serializzato</b> </td> 
   <td colname="col2"> <p>Una coppia chiave-valore serializzata è composta da una singola chiave e da più valori. Questo può essere un modo efficiente per organizzare i dati, ma le coppie chiave-valore serializzate richiedono simboli specifici per separare ogni chiave e ciascun set chiave-valore. </p> </td> 
   <td colname="col3"> <code> key 1 = val 1, val 2, val 3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimitatori e separatori per coppie chiave-valore serializzate {#delimiters-separators}

Con coppie chiave-valore serializzate, è necessario specificare i marcatori che separano i valori all&#39;interno e tra queste variabili. Audience Manager richiede i seguenti delimitatori e separatori:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requisiti per </th> 
   <th colname="col2" class="entry"> Simbolo </th> 
   <th colname="col3" class="entry"> Separa individui </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimitatori</b> </td> 
   <td colname="col2"> Ampersand &amp; e </td> 
   <td colname="col3"> <p>Coppie chiave-valore: </p> <p><code> key 1 = val 1 &amp; key 2 = val 2, val 3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separatori</b> </td> 
   <td colname="col2"> Virgola, </td> 
   <td colname="col3"> <p>Valori all'interno delle coppie chiave-valore: </p> <p><code> key 1 = val 1, val 2, val 3 &amp; key 2 = vala, valb, valc</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Inviare dati al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Prefissi chiave chiave e variabili supportate dal DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Coppie chiave-valore spiegate](../../../reference/key-value-pairs-explained.md)

