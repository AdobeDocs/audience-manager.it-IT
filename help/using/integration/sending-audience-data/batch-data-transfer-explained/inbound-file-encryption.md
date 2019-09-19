---
description: Come opzione, potete crittografare i file di dati con crittografia PGP al momento dell'invio ad Audience Manager.
seo-description: Come opzione, potete crittografare i file di dati con crittografia PGP al momento dell'invio ad Audience Manager.
seo-title: Crittografia PGP file per i tipi di dati in entrata
solution: Audience Manager
title: Crittografia PGP file per i tipi di dati in entrata
uuid: 89cache1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Crittografia PGP file per i tipi di dati in entrata{#file-pgp-encryption-for-inbound-data-types}

Come opzione, potete crittografare i file di dati con [!DNL PGP] crittografia al momento dell'invio ad Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Al momento non è supportata la crittografia e la compressione sullo stesso file di dati in entrata. È possibile selezionare per cifrare o [comprimere](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) i file in entrata.

Seguire i passaggi descritti di seguito per cifrare i file di dati in entrata.

1. Scaricate la chiave [pubblica di](./assets/adobe_pgp.pub)Audience Manager.
1. Importa la chiave pubblica nello store affidabile.

   Ad esempio, se utilizzate [!DNL GPG], il comando potrebbe essere simile al seguente:

   `gpg --import adobe_pgp.pub`

1. Convalidate che la chiave sia stata importata correttamente eseguendo il comando seguente:

   `gpg --list-keys`

   Dovresti visualizzare un messaggio simile al seguente:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Crittografare i dati in entrata utilizzando il comando seguente:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Tutti i dati crittografati devono utilizzare `.pgp` o `.gpg` come estensione del file (ad esempio `ftp_dpm_100_123456789.sync.pgp` o `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supporta solo l'algoritmo di cifratura [!DNL Advanced Encryption Standard (AES)] dei dati. Audience Manager supporta qualsiasi dimensione chiave.