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


# Cifratura file PGP per i tipi di dati in entrata{#file-pgp-encryption-for-inbound-data-types}

Come opzione, puoi cifrare i file di dati con [!DNL PGP] cifratura quando li invii ad Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Al momento non supportiamo la crittografia e la compressione sullo stesso file di dati in entrata. È possibile selezionare o [comprimere](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) i file in entrata.

Seguire i passaggi descritti di seguito per cifrare i file di dati in entrata.

1. Scarica la [chiave pubblica di Audience Manager](./assets/adobe_pgp.pub).
1. Importare la chiave pubblica nell&#39;archivio affidabile.

   Ad esempio, se utilizzate [!DNL GPG], il comando potrebbe essere simile a quello di seguito:

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

   Tutti i dati crittografati devono essere utilizzati `.pgp` o `.gpg` come estensione del file (ad es. `ftp_dpm_100_123456789.sync.pgp` o `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supporta solo l&#39;algoritmo [!DNL Advanced Encryption Standard (AES)] di cifratura dati. Audience Manager supporta qualsiasi dimensione chiave.