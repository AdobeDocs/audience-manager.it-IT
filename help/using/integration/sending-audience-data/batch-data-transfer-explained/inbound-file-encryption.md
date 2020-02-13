---
description: Come opzione, potete crittografare i file di dati con crittografia PGP al momento dell'invio ad Audience Manager.
seo-description: Come opzione, potete crittografare i file di dati con crittografia PGP al momento dell'invio ad Audience Manager.
seo-title: Crittografia PGP file per i tipi di dati in entrata
solution: Audience Manager
title: Crittografia PGP file per i tipi di dati in entrata
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: b2e0b560a944f2ad63a48476be647f1355712342

---


# Crittografia PGP file per i tipi di dati in entrata{#file-pgp-encryption-for-inbound-data-types}

Potete crittografare i file di dati con [!DNL PGP] la crittografia quando li inviate ad Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] la crittografia include la compressione dei file. Quando inviate file [!DNL PGP] in entrata crittografati, accertatevi di non [comprimerli](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) utilizzando gzip (`.gz`).
>
>[!DNL PGP] i file in entrata crittografati che sono anche [compressi](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) non sono validi in Audience Manager.

Seguire i passaggi descritti di seguito per cifrare i file di dati in entrata.

1. Scaricate la chiave [pubblica di](./assets/adobe_pgp.pub)Audience Manager.
2. Importa la chiave pubblica nello store affidabile.

   Ad esempio, se utilizzate [!DNL GPG], il comando potrebbe essere simile al seguente:

   `gpg --import adobe_pgp.pub`

3. Convalidate che la chiave sia stata importata correttamente eseguendo il comando seguente:

   `gpg --list-keys`

   Dovresti visualizzare un messaggio simile al seguente:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Crittografare i dati in entrata utilizzando il comando seguente:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Tutti i dati crittografati devono utilizzare `.pgp` o `.gpg` come estensione del file (ad esempio `ftp_dpm_100_123456789.sync.pgp` o `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supporta solo l&#39;algoritmo di cifratura [!DNL Advanced Encryption Standard (AES)] dei dati. Audience Manager supporta qualsiasi dimensione chiave.
