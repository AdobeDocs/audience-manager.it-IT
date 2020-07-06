---
description: Domande frequenti sui file di feed di dati cliente (CDF, Customer Data Feed).
seo-description: Domande frequenti sui file di feed di dati cliente (CDF, Customer Data Feed).
seo-title: Domande frequenti sui feed di dati cliente
solution: Audience Manager
title: Domande frequenti sui feed di dati cliente
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 100%

---


# Domande frequenti sui feed di dati cliente {#customer-data-feed-faq}

Domande frequenti sui file di feed di dati cliente (CDF, Customer Data Feed).

## Archiviazione Amazon S3 {#amazon-s3-storage}

**Dove è memorizzato il file CDF su [!DNL Amazon]?**

Il file CDF viene memorizzato nella directory root `aam-cdf` su un server [!DNL Amazon S3]. Questo bucket predefinito è gestito da [!DNL Audience Manager]. Consulta anche [Customer Data Feed File Naming Conventions](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Il mio bucket di archiviazione è sicuro?**

Sì. I clienti possono accedere solo allo spazio di archiviazione personale. Avrai accesso in sola lettura al tuo bucket di archiviazione. Non avrai accesso in scrittura.

<br> 

**Posso personalizzare il bucket di archiviazione o archiviare i file in un’altra directory?**

No. Le opzioni di personalizzazione e di archiviazione alternativa non sono disponibili.

<br> 

**Nella mia directory manca un file per un’ora specifica. Dov’è?**

Un file mancante indica che [!DNL Audience Manager] non ha potuto elaborare i file CDF per quell’ora. Questo accade solitamente quando i nostri server sono indietro con l’elaborazione dei file CDF. In questo caso, il file non viene perso. Apparirà in una directory oraria successiva quando il nostro sistema ha la possibilità di recuperare. Consulta anche [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Come posso sapere quando i miei file CDF sono pronti?**

Consulta [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Dimensioni dei file {#file-sizes}

**Che tipo di dimensioni di file devo aspettarmi? Quanto è grande in media un file CDF?**

È difficile stimare le dimensioni dei file. Inoltre, ogni file può avere dimensioni diverse. Le dimensioni variano da ora a ora e giorno a giorno. Se desideri ricevere i file CDF, è utile che tu sia preparato a gestire molti dati.

<br> 

**Quanti file riceverò?**

Anche in questo caso, è difficile stimarlo. Tuttavia, se desideri ricevere i file CDF, è utile che tu sia preparato a gestire molti dati.

<br> 

## Integrità dei dati {#data-integrity}

**Come posso verificare l’integrità dei dati caricati su Amazon S3?**

[!DNL Amazon] divide i file di grandi dimensioni in parti più piccole e li carica su [!DNL Amazon S3] utilizzando il caricamento in più parti. Quindi genera un valore `ETag` per il caricamento in più parti. In primo luogo, calcola i singoli checksum MD5 di ciascuna parte caricata, quindi li concatena in una singola stringa. Poi calcola il checksum MD5 della stringa. Al checksum risultante (l’`ETag`) viene quindi aggiunto un trattino e il numero totale di parti utilizzate per il caricamento. Ad esempio, l’`ETag` per un file diviso in 5 parti durante il caricamento potrebbe essere simile al seguente: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Conservazione dei dati {#data-retension}

**Per quanto tempo vengono memorizzati i file CDF?**

I dati vengono eliminati dopo 8 (otto) giorni.

<br> 

**Posso ottenere i file CDF retroattivamente o per i giorni precedenti?**

Puoi generare file CDF solo per gli ultimi 8 giorni. I file CDF per gli intervalli precedenti agli 8 giorni non possono essere rigenerati.

>[!MORELIKETHIS]
>
>* [Customer Data Feeds](../features/cdf-files.md)

