---
description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Integrazioni di partner personalizzate
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
TQID: https://experienceleague.adobe.com/0QvyTQOmjkES1ZO47uu7JTh07-5--uHIgCbJ9iAYfrE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 15%

---

# Integrazioni di partner personalizzate {#custom-partner-integrations}

Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.

## Oracle Data Cloud {#oracle-data-cloud}

### Descrizione

Audience Manager inserisce cookie e dati di identificazione mobile da Oracle Data Cloud per Audience Marketplace tramite file di dati in entrata. Le specifiche di integrazione personalizzate descritte di seguito si riferiscono solo ai file di dati in entrata che contengono ID di dispositivi mobili (ID dispositivo IDFA e Android).

### Specifiche di integrazione

I file di dati in entrata ricevuti da Oracle Data Cloud differiscono dalla sintassi standard dei nomi di file in entrata descritta in [Requisiti Amazon S3 di nome e dimensione file per i file di dati in entrata](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) e dalla sintassi standard del contenuto dei file in entrata descritta in [Contenuto dei file di dati in entrata: sintassi, caratteri non validi, variabili ed esempi](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Gli elementi evidenziati di seguito sono obbligatori, oltre ai campi di implementazione standard per i file di dati in entrata. Per le descrizioni di tutti gli altri campi standard e degli elementi dei nomi di file, vedere Sintassi dei nomi di file e Sintassi del contenuto dei file nelle due pagine collegate in precedenza.

### Denominazione file

I nomi dei file ODC sono strutturati come segue:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

L&#39;elemento nome file `odc` identifica il file come importato da Oracle Data Cloud e indica al programma di convalida dei file in entrata di Audience Manager di elaborarlo come tale.

### Contenuto del file

I campi nel file di dati in entrata ODC devono essere visualizzati nell&#39;ordine indicato di seguito:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type` può essere:

* IDFA
* ID dispositivo Android

>[!IMPORTANT]
>
>Non inviare ID dispositivo IDFA e Android nello stesso file di dati in entrata.

## File in entrata ODC di esempio

Scarica il [file di esempio](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Questo file qualifica diversi identificatori IDFA per la 38838 degli ID caratteristica. Puoi aprire questo file in un editor di testo o di codice standard.
