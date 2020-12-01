---
description: Metodi che consentono di elencare a livello di programmazione  aree DCS Audienci Manager.
seo-description: Metodi che consentono di elencare a livello di programmazione  aree DCS Audienci Manager.
seo-title: Metodi API per le aree geografiche dei DCS
solution: Audience Manager
title: Metodi API per le aree geografiche dei DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 14%

---


# Metodi API per le aree geografiche dei DCS {#dcs-region-api-methods}

Metodi che consentono di elencare a livello di programmazione  aree di Audience Manager [!DNL DCS].

<!-- c_rest_api_regions.xml -->

Per un elenco delle aree e dei relativi numeri interi, vedere [ID regione DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elenca una specifica regione DCS {#list-specific-dcs-region}

Un metodo `GET` per elencare una regione [!DNL DCS] specifica.

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

Per un elenco delle aree e dei relativi numeri interi, vedere [ID regione DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elenca aree DCS {#list-dcs-regions}

Un metodo `GET` per elencare le aree [!DNL DCS].

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

Per un elenco delle aree e dei relativi numeri interi, vedere [ID regione DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
