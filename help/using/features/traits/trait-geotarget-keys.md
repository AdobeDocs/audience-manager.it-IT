---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per eseguire il targeting degli utenti con variabili geografiche in tutte le proprietà dell'account Audience Manager.
seo-description: Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per eseguire il targeting degli utenti con variabili geografiche in tutte le proprietà dell'account Audience Manager.
seo-title: Geotargeting with Platform-level Keys
solution: Audience Manager
title: Geotargeting with Platform-level Keys
uuid: c 7 e 4 cbfe-e 564-404 e-a 565-bbe 5 fd 2 fb 519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per eseguire il targeting degli utenti con variabili geografiche in tutte le proprietà dell'account Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#platform-variables}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#adding-values}

Per alcune chiavi a livello di piattaforma, potete specificare il valore stesso. With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#user-defined-keys}

Il valore viene specificato quando si creano caratteristiche con queste coppie chiave-valore:

| Chiave | Per il targeting |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Platform Level Keys Defined by IP Address {#keys-ip-address}

We work with [Digital Envoy](https://www.digitalenvoy.com/) to obtain and update the demographic and geographic data for the keys below. The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you'll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| Chiave | Per il targeting |
|--- |--- |
| d_ area_ code | [Codici Area del Nord America](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes). Ad esempio: <ul><li>**Caratteristica**: d_ area_ code = 801</li><li>**Nome caratteristica**: Utah</li></ul> |
| d_ city | Città e città. Download the [cities list](assets/d_city.txt).  Ad esempio: <ul><li>Caratteristica: d_ city = bonn</li><li>Nome caratteristica: Bonn</li></ul> **Suggerimento**: Puoi usare `d_city` abbinata `d_country` per assicurarti di non destinare due città con lo stesso nome in diversi paesi. You can be even more specific in your targeting by using `d_postal_code`. |
| d_ country | I valori corrispondono ai codici dei paesi ISO. For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>Il targeting per il Regno Unito è l'unico caso speciale che non rispetta ISO 3166. Dovete utilizzare "UK" invece di "GB" per il targeting nel Regno Unito. Per eseguire il targeting delle Antille olandesi, il codice "AN" è stato dichiarato obsoleto dal 2010. L'area è stata dissolvita in cinque unità territoriali separate. L'implicazione prevede che per il targeting nelle Antille olandesi non venga utilizzato "AN", ma una combinazione dei codici dei Paesi per "CW", "SX" e "BQ." For example:  <br>  Trait:  d_country=CZ  <br>  Trait Name: Czech Republic <br>  Trait:  d_country=UK <br>  Trait Name: United Kingdom  <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>  Trait Name: Netherlands Antilles |
| d_ dma_ code | Codici DMA delle aree metropolitane. Download the [DMA region list](assets/DMAregions.csv) (.csv format).  Ad esempio: <ul><li>Caratteristica: d_ dma_ code = 807</li><li>Nome caratteristica: San Francisco</li></ul> |
| d_ lat | Latitudine (ad es. d_ lat = 40.75). Download the [latitudes list](assets/d_lat.txt). |
| d_ long | Longitudine (ad es. d_ long = 73.98). Download the [longitudes list](assets/d_long.txt). |
| d_ postal_ code | Codici ZIP (escludi il codice esteso +4). Download the  [postal codes list](assets/d_postal_code.txt).  Ad esempio: <ul><li>Caratteristica: d_ postal_ code = 84004 </li><li>Nome caratteristica: Alpini</li></ul> |
| d_ state | Abbreviazione di 2 caratteri per uno stato USA. Download the [states codes list](assets/d_state.txt).  Ad esempio: <ul><li>Caratteristica: d_ state = NY </li><li>Nome caratteristica: New York</li></ul>d_ state contiene valori ripetuti per stati diversi nei diversi paesi. Ad esempio, d_ state = = "on" corrisponde a più stati: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibia). È consigliabile associare questo segnale ad altri, ad esempio d_ country per il geotargeting più specifico. |
| d_ region | ID alfanumerici regionali. Download the [region list](assets/Country_RegionCodes_City.csv).  Quindi, potete usare questo elenco per associare gli ID di regione ai nomi delle aree. |
| d_ isp | ISP/organizzazione. Download the [ISP List](assets/d_isp.txt). |

The list of [all location-based signals](assets/all.csv) comprises all the signals above, in the following order: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ LIKE_ THIS]
>
>* [Requisiti di prefisso per variabili chiave](../../features/traits/trait-variable-prefixes.md)

