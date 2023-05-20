---
description: Questa sezione descrive come analizzare una risposta DCS per recuperare gli ID visitatore e di regione necessari per effettuare chiamate in tempo reale al DCS.
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: Ottenere ID utente e aree geografiche da una risposta DCS
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 15%

---

# Ottenere ID utente e aree geografiche da una risposta DCS {#get-user-ids-and-regions-from-a-dcs-response}

Questa sezione descrive come analizzare una [!DNL DCS] risposta per recuperare gli ID visitatore e area geografica necessari per effettuare chiamate in tempo reale al [!DNL DCS].

## ID utente e regione {#user-region-ids}

A [!DNL DCS] la risposta contiene dati sui visitatori del sito. È necessario disporre del visitatore e dell&#39;ID di regione prima di poter effettuare chiamate server-to-server al [!DNL DCS].

* L’ID utente è necessario per identificare e associare dati a un visitatore specifico.
* L&#39;ID di regione è obbligatorio perché è associato a un nome di server regionale, che è necessario inviare dati al [!DNL DCS]. Il [!DNL DCS] memorizza le informazioni nei data center geograficamente più vicini ai visitatori del sito. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Questi parametri sono descritti di seguito. Codice in *corsivo* rappresenta un segnaposto variabile.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Tipo di dati </th> 
   <th colname="col3" class="entry"> Esempio </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risposta di esempio {#sample-response}

Questa semplice risposta mostra `UUID` e area geografica `ID`. Si tratta solo di dati di esempio. I file di registro potrebbero essere più lunghi e complessi.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Passaggi successivi {#next-steps}

Una volta che hai l’ID utente e il nome del server regionale, puoi iniziare a inviare e ricevere [!DNL DCS] dati. Consulta [Esecuzione di chiamate API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
