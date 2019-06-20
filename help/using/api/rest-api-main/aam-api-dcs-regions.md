---
description: Metodi che consentono di elencare in modo programmatico le regioni DCS di Audience Manager.
seo-description: Metodi che consentono di elencare in modo programmatico le regioni DCS di Audience Manager.
seo-title: Metodi API per regione DCS
solution: Audience Manager
title: Metodi API per regione DCS
uuid: 00 b 70927-b 3 b 7-46 bb -8 be 1-37 c 6100 ecf 80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Metodi API per regione DCS {#dcs-region-api-methods}

Metodi che consentono di elencare in modo programmatico [!UICONTROL DCS] le aree di Audience Manager.

<!-- c_rest_api_regions.xml -->

Per un elenco delle regioni e dei relativi integer, vedi [ID regioni DCS, Posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elenca una regione DCS specifica {#list-specific-dcs-region}

`GET` Un metodo per elencare un&#39;area specifica [!UICONTROL DCS] .

<!-- r_rest_api_regions_list_specific.xml -->

### Richiesta

`GET /v1/dcs-regions/`*`<id>`*

### Risposta di esempio

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Restituisce `200 OK` in caso di esito positivo.

Per un elenco delle regioni e dei relativi integer, vedi [ID regioni DCS, Posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elenca regioni DCS {#list-dcs-regions}

`GET` Un metodo per l&#39;elenco [!UICONTROL DCS] delle aree.

<!-- r_rest_api_regions_list.xml -->

### Richiesta

`GET /v1/dcs-regions/`

### Risposta di esempio

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Restituisce `200 OK` in caso di esito positivo.

Per un elenco delle regioni e dei relativi integer, vedi [ID regioni DCS, Posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
