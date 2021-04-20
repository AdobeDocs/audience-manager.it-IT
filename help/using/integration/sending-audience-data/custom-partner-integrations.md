---
description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-title: Integrazioni di partner personalizzate
solution: Audience Manager
title: Integrazioni di partner personalizzate
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 22%

---

# Integrazioni di partner personalizzate {#custom-partner-integrations}

Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.

## Oracle Data Cloud {#oracle-data-cloud}

### Descrizione

Audience Manager inserisce cookie e dati di identificazione mobile da Oracle Data Cloud per Audience Marketplace tramite file di dati in entrata. Le specifiche di integrazione personalizzate descritte di seguito si riferiscono solo ai file di dati in entrata che contengono ID mobili (IDFA e ID dispositivo Android).

### Specifiche di integrazione

I file di dati in entrata ricevuti da Oracle Data Cloud sono diversi dalla sintassi standard del nome file in entrata descritta in [Requisiti di nome Amazon S3 e dimensione file per i file in entrata](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) e dalla sintassi standard del contenuto del file in entrata descritta in [Contenuto del file di dati in entrata: Sintassi, caratteri non validi, variabili ed esempi](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Oltre ai campi di implementazione standard per i file di dati in entrata, sono necessari gli elementi evidenziati di seguito. Per una descrizione di tutti gli altri campi e elementi nome file standard, vedere Sintassi nome file e sintassi contenuto file nelle due pagine collegate sopra.

### Denominazione dei file

I nomi dei file ODC sono strutturati come segue:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

L’elemento `odc` nome file identifica il file come importato da Oracle Data Cloud e indica al validatore file in entrata Audience Manager di elaborarlo come tale.

### Contenuto del file

I campi nel file di dati in entrata ODC devono essere visualizzati nell’ordine indicato di seguito:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

Il `ID type` può essere:

* IDFA
* ID dispositivo Android

>[!IMPORTANT]
>
>Non inviare ID dispositivo IDFA e Android nello stesso file di dati in entrata.

## File in entrata ODC di esempio

Scarica il [file di esempio](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Questo file qualifica diversi IDFA per l’ID caratteristica 38838. Puoi aprire questo file in un editor di testo o di codice standard.
