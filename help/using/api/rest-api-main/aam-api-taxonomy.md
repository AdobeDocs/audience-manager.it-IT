---
description: Metodi che consentono di visualizzare la tassonomia comune di Audience Manager. Questo schema di classificazione facoltativo organizza le caratteristiche in categorie standard di settore.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Metodi API tassonomici
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
TQID: https://experienceleague.adobe.com/LIHEWvF3t-VNHJEviomvCF-dxE2Jy-BFxBynonvwP3w
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 1%

---

# Metodi API tassonomici {#taxonomic-api-methods}

Metodi che consentono di visualizzare la tassonomia comune di Audience Manager. Questo schema di classificazione facoltativo organizza le caratteristiche in categorie standard di settore.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Non è possibile creare nuove categorie tassonomiche o classificare le caratteristiche con questi metodi. Per classificare una caratteristica, specificare il `categoryId` appropriato con un metodo di creazione o aggiornamento della caratteristica.

## Restituire una tassonomia specifica {#return-specific-taxonomy}

Un metodo `GET` che restituisce i dettagli sulla categoria tassonomica specificata.

<!-- r_rest_api_taxonomy.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Risposta

In caso di esito positivo, la risposta restituisce `200 OK` e la categoria per l’ID specificato. Una richiesta non riuscita restituisce `404 No Content` se l&#39;ID non esiste.

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

Un metodo `GET` che restituisce un elenco delle categorie di primo livello in un array.

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

Metodo `GET` che restituisce sottocategorie per la categoria padre specificata in un array.

<!-- r_rest_api_taxonomy_sub.xml -->

### Richiesta

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Risposta

In caso di esito positivo, la risposta restituisce `200 OK` e la categoria per l’ID specificato. Una richiesta non riuscita restituisce `404 No Content` se l&#39;ID non esiste. Troncato per brevità.

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
