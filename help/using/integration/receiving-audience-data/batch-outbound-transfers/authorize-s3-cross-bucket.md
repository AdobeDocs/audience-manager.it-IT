---
description: Il processo di trasferimento dei dati in uscita per i clienti che utilizzano Amazon Simple Storage Service (Amazon S3) richiede di richiedere la chiave di accesso e la chiave segreta di Amazon S3, per poter consegnare i file di dati in uscita al bucket.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file in uscita
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 9c0254e8a29ffeb0353ed6faa898b74bcae7cef1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file in uscita {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Il processo [!UICONTROL Outbound Data Transfer] per i clienti che utilizzano [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) richiede che venga richiesta la chiave di accesso e la chiave segreta [!DNL Amazon S3] per recapitare i file di dati in uscita nel bucket.

Se preferisci non condividere con noi la chiave di accesso e la chiave segreta di [!DNL Amazon S3], contatta il tuo consulente [!DNL Audience Manager] o l&#39;Assistenza clienti e configureranno [!DNL Cross-Account Bucket Permissions] per te.

Devi solo aggiungere l&#39;ID account [!DNL Amazon S3] a un elenco consentiti per il bucket [!DNL S3] in cui desideri ricevere i file di dati in uscita, come descritto nella [documentazione di Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Il tuo consulente [!DNL Audience Manager] o l&#39;Assistenza clienti ti forniranno l&#39;ID account [!DNL Amazon S3].

>[!NOTE]
>
>A causa del limite di dimensioni degli oggetti di Amazon S3, Audience Manager supporta dimensioni suddivise fino a 1 TB. Se non si specifica alcuna dimensione di divisione, viene applicato automaticamente il limite di 1 TB.

