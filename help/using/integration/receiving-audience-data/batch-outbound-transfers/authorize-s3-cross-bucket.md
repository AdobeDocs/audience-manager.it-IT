---
description: Il processo di trasferimento dei dati in uscita per i clienti che utilizzano  Amazon Simple Storage Service ( Amazon S3) richiede la richiesta della chiave di accesso e della chiave segreta  Amazon S3, al fine di inviare i file di dati in uscita al bucket.
seo-description: Il processo di trasferimento dei dati in uscita per i clienti che utilizzano  Amazon Simple Storage Service ( Amazon S3) richiede la richiesta della chiave di accesso e della chiave segreta  Amazon S3, al fine di inviare i file di dati in uscita al bucket.
seo-title: Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file un uscita
solution: Audience Manager
title: Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file un uscita
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file un uscita {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Il processo [!UICONTROL Outbound Data Transfer] per i clienti che utilizzano [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) richiede che venga richiesta la chiave di accesso e la chiave segreta [!DNL Amazon S3], al fine di inviare i file di dati in uscita al bucket.

Se preferisci non condividere con noi la chiave di accesso e la chiave segreta [!DNL Amazon S3], contatta il tuo &lt;a1/> consulente o l&#39;Assistenza clienti e questi configureranno [!DNL Audience Manager] per te. [!DNL Cross-Account Bucket Permissions] È sufficiente aggiungere il nostro ID account [!DNL Amazon S3] a un elenco consentiti  per il periodo fisso [!DNL S3] in cui si desidera ricevere i file di dati in uscita, come descritto nella [ documentazione di Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Il tuo [!DNL Audience Manager] consulente o l&#39;Assistenza clienti ti fornirà il nostro ID account [!DNL Amazon S3].