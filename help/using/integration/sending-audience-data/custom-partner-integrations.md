---
description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-title: Integrazioni partner personalizzate
solution: Audience Manager
title: Integrazioni partner personalizzate
translation-type: tm+mt
source-git-commit: c069c901df6d8737f611d27ce7dffd4072e50adf

---


# Integrazioni partner personalizzate {#custom-partner-integrations}

Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.

## Oracle Data Cloud {#oracle-data-cloud}

### Descrizione

Audience Manager inserisce cookie e dati di identificazione mobile da Oracle Data Cloud per Audience Marketplace tramite file di dati in entrata. Le specifiche di integrazione personalizzata descritte di seguito fanno riferimento solo ai file di dati in entrata che contengono ID dispositivo mobile (IDFA e ID dispositivo Android).

### Specifiche di integrazione

I file di dati in entrata ricevuti da Oracle Data Cloud sono diversi dalla sintassi standard del nome file in entrata descritta in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) (Requisiti per il nome e la dimensione del file in entrata) e dalla sintassi standard del contenuto del file in entrata descritta in Contenuti file di dati in [ingresso: Sintassi, caratteri non validi, variabili ed esempi](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Gli elementi evidenziati di seguito sono obbligatori, oltre ai campi di implementazione standard per i file di dati in entrata. Per una descrizione di tutti gli altri campi standard e degli elementi del nome file, vedere Sintassi del nome file e sintassi del contenuto del file nelle due pagine collegate sopra.

### Denominazione dei file

I nomi dei file ODC sono strutturati come:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

L&#39;elemento nome `odc` file identifica il file come importato da Oracle Data Cloud e indica al validatore file in ingresso di Audience Manager di elaborarlo come tale.

### Contenuto file

I campi nel file di dati in entrata ODC devono essere visualizzati nell&#39;ordine indicato di seguito:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

È `ID type` possibile:

* IDFA
* ID dispositivo Android

>[!IMPORTANT]
>
>Non inviare ID dispositivo IDFA e Android nello stesso file di dati in entrata.

## Esempio di file ODC in ingresso

Scaricate il file [di](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)esempio. Questo file qualifica diversi IDFA per l’ID caratteristica 38838. Potete aprire questo file in un editor di testo o codice standard.