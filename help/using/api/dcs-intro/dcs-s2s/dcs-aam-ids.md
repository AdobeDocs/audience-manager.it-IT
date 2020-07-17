---
description: Questa sezione descrive come analizzare una risposta DCS per recuperare gli ID visitatore e regione richiesti per effettuare chiamate in tempo reale al DCS.
seo-description: Questa sezione descrive come analizzare una risposta DCS per recuperare gli ID visitatore e regione richiesti per effettuare chiamate in tempo reale al DCS.
seo-title: Ottenere ID utente e aree geografiche da una risposta DCS
solution: Audience Manager
title: Ottenere ID utente e aree geografiche da una risposta DCS
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 17%

---


# Ottenere ID utente e aree geografiche da una risposta DCS {#get-user-ids-and-regions-from-a-dcs-response}

Questa sezione descrive come analizzare una [!DNL DCS] risposta per recuperare gli ID visitatore e regione richiesti per effettuare chiamate in tempo reale al visitatore [!DNL DCS].

## ID utente e regione {#user-region-ids}

Una [!DNL DCS] risposta contiene i dati sui visitatori del sito. Prima di effettuare chiamate server-to-server al [!DNL DCS], è necessario disporre dell’ID visitatore e dell’ID di regione.

* L&#39;ID utente è necessario per identificare e associare i dati a un particolare visitatore.
* L&#39;ID di regione è obbligatorio perché è associato a un nome di server regionale, che è necessario inviare ai [!DNL DCS]. Le informazioni [!DNL DCS] vengono memorizzate nei centri dati geograficamente più vicini ai visitatori del sito. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Questi parametri sono descritti di seguito. Il codice in *corsivo* rappresenta un segnaposto variabile.

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
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Risposta di esempio {#sample-response}

Questa semplice risposta mostra la `UUID` regione `ID`. Nota: si tratta solo di dati di esempio. I file di registro potrebbero essere più lunghi e complessi.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Passaggi successivi {#next-steps}

Una volta ottenuto l&#39;ID utente e il nome del server regionale, potete iniziare a inviare e ricevere [!DNL DCS] i dati. Consultate [Effettuare chiamate](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)DCS API.
