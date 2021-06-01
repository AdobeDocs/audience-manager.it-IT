---
description: Metodi che consentono di elencare in modo programmatico le aree DCS di Audience Manager.
seo-description: Metodi che consentono di elencare in modo programmatico le aree DCS di Audience Manager.
seo-title: Metodi API per le aree geografiche dei DCS
solution: Audience Manager
title: Metodi API per le aree geografiche dei DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 15%

---

# Metodi API per le aree geografiche dei DCS {#dcs-region-api-methods}

Metodi che consentono di elencare in modo programmatico le aree di Audience Manager [!DNL DCS] .

<!-- c_rest_api_regions.xml -->

Per un elenco delle aree e dei relativi numeri interi, consulta [ID regioni DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elencare un&#39;area geografica specifica DCS {#list-specific-dcs-region}

Un metodo `GET` per elencare una regione specifica [!DNL DCS].

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

Per un elenco delle aree e dei relativi numeri interi, consulta [ID regioni DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Elenca regioni DCS {#list-dcs-regions}

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

Per un elenco delle aree e dei relativi numeri interi, consulta [ID regioni DCS, posizioni e nomi host](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
