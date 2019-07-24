---
description: I componenti di elaborazione dati includono Hadoop, Snowflating, SOLR e Tableau.
seo-description: I componenti di elaborazione dati includono Hadoop, Snowflating, SOLR e Tableau.
seo-title: Componenti elaborazione dati
solution: Audience Manager
title: Componenti elaborazione dati
uuid: d 458 d 869-7 a 23-4016-871 d -0 b 994 cf 4 af 06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Processing Components{#data-processing-components}

I componenti di elaborazione dati includono Hadoop, Snowflating, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utilizza i seguenti componenti per elaborare i dati:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. Altri elementi Hadoop importanti includono:

* **Hive:** Un data warehouse per Hadoop. Hive gestisce le query ad hoc ai dati memorizzati in Hadoop.

* **Hbase:** Un database Hadoop molto grande. Elabora e gestisce dati in entrata e in uscita, regole delle caratteristiche, informazioni algoritmiche algoritmiche ed esegue molte altre funzioni correlate alla memorizzazione e allo spostamento di dati in sistemi diversi.

I clienti non hanno accesso diretto a tali sistemi. Tuttavia, i clienti lavorano con loro indirettamente in quanto questi componenti archiviano dati importanti sui visitatori del sito.

## Snowflake {#snowflake}

[Snowflating](https://www.snowflake.net/) è un grande database cloud. Fornisce dati a molti grafici del dashboard e alle relative caselle di testo che mostrano la modifica % per ogni elemento del grafico. If you use [!DNL Audience Manager] and look at the dashboard reports, you're interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [Report sulle caratteristiche giornaliere](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Report sulla distribuzione e sulle prestazioni](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report).
* [Report segnali inutilizzati](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR è un database open-source e un sistema server Apache. Offre funzionalità di ricerca avanzate e rapide sui nostri grandi set di dati. As an [!DNL Audience Manager] customer, you can see SOLR in action when you build segments. It provides data to the [!UICONTROL Estimated Historic Segment Size] report. SOLR è ideale per questo ruolo a causa della velocità. Ad esempio, SOLR è in grado di aggiornare i dati delle dimensioni storiche mentre si creano regole e aggiungere nuove caratteristiche a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilizza [Tableau](https://www.tableausoftware.com/) per visualizzare i dati nei report [interattivi](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e nei report [di ottimizzazione dell'audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md). I rapporti interattivi mostrano prestazioni e sovrapposizione dati per caratteristiche e segmenti. Invece di utilizzare i numeri disposti nelle colonne e nelle righe, restituiscono dati con forme, colori e dimensioni diverse. Inoltre, potete scegliere singoli o gruppi di punti dati e analizzare i risultati del rapporto per ulteriori dettagli. Queste tecniche di visualizzazione e l'interattività dei report facilitano la comprensione di grandi quantità di dati numerici.



![](assets/advertiser_analytics.png)

