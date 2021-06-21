---
description: Invia o aggiorna i file di metadati inviandoli a una speciale directory Amazon S3 per il tuo account di Audience Manager. Fai riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-description: Invia o aggiorna i file di metadati inviandoli a una speciale directory Amazon S3 per il tuo account di Audience Manager. Fai riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.
seo-title: Metodi di distribuzione dei file di metadati
solution: Audience Manager
title: Metodi di distribuzione dei file di metadati
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: File di registro
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---

# Metodi di distribuzione dei file di metadati{#delivery-methods-for-metadata-files}

Invia o aggiorna i file di metadati inviandoli a una directory speciale [!DNL Amazon S3] per il tuo account di Audience Manager. Fai riferimento a questa sezione per informazioni sui percorsi di consegna/directory, sui tempi di elaborazione dei file e sugli aggiornamenti.

>[!IMPORTANT]
>
> Contatta il tuo consulente di Audience Manager o l’Assistenza clienti per iniziare e impostare una directory [!DNL Amazon S3] per i file di metadati.

## Sintassi ed esempio di percorso di consegna {#syntax}

I dati vengono memorizzati in uno spazio dei nomi separato per ogni cliente in una directory [!DNL Amazon S3] . Il percorso del file segue la sintassi mostrata di seguito. Le parentesi angolari `<>` indicano un segnaposto variabile. Gli altri elementi sono costanti e non cambiano.

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
| `.../log_ingestion/` | Questo è l&#39;inizio del percorso di archiviazione della directory. Riceverai il percorso completo quando tutto è configurato. |
| `pid=<AAM ID>` | Questa coppia chiave-valore contiene l&#39;ID cliente Audience Manager. |
| `dpid=<d_src>` | Questa coppia chiave-valore contiene l&#39;ID origine dati trasmesso in una chiamata evento. L’ID dell’origine dati è il valore che collega tutto il contenuto del file ai dati effettivi a cui appartiene. </br> Ad esempio, supponiamo che tu abbia un creativo con l’ID 123 e il nome &quot;Advertiser Creative A&quot;. Poiché una chiamata evento passa solo nell’ID, devi includere &quot;Advertiser Creative A&quot; nel file di metadati. La campagna e il contenuto creativo appartengono a un’origine dati. L’ID dell’origine dati è ciò che li collega tra loro e ci consente di associare con precisione il contenuto del file a un ID inviato in una chiamata dell’evento. Consulta [Come gli ID delle chiamate evento determinano i nomi dei file, i contenuti e i percorsi di consegna](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Questo è il nome del file. Consulta [Convenzioni di denominazione per i file di metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Tempi e aggiornamenti di elaborazione dei file {#processing-times}

I file di metadati vengono elaborati quattro volte al giorno, a intervalli regolari.

Per aggiornare i record di metadati, è sufficiente inviare un file contenente nuove informazioni. Non è necessario inviare aggiornamenti completi ogni volta.
