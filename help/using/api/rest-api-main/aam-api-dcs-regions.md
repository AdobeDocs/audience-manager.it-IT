---
description: Metodi che consentono di elencare a livello di programmazione le aree DCS di Audience Manager.
seo-description: Metodi che consentono di elencare a livello di programmazione le aree DCS di Audience Manager.
seo-title: Metodi API per regione DCS
solution: Audience Manager
title: Metodi API per regione DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Metodi API per regione DCS {#dcs-region-api-methods}

Metodi che consentono di elencare a livello di programmazione [!UICONTROL DCS] le aree di Audience Manager.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elenca una specifica area DCS {#list-specific-dcs-region}

Un `GET` metodo per elencare una [!UICONTROL DCS] regione specifica.

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

Restituisce `200 OK` se ha esito positivo.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elenca regioni DCS {#list-dcs-regions}

Un `GET` metodo per elencare [!UICONTROL DCS] le aree.

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

Restituisce `200 OK` se ha esito positivo.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
