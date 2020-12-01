---
description: Inviate o aggiornate i file di metadati inviandoli a una speciale directory  Amazon S3 per il vostro account di Audience Manager . Fare riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-description: Inviate o aggiornate i file di metadati inviandoli a una speciale directory  Amazon S3 per il vostro account di Audience Manager . Fare riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-title: Metodi di distribuzione dei file di metadati
solution: Audience Manager
title: Metodi di distribuzione dei file di metadati
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 4%

---


# Metodi di distribuzione dei file di metadati{#delivery-methods-for-metadata-files}

Inviate o aggiornate i file di metadati inviandoli a una directory [!DNL Amazon S3] speciale per l&#39;account  Audience Manager. Fare riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

>[!IMPORTANT]
>
> Contatta il tuo consulente  Audience Manager o l&#39;Assistenza clienti per iniziare e configurare una directory [!DNL Amazon S3] per i file di metadati.

## Sintassi percorso di consegna ed esempio {#syntax}

I dati vengono memorizzati in uno spazio dei nomi separato per ciascun cliente in una directory [!DNL Amazon S3]. Il percorso del file segue la sintassi indicata di seguito. Nota: le parentesi angolari `<>` indicano un segnaposto variabile. Gli altri elementi sono costanti e non vengono modificati.

**Sintassi:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Esempio:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

La tabella seguente definisce ciascuno di questi elementi in un percorso di consegna dei file.


| Parametro file | Descrizione |
---------|----------|
| `.../log_ingestion/` | Questo è l&#39;inizio del percorso di memorizzazione della directory. Riceverai il percorso completo quando tutto è configurato. |
| `pid=<AAM ID>` | Questa coppia chiave-valore contiene l&#39;ID cliente  Audience Manager. |
| `dpid=<d_src>` | Questa coppia chiave-valore contiene l’ID origine dati passato in una chiamata dell’evento. L&#39;ID origine dati è il valore che lega tutto il contenuto del file ai dati effettivi a cui appartiene. </br> Ad esempio, supponete di avere un creativo con l’ID 123 e il nome &quot;Advertiser Creative A&quot;. Poiché una chiamata di evento passa solo all’ID, è necessario includere &quot;Advertiser Creative A&quot; nel file di metadati. La campagna e la creatività appartengono a un&#39;origine dati. L’ID origine dati è ciò che li collega insieme e ci consente di associare accuratamente il contenuto del file a un ID inviato in una chiamata dell’evento. Consultate [Come gli ID di chiamate evento determinano i nomi dei file, i contenuti e i percorsi di consegna](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Questo è il nome del file. Consultate [Convenzioni di denominazione per i file di metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Tempi e aggiornamenti dell&#39;elaborazione dei file {#processing-times}

I file di metadati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i record di metadati, è sufficiente inviare un file contenente nuove informazioni. Non è necessario inviare aggiornamenti completi ogni volta.
