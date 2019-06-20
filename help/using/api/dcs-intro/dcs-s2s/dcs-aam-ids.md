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


# Ottieni ID utente e regioni da una risposta DCS {#get-user-ids-and-regions-from-a-dcs-response}

Questa sezione descrive come analizzare una [!UICONTROL DCS] risposta per recuperare gli ID visitatore e regione necessari per effettuare chiamate in tempo reale all &#39; [!UICONTROL DCS].

## ID utente e regione {#user-region-ids}

Una [!UICONTROL DCS] risposta contiene dati sui visitatori del sito. È necessario disporre del visitatore e dell&#39;ID di regione prima di poter effettuare chiamate server-to-server al [!UICONTROL DCS].

* L&#39;ID utente è richiesto per identificare e associare dati a un particolare visitatore.
* L&#39;ID di regione è richiesto perché è associato a un nome server regionale, che è necessario inviare a [!UICONTROL DCS]tale nome. Le [!UICONTROL DCS] informazioni memorizzano informazioni nei centri dati geograficamente più vicini ai visitatori del sito. Consulta [ID regioni DCS, posizioni e nomi host](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Questi parametri sono descritti di seguito. Il codice in *corsivo* rappresenta un segnaposto variabile.

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

Questa semplice risposta mostra l&#39;area `UUID` e l&#39;area `ID`. Nota, si tratta di dati di esempio. I file di registro possono essere più lunghi e complessi.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Passaggi successivi {#next-steps}

Una volta ottenuto l&#39;ID utente e il nome del server regionale, puoi iniziare a inviare e ricevere [!UICONTROL DCS] dati. Consultate [Creazione di chiamate DCS API](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
