---
description: Informazioni su Amazon Simple Storage Service (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Informazioni su Amazon S3
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Amazon S3: informazioni{#amazon-s-about}

Informazioni su Amazon Simple Storage Service (Amazon S3).

Come best practice, consigliamo di utilizzare Amazon S3 invece di FTP come metodo per ottenere file da e consegnare file ai partner. Amazon S3 fornisce una semplice interfaccia di servizi web che può essere utilizzata per memorizzare e recuperare qualsiasi quantità di dati, in qualsiasi momento, da qualsiasi punto del web.

I vantaggi dell’utilizzo di Amazon S3 includono:

* **Scalabilità:** Amazon S3 fornisce una scalabilità quasi illimitata.
* **Affidabilità e disponibilità:** Amazon S3 fornisce servizi di archiviazione ad alta disponibilità e resistenza elevata.
* **Velocità:** Amazon S3 consente trasferimenti di dati rapidi.
* **Facilità d&#39;uso:** Amazon S3 è molto facile da usare e da implementare. L’implementazione sarà operativa tra circa un’ora. L’implementazione di una directory FTP richiede molto più tempo.
* **Caricamenti in più parti:** I file di grandi dimensioni possono essere caricati in modo rapido ed efficiente come caricamenti in più parti.
* **Sicurezza:** Amazon S3 fornisce una sicurezza elevata.

   * Tutte le directory sono accessibili solo al cliente o client appropriato.
   * Supporto del protocollo HTTPS per caricamenti e download. Utilizzare sempre HTTPS durante il trasferimento dei file in [!DNL Audience Manager].
   * Amazon S3 fornisce la crittografia a riposo per la crittografia di [file di dati in uscita](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Viene utilizzato il metodo di crittografia [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html), che consente la generazione e la gestione automatica delle chiavi di crittografia da parte di Amazon S3.

* **Supporto debug e backup:** Amazon S3 consente a [!DNL Audience Manager] di conservare copie esatte dei file per semplificare il debug o i ritrasferimenti.

Per ulteriori informazioni su Amazon S3, consulta le seguenti risorse:

[Servizio di archiviazione semplice di Amazon (Amazon S3)](https://aws.amazon.com/s3/) sul sito Web Amazon Web Services.

[Guida introduttiva ad Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) nel sito Web della documentazione di AWS.
