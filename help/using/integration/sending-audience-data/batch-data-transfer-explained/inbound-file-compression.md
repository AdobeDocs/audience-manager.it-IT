---
description: Come opzione, potete comprimere i file di dati quando li inviate ad Audience Manager.
seo-description: Come opzione, potete comprimere i file di dati quando li inviate ad Audience Manager.
seo-title: Compressione file per i file di trasferimento dati in entrata
solution: Audience Manager
title: Compressione file per i file di trasferimento dati in entrata
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Compressione file per i file di trasferimento dati in entrata{#file-compression-for-inbound-data-transfer-files}

Come opzione, potete comprimere i file di dati quando li inviate ad Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supporta la compressione gzip ( `.gz`) per i trasferimenti di dati in entrata e asincrona.

Audience Manager supporta anche i file non compressi.

>[!IMPORTANT]
>
>Al momento non è supportata la crittografia e la compressione sullo stesso file di dati in entrata. È possibile selezionare per [cifrare](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) o comprimere i file in entrata.

## Compressione Amazon S3

Per la consegna a [!DNL Amazon S3], è necessario utilizzare file `.gz` o file non compressi. I file compressi devono essere di almeno 1 GB. Se le dimensioni dei file sono maggiori, parla del file e del processo di trasferimento con l'Assistenza clienti. Anche se [!DNL Audience Manager] può gestire file molto grandi, ci possono essere modi per ridurre la dimensione del file o rendere il trasferimento di dati più efficiente.

>[!IMPORTANT]
>
>Il [!DNL FTP] client deve utilizzare la modalità binaria per trasferire i file compressi o crittografati. I file compressi o crittografati inviati in [!DNL ASCII] modalità danneggiano il file di trasferimento dei dati.

## Best practice

* I file devono essere [!DNL .gzip] compressi (e avere un'estensione di [!DNL .gz] file).
* La dimensione massima del file compresso per un file `.gz` compresso è di 1 GB.
* Le dimensioni di divisione ottimali, per l'elaborazione più rapida e veloce dei file, sono circa 1 GB non compressi o 200-300 MB compressi.
* [!DNL Amazon S3] impone un proprio limite di dimensione file di 5 GB per i file caricati.