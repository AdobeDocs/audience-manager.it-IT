---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting di utenti con variabili geografiche in tutte le proprietà nell’account Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting con chiavi a livello di piattaforma
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# Geotargeting con chiavi a livello di piattaforma {#geotargeting-with-platform-level-keys}

Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting di utenti con variabili geografiche in tutte le proprietà nell’account Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Finalità delle variabili a livello di piattaforma {#platform-variables}

Le variabili a livello di piattaforma consentono di acquisire i dati trasmessi da un particolare sito e renderli disponibili per il targeting in tutte le proprietà nell&#39;account [!DNL Audience Manager]. Queste variabili sono formate da [coppie chiave-valore](../../reference/key-value-pairs-explained.md) con la chiave con prefisso `d_`, come illustrato di seguito.

## Aggiunta di valori alle chiavi a livello di piattaforma {#adding-values}

Per alcune chiavi a livello di piattaforma, puoi specificare il valore autonomamente. Con altri, le chiavi sono associate agli indirizzi [!DNL IP] corrispondenti trasmessi durante una chiamata evento. In entrambi i casi, è comunque necessario specificare il valore durante la creazione delle caratteristiche in [!UICONTROL Trait Builder].

## Chiavi a livello di piattaforma definite dall&#39;utente {#user-defined-keys}

Se disponi già di un processo per definire e raccogliere coppie chiave-valore, o lo stai impostando, utilizza questa opzione. Se desideri utilizzare chiavi predefinite tramite indirizzo IP, continua con la sezione successiva. Nel caso di chiavi definite dall’utente, specifica il valore quando crei caratteristiche con queste coppie chiave-valore:

| Chiave | Per il targeting |
|---|---|
| `d_zx` | Codice postale (ad esempio, `d_zx=10022`). |

## Chiavi a livello di piattaforma definite dall&#39;indirizzo IP {#keys-ip-address}

Lavoriamo con [Digital Envoy](https://www.digitalenvoy.com/) per ottenere e aggiornare i dati demografici e geografici per le chiavi seguenti. I valori per queste chiavi sono determinati dalla corrispondenza degli indirizzi [!DNL IP] ai dati geografici e demografici corrispondenti. Tuttavia, sarà comunque necessario immettere il parametro value durante la creazione della coppia chiave-valore in [!UICONTROL Trait Builder].

| Chiave | Per il targeting |
|--- |--- |
| d_area_code | [Codici area Nord America](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Ad esempio: <ul><li>**Caratteristica**: d_area_code=801</li><li>**Nome caratteristica**: Utah</li></ul> |
| d_city | Città e paesi. Scarica l&#39;[elenco delle città](assets/d_city.txt).  Ad esempio: <ul><li>Caratteristica: d_city=bonn</li><li>Nome caratteristica: Bonn</li></ul> **Suggerimento**: è possibile utilizzare `d_city` in combinazione con `d_country` per assicurarsi di non eseguire il targeting di due città con lo stesso nome in paesi diversi. Puoi essere ancora più specifico nel targeting utilizzando `d_postal_code`. |
| d_country | I valori corrispondono ai codici paese ISO. Per un elenco di codici ricercabili, vedere [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>  Il targeting per il Regno Unito è l&#39;unico caso speciale che non rispetta la norma ISO 3166. Utilizza &quot;UK&quot; invece di &quot;GB&quot; per il targeting nel Regno Unito.  Per colpire le Antille olandesi, il codice &quot;AN&quot; è stato dichiarato obsoleto dal 2010. L&#39;area è stata sciolta in cinque unità territoriali separate. L&#39;implicazione è che per il targeting nelle Antille olandesi non si dovrebbe usare &quot;AN&quot;, ma una combinazione dei codici paese per &quot;CW&quot;, &quot;SX&quot; e &quot;BQ&quot;.  Esempio: <br>  Caratteristica: d_country=CZ <br>  Nome caratteristica: Repubblica Ceca <br>  Caratteristica: d_country=UK <br>  Nome caratteristica: Regno Unito <br>  Caratteristica: d_country=CW O d_country=SX O d_country=BQ <br>  Nome caratteristica: Antille olandesi |
| d_dma_code | Codici DMA dell&#39;area metropolitana. Scarica l&#39;elenco delle aree geografiche di [DMA](assets/DMAregions.csv) (formato .csv).  Ad esempio: <ul><li>Caratteristica: d_dma_code=807</li><li>Nome caratteristica: San Francisco</li></ul> |
| d_lat | Latitudine (ad esempio d_lat=40,75). Scarica l&#39;[elenco latitudini](assets/d_lat.txt). |
| d_long | Longitudine (ad esempio d_long=73,98). Scarica l&#39;[elenco longitudini](assets/d_long.txt). |
| d_postal_code | Codici postali (escluso il codice esteso +4). Scarica l&#39;[elenco codici postali](assets/d_postal_code.txt).  Ad esempio: <ul><li>Caratteristica: d_postal_code=84004 </li><li>Nome caratteristica: alpino</li></ul> |
| d_state | Abbreviazione di 2 caratteri per uno stato degli Stati Uniti. Scarica l&#39;elenco di codici di [stati](assets/d_state.txt).  Ad esempio: <ul><li>Caratteristica: d_state=NY </li><li>Nome caratteristica: New York</li></ul>d_state contiene valori ripetuti per stati diversi in paesi diversi. Ad esempio, d_state == &quot;on&quot; corrisponde a più stati: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibia). Consigliamo di associare questo segnale ad altri, come ad esempio d_country, per un geotargeting più specifico. |
| d_region | ID alfanumerici regionali. Scarica l&#39;[elenco di aree](assets/Country_RegionCodes_City.csv).  Quindi, puoi utilizzare questo elenco per far corrispondere gli ID di regione ai nomi di regione. |
| d_isp | ISP/organizzazione. Scarica l&#39;[elenco ISP](assets/d_isp.txt). |

L&#39;elenco di [tutti i segnali basati sulla posizione](assets/all.txt) comprende tutti i segnali indicati sopra, nell&#39;ordine seguente: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md)
