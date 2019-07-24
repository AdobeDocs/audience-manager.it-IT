---
description: Domande frequenti sui file Feed dati cliente (CDF).
seo-description: Domande frequenti sui file Feed dati cliente (CDF).
seo-title: Domande frequenti sui feed dei dati cliente
solution: Audience Manager
title: Domande frequenti sui feed dei dati cliente
uuid: 7183 b 3 e 2-e 999-4 e 1 e -892 f -2 bab 335 c 13 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feed FAQ{#customer-data-feed-faq}

Domande frequenti sui file Feed dati cliente (CDF).

## Amazon S3 Storage {#amazon-s3-storage}

**Da dove viene memorizzato il file CDF[!DNL Amazon]?**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. See also [Customer Data Feed File Naming Conventions](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Il mio spazio di archiviazione è protetto?**

Sì. I clienti possono accedere solo al proprio spazio di archiviazione. Disponete dell'accesso in sola lettura al bucket dell'archiviazione. Non si dispone di accesso in scrittura.

<br> 

**È possibile personalizzare lo spazio di archiviazione o archiviare i file in un'altra directory?**

No. La personalizzazione e le opzioni di archiviazione alternative non sono disponibili.

<br> 

**Nella directory della mia directory manca un file per un'ora particolare. Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. Questa situazione si verifica in genere quando i nostri server sono in grado di elaborare i file CDF. In questo caso, il file non viene perso. Apparirà in una directory oraria successiva dopo che il sistema avrà la possibilità di aggiornarsi. See also, [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Come è possibile sapere quando i file CDF sono pronti?**

See [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## File Sizes {#file-sizes}

**Che tipo di file è previsto? How big is an average CDF file?**

È difficile stimare le dimensioni dei file. Inoltre, ciascun file può avere dimensioni diverse. Le dimensioni variano da ora a ora e giorno al giorno. Se si desidera ricevere file CDF, è utile prepararsi a gestire molti dati.

<br> 

**Quanti file ricevere?**

Anche in questo caso è difficile stimarlo. Tuttavia, se si desidera ricevere file CDF è utile prepararsi a gestire molti dati.

<br> 

## Data Integrity {#data-integrity}

**Come si verifica l'integrità dei dati caricati in Amazon S 3?**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] genera un `ETag` valore per caricamenti multiparte. Prima calcola i singoli checksum MD 5 di ciascuna parte caricata, quindi li concatena in una singola stringa. Quindi, calcola il checksum MD 5 della stringa. The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**Per quanto tempo memorizzi i file CDF?**

I dati vengono eliminati dopo 8 (otto) giorni.

<br> 

**È possibile ottenere file CDF in modo retroattivo o per giorni precedenti?**

È possibile generare solo i file CDF per gli ultimi 8 giorni. Non è possibile generare nuovamente i file CDF per intervalli precedenti ai precedenti 8 giorni.

>[!MORE_ LIKE_ THIS]
>
>* [Feed dati cliente](../features/cdf-files.md)

