---
description: Come opzione, è possibile crittografare i file di dati con crittografia PGP durante l’invio ad Audience Manager.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: Crittografia PGP dei file per i tipi di dati in entrata
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 8%

---

# Crittografia PGP dei file per i tipi di dati in entrata{#file-pgp-encryption-for-inbound-data-types}

È possibile crittografare i file di dati con [!DNL PGP] durante l&#39;invio all&#39;Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] la crittografia include la compressione dei file. Durante l’invio [!DNL PGP] file in entrata crittografati, assicurati di non [comprimere](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) utilizzando gzip (`.gz`).
>
>[!DNL PGP] file in entrata crittografati che sono anche [compresso](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) non sono validi in Audience Manager.

Segui i passaggi descritti di seguito per crittografare i file di dati in entrata.

1. Scarica il file [Chiave pubblica Audience Manager](./assets/adobe_pgp.pub).
2. Importa la chiave pubblica nell&#39;archivio attendibile.

   Ad esempio, se utilizzi [!DNL GPG], il comando potrebbe essere simile al seguente:

   `gpg --import adobe_pgp.pub`

3. Verifica che la chiave sia stata importata correttamente eseguendo il seguente comando:

   `gpg --list-keys`

   Dovresti visualizzare un messaggio simile al seguente:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Crittografa i dati in entrata utilizzando il comando seguente:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Tutti i dati crittografati devono utilizzare `.pgp` o `.gpg` come estensione del file (ad es. `ftp_dpm_100_123456789.sync.pgp` o `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >L&#39;Audience Manager supporta solo [!DNL Advanced Encryption Standard (AES)] algoritmo di crittografia dei dati. Audience Manager supporta qualsiasi dimensione di chiave.
