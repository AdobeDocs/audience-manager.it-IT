---
description: Un report Trend restituisce dati di tendenza su caratteristiche e segmenti.
seo-description: Un report Trend restituisce dati di tendenza su caratteristiche e segmenti.
seo-title: Report tendenze
solution: Audience Manager
title: Report tendenze
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Report tendenze{#trend-reports}

Un report Trend restituisce dati di tendenza su caratteristiche e segmenti.

## Panoramica {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utilizza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo di utenti ai [!UICONTROL Trend] rapporti. Gli utenti possono visualizzare solo le caratteristiche e i segmenti nei rapporti che dispongono delle autorizzazioni per visualizzare. [!UICONTROL RBAC] consente di controllare i dati che possono essere visualizzati dai team interni.

Ad esempio, un'agenzia che gestisce diversi account di inserzionisti può configurare le autorizzazioni per gruppi di utenti in modo che un team che gestisce l'account dell'inserzionista A non possa vedere i dati di reporting dell'inserzionista B.

Esegui un [!UICONTROL Trend] report quando è necessario:

* Rivedete i dati delle tendenze per caratteristiche e segmenti.
* Tieni traccia delle tendenze di 1, 7, 14, 30, 60 e intervalli di 90 giorni.
* Confronta caratteristiche e tendenze dei segmenti nel tempo.
* Identificare caratteristiche e segmenti di prestazioni forti o insufficienti.
* Esporta dati (formato CSV) per ulteriori analisi e condivisione.

L'illustrazione seguente fornisce una panoramica di alto livello degli elementi chiave nel [!UICONTROL Trend] rapporto.

![](assets/trend_reports.png)

1. Configurate le seguenti opzioni:

   **** Tipo di rapporto: Selezionare il tipo di rapporto desiderato (Caratteristiche o Segmento).

   **** Intervallo date: Specifica l'intervallo di date per il rapporto (data di inizio e data di fine).

   **** Intervallo di visualizzazione: Specificate l'intervallo di visualizzazione (intervalli di 1, 7, 14, 30, 60 e 90 giorni).

2. Cercare una caratteristica o segmento per nome o ID.
3. Dall’elenco delle cartelle, trascinate le caratteristiche o i segmenti da includere nel rapporto sul [!UICONTROL Selections] pannello a destra.
4. Generate il rapporto per visualizzare i dati in formato grafico o esportarlo in formato CSV.

## Eseguire un report di tendenze {#run-trend-report}

Questa procedura descrive come eseguire un [!UICONTROL Trend] rapporto.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Nel **[!UICONTROL Analytics]** dashboard, fate clic su **[!UICONTROL Trend Reports]**.
1. Dall’elenco a **[!UICONTROL Report Type]** discesa, selezionate il tipo desiderato: **[!UICONTROL Trait]** o **[!UICONTROL Segment]**.
1. Fai clic sulle caselle delle date per visualizzare un calendario, quindi seleziona le date di inizio e di fine del rapporto.
1. Specificate l'intervallo di visualizzazione: entro 1, 7, 14, 30, 60 o 90 giorni.
1. Cercare una caratteristica o segmento per nome o ID.
1. Dall’elenco delle cartelle, trascinate le caratteristiche o i segmenti da includere nel rapporto sul [!UICONTROL Selections] pannello a destra.

   Per ottenere prestazioni ottimali, esegui un [!UICONTROL Trend] rapporto su meno di 20 caratteristiche o segmenti alla volta.
1. Fate clic **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, a seconda del tipo di rapporto che state visualizzando (Caratteristiche o Segmenti).

   Queste opzioni ignorano tutte le cartelle e i grafici solo i tratti o i segmenti selezionati singolarmente.

   Oppure

   Fate clic **[!UICONTROL Export to CSV]** per esportare la caratteristica o i dati del segmento e tutte le cartelle in formato CSV per ulteriori analisi e condivisione. Questo consente di esportare gli intervalli [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]e [!UICONTROL Total Trait Population] per tutti i giorni.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sono calcolati [!UICONTROL Rule-based Traits] solo per.

1. (Facoltativo) Passa il puntatore del mouse sulle singole caratteristiche o segmenti per visualizzare il numero di visite e la data di ciascun punto dati.

   È possibile fare clic sulle intestazioni delle colonne nella tabella per ordinare i risultati in ordine crescente o decrescente.

Per [!UICONTROL Trended Trait] i report, gli zero indicano che [!DNL Audience Manager] non sono stati raccolti dati per quel giorno. Voci vuote indicano che la caratteristica non esisteva. L'esempio seguente mostra esempi di entrambi i tipi di voci:

![](assets/trended_data.png)
