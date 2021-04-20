---
description: Come opzione, è possibile comprimere i file di dati quando vengono inviati ad Audience Manager.
seo-description: Come opzione, è possibile comprimere i file di dati quando vengono inviati ad Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Compressione file per i file di trasferimento dati in entrata
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 9%

---

# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

È possibile comprimere i file di dati quando vengono inviati ad Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supporta la compressione gzip (`.gz`) per i trasferimenti di dati in entrata e in modo asincrono.

Audience Manager supporta anche i file non compressi.

>[!IMPORTANT]
>
>Non è supportata la crittografia su file in entrata compressi con gzip (`.gz`).
>
>Per crittografare e comprimere i file in entrata, utilizza la [crittografia PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] La crittografia include la compressione dei file.

## Compressione Amazon S3

Per la consegna a [!DNL Amazon S3], è necessario utilizzare `.gz` o file non compressi. I file compressi devono essere di 1 GB o più piccoli. Se i file sono più grandi, rivolgiti all’Assistenza clienti per discutere del processo di trasferimento e dei file. Anche se [!DNL Audience Manager] può gestire file di grandi dimensioni, ci possono essere modi per ridurre la dimensione del file o rendere il trasferimento dei dati più efficiente.

>[!IMPORTANT]
>
>Il client [!DNL FTP] deve utilizzare la modalità binaria per trasferire file compressi o crittografati. I file compressi o crittografati inviati in modalità [!DNL ASCII] danneggiano il file di trasferimento dei dati.

## Best practice

* I file devono essere compressi [!DNL .gzip] (e avere un&#39;estensione di file [!DNL .gz]).
* La dimensione massima del file compresso per un file `.gz` compresso è di 1 GB.
* Le dimensioni di divisione ottimali, per l&#39;elaborazione più rapida/veloce dei file, sono circa 1 GB non compressi o 200-300 MB compressi.
* [!DNL Amazon S3] impone un proprio limite di dimensione del file di 5 GB per i file caricati.
