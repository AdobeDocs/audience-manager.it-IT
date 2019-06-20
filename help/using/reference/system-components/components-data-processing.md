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


# Componenti elaborazione dati{#data-processing-components}

I componenti di elaborazione dati includono Hadoop, Snowflating, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utilizza i seguenti componenti per elaborare i dati:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop è il database principale che contiene tutto [!DNL Audience Manager] ciò che è noto a un utente. Ad esempio, quando i server cache [profilo](../../reference/system-components/components-data-collection.md) creano file di registro contenenti dati sui tuoi utenti, questi vengono inviati ad Hadoop per l&#39;archiviazione. Altri elementi Hadoop importanti includono:

* **Hive:** Un data warehouse per Hadoop. Hive gestisce le query ad hoc ai dati memorizzati in Hadoop.

* **Hbase:** Un database Hadoop molto grande. Elabora e gestisce dati in entrata e in uscita, regole delle caratteristiche, informazioni algoritmiche algoritmiche ed esegue molte altre funzioni correlate alla memorizzazione e allo spostamento di dati in sistemi diversi.

I clienti non hanno accesso diretto a tali sistemi. Tuttavia, i clienti lavorano con loro indirettamente in quanto questi componenti archiviano dati importanti sui visitatori del sito.

## Fiocco di neve {#snowflake}

[Snowflating](https://www.snowflake.net/) è un grande database cloud. Fornisce dati a molti grafici del dashboard e alle relative caselle di testo che mostrano la modifica % per ogni elemento del grafico. If you use [!DNL Audience Manager] and look at the dashboard reports, you&#39;re interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Non si tratta di un elenco completo, ma alcuni rapporti comuni di dashboard [!UICONTROL Snowflake] sono tenuti a includere:

* [Report sulle caratteristiche giornaliere](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Report sulla distribuzione e sulle prestazioni](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* Tutti i rapporti di sovrapposizione (consultate [la sezione Rapporti](/help/using/reporting/dynamic-reports/dynamic-reports.md) interattivi per informazioni su ciascun rapporto di sovrapposizione).
* [Report segnali inutilizzati](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR è un database open-source e un sistema server Apache. Offre funzionalità di ricerca avanzate e rapide sui nostri grandi set di dati. In qualità [!DNL Audience Manager] di cliente, quando crei segmenti puoi vedere SOLR in azione. Fornisce dati al [!UICONTROL Estimated Historic Segment Size] rapporto. SOLR è ideale per questo ruolo a causa della velocità. Ad esempio, SOLR è in grado di aggiornare i dati delle dimensioni storiche mentre si creano regole e aggiungere nuove caratteristiche a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilizza [Tableau](https://www.tableausoftware.com/) per visualizzare i dati nei report [interattivi](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e nei report [di ottimizzazione dell&#39;audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md). I rapporti interattivi mostrano prestazioni e sovrapposizione dati per caratteristiche e segmenti. Invece di utilizzare i numeri disposti nelle colonne e nelle righe, restituiscono dati con forme, colori e dimensioni diverse. Inoltre, potete scegliere singoli o gruppi di punti dati e analizzare i risultati del rapporto per ulteriori dettagli. Queste tecniche di visualizzazione e l&#39;interattività dei report facilitano la comprensione di grandi quantità di dati numerici.



![](assets/advertiser_analytics.png)

