---
description: Per inviare dati dal bucket Amazon S3 ad Audienci Manager, devi prima richiedere la configurazione di un ruolo Amazon S3 dedicato.
solution: Audience Manager
title: Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file in entrata
feature: Inbound Data Transfers
source-git-commit: 17cee6971ca1d5cda8f272558a46220227fc51f7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file in entrata {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Per inviare dati dal bucket Amazon S3 ad Audienci Manager, devi prima richiedere la configurazione di un ruolo Amazon S3 dedicato.

A questo scopo, segui i passaggi descritti di seguito.

1. Contatta l’Assistenza clienti e richiedi un metodo alternativo per l’invio di file agli Audienci Manager.
2. Fornisci all’Assistenza clienti i [!DNL Amazon Resource Name (ARN)] per un ruolo nell’account Amazon S3 che utilizzerai per inviare file. _Questo ruolo deve essere creato prima di contattare l&#39;Assistenza clienti_. Al termine della configurazione, l’Assistenza clienti ti fornirà [!DNL Amazon Resource Name (ARN)] per il ruolo appena creato.
3. Modifica le autorizzazioni del ruolo Amazon S3 esistente per assumere il ruolo fornito dall’Assistenza clienti.

>[!NOTE]
>
>Quando trasferisci i dati in entrata nel bucket Audienci Manager Amazon S3, assicurati di utilizzare il `bucket-owner-full-control` [elenco di controllo di accesso](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) affinché Audience Manager possa elaborare correttamente i dati.
>
>Esempio per il comando Amazon Web Services: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`

