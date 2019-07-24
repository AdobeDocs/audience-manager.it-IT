---
description: Come opzione, puoi comprimere i file di dati quando li invii ad Audience Manager.
seo-description: Come opzione, puoi comprimere i file di dati quando li invii ad Audience Manager.
seo-title: Compressione file per file di trasferimento dati in entrata
solution: Audience Manager
title: Compressione file per file di trasferimento dati in entrata
uuid: 2 a 68 f 69 c -60 b 0-4002-863 b -302 d 2320 e 356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

Come opzione, puoi comprimere i file di dati quando li invii ad Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip ( `.gz`) compression for inbound, asynchronous data transfers.

Audience Manager supporta anche file non compressi.

>[!IMPORTANT]
>
>Al momento non supportiamo la crittografia e la compressione sullo stesso file di dati in entrata. You can select to either [encrypt](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) or compress your inbound files.

## Amazon S 3 Compression

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. I file compressi devono essere di almeno 1 GB. Se i file sono più grandi, consulta il file e il processo di trasferimento con l'Assistenza clienti. Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>[!DNL FTP] Il client deve utilizzare la modalità binaria per trasferire file compressi o codificati. Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## Best practice

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* The maximum compressed file size for a `.gz` compressed file is 1 GB.
* Le dimensioni divise ottimizzate, per l'elaborazione più rapida o rapida dei file, sono di circa 1 GB non compresse o 200-300 MB.
* [!DNL Amazon S3] impone un limite di dimensioni file pari a 5 GB per i file caricati.