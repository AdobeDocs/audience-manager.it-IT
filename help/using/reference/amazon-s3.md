---
description: Informazioni su Amazon Simple Storage Service (Amazon S3).
seo-description: Informazioni su Amazon Simple Storage Service (Amazon S3).
seo-title: Informazioni su Amazon S3
solution: Audience Manager
title: Informazioni su Amazon S3
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: 'Riferimenti '
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Informazioni su Amazon S3{#amazon-s-about}

Informazioni su Amazon Simple Storage Service (Amazon S3).

Come best practice, consigliamo di utilizzare Amazon S3 invece di FTP come metodo per ottenere file da e consegnare file ai partner. Amazon S3 fornisce una semplice interfaccia di servizi web che può essere utilizzata per memorizzare e recuperare qualsiasi quantità di dati, in qualsiasi momento, da qualsiasi punto del web.

I vantaggi dell’utilizzo di Amazon S3 includono:

* **Scalabilità:** Amazon S3 offre una scalabilità quasi illimitata.
* **Affidabilità e disponibilità:** Amazon S3 fornisce servizi di storage ad alta durabilità e ad alta disponibilità.
* **Velocità:** Amazon S3 consente trasferimenti rapidi dei dati.
* **Facilità di utilizzo:** Amazon S3 è molto facile da usare e da implementare. L’implementazione può essere in esecuzione in circa un’ora. L&#39;implementazione di una directory FTP richiede molto più tempo.
* **Caricamenti in più parti:** i file di grandi dimensioni possono essere caricati in modo rapido ed efficiente come file in più parti.
* **Sicurezza:** Amazon S3 offre una protezione avanzata.

   * Tutte le directory sono accessibili solo al cliente o al client appropriato.
   * Supporto del protocollo HTTPS per caricamenti e download. È sempre necessario utilizzare HTTPS durante il trasferimento di file in [!DNL Audience Manager].
   * Amazon S3 fornisce la crittografia-at-rest per la crittografia dei [file di dati in uscita](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Utilizziamo il metodo di crittografia [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html), che consente di generare e gestire automaticamente le chiavi di crittografia da Amazon S3.

* **Supporto per il debug e il backup:** Amazon S3 consente  [!DNL Audience Manager] di conservare copie esatte dei file per semplificare il debug o il re-trasferimento.

Per ulteriori informazioni su Amazon S3, consulta le risorse seguenti:

[Servizio di archiviazione semplice Amazon (Amazon S3)](https://aws.amazon.com/s3/)  sul sito web Amazon Web Services.

[Guida introduttiva ad Amazon Simple Storage ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Service sul sito web della documentazione AWS.
