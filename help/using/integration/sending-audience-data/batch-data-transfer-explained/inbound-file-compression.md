---
description: Come opzione, puoi comprimere i file di dati quando li invii ad Audience Manager.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Compressione file per i file di trasferimento dati in entrata
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Compressione file per i file di trasferimento dati in entrata{#file-compression-for-inbound-data-transfer-files}

Puoi comprimere i file di dati quando li invii ad Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supporta la compressione gzip (`.gz`) per i trasferimenti di dati asincroni in entrata.

Audience Manager supporta anche i file non compressi.

>[!IMPORTANT]
>
>La crittografia per i file in entrata compressi con gzip (`.gz`) non è supportata.
>
>Per crittografare e comprimere i file in entrata, utilizzare la crittografia [PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). La crittografia [!DNL PGP] include la compressione dei file.

## Compressione Amazon S3

Per la consegna a [!DNL Amazon S3], è necessario utilizzare `.gz` o file non compressi. I file compressi devono essere di almeno 1 GB. Se i file sono più grandi, consulta l’Assistenza clienti per informazioni sul processo di trasferimento e file. Anche se [!DNL Audience Manager] è in grado di gestire file di grandi dimensioni, è possibile ridurre le dimensioni del file o rendere più efficiente il trasferimento dei dati.

>[!IMPORTANT]
>
>Il client [!DNL FTP] deve utilizzare la modalità binaria per trasferire i file compressi o crittografati. I file compressi o crittografati inviati in modalità [!DNL ASCII] danneggeranno il file di trasferimento dati.

## Best practice

* I file devono essere compressi [!DNL .gzip] (e avere l&#39;estensione [!DNL .gz]).
* La dimensione massima del file compresso per un file compresso `.gz` è 1 GB.
* Le dimensioni di suddivisione ottimali, per l&#39;elaborazione più rapida/tempestiva dei file, sono di circa 1 GB non compressi o 200-300 MB compressi.
* [!DNL Amazon S3] impone un limite di 5 GB per le dimensioni dei file caricati.
