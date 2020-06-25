---
description: I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.
seo-description: I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.
seo-title: Componenti di elaborazione dati
solution: Audience Manager
title: Componenti di elaborazione dati
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# Componenti di elaborazione dati{#data-processing-components}

I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

 Audience Manager utilizza i seguenti componenti per elaborare i dati:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop è il database principale che contiene tutto ciò che [!DNL Audience Manager] sa su un utente. Ad esempio, quando i server [cache](../../reference/system-components/components-data-collection.md) profilo creano file di registro contenenti dati sugli utenti, questi li inviano ad Hadoop per l&#39;archiviazione. Altri importanti elementi Hadoop:

* **Alveare:** Una data warehouse per Hadoop. Hive gestisce le query ad hoc ai dati memorizzati in Hadoop.

* **HBase:** Un database Hadoop molto grande. Elabora e gestisce dati in entrata e in uscita, regole sulle caratteristiche, informazioni sulla modellazione algoritmica ed esegue molte altre funzioni relative alla memorizzazione e allo spostamento dei dati in sistemi diversi.

I clienti non hanno accesso diretto a questi sistemi. Tuttavia, i clienti collaborano indirettamente con loro, in quanto questi componenti memorizzano dati importanti sui visitatori del sito.

## Fiocco di neve {#snowflake}

[Snowflake](https://www.snowflake.net/) è un enorme database cloud. Fornisce i dati a molti grafici del dashboard e alle relative caselle di testo che mostrano la modifica % per ogni elemento del grafico. Se utilizzate [!DNL Audience Manager] e osservate i rapporti del dashboard, interagite con i dati forniti da [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Non si tratta di un elenco completo, ma alcuni report comuni della dashboard che [!UICONTROL Snowflake] sono responsabili includono:

* [Report Variazione caratteristica giornaliera](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Tutti i rapporti di sovrapposizione (consultate la sezione Rapporti [](/help/using/reporting/dynamic-reports/dynamic-reports.md) interattivi per informazioni su ciascun rapporto di sovrapposizione).
* [Report Segnali non utilizzati](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR è un database e un sistema server open-source da Apache. Offre funzionalità di ricerca robuste e veloci sui nostri grandi set di dati. In qualità di cliente, puoi vedere SOLR in azione quando crei segmenti. [!DNL Audience Manager] Fornisce i dati al [!UICONTROL Estimated Historic Segment Size] report. SOLR è ideale per questo ruolo a causa della sua velocità. Ad esempio, SOLR è in grado di aggiornare i dati delle dimensioni storiche quando si creano regole e si aggiungono nuove caratteristiche a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilizza [Tableau](https://www.tableausoftware.com/) per visualizzare i dati nei report [](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) interattivi e nei report [di ottimizzazione dell&#39;](../../reporting/audience-optimization-reports/audience-optimization-reports.md)audience. I rapporti interattivi visualizzano le prestazioni e i dati di sovrapposizione per caratteristiche e segmenti. Invece di usare numeri disposti in colonne e righe, restituiscono i dati utilizzando forme, colori e dimensioni diversi. Inoltre, puoi scegliere punti dati singoli o gruppi e approfondire i risultati del rapporto per maggiori dettagli. Queste tecniche di visualizzazione e l&#39;interattività dei report consentono di comprendere più facilmente grandi quantità di dati numerici.



![](assets/advertiser_analytics.png)

