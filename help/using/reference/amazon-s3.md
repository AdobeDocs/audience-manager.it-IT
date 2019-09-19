---
description: Informazioni su Amazon Simple Storage Service (Amazon S3).
seo-description: Informazioni su Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3 Informazioni
solution: Audience Manager
title: Amazon S3 Informazioni
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: Informazioni{#amazon-s-about}

Informazioni su Amazon Simple Storage Service (Amazon S3).

Come procedura ottimale, si consiglia di utilizzare Amazon S3 invece di FTP come metodo per ottenere file da e consegnare file ai partner. Amazon S3 fornisce una semplice interfaccia di servizi Web che può essere utilizzata per memorizzare e recuperare qualsiasi quantità di dati, in qualsiasi momento, da qualsiasi punto del web.

I vantaggi dell'utilizzo di Amazon S3 includono:

* **** Scalabilità: Amazon S3 offre una scalabilità quasi illimitata.
* **** Affidabilità e disponibilità: Amazon S3 offre elevata durata e servizi di storage ad alta disponibilità.
* **** Velocità: Amazon S3 consente trasferimenti rapidi di dati.
* **** Facilità di utilizzo: Amazon S3 è molto facile da usare e da implementare. L'implementazione può essere operativa in circa un'ora. L'implementazione di una directory FTP richiede molto più tempo.
* **** Caricamenti con più parti: I file di grandi dimensioni possono essere caricati in modo rapido ed efficiente durante il caricamento di più parti.
* **** Sicurezza: Amazon S3 fornisce una forte sicurezza.

   * Tutte le directory sono accessibili solo al cliente o al cliente appropriato.
   * Supporto del protocollo HTTPS per caricamenti e download. È sempre necessario utilizzare HTTPS quando si trasferiscono i file in [!DNL Audience Manager].
   * Amazon S3 fornisce la crittografia a riposo per la crittografia dei file [di dati](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)in uscita. Utilizziamo il metodo di crittografia [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) , che consente di generare e gestire automaticamente le chiavi di crittografia da Amazon S3.

* **** Supporto per debug e backup: Amazon S3 consente [!DNL Audience Manager] di conservare copie esatte dei file per facilitare il debug o i ri-trasferimenti.

Per ulteriori informazioni su Amazon S3, consultate le risorse seguenti:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) sul sito Web Amazon Web Services.

[Guida introduttiva ad Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) disponibile sul sito Web della documentazione AWS.
