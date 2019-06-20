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


# Amazon S 3: Informazioni{#amazon-s-about}

Informazioni su Amazon Simple Storage Service (Amazon S 3).

Come procedura ottimale, consigliamo di utilizzare Amazon S 3 invece dell&#39;FTP come metodo per ottenere file e inviare file ai partner. Amazon S 3 offre una semplice interfaccia dei servizi Web che può essere utilizzata per archiviare e recuperare tutti i dati, in qualsiasi momento, da qualsiasi punto del Web.

I vantaggi dell&#39;utilizzo di Amazon S 3 includono:

* **Scalabilità:** Amazon S 3 offre scalabilità quasi illimitata.
* **Affidabilità e disponibilità:** Amazon S 3 offre un&#39;alta durata e servizi di archiviazione ad alta disponibilità.
* **Velocità:** Amazon S 3 consente trasferimenti di dati veloci.
* **Facilità di utilizzo:** Amazon S 3 è molto facile da utilizzare e da implementare. La vostra implementazione può essere attivata per circa un&#39;ora. L&#39;implementazione di una directory FTP richiede molto più tempo.
* **Caricamenti multiparte:** I file di grandi dimensioni possono essere caricati in modo rapido ed efficiente come caricamenti di file multiparte.
* **Protezione:** Amazon S 3 offre una protezione efficace.

   * Tutte le directory sono accessibili solo al cliente o client appropriato.
   * Supporto del protocollo HTTPS per caricamenti e download. È sempre necessario utilizzare HTTPS per il trasferimento di file [!DNL Audience Manager].
   * Amazon S 3 fornisce la cifratura per la cifratura [di file di dati in uscita](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Utilizziamo il [metodo di](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) cifratura SSE-S 3, che consente la generazione e la gestione automatica dei tasti di cifratura da Amazon S 3.

* **Debug and Backup Support:** Amazon S 3 consente [!DNL Audience Manager] di conservare copie esatte dei file per semplificare il debug o il trasferimento.

Per ulteriori informazioni su Amazon S 3, consulta le risorse seguenti:

[Amazon Simple Storage Service (Amazon S 3)](https://aws.amazon.com/s3/) sul sito Web Amazon Web Services.

[Guida introduttiva ad Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) nel sito Web della documentazione AWS.
