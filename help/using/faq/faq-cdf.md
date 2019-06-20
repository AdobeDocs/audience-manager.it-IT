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


# Domande frequenti sui feed dei dati cliente{#customer-data-feed-faq}

Domande frequenti sui file Feed dati cliente (CDF).

## Amazon S 3 Storage {#amazon-s3-storage}

**Da dove viene memorizzato il file CDF[!DNL Amazon]?**

Il file CDF viene memorizzato nella directory `aam-cdf` principale di un [!DNL Amazon S3] server. Questo intervallo predefinito è gestito da [!DNL Audience Manager]. Consultate anche [Convenzioni](../features/cdf-files.md#cdf-naming-conventions)di denominazione dei file dei feed di dati cliente.

<br> 

**Il mio spazio di archiviazione è protetto?**

Sì. I clienti possono accedere solo al proprio spazio di archiviazione. Disponete dell&#39;accesso in sola lettura al bucket dell&#39;archiviazione. Non si dispone di accesso in scrittura.

<br> 

**È possibile personalizzare lo spazio di archiviazione o archiviare i file in un&#39;altra directory?**

No. La personalizzazione e le opzioni di archiviazione alternative non sono disponibili.

<br> 

**Nella directory della mia directory manca un file per un&#39;ora particolare. Dove si trova?**

Un file mancante non [!DNL Audience Manager] era in grado di elaborare i file CDF per quell&#39;ora. Questa situazione si verifica in genere quando i nostri server sono in grado di elaborare i file CDF. In questo caso, il file non viene perso. Apparirà in una directory oraria successiva dopo che il sistema avrà la possibilità di aggiornarsi. Vedi anche Notifiche di elaborazione dei file feed dati [cliente](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Come è possibile sapere quando i file CDF sono pronti?**

Consultate [Notifiche di elaborazione dei file feed dati cliente](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Dimensioni file {#file-sizes}

**Che tipo di file è previsto? Quanto è grande un file CDF?**

È difficile stimare le dimensioni dei file. Inoltre, ciascun file può avere dimensioni diverse. Le dimensioni variano da ora a ora e giorno al giorno. Se si desidera ricevere file CDF, è utile prepararsi a gestire molti dati.

<br> 

**Quanti file ricevere?**

Anche in questo caso è difficile stimarlo. Tuttavia, se si desidera ricevere file CDF è utile prepararsi a gestire molti dati.

<br> 

## Integrità dei dati {#data-integrity}

**Come si verifica l&#39;integrità dei dati caricati in Amazon S 3?**

I file di dimensioni superiori a 16 mib vengono suddivisi in blocchi 16 mib e caricati in [!DNL Amazon S3] base al caricamento con più parti.

[!DNL Amazon] genera un `ETag` valore per caricamenti multiparte. Prima calcola i singoli checksum MD 5 di ciascuna parte caricata, quindi li concatena in una singola stringa. Quindi, calcola il checksum MD 5 della stringa. Il checksum risultante (the `ETag`) viene quindi aggiunto a un trattino e al numero totale di parti utilizzate per il caricamento. Ad esempio, il `ETag` file che è stato suddiviso in 5 parti durante il caricamento potrebbe presentarsi come segue: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Conservazione dati {#data-retension}

**Per quanto tempo memorizzi i file CDF?**

I dati vengono eliminati dopo 8 (otto) giorni.

<br> 

**È possibile ottenere file CDF in modo retroattivo o per giorni precedenti?**

È possibile generare solo i file CDF per gli ultimi 8 giorni. Non è possibile generare nuovamente i file CDF per intervalli precedenti ai precedenti 8 giorni.

>[!MORE_ LIKE_ THIS]
>
>* [Feed dati cliente](../features/cdf-files.md)

