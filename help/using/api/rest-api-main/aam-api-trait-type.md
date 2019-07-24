---
description: Metodi facoltativi che consentono di assegnare caratteristiche a un tipo o a una categoria definita dall'utente, in genere in base alla funzione o ai processi di reporting interni.
seo-description: Metodi facoltativi che consentono di assegnare caratteristiche a un tipo o a una categoria definita dall'utente, in genere in base alla funzione o ai processi di reporting interni.
seo-title: Metodi del tipo Trait
solution: Audience Manager
title: Metodi del tipo Trait
uuid: 082931 d 5-457 b -4622-817 b -86303 f 38 c 26 a
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Trait Type Methods {#trait-type-methods}

Metodi facoltativi che consentono di assegnare caratteristiche a un tipo o a una categoria definita dall'utente, in genere in base alla funzione o ai processi di reporting interni.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trait type methods do not assign traits to categories used by the [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Queste etichette sono considerate come etichette separate dalla tassonomia comune.

For visual reference, [!UICONTROL Trait Types] is a dropdown control located in the [!DNL UI] under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Create a New Trait Type {#create-trait-type}

`POST` Metodo che consente di creare un nuovo tipo di caratteristica.

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

## Return Properties for a Trait Type {#return-props}

`GET` Un metodo che restituisce dettagli sul tipo di caratteristica specificato.

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

## Return Properties for all Trait Types {#return-props-all}

`GET` Un metodo che restituisce dettagli su tutti i tipi di caratteristiche in un array.

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
