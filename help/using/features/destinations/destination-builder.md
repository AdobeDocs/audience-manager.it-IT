---
description: Destination Builder consente di creare destinazioni URL DNL o basate su cookie. Non è possibile creare destinazioni da server a server (S2S) con Generatore di destinazioni, ma è possibile gestirne le mappature dei segmenti. Contatta il tuo consulente per configurare una destinazione S2S. Destination Builder (Generatore di destinazioni) si trova in Audience Data > Destinations (Dati pubblico > Destinazioni).
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Generatore di destinazione
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Generatore di destinazione {#destination-builder}

[!UICONTROL Destination Builder] consente di creare destinazioni basate su cookie o [!DNL URL]. Non è possibile creare destinazioni da server a server ([!DNL S2S]) con [!UICONTROL Destination Builder], ma è possibile gestirne i mapping di segmenti. Contattare il proprio consulente per configurare una destinazione [!DNL S2S]. [!UICONTROL Destination Builder] si trova in **[!UICONTROL Audience Data > Destinations]**.

## Impostazioni Generatore di destinazione {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] è costituito dalle sezioni e dalle impostazioni seguenti:

| Sezione [!UICONTROL Destination Builder] | Finalità |
|--- |--- |
| Informazioni di base | Utilizzato per denominare la destinazione, descriverla e selezionare il tipo di destinazione ([!DNL URL] o [!DNL cookie]) e la piattaforma (tutti, [!DNL Android], browser o [!DNL iOS]). |
| Configurazione | Include i controlli per: <br/><ul><li>Passaggio di dati chiave-valore a [!DNL URL] destinazioni. Puoi inviare dati come coppie chiave-valore singole o serializzate. Per informazioni dettagliate, vedere [Serializzazione di destinazione](../../features/destinations/key-value-pairs.md#destination-serialized) e [Coppie chiave-valore standard e seriali](../../features/destinations/key-value-pairs.md). </li><li>Elementi di una destinazione cookie come nome cookie, dominio, dimensione, intervallo di scadenza, formato dei dati, ecc.</li></ul> |
| Mappature dei segmenti | Consente di: <br/><ul><li>Cerca, aggiungi e gestisci i segmenti associati a tutti i tipi di destinazione. </li><li>Impostare le priorità di consegna per i singoli segmenti (solo per i segmenti basati su [!DNL cookie]).</li></ul> |

## Metodi di distribuzione dei dati {#data-delivery-methods}

Inviare informazioni a una destinazione trasmettendole tramite una stringa [!DNL URL], scrivendo su un browser [!DNL cookie] o tramite trasferimenti di dati da server a server offline.

* [!DNL URL] e destinazioni basate su cookie trasmettono i dati in modo sincrono, mentre un utente interviene su una pagina.
* La trasmissione dei dati server-to-server è asincrona e può verificarsi molto tempo dopo che un utente ha lasciato la pagina. Il tipo di consegna selezionato dipende dai requisiti aziendali e dal modo in cui un particolare partner dati desidera o può ricevere i dati.

Per ulteriori informazioni, vedere [Come scegliere un tipo di destinazione](../../features/destinations/destinations.md).
