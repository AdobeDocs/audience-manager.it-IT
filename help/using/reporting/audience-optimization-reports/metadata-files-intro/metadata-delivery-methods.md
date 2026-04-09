---
description: Invia o aggiorna i file di metadati inviandoli a una directory speciale Amazon S3 per il tuo account Audience Manager. Fai riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: Metodi di distribuzione dei file di metadati
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
TQID: https://experienceleague.adobe.com/1WX2-VoBmcDsUqntootQYpwQRtAOktxompEZfxVE9TE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 351
ht-degree: 0%

---

# Metodi di distribuzione dei file di metadati{#delivery-methods-for-metadata-files}

Invia o aggiorna i file di metadati inviandoli a una directory [!DNL Amazon S3] speciale per il tuo account Audience Manager. Fai riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

>[!IMPORTANT]
>
> Contatta il tuo consulente Audience Manager o l&#39;Assistenza clienti per iniziare e configurare una directory [!DNL Amazon S3] per i file di metadati.

## Sintassi ed esempio del percorso di consegna {#syntax}

I dati vengono memorizzati in uno spazio dei nomi separato per ogni cliente in una directory [!DNL Amazon S3]. Il percorso del file segue la sintassi illustrata di seguito. Le parentesi angolari `<>` indicano un segnaposto variabile. Gli altri elementi sono costanti e non cambiano.

**Sintassi:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Esempio:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

La tabella seguente definisce ciascuno di questi elementi in un percorso di consegna file.


| Parametro file | Descrizione |
|---------|----------|
| `.../log_ingestion/` | Inizio del percorso di archiviazione della directory. Riceverai il percorso completo quando tutto è configurato. |
| `pid=<AAM ID>` | Questa coppia chiave-valore contiene il tuo ID cliente Audience Manager. |
| `dpid=<d_src>` | Questa coppia chiave-valore contiene l&#39;ID origine dati trasmesso in una chiamata evento. L’ID dell’origine dati è il valore che lega tutti i contenuti del file ai dati effettivi a cui appartiene. </br> Ad esempio, supponiamo che tu abbia un contenuto creativo con l&#39;ID 123 e il nome &quot;Inserzionista Creative A.&quot; Poiché una chiamata evento passa solo nell’ID, devi includere &quot;Advertiser (Inserzionista) Creative A&quot; nel file di metadati. La campagna e la creatività appartengono a un’origine dati. L’ID dell’origine dati è ciò che unisce questi elementi e ci consente di associare con precisione il contenuto del file a un ID inviato in una chiamata dell’evento. Consulta [Come gli ID chiamata evento determinano i nomi dei file, i contenuti e i percorsi di consegna](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Questo è il nome del file. Consulta [Convenzioni di denominazione per i file di metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Tempi di elaborazione e aggiornamenti dei file {#processing-times}

I file di metadati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i record di metadati, invia un file contenente nuove informazioni. Non è necessario inviare aggiornamenti completi ogni volta.
