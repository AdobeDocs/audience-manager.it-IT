---
description: Continua qui per informazioni su come richiedere una risposta DCS in una chiamata /event. Questa sezione include un esempio di risposta e le definizioni per gli elementi dati comuni in una risposta.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Ricevere dati dal DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 4%

---

# Ricevere dati dal DCS {#receive-data-from-the-dcs}

Continua qui per informazioni su come richiedere un [!DNL DCS] risposta in un `/event` chiamare. Questa sezione include un esempio di risposta e le definizioni per gli elementi dati comuni in una risposta.

Prima di esaminare questo contenuto, consulta [Inviare dati al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parametri di risposta DCS: una revisione {#dcs-response-parameters}

Il tuo [!DNL DCS] la richiesta deve includere `d_rtbd=json` se desideri ricevere una risposta da [!DNL DCS]. Il [!DNL DCS] non restituirà dati se si omette questo parametro. Una chiamata di base al [!DNL DCS] per richiedere i dati utilizza la seguente sintassi:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Risposta di esempio {#sample-response}

Ricordalo dalla sezione [Inviare dati al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentazione, l&#39;azienda fittizia [!DNL Acme, Inc.] ha fatto questa chiamata:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Poiché questa chiamata include il parametro di risposta richiesto, il [!DNL DCS] ha restituito il [!DNL JSON] oggetto mostrato di seguito. Può essere simile o più complesso.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parametri di risposta {#response-parameters}

La tabella seguente elenca e definisce i parametri più comuni che è possibile visualizzare in una risposta da [!DNL DCS]. Questo si applica alle chiamate evento o ad altri [!DNL DCS] [!DNL API] query che restituiscono dati.

| Parametro | Descrizione |
|--- |--- |
| `c` | Un URL impostato come [Destinazione URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Il nome o l’ID impostato nel campo del nome del cookie di una [destinazione cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | I valori inviati alla destinazione definita dal parametro &quot;cn&quot;: &quot;nome destinazione&quot;. |
| `dcs_region` | Il [chiamate DCS server-to-server](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Questo oggetto contiene informazioni per tutte le destinazioni URL configurate nell’interfaccia utente. L’elenco di questo oggetto è dinamico in base alle azioni dell’utente. |
| `dmn` | Si tratta del dominio specificato nel campo Dominio cookie per una destinazione cookie. Consulta [Impostazioni facoltative per le destinazioni cookie](../../../features/destinations/cookie-destination-options.md).  Per le integrazioni server-to-server si consiglia di utilizzare un dominio come `aam-api.com`. |
| `e` | L’URL protetto che è stato impostato in una destinazione URL. |
| `stuff` | Questo oggetto contiene informazioni per tutte le destinazioni cookie. L’elenco di questo oggetto è dinamico in base alle azioni dell’utente. |
| `tid` | ID transazione, un ID univoco di 12 caratteri utilizzato a scopo di debug. Ogni chiamata /event al DCS riceve un tid a cui è possibile fare riferimento nelle richieste di supporto per ottenere una risposta migliore e più rapida. |
| `ttl` | Il valore time-to-live dei cookie in giorni. |
| `u` e `uuid` | ID utente univoco assegnato dall’Audience Manager. Questo è necessario se si sta creando [chiamate DCS server-to-server](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo di destinazione, iFrame (`iframe`) o immagine (`img`). |

>[!MORELIKETHIS]
>
>* [Prefissi chiave-valore e variabili supportati dal DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

