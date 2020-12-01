---
description: Per informazioni su come richiedere una risposta DCS in una chiamata /event, fate clic qui. Questa sezione include un esempio di risposta e le definizioni per gli elementi dati comuni in una risposta.
seo-description: Per informazioni su come richiedere una risposta DCS in una chiamata /event, fate clic qui. Questa sezione include un esempio di risposta e le definizioni per gli elementi dati comuni in una risposta.
seo-title: Ricevere dati dal DCS
solution: Audience Manager
title: Ricevere dati dal DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# Ricevere dati dal DCS {#receive-data-from-the-dcs}

Per informazioni su come richiedere una risposta [!DNL DCS] in una chiamata `/event`, fare clic qui. Questa sezione include un esempio di risposta e le definizioni per gli elementi dati comuni in una risposta.

Prima di consultare il contenuto, vedere [Invia dati a DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Parametri di risposta DCS: Revisione {#dcs-response-parameters}

La richiesta [!DNL DCS] deve includere `d_rtbd=json` se si desidera ricevere una risposta da [!DNL DCS]. Se si omette questo parametro, la [!DNL DCS] non restituirà i dati. Una chiamata di base a [!DNL DCS] per richiedere i dati utilizza la sintassi seguente:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Risposta di esempio {#sample-response}

Ricordate che dalla [Invia dati alla documentazione DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), la società fittizia [!DNL Acme, Inc.] ha effettuato questa chiamata:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Poiché questa chiamata include il parametro di risposta richiesto, l&#39;oggetto [!DNL DCS] ha restituito l&#39;oggetto [!DNL JSON] indicato di seguito. Il tuo può essere simile o più complesso.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Parametri di risposta {#response-parameters}

La tabella seguente elenca e definisce i parametri più comuni che si possono vedere in una risposta da [!DNL DCS]. Ciò vale per le chiamate di eventi o altre [!DNL DCS] [!DNL API] query che restituiscono dati.

| Parametro | Descrizione |
|--- |--- |
| `c` | Un URL impostato come [destinazione URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Nome o ID impostato nel campo del nome del cookie di una [destinazione del cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | I valori inviati alla destinazione definita dal parametro &quot;cn&quot;:&quot; target name&quot;. |
| `dcs_region` | Chiamate [server-to-server DCS](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Questo oggetto contiene informazioni per tutte le destinazioni URL configurate nell&#39;interfaccia utente. L&#39;elenco di questo oggetto è dinamico in base alle azioni dell&#39;utente. |
| `dmn` | Si tratta del dominio specificato nel campo Dominio cookie per una destinazione di cookie. Vedere [Impostazioni facoltative per le destinazioni dei cookie](../../../features/destinations/cookie-destination-options.md).  Per le integrazioni da server a server si consiglia di utilizzare un dominio come `aam-api.com`. |
| `e` | L&#39;URL protetto che è stato impostato in una destinazione URL. |
| `stuff` | Questo oggetto contiene informazioni per tutte le destinazioni Cookie. L&#39;elenco di questo oggetto è dinamico in base alle azioni dell&#39;utente. |
| `tid` | ID transazione, un ID univoco di 12 caratteri utilizzato per il debug. Ogni chiamata /event al DCS riceve un titolo a cui potete fare riferimento nelle richieste di supporto per una risposta migliore e più rapida. |
| `ttl` | Il valore time-to-live del cookie in giorni. |
| `u` e `uuid` | ID utente univoco assegnato dal Audience Manager . Questo è necessario se si effettuano [chiamate DCS da server a server](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Tipo di destinazione, iFrame (`iframe`) o immagine (`img`). |

>[!MORELIKETHIS]
>
>* [Prefissi e variabili chiave-valore supportati dal DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

