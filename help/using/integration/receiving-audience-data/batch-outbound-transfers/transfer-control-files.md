---
description: I file Transfer-control (.info) forniscono informazioni sui metadati sui trasferimenti di file in modo che i partner possano verificare che Audience Manager gestisca correttamente i trasferimenti di file.
seo-description: I file Transfer-control (.info) forniscono informazioni sui metadati sui trasferimenti di file in modo che i partner possano verificare che Audience Manager gestisca correttamente i trasferimenti di file.
seo-title: File di trasferimento del controllo per trasferimenti di file di registro
solution: Audience Manager
title: File di trasferimento del controllo per trasferimenti di file di registro
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Trasferimenti di dati in uscita
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 5%

---

# File di trasferimento del controllo per trasferimenti di file di registro {#transfer-control-files-for-log-file-transfers}

I file di trasferimento-controllo ([!DNL .info]) forniscono informazioni sui metadati sui trasferimenti di file in modo che i partner possano verificare che Audience Manager gestisca correttamente i trasferimenti di file.

[!DNL Audience Manager] invia un file di controllo del trasferimento a un partner con ogni trasferimento di file. A causa della natura multi-thread dell&#39;editore [!DNL FTP], il file di controllo del trasferimento potrebbe essere inviato prima che il trasferimento dei file effettivi sia terminato.

I metadati nel file [!DNL .info] consentono ai partner di:

* Determinare il completamento di un ciclo completo di trasferimento (è stato consegnato il numero totale di file nella sequenza);
* Determinare se un dato file della sequenza è completo/corretto (esaminando le dimensioni del file in byte e il numero totale di righe);
* Convalida il numero di righe nei file non elaborati visualizza il numero di righe dopo il caricamento dei file nel database all&#39;estremità ricevente (dimensione del file in righe).

## Convenzioni di denominazione dei file {#file-naming-conventions}

Il file transfer-control ha lo stesso nome della radice del batch/sequenza con estensione di file [!DNL .info].s

Ad esempio, se il primo file della sequenza è stato denominato: [!DNL ftp_12345_67890_full_1500727351632-1.sync], il file di controllo viene denominato [!DNL ftp_12345_67890_iter_1500727351632.info].

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
> I numeri totali batch sono esclusivi del file [!DNL .info] stesso. In altre parole, i totali non includono il file [!DNL .info], le sue dimensioni in byte o il suo conteggio delle righe.
>
> Le dimensioni dei byte dei file e dei conteggi delle righe includono qualsiasi riga/riga di intestazione e distanziatore (vuoto). Per ottenere il conteggio delle righe/righe di dati effettive, sottrai le intestazioni.
>
> Le righe totali in batch e le dimensioni totali dei byte includono qualsiasi riga di intestazione e spazio.
