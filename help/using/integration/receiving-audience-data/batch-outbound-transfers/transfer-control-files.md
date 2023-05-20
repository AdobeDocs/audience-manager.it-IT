---
description: I file di controllo del trasferimento (.info) forniscono informazioni sui metadati sui trasferimenti di file in modo che i partner possano verificare che i trasferimenti di file gestiti da Audience Manager siano corretti.
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: File di trasferimento del controllo per trasferimenti di file di registro
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# File di trasferimento del controllo per trasferimenti di file di registro {#transfer-control-files-for-log-file-transfers}

Controllo di trasferimento ([!DNL .info]) forniscono informazioni sui metadati relativi ai trasferimenti di file, in modo che i partner possano verificare che i trasferimenti di file gestiti da Audience Manager siano corretti.

[!DNL Audience Manager] invia un file di controllo di trasferimento a un partner per ogni trasferimento di file. Data la natura multi-thread del [!DNL FTP] publisher, il file di controllo di trasferimento potrebbe essere inviato prima del completamento del trasferimento dei file effettivi.

I metadati in [!DNL .info] file consente ai partner di:

* determinare quando è stato completato un ciclo completo di trasferimento (il numero totale di file nella sequenza è stato consegnato);
* Determinare se un determinato file nella sequenza è completo/corretto (esaminando la dimensione del file in byte e il numero totale di righe);
* Convalida il numero di righe nei file non elaborati verifica il numero di righe dopo che i file sono stati caricati nel database all’estremità ricevente (dimensione del file in righe).

## Convenzioni di denominazione dei file {#file-naming-conventions}

Il file di controllo di trasferimento ha lo stesso nome della radice del batch/sequenza con un [!DNL .info] estensione file.s

Ad esempio, se il primo file della sequenza è stato denominato: [!DNL ftp_12345_67890_full_1500727351632-1.sync], il nome del control file [!DNL ftp_12345_67890_iter_1500727351632.info].

## Formato file {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[!NOTE]
>
> I numeri totali del batch sono esclusi [!DNL .info] file stesso. In altre parole, i totali non includono [!DNL .info] file, le dimensioni in byte o il numero di righe.
>
> Le dimensioni in byte dei file e il numero di righe includono tutte le righe e le righe di intestazione e di spaziatura (vuote). Per ottenere il conteggio delle righe/righe di dati effettive, sottrai le intestazioni.
>
> Le righe totali in batch e le dimensioni totali in byte includono tutte le righe di intestazione e di spazio.
