---
description: Metodi che consentono di visualizzare la tassonomia Audience Manager. Questo schema di classificazione facoltativo organizza caratteristiche nelle categorie standard di settore.
seo-description: Metodi che consentono di visualizzare la tassonomia Audience Manager. Questo schema di classificazione facoltativo organizza caratteristiche nelle categorie standard di settore.
seo-title: Metodi API Tassonomic
solution: Audience Manager
title: Metodi API Tassonomic
uuid: 4 ee 29 ba 5-e 9 ba -4498-a 6 ee -7343227 dd 7 ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomic API Methods {#taxonomic-api-methods}

Metodi che consentono di visualizzare la tassonomia Audience Manager. Questo schema di classificazione facoltativo organizza caratteristiche nelle categorie standard di settore.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Non è possibile creare nuove categorie tassonomiche né classificare le caratteristiche con questi metodi. To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

`GET` Un metodo che restituisce dettagli sulla categoria tassonomic specificata.

<!-- r_rest_api_taxonomy.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Risposta

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist.

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

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

`GET` Un metodo che restituisce un elenco delle categorie di livello principale in un array.

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

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

`GET` Un metodo che restituisce sottocategorie per la categoria principale specificata in un array.

<!-- r_rest_api_taxonomy_sub.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Risposta

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist. Troncato per brevità.

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
