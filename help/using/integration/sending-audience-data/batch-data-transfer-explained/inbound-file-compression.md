---
description: Come opzione, è possibile comprimere i file di dati durante l'invio a  Audience Manager.
seo-description: Come opzione, è possibile comprimere i file di dati durante l'invio a  Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Compressione file per i file di trasferimento dati in entrata
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 10%

---


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

È possibile comprimere i file di dati durante l&#39;invio a  Audience Manager.

<!-- inbound-file-compression.xml -->

 Audience Manager supporta la compressione gzip (`.gz`) per i trasferimenti di dati in entrata e asincrona.

 Audience Manager supporta anche i file non compressi.

>[!IMPORTANT]
>
>Non è supportata la crittografia per i file in entrata compressi con gzip (`.gz`).
>
>Per cifrare e comprimere i file in entrata, utilizzare la crittografia [PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] la crittografia include la compressione dei file.

##  Compressione Amazon S3

Per la distribuzione in [!DNL Amazon S3], è necessario utilizzare `.gz` o file non compressi. I file compressi devono essere di almeno 1 GB. Se le dimensioni dei file sono maggiori, parla del file e del processo di trasferimento con l&#39;Assistenza clienti. Anche se [!DNL Audience Manager] può gestire file molto grandi, ci possono essere modi per ridurre la dimensione del file o rendere il trasferimento di dati più efficiente.

>[!IMPORTANT]
>
>Il client [!DNL FTP] deve utilizzare la modalità binaria per trasferire i file compressi o crittografati. I file compressi o crittografati inviati in modalità [!DNL ASCII] danneggiano il file di trasferimento dei dati.

## Best practice

* I file devono essere compressi [!DNL .gzip] (e avere un&#39;estensione [!DNL .gz]).
* La dimensione massima del file compresso per un file compresso `.gz` è di 1 GB.
* Le dimensioni di divisione ottimali, per l&#39;elaborazione più rapida e veloce dei file, sono circa 1 GB non compressi o 200-300 MB compressi.
* [!DNL Amazon S3] impone un proprio limite di dimensione file di 5 GB per i file caricati.
