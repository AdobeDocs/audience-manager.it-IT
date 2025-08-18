---
description: I componenti dell’azione dati includono Customer Data Feeds, Data Collection Server, Publishers SFTP/S3/HTTP, IRIS e Profile Cache Server.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: Componenti azione dati
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# Componenti azione dati{#data-action-components}

I componenti dell’azione dati includono Customer Data Feeds, Data Collection Server, Publishers SFTP/S3/HTTP, IRIS e Profile Cache Server.

<!-- 

c_compact.xml

 -->

I componenti delle azioni sono sistemi e processi che consentono di spostare i dati da e verso [!DNL Audience Manager] e (per la mancanza di una frase migliore) di eseguire operazioni. Questi [!DNL Audience Manager] componenti includono:

## Feed di dati cliente (CDF, Customer Data Feeds) {#cdf}

[!UICONTROL CDF] sono file inviati ogni ora ai clienti. Questi contengono gli ID utente e gli ID segmento associati, gli ID caratteristica e altri dati. Per ulteriori informazioni, consulta [Panoramica sui feed di dati dei clienti](../../features/cdf-files.md).

## Server di raccolta dati (DCS) {#dcs}

Consulta [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Gli editori [!UICONTROL SFTP/S3] ricevono dati ID sincronizzati da [!UICONTROL Outbound Feed Converter]. Quando questi file sono pronti, [!UICONTROL SFTP/S3 publishers] invia questi dati a una destinazione specificata dal client. Questi file contengono dati ID sincronizzati con una mappatura uno-a-molti di [!DNL Audience Manager] ID utente (UUID) in:

* ID dispositivo/ID provider dati (DPUUID)
* ID segmento qualificati
* ID delle caratteristiche

I clienti [!DNL Audience Manager] non hanno accesso alle funzionalità che controllano direttamente [!UICONTROL SFPT/S3 publishers]. I clienti utilizzano questo servizio indirettamente quando creano e inviano dati alle destinazioni. Il sistema [!UICONTROL SFTP/S3] è essenzialmente un processo di processo automatizzato eseguito a intervalli pianificati.

## IRIS {#iris}

Nella mitologia greca, [!UICONTROL Iris] è una figura che viaggia e consegna messaggi rapidamente. Il sistema [!UICONTROL IRIS] è un omonimo che riflette le caratteristiche di questa figura del mondo antico. In termini moderni, [!UICONTROL IRIS] è un servizio di sincronizzazione dei cookie e trasferimento dati a bassa latenza e ad alta frequenza.

[!UICONTROL IRIS] funziona con lo stesso tipo di dati del sistema [!UICONTROL SFTP/S3]. Tuttavia, [!UICONTROL IRIS] è diverso perché invia i dati alle destinazioni in tempo reale anziché a intervalli impostati. Questo è un sistema separato perché gli editori [!UICONTROL SFTP/S3] non possono inviare dati a una destinazione HTTP e non sono progettati per trasferimenti di dati in tempo reale.

Nessun controllo dell&#39;interfaccia utente che consente ai clienti di utilizzare direttamente [!UICONTROL IRIS]. I clienti lavorano indirettamente con [!UICONTROL IRIS] quando creano e inviano dati alle destinazioni e per altri processi che richiedono trasferimenti rapidi di dati.

Esempi di servizi e funzionalità di [!UICONTROL IRIS] includono:

* Sincronizzazione rapida (entro 30 secondi) per cookie e segmenti. Può sincronizzare il cookie [!DNL Audience Manager], i cookie partner o entrambi.
* Trasferimenti di dati in tempo reale. [!UICONTROL IRIS] è responsabile dell&#39;invio in tempo reale di eventi di qualificazione dei segmenti a un partner o a un&#39;altra destinazione. Questi dati sono in formato JSON e vengono inviati tramite una richiesta HTTP `POST`.

* Trasferimenti di dati in blocco da server a server: se si scambiano grandi quantità di dati con [!DNL Audience Manager], [!UICONTROL IRIS] è il sistema utilizzato dai server per trasferire i dati.

* Infrastruttura affidabile, scalabile e a tolleranza di errore. I sistemi che alimentano [!UICONTROL IRIS] includono Amazon SQS, Amazon EC2 e Cassandra.

**Regole di mappatura dei segmenti**

Per ottimizzare il traffico tra [!UICONTROL IRIS] e le destinazioni dei segmenti, [!UICONTROL IRIS] invia segmenti alle destinazioni in base a un set di regole.

1. **Qualificazione del nuovo segmento**: quando un dispositivo è idoneo per un nuovo segmento, [!UICONTROL IRIS] invia tutti i segmenti associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti.

1. **Nuova interdizione di segmento**: quando un dispositivo non è più idoneo per un segmento, [!UICONTROL IRIS] invia tutte le qualifiche e le interdizioni di segmento associate a tale dispositivo a tutte le destinazioni mappate a questi segmenti.

1. **Aggiornamenti della mappatura di destinazione**: quando viene aggiornata una mappatura di destinazione, [!UICONTROL IRIS] invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a questi segmenti, la volta successiva che Audience Manager vede il dispositivo.

1. **Aggiornamenti del grafo di dispositivi**: quando un ID dispositivo viene aggiunto o rimosso dal grafo di dispositivi utilizzato per valutare un segmento, [!UICONTROL IRIS] invia tutti i segmenti associati a tale dispositivo a tutte le destinazioni mappate a questi segmenti, la prossima volta che Audience Manager vede il dispositivo.

>[!IMPORTANT]
>
>Se Audience Manager non rileva nessuno degli aggiornamenti di cui sopra per 3 giorni consecutivi, [!UICONTROL IRIS] invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a questi segmenti, la prossima volta che Audience Manager vede il dispositivo.

**File di dati di esempio**

L&#39;esempio seguente contiene dati di segmenti in tempo reale da [!UICONTROL IRIS]. Tieni presente che si tratta solo di dati di esempio. Ogni cliente può avere requisiti di formattazione diversi, che possono variare nel contenuto.

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

## Server cache profili (PCS) {#pcs}

Consulta [Data Collection Components](../../reference/system-components/components-data-collection.md).
