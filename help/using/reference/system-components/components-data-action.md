---
description: I componenti delle azioni dati includono Feed dati cliente, Server di raccolta dati, editori SFTP/S3/HTTP, IRIS e Server cache profilo.
seo-description: I componenti delle azioni dati includono Feed dati cliente, Server di raccolta dati, editori SFTP/S3/HTTP, IRIS e Server cache profilo.
seo-title: Componenti azione dati
solution: Audience Manager
title: Componenti azione dati
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 0%

---


# Componenti azione dati{#data-action-components}

I componenti delle azioni dati includono Feed dati cliente, Server di raccolta dati, editori SFTP/S3/HTTP, IRIS e Server cache profilo.

<!-- 

c_compact.xml

 -->

I componenti azione sono sistemi e processi che consentono di spostare i dati all&#39;interno e all&#39;esterno [!DNL Audience Manager] (per mancanza di una frase migliore). Questi [!DNL Audience Manager] componenti includono:

## Feed dati cliente (CDF) {#cdf}

[!UICONTROL CDF] sono file inviati ogni ora ai clienti. Questi contengono ID utente insieme agli ID del segmento, agli ID delle caratteristiche e ad altri dati associati. Per ulteriori informazioni, consulta Panoramica sui feed di dati [cliente](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

Consulta Componenti [per la raccolta](../../reference/system-components/components-data-collection.md)dati.

## SFTP/S3 {#sftp-s3}

Gli [!UICONTROL SFTP/S3] editori ricevono i dati ID sincronizzati dall&#39; [!UICONTROL Outbound Feed Converter]. Quando questi file sono pronti, l&#39; [!UICONTROL SFTP/S3 publishers] invio di questi dati a una destinazione specificata dal client. Questi file contengono dati ID sincronizzati con una mappatura uno-molti degli ID [!DNL Audience Manager] utente (UUID) per:

* ID dispositivo/ID provider di dati (DPUUID)
* ID segmento qualificati
* ID caratteristica

[!DNL Audience Manager] i clienti non hanno accesso alle funzioni che controllano direttamente il [!UICONTROL SFPT/S3 publishers]. I clienti utilizzano indirettamente questo servizio quando creano e inviano dati alle destinazioni. Il [!UICONTROL SFTP/S3] sistema è essenzialmente un processo di lavoro automatizzato che viene eseguito a intervalli pianificati.

## IRIS {#iris}

Nella mitologia greca, [!UICONTROL Iris] è una figura che viaggia e invia messaggi rapidamente. Il [!UICONTROL IRIS] sistema è un nome che riflette le caratteristiche di questa figura del mondo antico. In termini moderni, [!UICONTROL IRIS] è un servizio di sincronizzazione dei cookie ad alta frequenza a bassa latenza e trasferimento dei dati.

[!UICONTROL IRIS] funziona con lo stesso tipo di dati del [!UICONTROL SFTP/S3] sistema. Tuttavia, [!UICONTROL IRIS] è diverso perché invia dati alle destinazioni in tempo reale anziché a intervalli preimpostati. Questo è un sistema a parte, perché gli [!UICONTROL SFTP/S3] editori non possono inviare dati a una destinazione HTTP e non sono progettati per il trasferimento di dati in tempo reale.

Non sono disponibili controlli per l’interfaccia utente che consentono ai clienti di lavorare direttamente con [!UICONTROL IRIS]. I clienti lavorano [!UICONTROL IRIS] indirettamente quando creano e inviano dati a destinazioni e per altri processi che richiedono trasferimenti rapidi di dati.

Esempi di [!UICONTROL IRIS] servizi e funzionalità:

* Sincronizzazione rapida (entro 30 secondi) per cookie e segmenti. Può sincronizzare il [!DNL Audience Manager] cookie, i cookie del partner o entrambi.
* Trasferimenti di dati in tempo reale. [!UICONTROL IRIS] è responsabile dell&#39;invio di eventi di qualificazione del segmento in tempo reale a un partner o a un&#39;altra destinazione. Questi dati sono in formato JSON e inviati tramite una `POST` richiesta HTTP.

* Trasferimenti di dati in massa da server a server: Se si scambiano grandi quantità di dati con [!DNL Audience Manager], [!UICONTROL IRIS] è il sistema con cui i server interagiscono per trasferire i dati.

* Infrastruttura affidabile che funziona su larga scala ed è tollerante agli errori. I sistemi che alimentano [!UICONTROL IRIS] comprendono Amazon SQS, Amazon EC2 e Cassandra.

**Regole di mappatura segmenti**

Per ottimizzare il traffico tra destinazioni [!UICONTROL IRIS] e segmenti, [!UICONTROL IRIS] invia segmenti a destinazioni in base a un insieme di regole.

1. **Nuova qualifica** segmento: quando un dispositivo si qualifica per un nuovo segmento, [!UICONTROL IRIS] invia tutti i segmenti associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti.

1. **Nuova squalifica** segmento: quando un dispositivo non si qualifica più per un segmento, [!UICONTROL IRIS] invia tutte le qualifiche del segmento e le interdizioni associate a tale dispositivo a tutte le destinazioni mappate a tali segmenti.

1. **Aggiornamenti** della mappatura di destinazione: quando viene aggiornata una mappatura di destinazione, [!UICONTROL IRIS] invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a questi segmenti, la volta successiva  Audience Manager vede il dispositivo.

1. **Aggiornamenti** del grafico del dispositivo: quando un ID dispositivo viene aggiunto o rimosso dal grafico del dispositivo utilizzato per valutare un segmento, [!UICONTROL IRIS] invia tutti i segmenti associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti, la prossima volta che Audience Manager vede il dispositivo .

>[!IMPORTANT]
>
>Se  Audience Manager non rileva nessuno degli aggiornamenti precedenti per 3 giorni consecutivi, [!UICONTROL IRIS] invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a questi segmenti, la prossima volta che  Audience Manager visualizzerà il dispositivo.

**Esempio di file di dati**

L&#39;esempio seguente contiene i dati del segmento in tempo reale provenienti da [!UICONTROL IRIS]. Tenere presente che si tratta solo di dati di esempio. Ogni cliente può avere requisiti di formattazione diversi, in modo che i contenuti possano variare.

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

## Server cache profilo (PCS) {#pcs}

Consulta Componenti [per la raccolta](../../reference/system-components/components-data-collection.md)dati.
