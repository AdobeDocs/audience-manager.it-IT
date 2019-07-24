---
description: I componenti delle azioni dei dati includono Feed dati cliente, Data Collection Server, SFTP/S 3/HTTP edshers, IRIS e Caching Server profilo.
seo-description: I componenti delle azioni dei dati includono Feed dati cliente, Data Collection Server, SFTP/S 3/HTTP edshers, IRIS e Caching Server profilo.
seo-title: Componenti azioni dati
solution: Audience Manager
title: Componenti azioni dati
uuid: c 4 c 4 cc 46-8 c 96-4 ef 5-8269-571 cc 5 ac 9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Action Components{#data-action-components}

I componenti delle azioni dei dati includono Feed dati cliente, Data Collection Server, SFTP/S 3/HTTP edshers, IRIS e Caching Server profilo.

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. [!DNL Audience Manager] Questi componenti includono:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] sono file inviati oraria ai clienti. Questi contengono ID utente insieme agli ID segmento associati, agli ID tratti e ad altri dati. For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

The [!UICONTROL SFTP/S3] publishers receive synchronized ID data from the [!UICONTROL Outbound Feed Converter]. When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* ID dispositivo/ID fornitore dati (DPUUID)
* ID del segmento qualificato
* ID caratteristiche

[!DNL Audience Manager] i clienti non hanno accesso alle funzionalità che controllano direttamente [!UICONTROL SFPT/S3 publishers]. I clienti utilizzano questo servizio indirettamente quando creano e inviano dati alle destinazioni. The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. [!UICONTROL IRIS] Il sistema è un namespace che riflette le caratteristiche di questa figura dall'antico mondo. In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] funziona con lo stesso tipo di dati del [!UICONTROL SFTP/S3] sistema. However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. This is a separate system because the [!UICONTROL SFTP/S3] publishers can't send data to an HTTP destination and they're not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

Examples of [!UICONTROL IRIS] services and features include:

* La sincronizzazione rapida (entro 30 secondi) per i cookie e i segmenti. It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both.
* Trasferimenti di dati in tempo reale. [!UICONTROL IRIS] è responsabile dell'invio di eventi di qualificazione segmenti in tempo reale a un partner o a un'altra destinazione. This data is JSON-formatted and sent via an HTTP `POST` request.

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data.

* Infrastruttura affidabile che funziona in scala ed è tollerante. Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**Regole di mappatura segmenti**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **Nuova qualifica segmento**: quando un dispositivo si qualifica per un nuovo segmento, [!UICONTROL IRIS] invia tutti i segmenti associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti.

1. **Nuova disattivazione del segmento**: quando un dispositivo non si qualifica più per un segmento, [!UICONTROL IRIS] invia tutte le qualifiche e i sottotitoli del segmento associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti.

1. **Aggiornamenti della mappatura destinazione**: quando viene aggiornata una mappatura di destinazione [!UICONTROL IRIS] , invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a tali segmenti, alla successiva visualizzazione del dispositivo da Audience Manager.

1. **Aggiornamenti del grafico del dispositivo**: quando un ID dispositivo viene aggiunto o rimosso dal grafico del dispositivo utilizzato per valutare un segmento, [!UICONTROL IRIS] invia tutti i segmenti associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti, alla successiva visualizzazione del dispositivo da Audience Manager.

>[!IMPORTANT]
>
>If Audience Manager doesn't detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**File di dati di esempio**

The following example contains real-time segment data from [!UICONTROL IRIS]. Tenere presente che si tratta di dati di esempio. Ogni cliente può avere requisiti di formattazione diversi, in modo che il contenuto possa variare.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Profile Cache Server (PCS) {#pcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).
