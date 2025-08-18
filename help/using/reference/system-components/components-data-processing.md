---
description: I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: Componenti di elaborazione dati
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---

# Componenti di elaborazione dati{#data-processing-components}

I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utilizza i seguenti componenti per elaborare i dati:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop è il database principale che contiene tutto ciò che [!DNL Audience Manager] conosce di un utente. Ad esempio, quando i [server cache profili](../../reference/system-components/components-data-collection.md) creano file di registro contenenti dati sugli utenti, inviano tali dati a Hadoop per l&#39;archiviazione. Altri importanti elementi di Hadoop includono:

* **Hive:** data warehouse per Hadoop. Hive gestisce le query ad hoc sui dati memorizzati in Hadoop.

* **HBase:** Database di Hadoop di grandi dimensioni. Elabora e gestisce i dati in entrata e in uscita, le regole sulle caratteristiche, le informazioni sulla modellazione algoritmica ed esegue molte altre funzioni correlate all&#39;archiviazione e allo spostamento dei dati in sistemi diversi.

I clienti non hanno accesso diretto a questi sistemi. Tuttavia, i clienti lavorano indirettamente con loro, in quanto questi componenti memorizzano dati importanti sui visitatori del loro sito.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) è un enorme database cloud. Fornisce dati a molti dei grafici del dashboard e alle relative caselle di testo che visualizzano la percentuale di variazione per ogni elemento del grafico. Se si utilizza [!DNL Audience Manager] e si esaminano i report del dashboard, si interagisce con i dati forniti da [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Non si tratta affatto di un elenco completo, ma alcuni report comuni del dashboard di cui [!UICONTROL Snowflake] è responsabile includono:

* [Rapporto sulla variazione giornaliera delle caratteristiche](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Tutti i report di sovrapposizione (vedere la sezione [Report interattivi](/help/using/reporting/dynamic-reports/dynamic-reports.md) per informazioni su ogni report di sovrapposizione).
* [Rapporto sui segnali non utilizzati](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR è un database open-source e un sistema server di Apache. Fornisce funzionalità di ricerca affidabili e veloci sui nostri grandi set di dati. In qualità di cliente [!DNL Audience Manager], puoi vedere SOLR in azione quando crei segmenti. Fornisce dati al report [!UICONTROL Estimated Historic Segment Size]. SOLR è ideale per questo ruolo a causa della sua velocità. Ad esempio, SOLR è in grado di aggiornare i dati delle dimensioni storiche durante la creazione delle regole e l&#39;aggiunta di nuove caratteristiche a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilizza [Tableau](https://www.tableausoftware.com/) per visualizzare i dati nei [report interattivi](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e nei [report Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). I rapporti interattivi visualizzano i dati sulle prestazioni e sulla sovrapposizione per caratteristiche e segmenti. Invece di utilizzare numeri disposti in colonne e righe, restituiscono dati utilizzando forme, colori e dimensioni diversi. Inoltre, puoi scegliere singoli punti dati o gruppi di punti dati ed approfondire i risultati del rapporto per ulteriori dettagli. Queste tecniche di visualizzazione e l’interattività dei rapporti facilitano la comprensione di grandi quantità di dati numerici.



![](assets/advertiser_analytics.png)
