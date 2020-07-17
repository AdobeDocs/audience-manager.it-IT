---
description: I file di controllo del trasferimento (.info) forniscono informazioni sui metadati sui trasferimenti di file in modo che i partner possano verificare che  i trasferimenti di file Audience Manager siano gestiti correttamente.
seo-description: I file di controllo del trasferimento (.info) forniscono informazioni sui metadati sui trasferimenti di file in modo che i partner possano verificare che  i trasferimenti di file Audience Manager siano gestiti correttamente.
seo-title: File di trasferimento del controllo per trasferimenti di file di registro
solution: Audience Manager
title: File di trasferimento del controllo per trasferimenti di file di registro
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 5%

---


# File di trasferimento del controllo per trasferimenti di file di registro {#transfer-control-files-for-log-file-transfers}

I file con controllo del trasferimento ([!DNL .info]) forniscono informazioni sui metadati relativi ai trasferimenti di file, in modo che i partner possano verificare che  Audience Manager abbia gestito correttamente i trasferimenti di file.

[!DNL Audience Manager] invia un file di trasferimento a un partner con ogni trasferimento di file. A causa della natura multithread dell&#39; [!DNL FTP] editore, il file di controllo del trasferimento potrebbe essere inviato prima del termine del trasferimento dei file effettivi.

I metadati contenuti nel [!DNL .info] file consentono ai partner di:

* Determinare il termine di un ciclo completo di trasferimento (il numero totale di file nella sequenza è stato consegnato);
* Determinare se un dato file nella sequenza è completo/corretto (esaminando la dimensione del file in byte e il numero totale di righe);
* Convalidare il numero di righe nelle versioni di file non elaborati il numero di righe dopo che i file sono stati caricati nel database all&#39;estremità ricevente (dimensione del file nelle righe).

## Convenzioni di denominazione dei file {#file-naming-conventions}

Il file transfer-control ha lo stesso nome della radice del batch/sequenza con estensione [!DNL .info] file.s

Ad esempio, se il primo file della sequenza è stato denominato: [!DNL ftp_12345_67890_full_1500727351632-1.sync], il file di controllo verrà denominato [!DNL ftp_12345_67890_iter_1500727351632.info].

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

>[NOTA]
>
> I numeri totali del batch sono esclusi dal [!DNL .info] file stesso. In altre parole, i totali non includono il [!DNL .info] file, la dimensione dei byte o il conteggio delle righe.
>
> Le dimensioni byte dei file e dei conteggi delle righe sono comprese nelle righe/righe di intestazione e distanziatore (vuote). Per ottenere il conteggio delle righe/righe di dati effettive, sottrarre le intestazioni.
>
> Le righe totali in batch e le dimensioni totali in byte sono comprensive di qualsiasi riga di intestazione e di spazio.