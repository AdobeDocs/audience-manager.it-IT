---
description: Per informazioni su come richiedere una risposta DCS in una chiamata /event, continuate qui. Questa sezione include un esempio di risposta e definizioni per gli elementi dati comuni di una risposta.
seo-description: Per informazioni su come richiedere una risposta DCS in una chiamata /event, continuate qui. Questa sezione include un esempio di risposta e definizioni per gli elementi dati comuni di una risposta.
seo-title: Ricevere dati dal DCS
solution: Audience Manager
title: Ricevere dati dal DCS
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. Questa sezione include un esempio di risposta e definizioni per gli elementi dati comuni di una risposta.

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS Response Parameters: A Review {#dcs-response-parameters}

Your [!UICONTROL DCS] request must include `d_rtbd=json` if you want to receive a response from the [!UICONTROL DCS]. The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

## Risposta di esempio {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. Il vostro potrebbe essere simile o più complesso.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parametri di risposta {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| Parametro | Descrizione |
|--- |--- |
| `c` | A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination). |
| `cn` | The name or ID set in the cookie name field of a [cookie destination](../../../features/destinations/manage-destinations.md#create-cookie-destination). |
| `cv` | I valori inviati alla destinazione definita dalla "cn": " destinaton name ". |
| `dcs_region` | The [server-to-server DCS calls](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Questo oggetto contiene informazioni per tutte le destinazioni URL configurate nell'interfaccia utente. L'elenco di questo oggetto è dinamico in base alle azioni dell'utente. |
| `dmn` | Questo è il dominio specificato nel campo Dominio cookie per una destinazione del cookie. See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`. |
| `e` | L'URL protetto impostato in una destinazione URL. |
| `stuff` | Questo oggetto contiene informazioni per tutte le destinazioni dei cookie. L'elenco di questo oggetto è dinamico in base alle azioni dell'utente. |
| `tid` | ID transazione, ID univoco di 12 caratteri utilizzato a scopo di debug. Ogni chiamata /event al DCS riceve un tid a cui potete fare riferimento nel supporto per una risposta migliore e più rapida. |
| `ttl` | Il valore time-to-live del cookie in giorni. |
| `u` e `uuid` | ID utente univoco assegnato da Audience Manager. This is required if you're making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Prefissi chiave chiave e variabili supportate dal DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

