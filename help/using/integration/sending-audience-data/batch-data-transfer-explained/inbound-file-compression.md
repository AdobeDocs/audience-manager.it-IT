---
description: Come opzione, puoi comprimere i file di dati quando li invii ad Audience Manager.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: File Compression for Inbound Data Transfer Files
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 7%

---

# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

Puoi comprimere i file di dati quando li invii a Audience Manager.

<!-- inbound-file-compression.xml -->

L’Audience Manager supporta gzip (`.gz`) per trasferimenti di dati asincroni in entrata.

Audience Manager supporta anche i file non compressi.

>[!IMPORTANT]
>
>La crittografia per i file in entrata compressi con gzip non è supportata (`.gz`).
>
>Per crittografare e comprimere i file in entrata, utilizzare [Crittografia PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] la crittografia include la compressione dei file.

## Compressione Amazon S3

Per la consegna a [!DNL Amazon S3], è necessario utilizzare `.gz` o file non compressi. I file compressi devono essere di almeno 1 GB. Se i file sono più grandi, consulta l’Assistenza clienti per informazioni sul processo di trasferimento e file. Anche se [!DNL Audience Manager] può gestire file molto grandi, ci possono essere modi per ridurre la dimensione del file o rendere più efficiente il trasferimento di dati.

>[!IMPORTANT]
>
>Il tuo [!DNL FTP] il client deve utilizzare la modalità binaria per trasferire i file compressi o crittografati. File compressi o crittografati inviati [!DNL ASCII] La modalità danneggerà il file di trasferimento dati.

## Best practice

* I file devono essere [!DNL .gzip] compresso (e hanno un [!DNL .gz] file).
* Dimensione massima del file compresso per un `.gz` il file compresso è di 1 GB.
* Le dimensioni di suddivisione ottimali, per l&#39;elaborazione più rapida/tempestiva dei file, sono di circa 1 GB non compressi o 200-300 MB compressi.
* [!DNL Amazon S3] impone un proprio limite di 5 GB per le dimensioni dei file caricati.
