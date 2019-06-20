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


# Compressione file per file di trasferimento dati in entrata{#file-compression-for-inbound-data-transfer-files}

Come opzione, puoi comprimere i file di dati quando li invii ad Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supporta la compressione gzip ( `.gz`) per trasferimenti di dati asincroni e in ingresso.

Audience Manager supporta anche file non compressi.

>[!IMPORTANT]
>
>Al momento non supportiamo la crittografia e la compressione sullo stesso file di dati in entrata. È possibile selezionare [o](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) comprimere i file in entrata.

## Amazon S 3 Compression

Per la consegna, [!DNL Amazon S3]dovete usare file `.gz` o file non compressi. I file compressi devono essere di almeno 1 GB. Se i file sono più grandi, consulta il file e il processo di trasferimento con l&#39;Assistenza clienti. Sebbene [!DNL Audience Manager] possano gestire file di grandi dimensioni, potrebbero essere disponibili modi per ridurre le dimensioni del file o rendere più efficiente il trasferimento di dati.

>[!IMPORTANT]
>
>[!DNL FTP] Il client deve utilizzare la modalità binaria per trasferire file compressi o codificati. I file compressi o cifrati inviati in [!DNL ASCII] modalità danneggieranno il file di trasferimento dati.

## Best practice

* I file devono essere [!DNL .gzip] compressi (e avere un&#39;estensione [!DNL .gz] di file).
* La dimensione massima del file compresso per un `.gz` file compresso è di 1 GB.
* Le dimensioni divise ottimizzate, per l&#39;elaborazione più rapida o rapida dei file, sono di circa 1 GB non compresse o 200-300 MB.
* [!DNL Amazon S3] impone un limite di dimensioni file pari a 5 GB per i file caricati.