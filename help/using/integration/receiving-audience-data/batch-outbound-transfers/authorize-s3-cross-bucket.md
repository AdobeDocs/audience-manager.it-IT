---
description: Il processo di trasferimento dei dati in uscita per i clienti che utilizzano Amazon Simple Storage Service (Amazon S3) richiede la richiesta della chiave di accesso e della chiave segreta Amazon S3, al fine di consegnare i file di dati in uscita al tuo bucket.
seo-description: Il processo di trasferimento dei dati in uscita per i clienti che utilizzano Amazon Simple Storage Service (Amazon S3) richiede la richiesta della chiave di accesso e della chiave segreta Amazon S3, al fine di consegnare i file di dati in uscita al tuo bucket.
seo-title: Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file un uscita
solution: Audience Manager
title: Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file un uscita
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Trasferimenti di dati in uscita
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 14%

---

# Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file un uscita {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Il processo [!UICONTROL Outbound Data Transfer] per i clienti che utilizzano [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) richiede la richiesta della chiave di accesso e della chiave segreta [!DNL Amazon S3] al fine di consegnare i file di dati in uscita al tuo bucket.

Se preferisci non condividere la tua chiave di accesso e la tua chiave segreta [!DNL Amazon S3] con noi, contatta il tuo consulente [!DNL Audience Manager] o l&#39;Assistenza clienti e configureranno [!DNL Cross-Account Bucket Permissions] per te. Devi solo aggiungere il nostro ID account [!DNL Amazon S3] a un elenco consentiti per il bucket [!DNL S3] in cui desideri ricevere i file di dati in uscita, come descritto nella [documentazione di Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Il tuo consulente [!DNL Audience Manager] o l&#39;Assistenza clienti ti fornirà il nostro ID account [!DNL Amazon S3].
