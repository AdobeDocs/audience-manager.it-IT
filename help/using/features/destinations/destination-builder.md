---
description: Il Generatore di destinazioni consente di creare destinazioni URL basate su cookie o DNL. Non è possibile creare destinazioni server-to-server (S2S) con Generatore di destinazione, ma è possibile gestirne le mappature dei segmenti. Contatta il tuo consulente per impostare una destinazione S2S. Il Generatore di destinazione si trova in Dati audience > Destinazioni.
seo-description: Il Generatore di destinazioni consente di creare destinazioni URL basate su cookie o DNL. Non è possibile creare destinazioni server-to-server (S2S) con Generatore di destinazione, ma è possibile gestirne le mappature dei segmenti. Contatta il tuo consulente per impostare una destinazione S2S. Il Generatore di destinazione si trova in Dati audience > Destinazioni.
seo-title: Generatore di destinazioni
solution: Audience Manager
title: Generatore di destinazioni
feature: Nozioni di base sulle destinazioni
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Generatore di destinazioni {#destination-builder}

[!UICONTROL Destination Builder] consente di creare  [!DNL URL] destinazioni basate su cookie. Non è possibile creare destinazioni da server a server ([!DNL S2S]) con [!UICONTROL Destination Builder], ma è possibile gestirne le mappature dei segmenti. Contatta il tuo consulente per impostare una destinazione [!DNL S2S]. [!UICONTROL Destination Builder] si trova in  **[!UICONTROL Audience Data > Destinations]**.

## Impostazioni del Generatore di destinazioni {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] è costituito dalle sezioni e impostazioni seguenti:

| [!UICONTROL Destination Builder] Sezione | Finalità |
|--- |--- |
| Informazioni di base | Utilizzato per denominare la destinazione, descriverla e selezionare il tipo di destinazione ([!DNL URL] o [!DNL cookie]) e la piattaforma (all, [!DNL Android], il browser o [!DNL iOS]). |
| Configurazione | Include controlli per: <br/><ul><li>Trasferimento dei dati chiave-valore alle destinazioni [!DNL URL]. Puoi inviare dati come coppie chiave-valore singole o serializzate. Per informazioni dettagliate, vedere [Serializzazione di destinazione](../../features/destinations/key-value-pairs.md#destination-serialized) e [Coppie chiave-valore standard e seriali](../../features/destinations/key-value-pairs.md). </li><li>Elementi di una destinazione cookie come nome cookie, dominio, dimensione, intervallo di scadenza, formato dati, ecc.</li></ul> |
| Mappature dei segmenti | Consente di: <br/><ul><li>Cerca, aggiungi e gestisci i segmenti associati a tutti i tipi di destinazione. </li><li>Imposta le priorità di consegna sui singoli segmenti (solo per i segmenti basati su [!DNL cookie]).</li></ul> |

## Metodi di consegna dei dati {#data-delivery-methods}

Inviare informazioni a una destinazione trasmettendole attraverso una stringa [!DNL URL], scrivendo in un browser [!DNL cookie] o tramite trasferimenti offline di dati da server a server.

* [!DNL URL] e le destinazioni basate su cookie trasmettono i dati in modo sincrono, man mano che un utente agisce su una pagina.
* La trasmissione dati server-to-server è asincrona e può verificarsi a lungo dopo che un utente ha lasciato la pagina. Il tipo di consegna selezionato dipende dai requisiti aziendali e dal modo in cui un particolare partner di dati desidera o può ricevere i dati.

Per ulteriori informazioni, consulta [Come scegliere un tipo di destinazione](../../features/destinations/destinations.md) .
