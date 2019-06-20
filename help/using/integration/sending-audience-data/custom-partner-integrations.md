---
description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-description: Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.
seo-title: Integrazioni partner personalizzate
solution: Audience Manager
title: Integrazioni partner personalizzate
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Integrazioni partner personalizzate {#custom-partner-integrations}

Questa pagina elenca le integrazioni personalizzate tra Audience Manager e partner di dati.

## Oracle Data Cloud {#oracle-data-cloud}

**Descrizione**

Audience Manager inserisce cookie e dati di identificazione mobile da Oracle Data Cloud per Audience Marketplace tramite file di dati in entrata. Le specifiche di integrazione personalizzate descritte di seguito fanno riferimento solo a file di dati in entrata contenenti ID mobili (IDFA e ID dispositivo Android).

<br> 

**Specifiche di integrazione**

I file di dati in entrata ricevuti da Oracle Data Cloud differiscono dalla sintassi standard del nome file descritta in [Amazon S 3 Nome e Dimensione file per i file di dati in entrata](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) e dalla sintassi standard del contenuto del file in entrata descritta in [Contenuti del file di dati in entrata: Sintassi, Caratteri non validi, variabili ed esempi](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Sono necessari gli elementi evidenziati sotto, oltre ai campi di implementazione standard per i file di dati in entrata. Per le descrizioni di tutti gli altri campi standard e nomi del file, vedere Sintassi nome file e Sintassi contenuto file nelle due pagine collegate sopra.

<br> 

**Denominazione dei file**

I nomi dei file ODC sono strutturati come:

<pre>ftp_ dpm_<b>odc</b>_ DPID [_ DPID_ TARGET_ DATA_ OWNER]_ TIMESTAMP (. sync |. overwrite) [. SPLIT_ NUMBER] [.gz]</pre>

L&#39;elemento nome `odc` file identifica il file come importato da Oracle Data Cloud e indica all&#39;autore del file in ingresso di Audience Manager di elaborarlo come tale.

<br> 

**Contenuto dei file**

I campi nel file di dati in entrata ODC devono essere visualizzati nell&#39;ordine indicato di seguito:

<pre>&lt;<b>Tipo ID</b>&gt; &lt; TAB &gt; &lt; ID utente &gt; &lt; TAB &gt; &lt; ID caratteristica &gt;, &lt; ID caratteristica &gt;, &lt; ID caratteristica &gt;,…</pre>

`ID type` Può essere:

* IDFA
* ID dispositivo Android

>[!IMPORTANT]
>
>Non inviare ID dispositivo IDFA e Android nello stesso file di dati in entrata.

<br> 

**File in entrata ODC di esempio**

Scaricate il [file di esempio](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Questo file qualifica diversi IDFAS per l&#39;ID caratteristica 38838. Potete aprire questo file in un editor di testo standard o in un editor di codice.