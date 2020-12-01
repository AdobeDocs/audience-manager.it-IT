---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che potete utilizzare per eseguire il targeting degli utenti con variabili geografiche per tutte le proprietà dell'account del Audience Manager .
seo-description: Descrive le coppie chiave-valore comuni a livello di piattaforma che potete utilizzare per eseguire il targeting degli utenti con variabili geografiche per tutte le proprietà dell'account del Audience Manager .
seo-title: Geotargeting con chiavi a livello di piattaforma
solution: Audience Manager
title: Geotargeting con chiavi a livello di piattaforma
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---


# Geotargeting con chiavi a livello di piattaforma {#geotargeting-with-platform-level-keys}

Descrive le coppie chiave-valore comuni a livello di piattaforma che potete utilizzare per eseguire il targeting degli utenti con variabili geografiche per tutte le proprietà dell&#39;account del Audience Manager .

<!-- c_tb_platform_vars.xml -->

## Scopo delle variabili a livello di piattaforma {#platform-variables}

Le variabili a livello di piattaforma consentono di prendere i dati passati da un particolare sito e renderli disponibili per il targeting tra tutte le proprietà dell&#39;account [!DNL Audience Manager]. Queste variabili sono formate da [coppie chiave-valore](../../reference/key-value-pairs-explained.md) con il prefisso chiave `d_` come mostrato di seguito.

## Aggiunta di valori alle chiavi a livello di piattaforma {#adding-values}

Per alcune chiavi a livello di piattaforma, potete specificare il valore. Con altri, le chiavi sono associate agli indirizzi [!DNL IP] corrispondenti passati in una chiamata dell&#39;evento. In entrambi i casi, è comunque necessario specificare il valore al momento della creazione delle caratteristiche in [!UICONTROL Trait Builder].

## Tasti a livello di piattaforma definiti dall&#39;utente {#user-defined-keys}

È possibile specificare il valore quando si creano caratteristiche con le seguenti coppie chiave-valore:

| Chiave | Per il targeting |
|---|---|
| `d_zx` | Codice ZIP (ad esempio, `d_zx=10022`). |

## Tasti a livello di piattaforma definiti dall&#39;indirizzo IP {#keys-ip-address}

Lavoriamo con [Inviato digitale](https://www.digitalenvoy.com/) per ottenere e aggiornare i dati demografici e geografici per le chiavi riportate di seguito. I valori di queste chiavi sono determinati dalla corrispondenza degli indirizzi [!DNL IP] con i dati geografici e demografici corrispondenti. Tuttavia, sarà comunque necessario inserire il parametro value durante la creazione della coppia chiave-valore in [!UICONTROL Trait Builder].

| Chiave | Per il targeting |
|--- |--- |
| d_area_code | [Codici](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes) dell&#39;area nordamericana.  Ad esempio: <ul><li>**Caratteristiche**: d_area_code=801</li><li>**Nome** caratteristica: Utah</li></ul> |
| d_city | Città. Scaricate l&#39; [elenco città](assets/d_city.txt).  Ad esempio: <ul><li>Caratteristiche:  d_city=bonn</li><li>Nome caratteristica: Bonn</li></ul> **Suggerimento**: Puoi usare  `d_city` insieme  `d_country` per essere sicuro di non avere come destinazione due città con lo stesso nome in paesi diversi. Potete essere ancora più specifici nel targeting utilizzando `d_postal_code`. |
| d_country | I valori corrispondono ai codici paese ISO. Per un elenco di codici ricercabile, vedere la [piattaforma di ricerca online ISO](https://www.iso.org/obp/ui/#home). <br>  Il targeting per il Regno Unito è l&#39;unico caso speciale che non rispetta la norma ISO 3166. Per il targeting nel Regno Unito è necessario utilizzare &quot;UK&quot; invece di &quot;GB&quot;.  Per colpire le Antille olandesi, il codice &quot;AN&quot; è stato dichiarato obsoleto dal 2010. La zona è stata sciolta in cinque unità territoriali separate. L&#39;implicazione è che per il targeting nelle Antille olandesi, non si dovrebbe utilizzare &quot;AN&quot;, ma una combinazione dei codici paese per &quot;CW&quot;, &quot;SX&quot; e &quot;BQ.&quot;  Ad esempio:  <br>  Caratteristiche:  d_country=CZ <br>  Nome caratteristica: Repubblica Ceca <br>  Caratteristiche:  d_country=UK <br>  Nome caratteristica: Regno Unito <br>  Caratteristiche:  d_country=CW OR d_country=SX OR d_country=BQ <br>  Nome caratteristica: Antille olandesi |
| d_dma_code | Codici DMA dell&#39;area metropolitana. Scaricare l&#39;elenco [regione DMA](assets/DMAregions.csv) (.csv format).  Ad esempio: <ul><li>Caratteristiche:  d_dma_code=807</li><li>Nome caratteristica: San Francisco</li></ul> |
| d_lat | Latitudine (ad esempio d_lat=40.75). Scaricate l&#39; [elenco di latitudini](assets/d_lat.txt). |
| d_long | Longitudine (ad esempio, d_long=73.98). Scaricare l&#39;elenco [longitudini](assets/d_long.txt). |
| d_postal_code | Codici di avviamento postale (escluso il codice esteso +4). Scaricate l&#39; [elenco codici postali](assets/d_postal_code.txt).  Ad esempio: <ul><li>Caratteristiche:  d_postal_code=84004 </li><li>Nome caratteristica: alpino</li></ul> |
| d_state | Abbreviazione di 2 caratteri per uno stato US. Scaricare l&#39;elenco dei codici [stati](assets/d_state.txt).  Ad esempio: <ul><li>Caratteristiche:  d_state=NY </li><li>Nome caratteristica: New York</li></ul>d_state contiene valori ripetuti per stati diversi in diversi paesi. Ad esempio, d_state == &quot;on&quot; corrisponde a più stati: Ontario (Canada), Ondo (Nigeria), Oshana (Namibia). È consigliabile associare questo segnale ad altri, ad esempio d_country, per un geotargeting più specifico. |
| d_region | ID alfanumerici internazionali. Scaricare l&#39;elenco [regione](assets/Country_RegionCodes_City.csv).  Quindi, potete utilizzare questo elenco per far corrispondere gli ID di regione ai nomi di regione. |
| d_isp | ISP/organizzazione. Scaricate l&#39; [elenco ISP](assets/d_isp.txt). |

L&#39;elenco di [tutti i segnali basati sulla posizione](assets/all.txt) comprende tutti i segnali di cui sopra, nell&#39;ordine seguente: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md)

