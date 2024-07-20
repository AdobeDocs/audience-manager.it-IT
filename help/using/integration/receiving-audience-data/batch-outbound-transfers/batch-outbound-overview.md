---
description: Audience Manager invia dati batch a provider di contenuti di terze parti in base a queste specifiche.
seo-description: Adobe Audience Manager (AAM) sends batch data to third-party content providers according to these specifications.
seo-title: Batch Outbound Data Transfers in Adobe Audience Manager (AAM)
title: Trasferimenti in batch di dati in uscita
feature: Outbound Data Transfers
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Trasferimenti in batch di dati in uscita

Audience Manager invia dati batch a provider di contenuti di terze parti in base a queste specifiche.

* [Nome dei file di dati in uscita: sintassi ed esempi](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

  Descrive i campi obbligatori, la sintassi e le convenzioni utilizzati per denominare un file di dati in uscita.

* [Configurare l’integrazione del trasferimento di dati in batch](batch-server-configuration.md)

  Descrive i metodi tramite i quali è possibile configurare l’integrazione di trasferimento dati in batch.

* [File di trasferimento dei controlli per trasferimenti di file di registro](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

  I file di controllo del trasferimento (.info) forniscono informazioni sui metadati sui trasferimenti di file in modo che i partner possano verificare che i trasferimenti di file gestiti da Audience Manager siano corretti.

* [Macro modello in uscita](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

  Elenca le macro utilizzabili per creare modelli in uscita. ad esempio macro per nomi di file, macro per intestazioni e macro per contenuti.

* [Esempi di macro in uscita](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

  Esempi di utilizzo di alcune delle macro comuni per la creazione di modelli di file in uscita.

* [Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file in uscita](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

  Il processo di trasferimento dei dati in uscita per i clienti che utilizzano Amazon Simple Storage Service (Amazon S3) richiede di richiedere la chiave di accesso e la chiave segreta di Amazon S3, per poter consegnare i file di dati in uscita al bucket.
