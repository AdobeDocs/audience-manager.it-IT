---
description: Il processo di trasferimento dati in uscita per i clienti che utilizzano Amazon Simple Storage Service (Amazon S3) richiede che venga richiesto il codice di accesso e la chiave segreta Amazon S3, al fine di inviare i file di dati in uscita al bucket.
seo-description: Il processo di trasferimento dati in uscita per i clienti che utilizzano Amazon Simple Storage Service (Amazon S3) richiede che venga richiesto il codice di accesso e la chiave segreta Amazon S3, al fine di inviare i file di dati in uscita al bucket.
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

Il [!UICONTROL Outbound Data Transfer] processo per i clienti che utilizzano [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) richiede che noi chiediamo la tua chiave di [!DNL Amazon S3] accesso e la chiave segreta, al fine di consegnare i file di dati in uscita al tuo bucket.

Se preferisci non condividere con noi la tua chiave [!DNL Amazon S3] di accesso e la chiave segreta, contatta il tuo [!DNL Audience Manager] consulente o l&#39;Assistenza clienti e ti installeranno [!DNL Cross-Account Bucket Permissions] . È sufficiente aggiungere il nostro [!DNL Amazon S3] ID account a un elenco di consenso per il [!DNL S3] bucket in cui si desidera ricevere i file di dati in uscita, come descritto nella documentazione [di](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)Amazon S3. Il tuo [!DNL Audience Manager] consulente o l&#39;Assistenza clienti ti fornirà il nostro [!DNL Amazon S3] ID account.