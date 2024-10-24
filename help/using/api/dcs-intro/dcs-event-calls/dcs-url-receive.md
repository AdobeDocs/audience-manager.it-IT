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
ht-degree: 1%

---

# Ricevere dati dal DCS {#receive-data-from-the-dcs}

Continuare qui per informazioni su come richiedere una risposta [!DNL DCS] in una chiamata `/event`. Questa sezione include un esempio di risposta e le definizioni per gli elementi dati comuni in una risposta.

Prima di esaminare questo contenuto, vedi [Inviare dati al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parametri di risposta DCS: una revisione {#dcs-response-parameters}

La richiesta di [!DNL DCS] deve includere `d_rtbd=json` se si desidera ricevere una risposta da [!DNL DCS]. [!DNL DCS] non restituirà dati se si omette questo parametro. Una chiamata di base a [!DNL DCS] per richiedere i dati utilizza questa sintassi:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Risposta di esempio {#sample-response}

Ricorda che dalla documentazione di [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), l&#39;azienda fittizia [!DNL Acme, Inc.] ha effettuato questa chiamata:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Poiché questa chiamata include il parametro di risposta richiesto, [!DNL DCS] ha restituito l&#39;oggetto [!DNL JSON] mostrato di seguito. Può essere simile o più complesso.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parametri di risposta {#response-parameters}

La tabella seguente elenca e definisce i parametri più comuni che è possibile visualizzare in una risposta di [!DNL DCS]. Ciò si applica alle chiamate evento o ad altre query [!DNL DCS] [!DNL API] che restituiscono dati.

| Parametro | Descrizione |
|--- |--- |
| `c` | URL impostato come [destinazione URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Nome o ID impostato nel campo del nome cookie di una [destinazione cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | I valori inviati alla destinazione definita dal parametro &quot;cn&quot;: &quot;nome destinazione&quot;. |
| `dcs_region` | [chiamate DCS server-to-server](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Questo oggetto contiene informazioni per tutte le destinazioni URL configurate nell’interfaccia utente. L’elenco di questo oggetto è dinamico in base alle azioni dell’utente. |
| `dmn` | Si tratta del dominio specificato nel campo Dominio cookie per una destinazione cookie. Consulta [Impostazioni facoltative per le destinazioni cookie](../../../features/destinations/cookie-destination-options.md).  Per le integrazioni server-to-server si consiglia di utilizzare un dominio come `aam-api.com`. |
| `e` | L’URL protetto che è stato impostato in una destinazione URL. |
| `stuff` | Questo oggetto contiene informazioni per tutte le destinazioni cookie. L’elenco di questo oggetto è dinamico in base alle azioni dell’utente. |
| `tid` | ID transazione, un ID univoco di 12 caratteri utilizzato a scopo di debug. Ogni chiamata /event al DCS riceve un tid a cui è possibile fare riferimento nelle richieste di supporto per ottenere una risposta migliore e più rapida. |
| `ttl` | Il valore time-to-live dei cookie in giorni. |
| `u` e `uuid` | ID utente univoco assegnato dall’Audience Manager. Questa operazione è necessaria se si stanno effettuando [chiamate DCS server-to-server](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo di destinazione, iFrame (`iframe`) o immagine (`img`). |

>[!MORELIKETHIS]
>
>* [Prefissi chiave-valore e variabili supportati dal DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
