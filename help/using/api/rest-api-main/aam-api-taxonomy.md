---
description: Metodi che consentono di visualizzare la tassonomia comune di Audience Manager. Questo sistema di classificazione opzionale organizza le caratteristiche in categorie standard di settore.
seo-description: Metodi che consentono di visualizzare la tassonomia comune di Audience Manager. Questo sistema di classificazione opzionale organizza le caratteristiche in categorie standard di settore.
seo-title: Metodi API tassonomici
solution: Audience Manager
title: Metodi API tassonomici
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Metodi API tassonomici {#taxonomic-api-methods}

Metodi che consentono di visualizzare la tassonomia comune di Audience Manager. Questo sistema di classificazione opzionale organizza le caratteristiche in categorie standard di settore.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Non è possibile creare nuove categorie tassonomiche o classificare le caratteristiche con questi metodi. Per classificare una caratteristica, specificate la caratteristica appropriata `categoryId` con un metodo di creazione o aggiornamento della caratteristica.

## Restituire una tassonomia specifica {#return-specific-taxonomy}

Un `GET` metodo che restituisce dettagli sulla categoria tassonomica specificata.

<!-- r_rest_api_taxonomy.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Risposta

Una risposta corretta restituisce `200 OK` e la categoria per l’ID specificato. Una richiesta non riuscita restituisce `404 No Content` se l’ID non esiste.

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

## Restituisce tutte le categorie tassonomiche {#return-all-taxonomy-categories}

Un `GET` metodo che restituisce un elenco delle categorie di livello principale in un array.

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

## Sottocategorie tassonomiche {#return-taxonomy-sub-categories}

Un `GET` metodo che restituisce sottocategorie per la categoria principale specificata in un array.

<!-- r_rest_api_taxonomy_sub.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Risposta

Una risposta corretta restituisce `200 OK` e la categoria per l’ID specificato. Una richiesta non riuscita restituisce `404 No Content` se l’ID non esiste. Troncato per brevità.

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
