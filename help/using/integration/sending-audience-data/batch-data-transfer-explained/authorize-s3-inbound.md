---
description: Per inviare dati dal bucket Amazon S3 ad Audience Manager, devi prima richiedere la configurazione di un ruolo Amazon S3 dedicato.
solution: Audience Manager
title: Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file in entrata
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Utilizzo delle autorizzazioni bucket tra account diversi di Amazon S3 per i file in entrata {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Per inviare dati dal bucket Amazon S3 ad Audience Manager, devi prima richiedere la configurazione di un ruolo Amazon S3 dedicato.

A questo scopo, segui i passaggi descritti di seguito.

1. Contatta l’Assistenza clienti e richiedi un metodo alternativo per l’invio di file ad Audience Manager.
2. Fornisci all&#39;Assistenza clienti [!DNL Amazon Resource Name (ARN)] un ruolo nel tuo account Amazon S3 che utilizzerai per inviare file. _È necessario creare questo ruolo prima di contattare l&#39;Assistenza clienti_. Al termine della configurazione, l&#39;Assistenza clienti ti fornirà [!DNL Amazon Resource Name (ARN)] per il ruolo appena creato.
3. Modifica le autorizzazioni del ruolo Amazon S3 esistente per assumere il ruolo fornito dall’Assistenza clienti.

>[!NOTE]
>
>Durante il trasferimento dei dati in entrata al bucket Audience Manager Amazon S3, assicurati di utilizzare l&#39;`bucket-owner-full-control` [elenco di controllo degli accessi](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) affinché Audience Manager possa elaborare correttamente i dati.
>
>Esempio per il comando Amazon Web Services: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
