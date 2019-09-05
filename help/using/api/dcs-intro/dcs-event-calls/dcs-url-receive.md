---
description: Per informazioni su come richiedere una risposta DCS in una chiamata /event, continuate qui. Questa sezione include un esempio di risposta e definizioni per gli elementi dati comuni di una risposta.
seo-description: Per informazioni su come richiedere una risposta DCS in una chiamata /event, continuate qui. Questa sezione include un esempio di risposta e definizioni per gli elementi dati comuni di una risposta.
seo-title: Ricevere dati dal DCS
solution: Audience Manager
title: Ricevere dati dal DCS
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Ricevere dati dal DCS {#receive-data-from-the-dcs}

Per informazioni su come richiedere una [!UICONTROL DCS] risposta in `/event` una chiamata, continuate qui. Questa sezione include un esempio di risposta e definizioni per gli elementi dati comuni di una risposta.

Prima di rivedere il contenuto, vedi [Invia dati al DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parametri di risposta DCS: Una revisione {#dcs-response-parameters}

La [!UICONTROL DCS] richiesta deve includere `d_rtbd=json` se desiderate ricevere una risposta dall ' [!UICONTROL DCS]. Se [!UICONTROL DCS] si omette questo parametro, i dati non vengono restituiti. Una chiamata di base ai [!UICONTROL DCS] dati di richiesta utilizza questa sintassi:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Risposta di esempio {#sample-response}

Ricorda che, dall' [invio di dati alla](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentazione DCS, l'azienda fittizia ha [!DNL Acme, Inc.] fatto questa chiamata:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Poiché questa chiamata include il parametro di risposta richiesto, l' [!UICONTROL DCS][!DNL JSON] oggetto riportato di seguito viene restituito. Il vostro potrebbe essere simile o più complesso.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parametri di risposta {#response-parameters}

Nella tabella seguente sono elencati e definiti i parametri più comuni che si possono vedere in una risposta dall ' [!UICONTROL DCS]. Ciò si applica alle chiamate dell'evento o ad altre [!UICONTROL DCS][!DNL API] query che restituiscono dati.

| Parametro | Descrizione |
|--- |--- |
| `c` | Un URL impostato come destinazione [URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Nome o ID impostato nel campo nome del cookie di una [destinazione del cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | I valori inviati alla destinazione definita dalla "cn": " destinaton name ". |
| `dcs_region` | Le chiamate DCS [server-to-server](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Questo oggetto contiene informazioni per tutte le destinazioni URL configurate nell'interfaccia utente. L'elenco di questo oggetto è dinamico in base alle azioni dell'utente. |
| `dmn` | Questo è il dominio specificato nel campo Dominio cookie per una destinazione del cookie. Consultate [Impostazioni facoltative per destinazioni cookie](../../../features/destinations/cookie-destination-options.md). Per le integrazioni Server, consigliamo di utilizzare un dominio come `aam-api.com`. |
| `e` | L'URL protetto impostato in una destinazione URL. |
| `stuff` | Questo oggetto contiene informazioni per tutte le destinazioni dei cookie. L'elenco di questo oggetto è dinamico in base alle azioni dell'utente. |
| `tid` | ID transazione, ID univoco di 12 caratteri utilizzato a scopo di debug. Ogni chiamata /event al DCS riceve un tid a cui potete fare riferimento nel supporto per una risposta migliore e più rapida. |
| `ttl` | Il valore time-to-live del cookie in giorni. |
| `u` e `uuid` | ID utente univoco assegnato da Audience Manager. Questa funzione è necessaria se state effettuando [chiamate DCS server-to-server](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo di destinazione, iframe (`iframe`) o immagine (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Prefissi chiave chiave e variabili supportate dal DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

