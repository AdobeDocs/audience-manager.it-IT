---
description: Generatore di destinazione consente di creare destinazioni URL DNL o basate su cookie. Non è possibile creare destinazioni da server a server (S2S) con Generatore di destinazione, ma è possibile gestirne le mappature. Contatta il tuo consulente per configurare una destinazione S2S. Il Generatore di destinazioni si trova in Dati pubblico > Destinazioni.
seo-description: Generatore di destinazione consente di creare destinazioni URL DNL o basate su cookie. Non è possibile creare destinazioni da server a server (S2S) con Generatore di destinazione, ma è possibile gestirne le mappature. Contatta il tuo consulente per configurare una destinazione S2S. Il Generatore di destinazioni si trova in Dati pubblico > Destinazioni.
seo-title: Generatore di destinazioni
solution: Audience Manager
title: Generatore di destinazioni
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 2%

---


# Generatore di destinazioni {#destination-builder}

[!UICONTROL Destination Builder] consente di creare [!DNL URL] destinazioni basate su cookie. Non è possibile creare destinazioni da server a[!DNL S2S]server con [!UICONTROL Destination Builder], ma è possibile gestirne le mappature. Contatta il tuo consulente per configurare una [!DNL S2S] destinazione. [!UICONTROL Destination Builder] si trova in **[!UICONTROL Audience Data > Destinations]**.

## Impostazioni Generatore di destinazione {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] è costituito dalle sezioni e impostazioni seguenti:

| [!UICONTROL Destination Builder] Sezione | Finalità |
|--- |--- |
| Informazioni di base | Utilizzato per denominare la destinazione, descriverla e selezionare il tipo ([!DNL URL] o [!DNL cookie]) di destinazione e la piattaforma (tutto, [!DNL Android], browser o [!DNL iOS]). |
| Configurazione | Include controlli per: <br/><ul><li>Trasmissione di dati chiave-valore alle [!DNL URL] destinazioni. Puoi inviare i dati come coppie chiave-valore singole o serializzate. Per informazioni dettagliate, consultate Serializzazione [di](../../features/destinations/key-value-pairs.md#destination-serialized) destinazione e coppie chiave-valore [standard e seriali](../../features/destinations/key-value-pairs.md). </li><li>Elementi di una destinazione di cookie come nome di cookie, dominio, dimensione, intervallo di scadenza, formato dati, ecc.</li></ul> |
| Mappature dei segmenti | Consente di: <br/><ul><li>Cercare, aggiungere e gestire i segmenti associati a tutti i tipi di destinazione. </li><li>Definizione delle priorità di consegna per singoli segmenti (solo per segmenti [!DNL cookie]basati su).</li></ul> |

## Metodi di consegna dei dati {#data-delivery-methods}

Inviare informazioni a una destinazione trasmettendola attraverso una [!DNL URL] stringa, scrivendo in un browser [!DNL cookie]o trasferendo dati da server a server offline.

* [!DNL URL] e le destinazioni basate su cookie trasmettono i dati in modo sincrono, man mano che un utente interviene su una pagina.
* La trasmissione dei dati da server a server è asincrona e può avvenire molto tempo dopo che un utente ha lasciato la pagina. Il tipo di consegna selezionato dipende dai requisiti aziendali e dal modo in cui un particolare partner dati desidera o può ricevere i dati.

Per ulteriori informazioni, consulta [Scegliere un tipo](../../features/destinations/destinations.md) di destinazione.