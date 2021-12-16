---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting degli utenti con variabili geografiche per tutte le proprietà dell'account Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting con chiavi a livello di piattaforma
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---

# Geotargeting con chiavi a livello di piattaforma {#geotargeting-with-platform-level-keys}

Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting degli utenti con variabili geografiche per tutte le proprietà dell&#39;account Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Finalità delle variabili a livello di piattaforma {#platform-variables}

Le variabili a livello di piattaforma consentono di prendere i dati trasmessi da un particolare sito e di renderli disponibili per il targeting in tutte le proprietà del sito [!DNL Audience Manager] conto. Queste variabili sono costituite da [coppie chiave-valore](../../reference/key-value-pairs-explained.md) con la chiave preceduta da `d_` come mostrato di seguito.

## Aggiunta di valori alle chiavi a livello di piattaforma {#adding-values}

Per alcune chiavi a livello di piattaforma, puoi specificare autonomamente il valore. Con altri, le chiavi sono associate con corrispondenti [!DNL IP] indirizzi trasmessi durante una chiamata dell’evento. In entrambi i casi, è comunque necessario specificare il valore quando si creano le caratteristiche in [!UICONTROL Trait Builder].

## Chiavi a livello di piattaforma definite dall’utente {#user-defined-keys}

Se disponi già di un processo per definire e raccogliere coppie chiave-valore, utilizza questa opzione. Se desideri utilizzare chiavi predefinite per indirizzo IP, continua alla sezione successiva. Nel caso di chiavi definite dall&#39;utente, specifica il valore quando crei caratteristiche con queste coppie chiave-valore:

| Chiave | Per targeting |
|---|---|
| `d_zx` | CAP (ad esempio, `d_zx=10022`). |

## Chiavi a livello di piattaforma definite dall’indirizzo IP {#keys-ip-address}

Lavoriamo con [Inviato digitale](https://www.digitalenvoy.com/) ottenere e aggiornare i dati demografici e geografici per le chiavi riportate di seguito. I valori di queste chiavi sono determinati dalla corrispondenza [!DNL IP] indirizzi a dati geografici e demografici corrispondenti. Tuttavia, dovrai comunque immettere il parametro value quando crei la coppia chiave-valore in [!UICONTROL Trait Builder].

| Chiave | Per targeting |
|--- |--- |
| d_area_code | [Codici dell&#39;area Nord America](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Ad esempio: <ul><li>**Caratteristica**: d_area_code=801</li><li>**Nome della caratteristica**: Utah</li></ul> |
| d_city | Città e città. Scarica la [elenco città](assets/d_city.txt).  Ad esempio: <ul><li>Caratteristica: d_city=bonn</li><li>Nome caratteristica: Bonn</li></ul> **Suggerimento**: È possibile utilizzare `d_city` accoppiato con `d_country` per essere sicuri di non prendere di mira due città con lo stesso nome in paesi diversi. Puoi essere ancora più specifico nel targeting utilizzando `d_postal_code`. |
| d_country | I valori corrispondono ai codici paese ISO. Per un elenco di codici ricercabile, vedi [Piattaforma di navigazione online ISO](https://www.iso.org/obp/ui/#home). <br>  L&#39;obiettivo per il Regno Unito è l&#39;unico caso particolare che non rispetta la norma ISO 3166. Utilizza &quot;UK&quot; invece di &quot;GB&quot; per il targeting nel Regno Unito.  Per colpire le Antille olandesi, il codice &quot;AN&quot; è stato dichiarato obsoleto dal 2010. La zona è stata sciolta in cinque unità territoriali separate. L&#39;implicazione è che per il targeting nelle Antille olandesi, non si dovrebbe utilizzare &quot;AN&quot;, ma una combinazione dei codici paese per &quot;CW&quot;, &quot;SX&quot; e &quot;BQ.&quot;  Ad esempio:  <br>  Caratteristica: d_country=CZ  <br>  Nome caratteristica: Repubblica Ceca <br>  Caratteristica: d_country=UK <br>  Nome caratteristica: Regno Unito  <br>  Caratteristica: d_country=CW OR d_country=SX OR d_country=BQ  <br>  Nome caratteristica: Antille olandesi |
| d_dma_code | Codici DMA dell&#39;area metropolitana. Scarica la [Elenco delle aree DMA](assets/DMAregions.csv) (formato .csv).  Ad esempio: <ul><li>Caratteristica: d_dma_code=807</li><li>Nome caratteristica: San Francisco</li></ul> |
| d_lat | Latitudine (ad esempio d_lat=40.75). Scarica la [elenco delle latitudini](assets/d_lat.txt). |
| d_long | Longitudine (ad esempio d_long=73.98). Scarica la [elenco delle longitudini](assets/d_long.txt). |
| d_postal_code | Codici ZIP (escludere il codice esteso +4). Scarica la  [elenco dei codici postali](assets/d_postal_code.txt).  Ad esempio: <ul><li>Caratteristica: d_postal_code=84004 </li><li>Nome caratteristica: alpino</li></ul> |
| d_state | Abbreviazione a 2 caratteri per uno stato americano. Scarica la [elenco dei codici degli stati](assets/d_state.txt).  Ad esempio: <ul><li>Caratteristica: d_state=NY </li><li>Nome caratteristica: New York</li></ul>d_state contiene valori ripetuti per stati diversi in paesi diversi. Ad esempio, d_state == &quot;on&quot; corrisponde a più stati: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibia). Si consiglia di associare questo segnale ad altri, ad esempio d_country, per un geotargeting più specifico. |
| d_region | ID alfanumerici regionali. Scarica la [elenco di aree](assets/Country_RegionCodes_City.csv).  È quindi possibile utilizzare questo elenco per associare gli ID di regione ai nomi di regione. |
| d_isp | ISP/organizzazione. Scarica la [Elenco ISP](assets/d_isp.txt). |

L&#39;elenco di [tutti i segnali basati sulla posizione](assets/all.txt) comprende tutti i segnali di cui sopra, nel seguente ordine: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md)

