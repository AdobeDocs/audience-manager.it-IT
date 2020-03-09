---
description: Domande frequenti sui file Feed dati cliente (CDF).
seo-description: Domande frequenti sui file Feed dati cliente (CDF).
seo-title: Domande frequenti sui feed di dati cliente
solution: Audience Manager
title: Domande frequenti sui feed di dati cliente
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
translation-type: tm+mt
source-git-commit: 7018705c130bf7c65f3a69da5e4bd9e0666423bc

---


# Domande frequenti sui feed di dati cliente{#customer-data-feed-faq}

Domande frequenti sui file Feed dati cliente (CDF).

## Storage Amazon S3 {#amazon-s3-storage}

**Dove è memorizzato il file CDF[!DNL Amazon]?**

Il file CDF viene memorizzato nella directory `aam-cdf` principale di un [!DNL Amazon S3] server. Questo bucket predefinito è gestito da [!DNL Audience Manager]. Consultate anche Convenzioni di denominazione dei file dei feed di dati [cliente](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Il mio bucket di stoccaggio è sicuro?**

Sì. I clienti possono accedere solo allo spazio di archiviazione personale. Avrete accesso in sola lettura al bucket di archiviazione. Non avrete accesso in scrittura.

<br> 

**È possibile personalizzare il bucket di archiviazione o archiviare i file in un&#39;altra directory?**

No. Le opzioni di personalizzazione e di archiviazione alternativa non sono disponibili.

<br> 

**Nella mia directory manca un file per un&#39;ora particolare. Dov&#39;è?**

Un file mancante significa che [!DNL Audience Manager] non è stato possibile elaborare i file CDF per quell&#39;ora. Questo accade solitamente quando i nostri server si mettono in ritardo nell&#39;elaborazione dei file CDF. In questo caso, il file non viene perso. Apparirà in una directory oraria successiva dopo che il nostro sistema ha la possibilità di recuperare. Vedi anche Notifiche sull&#39;elaborazione dei file dei feed di dati [cliente](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Come posso sapere quando i miei file CDF sono pronti?**

Consulta Notifiche [di elaborazione dei file feed di dati](../features/cdf-files.md#cdf-file-processing-notifications)cliente.

<br> 

## Dimensioni file {#file-sizes}

**Che tipo di dimensioni di file devo aspettarmi? Quanto è grande un file CDF medio?**

È difficile stimare le dimensioni dei file. Inoltre, ogni file può avere dimensioni diverse. Le dimensioni variano da ora a ora e giorno a giorno. Se si desidera ricevere i file CDF, è utile essere preparati a gestire molti dati.

<br> 

**Quanti file riceverò?**

Anche in questo caso, è difficile stimarlo. Tuttavia, se si desidera ricevere i file CDF, è utile essere preparati a gestire molti dati.

<br> 

## Integrità dei dati {#data-integrity}

**Come posso verificare l&#39;integrità dei dati caricati su Amazon S3?**

[!DNL Amazon] divide i file di grandi dimensioni in parti più piccole e li carica [!DNL Amazon S3] utilizzando il caricamento multiparte. Quindi genera un `ETag` valore per il caricamento di più parti. In primo luogo, vengono calcolati i singoli checksum MD5 di ciascuna parte caricata, quindi li concatenano in una singola stringa. Quindi, calcola il checksum MD5 della stringa. Il checksum risultante (il `ETag`) viene quindi aggiunto con un trattino e il numero totale di parti utilizzate per il caricamento. Ad esempio, il `ETag` file diviso in 5 parti durante il caricamento potrebbe essere simile al seguente: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Conservazione dei dati {#data-retension}

**Per quanto tempo vengono memorizzati i file CDF?**

I dati vengono eliminati dopo 8 (8) giorni.

<br> 

**È possibile ottenere i file CDF retroattivamente o per i giorni precedenti?**

Potete generare file CDF solo per gli ultimi 8 giorni. I file CDF per gli intervalli precedenti agli 8 giorni non possono essere rigenerati.

>[!MORELIKETHIS]
>
>* [Feed dati cliente](../features/cdf-files.md)

