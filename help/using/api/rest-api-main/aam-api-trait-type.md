---
description: Metodi opzionali che consentono di assegnare caratteristiche a un tipo o una categoria definiti dall'utente, in genere in base alla funzione o per i propri processi di reporting interni.
seo-description: Metodi opzionali che consentono di assegnare caratteristiche a un tipo o una categoria definiti dall'utente, in genere in base alla funzione o per i propri processi di reporting interni.
seo-title: Metodi del tipo di caratteristica
solution: Audience Manager
title: Metodi del tipo di caratteristica
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 4%

---


# Metodi del tipo di caratteristica {#trait-type-methods}

Metodi opzionali che consentono di assegnare caratteristiche a un tipo o una categoria definiti dall&#39;utente, in genere in base alla funzione o per i propri processi di reporting interni.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>I metodi del tipo di caratteristica non assegnano caratteristiche alle categorie utilizzate dalla tassonomia [comune](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Pensate a queste etichette come etichette separate dalla tassonomia comune.

Per riferimento visivo, [!UICONTROL Trait Types] è un controllo a discesa situato nella [!DNL UI] sezione **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Crea nuovo tipo di caratteristica {#create-trait-type}

Metodo `POST` che consente di creare un nuovo tipo di caratteristica.

<!-- r_rest_api_create_trait_type.xml -->

### Richiesta

`POST https://api.demdex.com/v1/customer-trait-types`

### Richiesta di esempio

```
{
"name":"Custom trait type"
}
```

### Risposta

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Proprietà di ritorno per un tipo di caratteristica {#return-props}

Un `GET` metodo che restituisce dettagli sul tipo di caratteristica specificato.

<!-- r_rest_api_get_trait_type.xml -->

### Richiesta

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### Risposta

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Proprietà di restituzione per tutti i tipi di caratteristiche {#return-props-all}

Un `GET` metodo che restituisce dettagli su tutti i tipi di caratteristiche di un array.

<!-- r_rest_api_get_trait_types.xml -->

### Richiesta

`GET https://api.demdex.com/v1/customer-trait-types/`

### Risposta

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
