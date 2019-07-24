---
description: Come opzione, puoi cifrare file di dati con cifratura PGP quando li invii ad Audience Manager.
seo-description: Come opzione, puoi cifrare file di dati con cifratura PGP quando li invii ad Audience Manager.
seo-title: Cifratura file PGP per i tipi di dati in entrata
solution: Audience Manager
title: Cifratura file PGP per i tipi di dati in entrata
uuid: 89 caace 1-0259-48 fc -865 b-d 525 ec 7822 f 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

As an option, you can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Al momento non supportiamo la crittografia e la compressione sullo stesso file di dati in entrata. You can select to either encrypt or [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) your inbound files.

Seguire i passaggi descritti di seguito per cifrare i file di dati in entrata.

1. Download the [Audience Manager public key](./assets/adobe_pgp.pub).
1. Importare la chiave pubblica nell'archivio affidabile.

   For example, if you use [!DNL GPG], the command could be similar to the following:

   `gpg --import adobe_pgp.pub`

1. Convalidate che la chiave è stata importata correttamente eseguendo il comando seguente:

   `gpg --list-keys`

   Dovresti visualizzare un messaggio simile a quanto segue:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Cifra i dati in entrata utilizzando il comando seguente:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. Audience Manager supporta qualsiasi dimensione chiave.