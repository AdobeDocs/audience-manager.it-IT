---
description: Il processo di trasferimento dei dati in uscita per i clienti che utilizzano Amazon Simple Storage Service (Amazon S3) richiede di richiedere la chiave di accesso e la chiave segreta di Amazon S3, per poter consegnare i file di dati in uscita al bucket.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file un uscita
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 12%

---

# Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file un uscita {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Il [!UICONTROL Outbound Data Transfer] processo per i clienti che utilizzano [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) richiede di richiedere [!DNL Amazon S3] chiave di accesso e chiave segreta, per consegnare i file di dati in uscita al bucket.

Se preferisci non condividere il tuo [!DNL Amazon S3] chiave di accesso e chiave segreta con noi, contatta il tuo [!DNL Audience Manager] o l&#39;Assistenza clienti e configureranno [!DNL Cross-Account Bucket Permissions] per te. Devi solo aggiungere il nostro [!DNL Amazon S3] ID account in un elenco consentiti per [!DNL S3] bucket in cui desideri ricevere i file di dati in uscita, come descritto nella sezione [Documentazione di Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Il tuo [!DNL Audience Manager] consulente o assistenza clienti fornirà [!DNL Amazon S3] ID account.
