---
description: La funzione di creazione di destinazione consente di creare destinazioni URL basate su cookie o DNL. Non è possibile creare destinazioni server-to-server (S 2 S) con Generatore di destinazione, ma puoi gestirne le mappature dei segmenti. Contatta il tuo consulente per impostare una destinazione S 2 S. Il Generatore di destinazione si trova in Dati audience > Destinazioni.
seo-description: La funzione di creazione di destinazione consente di creare destinazioni URL basate su cookie o DNL. Non è possibile creare destinazioni server-to-server (S 2 S) con Generatore di destinazione, ma puoi gestirne le mappature dei segmenti. Contatta il tuo consulente per impostare una destinazione S 2 S. Il Generatore di destinazione si trova in Dati audience > Destinazioni.
seo-title: Generatore di destinazione
solution: Audience Manager
title: Generatore di destinazione
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Generatore di destinazione {#destination-builder}

[!UICONTROL Destination Builder] consente di creare una o più [!DNL URL] destinazioni basate su cookie. Non è possibile creare destinazioni server-to-server con[!DNL S2S][!UICONTROL Destination Builder], ma è possibile gestirne le mappature dei segmenti. Contatta il tuo consulente per configurare [!DNL S2S] una destinazione. [!UICONTROL Destination Builder] si trova in **[!UICONTROL Audience Data > Destinations]**.

## Impostazioni di Generatore di destinazione {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] sono costituite dalle seguenti sezioni e impostazioni:

| [!UICONTROL Destination Builder] Sezione | Finalità |
|--- |--- |
| Informazioni di base | Utilizzato per denominare la destinazione, descriverla e selezionare tipo di destinazione ([!DNL URL] o [!DNL cookie]) e piattaforma (tutto [!DNL Android], browser o [!DNL iOS]). |
| Configurazione | Include controlli per: <br/><ul><li>Trasmissione di dati chiave-valore alle [!DNL URL] destinazioni. È possibile inviare dati come coppie chiave-valore singole o serializzate. Per informazioni dettagliate, consultate Serializzazione [destinazione](../../features/destinations/key-value-pairs.md#destination-serialized) e [Standard e Chiave chiave-valore](../../features/destinations/key-value-pairs.md). </li><li>Elementi di una destinazione cookie come nome del cookie, dominio, dimensione, intervallo di scadenza, formato dati, ecc.</li></ul> |
| Mappature segmento | Consente di: <br/><ul><li>Cercare, aggiungere e gestire segmenti associati a tutti i tipi di destinazione. </li><li>Imposta le priorità di consegna su singoli segmenti (solo per segmenti basati su [!DNL cookie]segmenti).</li></ul> |

## Metodi di consegna dati {#data-delivery-methods}

Inviare informazioni a una destinazione passandola attraverso [!DNL URL] una stringa, scrivendo in un browser [!DNL cookie]o tramite trasferimento dati da server a server offline.

* [!DNL URL] e le destinazioni basate su cookie trasmettono i dati in modo sincrono, man mano che un utente utilizza una pagina.
* La trasmissione dei dati server-to-server è asincrona e può verificarsi molto dopo che un utente è uscito dalla pagina. Il tipo di consegna selezionato dipende dai requisiti aziendali e dal modo in cui un particolare partner di dati desidera o può ricevere dati.

Per [ulteriori informazioni, consultate Scegliere un tipo](../../features/destinations/destinations.md) di destinazione.