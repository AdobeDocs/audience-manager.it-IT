---
description: Questa sezione descrive come analizzare una risposta DCS per recuperare gli ID visitatore e regione necessari per effettuare chiamate in tempo reale al DCS.
seo-description: Questa sezione descrive come analizzare una risposta DCS per recuperare gli ID visitatore e regione necessari per effettuare chiamate in tempo reale al DCS.
seo-title: Ottieni ID utente e regioni da una risposta DCS
solution: Audience Manager
title: Ottieni ID utente e regioni da una risposta DCS
uuid: 08036045-3 b 26-4 d 40-8 e 94-7 d 0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

This section describes how to parse a [!UICONTROL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!UICONTROL DCS].

## User and Region IDs {#user-region-ids}

A [!UICONTROL DCS] response contains data about your site visitors. You need the visitor and region ID before you can make server-to-server calls to the [!UICONTROL DCS].

* L'ID utente è richiesto per identificare e associare dati a un particolare visitatore.
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Questi parametri sono descritti di seguito. Code in *italics* represents a variable placeholder.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Tipo dati </th> 
   <th colname="col3" class="entry"> Esempio  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>" uuid ": <i>ID utente</i></code></span> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p> <code> " uuid ": " 123456789 "</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>" dcs_ region ":<i>ID regione</i></code> </p> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p> <code> " dcs_ region ": 9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risposta di esempio {#sample-response}

This simple response shows the `UUID` and region `ID`. Nota, si tratta di dati di esempio. I file di registro possono essere più lunghi e complessi.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Passaggi successivi {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
