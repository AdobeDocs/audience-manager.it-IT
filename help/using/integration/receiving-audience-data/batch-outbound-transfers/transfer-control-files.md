---
description: I file di controllo del trasferimento (.info) forniscono i metadati sui trasferimenti dei file in modo che i partner possano verificare che Audience Manager sia stato gestito correttamente.
seo-description: I file di controllo del trasferimento (.info) forniscono i metadati sui trasferimenti dei file in modo che i partner possano verificare che Audience Manager sia stato gestito correttamente.
seo-title: File di controllo trasferimento per trasferimenti di file di registro
solution: Audience Manager
title: File di controllo trasferimento per trasferimenti di file di registro
uuid: ef 58213 e -7 b 37-4 c 5 a -8556-0 de 695706793
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# File di controllo trasferimento per trasferimenti di file di registro {#transfer-control-files-for-log-file-transfers}

I file transfer-control ([!DNL .info]) forniscono informazioni sui metadati sui trasferimenti di file, in modo che i partner possano verificare che Audience Manager sia stato gestito correttamente.

[!DNL Audience Manager] invia un file di controllo trasferimento a un partner con ogni trasferimento di file. A causa della natura multi thread dell&#39; [!DNL FTP] editore, il file di controllo del trasferimento potrebbe essere inviato prima che i file effettivi vengano trasferiti.

I metadati del [!DNL .info] file consentono ai partner di:

* Determinare quando è completato un ciclo di trasferimento completo (il numero totale di file nella sequenza è stato consegnato);
* Determinare se un determinato file nella sequenza è completo o corretto (verificando la dimensione del file in byte e il numero totale di righe);
* Convalidate il numero di righe in file grezzi per calcolare il numero di righe dopo che i file sono stati caricati nel database sulla fine ricevente (dimensione del file nelle righe).

## Convenzioni di denominazione dei file {#file-naming-conventions}

Il file di controllo del trasferimento ha lo stesso nome della directory principale del batch/sequenza con l&#39;estensione [!DNL .info] di un file.

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

>[NOTA]
>
> I numeri totali in batch sono esclusivamente [!DNL .info] del file stesso. ovvero, i totali non includono [!DNL .info] il file, le sue dimensioni del byte o il relativo conteggio delle linee.
>
> Le dimensioni dei file e i conteggi di riga sono inclusi di qualsiasi intestazione e riga (vuoto) righe/righe. Per ottenere il conteggio di righe/righe dati effettive, sottrarre intestazioni.
>
> Le righe totali in batch e dimensione totale byte sono incluse in tutte le righe di intestazione e spazio.