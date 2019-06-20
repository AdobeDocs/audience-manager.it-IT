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


# Componenti azioni dati{#data-action-components}

I componenti delle azioni dei dati includono Feed dati cliente, Data Collection Server, SFTP/S 3/HTTP edshers, IRIS e Caching Server profilo.

<!-- 

c_compact.xml

 -->

I componenti azione sono sistemi e processi che consentono di spostare i dati da e verso [!DNL Audience Manager] l&#39;esterno e (per la mancanza di una frase migliore). [!DNL Audience Manager] Questi componenti includono:

## Feed dati cliente (CDF) {#cdf}

[!UICONTROL CDF] sono file inviati oraria ai clienti. Questi contengono ID utente insieme agli ID segmento associati, agli ID tratti e ad altri dati. Per ulteriori informazioni, vedi [Panoramica feed dati cliente](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

Consulta [Componenti raccolta dati](../../reference/system-components/components-data-collection.md).

## SFTP/S 3 {#sftp-s3}

Gli [!UICONTROL SFTP/S3] editori ricevono dati ID sincronizzati dall &#39; [!UICONTROL Outbound Feed Converter]. Quando questi file sono pronti, l&#39; [!UICONTROL SFTP/S3 publishers] invio questi dati a una destinazione specificata dal client. Questi file contengono dati ID sincronizzati con una mappatura uno-molti degli [!DNL Audience Manager] ID utente (UUID) a:

* ID dispositivo/ID fornitore dati (DPUUID)
* ID del segmento qualificato
* ID caratteristiche

[!DNL Audience Manager] i clienti non hanno accesso alle funzionalità che controllano direttamente [!UICONTROL SFPT/S3 publishers]. I clienti utilizzano questo servizio indirettamente quando creano e inviano dati alle destinazioni. Il [!UICONTROL SFTP/S3] sistema è, essenzialmente, un processo automatizzato di lavoro che viene eseguito a intervalli pianificati.

## IRIS {#iris}

In greco, è un [!UICONTROL Iris] figure che viaggia e invia messaggi rapidamente. [!UICONTROL IRIS] Il sistema è un namespace che riflette le caratteristiche di questa figura dall&#39;antico mondo. Nei termini moderni, [!UICONTROL IRIS] si tratta di una sincronizzazione a bassa latenza, di un servizio di sincronizzazione ad alta frequenza e di un servizio di trasferimento dati.

[!UICONTROL IRIS] funziona con lo stesso tipo di dati del [!UICONTROL SFTP/S3] sistema. Tuttavia, è diverso [!UICONTROL IRIS] perché invia dati alle destinazioni in tempo reale anziché a intervalli impostati. Questo è un sistema a parte perché gli [!UICONTROL SFTP/S3] editori non possono inviare dati a una destinazione HTTP e non sono progettati per trasferimenti di dati in tempo reale.

Non sono disponibili controlli dell&#39;interfaccia utente con [!UICONTROL IRIS]cui i clienti possono lavorare direttamente. I clienti lavorano [!UICONTROL IRIS] indirettamente quando creano e inviano dati alle destinazioni e per altri processi che richiedono trasferimenti di dati rapidi.

Esempi di [!UICONTROL IRIS] servizi e funzionalità includono:

* La sincronizzazione rapida (entro 30 secondi) per i cookie e i segmenti. Può sincronizzare [!DNL Audience Manager] il cookie, i cookie del partner o entrambi.
* Trasferimenti di dati in tempo reale. [!UICONTROL IRIS] è responsabile dell&#39;invio di eventi di qualificazione segmenti in tempo reale a un partner o a un&#39;altra destinazione. Questi dati sono formattati in formato JSON e inviati tramite `POST` una richiesta HTTP.

* Trasferimenti di dati server-to-server in massa: Se si scambiano grandi quantità di dati con [!DNL Audience Manager], [!UICONTROL IRIS] è il sistema con cui i server interagiscono per trasferire i dati.

* Infrastruttura affidabile che funziona in scala ed è tollerante. Sistemi che includono [!UICONTROL IRIS] Amazon SQS, Amazon EC 2 e Cassandra.

**Regole di mappatura segmenti**

Per ottimizzare il traffico tra [!UICONTROL IRIS] e segmenti, [!UICONTROL IRIS] invia segmenti alle destinazioni in base a un set di regole.

1. **Nuova qualifica segmento**: quando un dispositivo si qualifica per un nuovo segmento, [!UICONTROL IRIS] invia tutti i segmenti associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti.

1. **Nuova disattivazione del segmento**: quando un dispositivo non si qualifica più per un segmento, [!UICONTROL IRIS] invia tutte le qualifiche e i sottotitoli del segmento associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti.

1. **Aggiornamenti della mappatura destinazione**: quando viene aggiornata una mappatura di destinazione [!UICONTROL IRIS] , invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a tali segmenti, alla successiva visualizzazione del dispositivo da Audience Manager.

1. **Aggiornamenti del grafico del dispositivo**: quando un ID dispositivo viene aggiunto o rimosso dal grafico del dispositivo utilizzato per valutare un segmento, [!UICONTROL IRIS] invia tutti i segmenti associati a tale dispositivo a tutte le destinazioni mappate a tali segmenti, alla successiva visualizzazione del dispositivo da Audience Manager.

>[!IMPORTANT]
>
>Se Audience Manager non rileva alcuno degli aggiornamenti sopra per 3 giorni consecutivi, [!UICONTROL IRIS] invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a questi segmenti, alla successiva visualizzazione del dispositivo da Audience Manager.

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

## Server cache profilo (PCS) {#pcs}

Consulta [Componenti raccolta dati](../../reference/system-components/components-data-collection.md).
