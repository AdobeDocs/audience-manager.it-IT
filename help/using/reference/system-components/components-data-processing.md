---
description: I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.
seo-description: I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.
seo-title: Componenti di elaborazione dei dati
solution: Audience Manager
title: Componenti di elaborazione dei dati
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 3%

---


# Componenti di elaborazione dei dati{#data-processing-components}

I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

 Audience Manager utilizza i seguenti componenti per elaborare i dati:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop è il database principale che contiene tutto ciò che [!DNL Audience Manager] conosce su un utente. Ad esempio, quando i [Server cache profilo](../../reference/system-components/components-data-collection.md) creano file di registro che contengono dati sugli utenti, questi inviano tali dati ad Hadoop per l&#39;archiviazione. Altri importanti elementi di Hadoop sono:

* **Hive:** Un data warehouse per Hadoop. Hive gestisce le query ad hoc ai dati memorizzati in Hadoop.

* **HBase:** Un database Hadoop molto grande. Elabora e gestisce dati in entrata e in uscita, regole sulle caratteristiche, informazioni sulla modellazione algoritmica ed esegue molte altre funzioni relative alla memorizzazione e allo spostamento dei dati in sistemi diversi.

I clienti non hanno accesso diretto a questi sistemi. Tuttavia, i clienti collaborano indirettamente con loro, in quanto questi componenti memorizzano dati importanti sui visitatori del sito.

## Snowflake {#snowflake}

[](https://www.snowflake.net/) Snowflakeè un enorme database cloud. Fornisce i dati a molti grafici del dashboard e alle relative caselle di testo che mostrano la modifica % per ogni elemento del grafico. Se utilizzate [!DNL Audience Manager] e osservate i rapporti del dashboard, interagite con i dati forniti da [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Non si tratta di un elenco completo, ma alcuni report comuni del dashboard responsabili di [!UICONTROL Snowflake] includono:

* [Rapporto sulla variazione giornaliera delle caratteristiche](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Tutti i rapporti di sovrapposizione (consultate la sezione [Rapporti interattivi](/help/using/reporting/dynamic-reports/dynamic-reports.md) per informazioni su ciascun rapporto di sovrapposizione).
* [Rapporto su segnali non utilizzati](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR è un database e un sistema server open-source da Apache. Offre funzionalità di ricerca robuste e veloci sui nostri grandi set di dati. Come cliente [!DNL Audience Manager], puoi vedere SOLR in azione quando crei segmenti. Fornisce i dati al report [!UICONTROL Estimated Historic Segment Size]. SOLR è ideale per questo ruolo a causa della sua velocità. Ad esempio, SOLR è in grado di aggiornare i dati delle dimensioni storiche quando si creano regole e si aggiungono nuove caratteristiche a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilizza i dati di visualizzazione  [](https://www.tableausoftware.com/) Tableauto nei  [Rapporti interattivi e nei Report](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) di  [Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). I rapporti interattivi visualizzano le prestazioni e i dati di sovrapposizione per caratteristiche e segmenti. Invece di usare numeri disposti in colonne e righe, restituiscono i dati utilizzando forme, colori e dimensioni diversi. Inoltre, puoi scegliere punti dati singoli o gruppi e approfondire i risultati del rapporto per maggiori dettagli. Queste tecniche di visualizzazione e l&#39;interattività dei report consentono di comprendere più facilmente grandi quantità di dati numerici.



![](assets/advertiser_analytics.png)

