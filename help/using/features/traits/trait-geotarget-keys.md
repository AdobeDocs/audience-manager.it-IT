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


# Geotargeting with Platform-level Keys {#geotargeting-with-platform-level-keys}

Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per eseguire il targeting degli utenti con variabili geografiche in tutte le proprietà dell&#39;account Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Scopo delle variabili a livello di piattaforma {#platform-variables}

Le variabili a livello di piattaforma consentono di prendere dati trasmessi da un particolare sito e renderli disponibili per il targeting in tutte le proprietà dell&#39; [!DNL Audience Manager] account. Queste variabili sono formate da [coppie chiave-valore](../../reference/key-value-pairs-explained.md) con la chiave prefissa, `d_` come mostrato di seguito.

## Aggiunta di valori a chiavi livello piattaforma {#adding-values}

Per alcune chiavi a livello di piattaforma, potete specificare il valore stesso. Con altri, le chiavi sono associate agli indirizzi corrispondenti [!DNL IP] trasmessi in una chiamata evento. In entrambi i casi, è comunque necessario specificare il valore al momento della creazione delle caratteristiche [!UICONTROL Trait Builder].

## Chiavi definite dall&#39;utente a livello di piattaforma {#user-defined-keys}

Il valore viene specificato quando si creano caratteristiche con queste coppie chiave-valore:

| Chiave | Per il targeting |
|---|---|
| `d_zx` | Codice ZIP (ad es., `d_zx=10022`). |

## Tasti a livello piattaforma definiti dall&#39;indirizzo IP {#keys-ip-address}

Collaboriamo [con Digital Emissy](https://www.digitalenvoy.com/) per ottenere e aggiornare i dati demografici e geografici per le chiavi riportate di seguito. I valori di queste chiavi sono determinati da [!DNL IP] indirizzi corrispondenti ai dati geografici e demografici corrispondenti. Tuttavia, al momento della creazione della coppia chiave-valore in [!UICONTROL Trait Builder].

| Chiave | Per il targeting |
|--- |--- |
| d_ area_ code | [Codici Area del Nord America](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes). Ad esempio: <ul><li>**Caratteristica**: d_ area_ code = 801</li><li>**Nome caratteristica**: Utah</li></ul> |
| d_ city | Città e città. Scaricate l&#39;elenco [delle città](assets/d_city.txt). Ad esempio: <ul><li>Caratteristica: d_ city = bonn</li><li>Nome caratteristica: Bonn</li></ul> **Suggerimento**: Puoi usare `d_city` abbinata `d_country` per assicurarti di non destinare due città con lo stesso nome in diversi paesi. You can be even more specific in your targeting by using `d_postal_code`. |
| d_ country | I valori corrispondono ai codici dei paesi ISO. Per un elenco di codici ricercabile, consultate la piattaforma [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>Il targeting per il Regno Unito è l&#39;unico caso speciale che non rispetta ISO 3166. Dovete utilizzare &quot;UK&quot; invece di &quot;GB&quot; per il targeting nel Regno Unito. Per eseguire il targeting delle Antille olandesi, il codice &quot;AN&quot; è stato dichiarato obsoleto dal 2010. L&#39;area è stata dissolvita in cinque unità territoriali separate. L&#39;implicazione prevede che per il targeting nelle Antille olandesi non venga utilizzato &quot;AN&quot;, ma una combinazione dei codici dei Paesi per &quot;CW&quot;, &quot;SX&quot; e &quot;BQ.&quot; Ad esempio: <br>Caratteristica: d_ country = CZ  <br>Trait Name: <br>Caratteristica Repubblica Ceca: d_ country = UK  <br>Trait Name: United Kingdom  <br>Trait: d_ country = CW OR d_ country = SX OR d_ country = BQ  <br>Trait Name: Antille olandesi |
| d_ dma_ code | Codici DMA delle aree metropolitane. Scarica l&#39;elenco delle regioni [DMA](assets/DMAregions.csv) (formato. csv). Ad esempio: <ul><li>Caratteristica: d_ dma_ code = 807</li><li>Nome caratteristica: San Francisco</li></ul> |
| d_ lat | Latitudine (ad es. d_ lat = 40.75). Scaricare l&#39;elenco [delle latezze](assets/d_lat.txt). |
| d_ long | Longitudine (ad es. d_ long = 73.98). Scaricate l&#39;elenco [longitudes](assets/d_long.txt). |
| d_ postal_ code | Codici ZIP (escludi il codice esteso +4). Scaricate l&#39;elenco dei codici [postali](assets/d_postal_code.txt). Ad esempio: <ul><li>Caratteristica: d_ postal_ code = 84004 </li><li>Nome caratteristica: Alpini</li></ul> |
| d_ state | Abbreviazione di 2 caratteri per uno stato USA. Scaricate l&#39;elenco dei codici [stati](assets/d_state.txt). Ad esempio: <ul><li>Caratteristica: d_ state = NY </li><li>Nome caratteristica: New York</li></ul>d_ state contiene valori ripetuti per stati diversi nei diversi paesi. Ad esempio, d_ state = = &quot;on&quot; corrisponde a più stati: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibia). È consigliabile associare questo segnale ad altri, ad esempio d_ country per il geotargeting più specifico. |
| d_ region | ID alfanumerici regionali. Scaricate l&#39;elenco [delle regioni](assets/Country_RegionCodes_City.csv). Quindi, potete usare questo elenco per associare gli ID di regione ai nomi delle aree. |
| d_ isp | ISP/organizzazione. Scaricate l&#39;elenco [ISP](assets/d_isp.txt). |

L&#39;elenco di [tutti i segnali basati sulla posizione](assets/all.csv) include tutti i segnali qui sopra, nel seguente ordine: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ LIKE_ THIS]
>
>* [Requisiti di prefisso per variabili chiave](../../features/traits/trait-variable-prefixes.md)

