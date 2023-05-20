---
description: I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: Componenti di elaborazione dei dati
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---

# Componenti di elaborazione dei dati{#data-processing-components}

I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

In Audience Manager vengono utilizzati i seguenti componenti per l’elaborazione dei dati:

## Hadoop {#hadoop}

In entrata [!DNL Audience Manager], Hadoop è il database principale che contiene tutto [!DNL Audience Manager] conosce un utente. Ad esempio, quando [Server cache profili](../../reference/system-components/components-data-collection.md) crea file di registro che contengono dati sugli utenti, che invia al Hadoop per l&#39;archiviazione. Altri importanti elementi del Hadoop includono:

* **Alveare:** Data warehouse per il Hadoop. Hive gestisce le query ad hoc sui dati memorizzati nel Hadoop.

* **HBase:** Un database di Hadoop molto grande. Elabora e gestisce i dati in entrata e in uscita, le regole sulle caratteristiche, le informazioni sulla modellazione algoritmica ed esegue molte altre funzioni correlate all&#39;archiviazione e allo spostamento dei dati in sistemi diversi.

I clienti non hanno accesso diretto a questi sistemi. Tuttavia, i clienti lavorano indirettamente con loro, in quanto questi componenti memorizzano dati importanti sui visitatori del loro sito.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) è un enorme database cloud. Fornisce dati a molti dei grafici del dashboard e alle relative caselle di testo che visualizzano la percentuale di variazione per ogni elemento del grafico. Se usa [!DNL Audience Manager] e dai un&#39;occhiata ai report della dashboard, stai interagendo con i dati forniti da [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Questo non è affatto un elenco completo, ma alcuni dashboard comuni segnalano che [!UICONTROL Snowflake] è responsabile di includere:

* [Rapporto sulla variazione giornaliera delle caratteristiche](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Tutti i rapporti di sovrapposizione (vedere [Rapporti interattivi](/help/using/reporting/dynamic-reports/dynamic-reports.md) sezione per informazioni su ciascun rapporto di sovrapposizione).
* [Rapporto su segnali non utilizzati](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR è un database open-source e un sistema server di Apache. Fornisce funzionalità di ricerca affidabili e veloci sui nostri grandi set di dati. Come un [!DNL Audience Manager] cliente, quando si creano i segmenti è possibile vedere SOLR in azione. Fornisce dati al [!UICONTROL Estimated Historic Segment Size] rapporto. SOLR è ideale per questo ruolo a causa della sua velocità. Ad esempio, SOLR è in grado di aggiornare i dati delle dimensioni storiche durante la creazione delle regole e l&#39;aggiunta di nuove caratteristiche a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilizza [Tableau](https://www.tableausoftware.com/) per visualizzare i dati in [Rapporti interattivi](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e [Rapporti di Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). I rapporti interattivi visualizzano i dati sulle prestazioni e sulla sovrapposizione per caratteristiche e segmenti. Invece di utilizzare numeri disposti in colonne e righe, restituiscono dati utilizzando forme, colori e dimensioni diversi. Inoltre, puoi scegliere singoli punti dati o gruppi di punti dati ed approfondire i risultati del rapporto per ulteriori dettagli. Queste tecniche di visualizzazione e l’interattività dei rapporti facilitano la comprensione di grandi quantità di dati numerici.



![](assets/advertiser_analytics.png)
