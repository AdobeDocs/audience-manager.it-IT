---
description: I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.
seo-description: I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.
seo-title: Componenti di elaborazione dei dati
solution: Audience Manager
title: Componenti di elaborazione dei dati
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 'Componenti di sistema '
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# Componenti di elaborazione dei dati{#data-processing-components}

I componenti per l’elaborazione dei dati includono Hadoop, Snowflake, SOLR e Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utilizza i seguenti componenti per elaborare i dati:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop è il database principale che contiene tutto ciò che [!DNL Audience Manager] conosce su un utente. Ad esempio, quando i [Server cache di profilo](../../reference/system-components/components-data-collection.md) creano file di registro contenenti dati sugli utenti, questi inviano tali dati al Hadoop per l&#39;archiviazione. Altri importanti elementi del Hadoop sono:

* **Hive:** un data warehouse per Hadoop. Hive gestisce query ad hoc ai dati memorizzati nel Hadoop.

* **HBase:** un database di Hadoop molto grande. Elabora e gestisce dati in entrata e in uscita, regole per le caratteristiche, informazioni sulla modellazione algoritmica ed esegue molte altre funzioni relative all’archiviazione e allo spostamento dei dati su sistemi diversi.

I clienti non hanno accesso diretto a questi sistemi. Tuttavia, i clienti lavorano indirettamente con loro, in quanto questi componenti memorizzano dati importanti sui visitatori del loro sito.

## Snowflake {#snowflake}

[](https://www.snowflake.net/) Snowflakeè un enorme database cloud. Fornisce i dati a molti grafici del dashboard e alle relative caselle di testo che mostrano la modifica della percentuale per ogni elemento del grafico. Se utilizzi [!DNL Audience Manager] e osserva i rapporti del dashboard, interagisci con i dati forniti da [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Questo non è affatto un elenco completo, ma alcuni report comuni della dashboard responsabili sono i seguenti:[!UICONTROL Snowflake]

* [Rapporto sulla variazione giornaliera delle caratteristiche](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Tutti i rapporti di sovrapposizione (consulta la sezione [Rapporti interattivi](/help/using/reporting/dynamic-reports/dynamic-reports.md) per informazioni su ciascun rapporto di sovrapposizione).
* [Rapporto su segnali non utilizzati](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR è un database open source e un sistema server di Apache. Offre funzionalità di ricerca affidabili e veloci sui nostri set di dati di grandi dimensioni. In qualità di cliente [!DNL Audience Manager], puoi vedere SOLR in azione quando crei segmenti. Fornisce i dati al report [!UICONTROL Estimated Historic Segment Size] . SOLR è ideale per questo ruolo a causa della sua velocità. Ad esempio, SOLR è in grado di aggiornare i dati della dimensione storica durante la creazione di regole e l&#39;aggiunta di nuove caratteristiche a un segmento.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilizza la visualizzazione  [](https://www.tableausoftware.com/) Tableauto dei dati nei rapporti  [interattivi ](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) e nei rapporti di  [Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). I rapporti interattivi mostrano le prestazioni e i dati di sovrapposizione per caratteristiche e segmenti. Invece di utilizzare i numeri disposti in colonne e righe, restituiscono i dati utilizzando forme, colori e dimensioni diversi. Inoltre, puoi scegliere singoli o gruppi di punti dati ed approfondire i risultati del rapporto per ulteriori dettagli. Queste tecniche di visualizzazione e l’interattività dei rapporti facilitano la comprensione di grandi quantità di dati numerici.



![](assets/advertiser_analytics.png)
