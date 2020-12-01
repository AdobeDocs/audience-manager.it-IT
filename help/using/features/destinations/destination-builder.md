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
ht-degree: 4%

---


# Generatore di destinazioni {#destination-builder}

[!UICONTROL Destination Builder] consente di creare  [!DNL URL] destinazioni basate su cookie. Non è possibile creare destinazioni da server a server ([!DNL S2S]) con [!UICONTROL Destination Builder], ma è possibile gestirne le mappature. Contatta il tuo consulente per configurare una [!DNL S2S] destinazione. [!UICONTROL Destination Builder] si trova in  **[!UICONTROL Audience Data > Destinations]**.

## Impostazioni Generatore di destinazione {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] è costituito dalle sezioni e impostazioni seguenti:

| [!UICONTROL Destination Builder] Sezione | Finalità |
|--- |--- |
| Informazioni di base | Utilizzato per denominare la destinazione, descriverla e selezionare il tipo di destinazione ([!DNL URL] o [!DNL cookie]) e la piattaforma (all, [!DNL Android], browser o [!DNL iOS]). |
| Configurazione | Include controlli per: <br/><ul><li>Trasmissione dei dati chiave-valore alle destinazioni [!DNL URL]. Puoi inviare i dati come coppie chiave-valore singole o serializzate. Per informazioni dettagliate, vedere [Serializzazione di destinazione](../../features/destinations/key-value-pairs.md#destination-serialized) e [Coppie chiave-valore standard e seriale](../../features/destinations/key-value-pairs.md). </li><li>Elementi di una destinazione di cookie come nome di cookie, dominio, dimensione, intervallo di scadenza, formato dati, ecc.</li></ul> |
| Mappature dei segmenti | Consente di: <br/><ul><li>Cercare, aggiungere e gestire i segmenti associati a tutti i tipi di destinazione. </li><li>Definizione delle priorità di consegna per i singoli segmenti (solo per i segmenti basati su [!DNL cookie]).</li></ul> |

## Metodi di consegna dei dati {#data-delivery-methods}

Inviare informazioni a una destinazione trasmettendola attraverso una stringa [!DNL URL], scrivendo in un browser [!DNL cookie] o tramite trasferimenti offline di dati da server a server.

* [!DNL URL] e le destinazioni basate su cookie trasmettono i dati in modo sincrono, man mano che un utente interviene su una pagina.
* La trasmissione dei dati da server a server è asincrona e può avvenire molto tempo dopo che un utente ha lasciato la pagina. Il tipo di consegna selezionato dipende dai requisiti aziendali e dal modo in cui un particolare partner dati desidera o può ricevere i dati.

Per ulteriori informazioni, vedere [Come scegliere un tipo di destinazione](../../features/destinations/destinations.md).