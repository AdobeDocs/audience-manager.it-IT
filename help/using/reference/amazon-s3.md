---
description: Informazioni su Amazon Simple Storage Service (Amazon S 3).
seo-description: Informazioni su Amazon Simple Storage Service (Amazon S 3).
seo-title: Amazon S 3 Informazioni
solution: Audience Manager
title: Amazon S 3 Informazioni
uuid: 8197 ecdf-df 8 f -488 d-bbc 0-d 8 d 4205 b 42 b 4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: About{#amazon-s-about}

Informazioni su Amazon Simple Storage Service (Amazon S 3).

Come procedura ottimale, consigliamo di utilizzare Amazon S 3 invece dell'FTP come metodo per ottenere file e inviare file ai partner. Amazon S 3 offre una semplice interfaccia dei servizi Web che può essere utilizzata per archiviare e recuperare tutti i dati, in qualsiasi momento, da qualsiasi punto del Web.

I vantaggi dell'utilizzo di Amazon S 3 includono:

* **Scalabilità:** Amazon S 3 offre scalabilità quasi illimitata.
* **Affidabilità e disponibilità:** Amazon S 3 offre un'alta durata e servizi di archiviazione ad alta disponibilità.
* **Velocità:** Amazon S 3 consente trasferimenti di dati veloci.
* **Facilità di utilizzo:** Amazon S 3 è molto facile da utilizzare e da implementare. La vostra implementazione può essere attivata per circa un'ora. L'implementazione di una directory FTP richiede molto più tempo.
* **Caricamenti multiparte:** I file di grandi dimensioni possono essere caricati in modo rapido ed efficiente come caricamenti di file multiparte.
* **Protezione:** Amazon S 3 offre una protezione efficace.

   * Tutte le directory sono accessibili solo al cliente o client appropriato.
   * Supporto del protocollo HTTPS per caricamenti e download. You should always use HTTPS when transferring files in [!DNL Audience Manager].
   * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **Debug and Backup Support:** Amazon S 3 consente [!DNL Audience Manager] di conservare copie esatte dei file per semplificare il debug o il trasferimento.

Per ulteriori informazioni su Amazon S 3, consulta le risorse seguenti:

[Amazon Simple Storage Service (Amazon S 3)](https://aws.amazon.com/s3/) sul sito Web Amazon Web Services.

[Guida introduttiva ad Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) nel sito Web della documentazione AWS.
