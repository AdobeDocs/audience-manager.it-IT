---
description: Metodi che consentono di elencare a livello di programmazione le aree DCS Audienci Manager.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: Metodi API per le aree geografiche dei DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%

---

# Metodi API per le aree geografiche dei DCS {#dcs-region-api-methods}

Metodi che consentono di elencare a livello di programmazione le aree Audienci Manager [!DNL DCS].

<!-- c_rest_api_regions.xml -->

Per un elenco delle regioni e dei numeri interi corrispondenti, vedere [ID regioni DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elencare una regione DCS specifica {#list-specific-dcs-region}

Un metodo `GET` per elencare un&#39;area specifica di [!DNL DCS].

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

In caso di esito positivo, restituisce `200 OK`.

Per un elenco delle regioni e dei numeri interi corrispondenti, vedere [ID regioni DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elenca aree geografiche DCS {#list-dcs-regions}

Un metodo `GET` per elencare [!DNL DCS] regioni.

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

In caso di esito positivo, restituisce `200 OK`.

Per un elenco delle regioni e dei numeri interi corrispondenti, vedere [ID regioni DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
