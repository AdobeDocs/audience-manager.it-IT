---
description: Destination Builder consente di creare destinazioni URL DNL o basate su cookie. Non è possibile creare destinazioni da server a server (S2S) con Generatore di destinazioni, ma è possibile gestirne le mappature dei segmenti. Contatta il tuo consulente per configurare una destinazione S2S. Destination Builder (Generatore di destinazioni) si trova in Audience Data > Destinations (Dati pubblico > Destinazioni).
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Generatore di destinazioni
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 4%

---

# Generatore di destinazioni {#destination-builder}

[!UICONTROL Destination Builder] consente di creare o [!DNL URL] destinazioni. Impossibile creare server-to-server ([!DNL S2S]) destinazioni con [!UICONTROL Destination Builder], ma puoi gestirne le mappature dei segmenti. Contatta il tuo consulente per configurare un [!DNL S2S] destinazione. [!UICONTROL Destination Builder] si trova in **[!UICONTROL Audience Data > Destinations]**.

## Impostazioni Generatore di destinazione {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] è costituito dalle sezioni e dalle impostazioni seguenti:

| [!UICONTROL Destination Builder] Sezione | Finalità |
|--- |--- |
| Informazioni di base | Utilizzato per denominare la destinazione, descriverla e selezionare il tipo di destinazione ([!DNL URL] o [!DNL cookie]), e la piattaforma (tutti, [!DNL Android], browser o [!DNL iOS]). |
| Configurazione | Include i controlli per: <br/><ul><li>Trasmissione di dati chiave-valore a [!DNL URL] destinazioni. Puoi inviare dati come coppie chiave-valore singole o serializzate. Per maggiori dettagli, vedere [Serializzazione della destinazione](../../features/destinations/key-value-pairs.md#destination-serialized) e [Coppie chiave-valore standard e seriali](../../features/destinations/key-value-pairs.md). </li><li>Elementi di una destinazione cookie come nome cookie, dominio, dimensione, intervallo di scadenza, formato dei dati, ecc.</li></ul> |
| Mappature dei segmenti | Consente di: <br/><ul><li>Cerca, aggiungi e gestisci i segmenti associati a tutti i tipi di destinazione. </li><li>Impostare le priorità di consegna per i singoli segmenti (per [!DNL cookie]solo segmenti basati su ).</li></ul> |

## Metodi di distribuzione dei dati {#data-delivery-methods}

Inviare informazioni a una destinazione trasmettendole attraverso un [!DNL URL] stringa, scrivendo in un browser [!DNL cookie]o tramite trasferimenti di dati da server a server offline.

* [!DNL URL] e le destinazioni basate su cookie trasmettono i dati in modo sincrono, mentre un utente interviene su una pagina.
* La trasmissione dei dati server-to-server è asincrona e può verificarsi molto tempo dopo che un utente ha lasciato la pagina. Il tipo di consegna selezionato dipende dai requisiti aziendali e dal modo in cui un particolare partner dati desidera o può ricevere i dati.

Consulta [Come scegliere un tipo di destinazione](../../features/destinations/destinations.md) per ulteriori informazioni.
