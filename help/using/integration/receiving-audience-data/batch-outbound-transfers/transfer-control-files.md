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


# Transfer-Control Files for Log File Transfers {#transfer-control-files-for-log-file-transfers}

Transfer-control ([!DNL .info]) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.

[!DNL Audience Manager] invia un file di controllo trasferimento a un partner con ogni trasferimento di file. Due to the multi-thread nature of the [!DNL FTP] publisher, the transfer-control file might be sent before the actual files are finished transferring.

The metadata in the [!DNL .info] file lets partners:

* Determinare quando è completato un ciclo di trasferimento completo (il numero totale di file nella sequenza è stato consegnato);
* Determinare se un determinato file nella sequenza è completo o corretto (verificando la dimensione del file in byte e il numero totale di righe);
* Convalidate il numero di righe in file grezzi per calcolare il numero di righe dopo che i file sono stati caricati nel database sulla fine ricevente (dimensione del file nelle righe).

## File Naming Conventions {#file-naming-conventions}

The transfer-control file has the same name as the root of the batch/sequence with a [!DNL .info] file extension.s

For example, if the first file in the sequence were named: [!DNL ftp_12345_67890_full_1500727351632-1.sync], the control file would be named [!DNL ftp_12345_67890_iter_1500727351632.info].

## File Format {#file-format}

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
> The batch total numbers are exclusive of the [!DNL .info] file itself. That is, the totals do not include the [!DNL .info] file, its byte size, or its line count.
>
> Le dimensioni dei file e i conteggi di riga sono inclusi di qualsiasi intestazione e riga (vuoto) righe/righe. Per ottenere il conteggio di righe/righe dati effettive, sottrarre intestazioni.
>
> Le righe totali in batch e dimensione totale byte sono incluse in tutte le righe di intestazione e spazio.