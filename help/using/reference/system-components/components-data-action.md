---
description: I componenti di azione dati includono Customer Data Feeds, Data Collection Server, editori SFTP/S3/HTTP, IRIS e Profile Cache Server.
seo-description: I componenti di azione dati includono Customer Data Feeds, Data Collection Server, editori SFTP/S3/HTTP, IRIS e Profile Cache Server.
seo-title: Componenti di azione sui dati
solution: Audience Manager
title: Componenti di azione sui dati
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 3%

---

# Componenti di azione sui dati{#data-action-components}

I componenti di azione dati includono Customer Data Feeds, Data Collection Server, editori SFTP/S3/HTTP, IRIS e Profile Cache Server.

<!-- 

c_compact.xml

 -->

I componenti azione sono sistemi e processi che ti consentono di spostare i dati in e fuori da [!DNL Audience Manager] e (per mancanza di una frase migliore) ti consentono di utilizzarli. Questi componenti [!DNL Audience Manager] includono:

## Feed di dati cliente (CDF, Customer Data Feeds) {#cdf}

[!UICONTROL CDF] sono file inviati ogni ora ai clienti. Contengono gli ID utente insieme agli ID del segmento, agli ID delle caratteristiche e ad altri dati associati. Per ulteriori informazioni, consulta [Panoramica sui feed di dati cliente](../../features/cdf-files.md).

## Server di raccolta dati (DCS) {#dcs}

Consulta [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Gli editori [!UICONTROL SFTP/S3] ricevono i dati ID sincronizzati da [!UICONTROL Outbound Feed Converter]. Quando questi file sono pronti, i [!UICONTROL SFTP/S3 publishers] inviano questi dati a una destinazione specificata dal client. Questi file contengono dati ID sincronizzati con una mappatura uno-molti degli ID utente [!DNL Audience Manager] (UUID) in:

* ID dispositivo/ID provider dati (DPUUID)
* ID segmento qualificati
* ID delle caratteristiche

[!DNL Audience Manager] i clienti non hanno accesso alle funzioni che controllano direttamente il  [!UICONTROL SFPT/S3 publishers]. I clienti utilizzano indirettamente questo servizio quando creano e inviano dati alle destinazioni. Il sistema [!UICONTROL SFTP/S3] è essenzialmente un processo di lavoro automatizzato che viene eseguito a intervalli pianificati.

## IRIS {#iris}

Nella mitologia greca, [!UICONTROL Iris] è una figura che viaggia e invia messaggi rapidamente. Il sistema [!UICONTROL IRIS] è un omonimo che riflette le caratteristiche di questa figura del mondo antico. In termini moderni, [!UICONTROL IRIS] è un servizio di sincronizzazione cookie ad alta frequenza e a bassa latenza e trasferimento dati.

[!UICONTROL IRIS] funziona con lo stesso tipo di dati del  [!UICONTROL SFTP/S3] sistema. Tuttavia, [!UICONTROL IRIS] è diverso perché invia dati alle destinazioni in tempo reale anziché a intervalli definiti. Questo è un sistema separato perché gli [!UICONTROL SFTP/S3] editori non possono inviare dati a una destinazione HTTP e non sono progettati per trasferimenti di dati in tempo reale.

Non sono disponibili controlli di interfaccia che consentono ai clienti di utilizzare direttamente [!UICONTROL IRIS]. I clienti lavorano in modo indiretto con [!UICONTROL IRIS] quando creano e inviano dati a destinazioni e per altri processi che richiedono trasferimenti rapidi di dati.

Esempi di servizi e funzionalità [!UICONTROL IRIS] includono:

* Sincronizzazione rapida (entro 30 secondi) per cookie e segmenti. Può sincronizzare il cookie [!DNL Audience Manager], i cookie partner o entrambi.
* Trasferimenti di dati in tempo reale. [!UICONTROL IRIS] è responsabile dell’invio di eventi di qualificazione dei segmenti in tempo reale a un partner o a un’altra destinazione. Questi dati sono in formato JSON e inviati tramite una richiesta HTTP `POST`.

* Trasferimenti in massa di dati da server a server: Se si scambiano grandi quantità di dati con [!DNL Audience Manager], [!UICONTROL IRIS] è il sistema con cui i server si impegnano a trasferire i dati.

* Infrastruttura affidabile che funziona su larga scala ed è tollerante agli errori. I sistemi che alimentano [!UICONTROL IRIS] includono Amazon SQS, Amazon EC2 e Cassandra.

**Regole di mappatura dei segmenti**

Per ottimizzare il traffico tra [!UICONTROL IRIS] e le destinazioni dei segmenti, [!UICONTROL IRIS] invia i segmenti alle destinazioni in base a un set di regole.

1. **Qualificazione** di un nuovo segmento: quando un dispositivo si qualifica per un nuovo segmento,  [!UICONTROL IRIS] invia tutti i segmenti associati a quel dispositivo a tutte le destinazioni mappate a questi segmenti.

1. **Nuova qualificazione** del segmento: quando un dispositivo non è più idoneo per un segmento,  [!UICONTROL IRIS] invia tutte le qualifiche e le interdizioni del segmento associate a quel dispositivo a tutte le destinazioni mappate a questi segmenti.

1. **Aggiornamenti** della mappatura della destinazione: quando una mappatura di destinazione viene aggiornata,  [!UICONTROL IRIS] invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a questi segmenti, la prossima volta che l’Audience Manager vede il dispositivo.

1. **Aggiornamenti** grafici dei dispositivi: quando un qualsiasi ID dispositivo viene aggiunto o rimosso dal grafico dei dispositivi utilizzato per valutare un segmento,  [!UICONTROL IRIS] invia tutti i segmenti associati a quel dispositivo a tutte le destinazioni mappate a questi segmenti, l’Audience Manager successivo visualizza il dispositivo.

>[!IMPORTANT]
>
>Se Audience Manager non rileva nessuno degli aggiornamenti precedenti per 3 giorni consecutivi, [!UICONTROL IRIS] invia tutti i segmenti associati a un dispositivo a tutte le destinazioni mappate a questi segmenti, l’Audience Manager successivo visualizzerà il dispositivo.

**File di dati di esempio**

L’esempio seguente contiene dati di segmento in tempo reale da [!UICONTROL IRIS]. Tieni presente che si tratta solo di dati di esempio. Ogni cliente può avere requisiti di formattazione diversi in modo che il contenuto possa variare.

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

## Server di cache del profilo (PCS) {#pcs}

Consulta [Data Collection Components](../../reference/system-components/components-data-collection.md).
