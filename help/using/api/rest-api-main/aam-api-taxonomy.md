---
description: Metodi che consentono di visualizzare l’Audience Manager di tassonomia comune. Questo schema di classificazione facoltativo organizza le caratteristiche in categorie standard di settore.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Metodi API tassonomici
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 6%

---

# Metodi API tassonomici {#taxonomic-api-methods}

Metodi che consentono di visualizzare l’Audience Manager di tassonomia comune. Questo schema di classificazione facoltativo organizza le caratteristiche in categorie standard di settore.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Non è possibile creare nuove categorie tassonomiche o classificare le caratteristiche con questi metodi. Per classificare una caratteristica, specifica la `categoryId` con un metodo di creazione o aggiornamento delle caratteristiche.

## Restituire una tassonomia specifica {#return-specific-taxonomy}

A `GET` metodo che restituisce dettagli sulla categoria tassonomica specificata.

<!-- r_rest_api_taxonomy.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Risposta

In caso di esito positivo, la risposta restituisce `200 OK` e la categoria per l’ID specificato. Viene restituita una richiesta non riuscita `404 No Content` se l’ID non esiste.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## Restituisci tutte le categorie tassonomiche {#return-all-taxonomy-categories}

A `GET` che restituisce un elenco delle categorie di primo livello in un array.

<!-- r_rest_api_taxonomies.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`

### Risposta

Troncato per brevità.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## Restituisci sottocategorie tassonomiche {#return-taxonomy-sub-categories}

A `GET` metodo che restituisce sottocategorie per la categoria padre specificata in un array.

<!-- r_rest_api_taxonomy_sub.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Risposta

In caso di esito positivo, la risposta restituisce `200 OK` e la categoria per l’ID specificato. Viene restituita una richiesta non riuscita `404 No Content` se l’ID non esiste. Troncato per brevità.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
