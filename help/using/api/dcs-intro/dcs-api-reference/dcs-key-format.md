---
description: Quando si effettua una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Leggere questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.
seo-description: Quando si effettua una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Leggere questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.
seo-title: Formattazione delle coppie chiave-valore nelle chiamate DCS
solution: Audience Manager
title: Formattazione delle coppie chiave-valore nelle chiamate DCS
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 1%

---


# Formattazione delle coppie chiave-valore nelle chiamate DCS {#formatting-key-value-pairs-in-dcs-calls}

Quando si effettua una chiamata, l&#39;utente [!DNL DCS] accetta dati chiave-valore in formato standard o serializzato. Leggere questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.

## Coppie chiave e valore serializzato {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di valore chiave </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Esempio  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Una coppia chiave-valore standard è costituita da un singolo tasto e valore. Questa struttura organizza i dati in coppie chiave-valore separate. Ogni chiave viene dichiarata esplicitamente, anche quando viene utilizzata di nuovo per definire un valore diverso. Questo è il modo più comune per inviare i dati al DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serializzato</b> </td> 
   <td colname="col2"> <p>Una coppia chiave-valore serializzata è costituita da una chiave singola e da più valori. Questo può essere un modo efficiente per organizzare i dati, ma le coppie chiave-valore serializzate richiedono simboli specifici per separare ogni chiave e ogni insieme chiave-valore. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimitatori e separatori per coppie chiave-valore serializzate {#delimiters-separators}

Con coppie chiave-valore serializzate, dovete specificare gli indicatori che separano i valori all&#39;interno e tra queste variabili.  Audience Manager richiede i seguenti delimitatori e separatori:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requisiti per </th> 
   <th colname="col2" class="entry"> Simbolo </th> 
   <th colname="col3" class="entry"> Separa individualmente </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Delimitatori</b> </td> 
   <td colname="col2"> Ampersand &amp; </td> 
   <td colname="col3"> <p>Coppie chiave-valore: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Separatori</b> </td> 
   <td colname="col2"> Virgola , </td> 
   <td colname="col3"> <p>Valori nelle coppie chiave-valore: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Inviare dati al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Prefissi e variabili chiave-valore supportati dal DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Spiegazione delle coppie chiave-valore](../../../reference/key-value-pairs-explained.md)

