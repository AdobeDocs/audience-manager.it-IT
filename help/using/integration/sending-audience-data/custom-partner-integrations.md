---
description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-title: Integrazioni partner personalizzate
solution: Audience Manager
title: Integrazioni partner personalizzate
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.

## Oracle Data Cloud {#oracle-data-cloud}

**Descrizione**

Audience Manager inserisce cookie e dati di identificazione mobile da Oracle Data Cloud per Audience Marketplace tramite file di dati in entrata. Le specifiche di integrazione personalizzate descritte di seguito fanno riferimento solo a file di dati in entrata contenenti ID mobili (IDFA e ID dispositivo Android).

<br> 

**Specifiche di integrazione**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Sono necessari gli elementi evidenziati sotto, oltre ai campi di implementazione standard per i file di dati in entrata. Per le descrizioni di tutti gli altri campi standard e nomi del file, vedere Sintassi nome file e Sintassi contenuto file nelle due pagine collegate sopra.

<br> 

**Denominazione dei file**

I nomi dei file ODC sono strutturati come:

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

The `odc` file name element identifies the file as being imported from the Oracle Data Cloud and instructs the Audience Manager inbound file validator to process it as such.

<br> 

**Contenuto dei file**

I campi nel file di dati in entrata ODC devono essere visualizzati nell'ordine indicato di seguito:

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

`ID type` Può essere:

* IDFA
* ID dispositivo Android

>[!IMPORTANT]
>
>Non inviare ID dispositivo IDFA e Android nello stesso file di dati in entrata.

<br> 

**File in entrata ODC di esempio**

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Questo file qualifica diversi IDFAS per l'ID caratteristica 38838. Potete aprire questo file in un editor di testo standard o in un editor di codice.