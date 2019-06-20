---
description: Un rapporto Tendenza restituisce dati sulle tendenze sui segmenti e sui segmenti.
seo-description: Un rapporto Tendenza restituisce dati sulle tendenze sui segmenti e sui segmenti.
seo-title: Report sulle tendenze
solution: Audience Manager
title: Report sulle tendenze
uuid: bedbe 7 d 4-7 cbb -4403-9104-312 f 9230 aea 1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Report sulle tendenze{#trend-reports}

Un rapporto Tendenza restituisce dati sulle tendenze sui segmenti e sui segmenti.

## Panoramica {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo utenti ai [!UICONTROL Trend] rapporti. Gli utenti possono vedere solo le caratteristiche e i segmenti nei rapporti che possono visualizzare. [!UICONTROL RBAC] consente di controllare quali dei team interni di dati di reporting sono in grado di visualizzare.

Ad esempio, un&#39;agenzia che gestisce diversi account pubblicitari può configurare le autorizzazioni del gruppo di utenti in modo che un team che gestisce l&#39;account dell&#39;inserzionista A non possa vedere i dati di reporting dell&#39;inserzionista B.

Eseguite [!UICONTROL Trend] un rapporto quando dovete:

* Rivedete i dati delle tendenze per caratteristiche e segmenti.
* Tieni traccia delle tendenze di 1, 7, 14, 30, 60 e 90 giorni.
* Confronta le tendenze e le tendenze del segmento nel tempo.
* Identificare caratteristiche e segmenti di prestazioni potenti o scadenti.
* Esportare dati (formato. csv) per un&#39;ulteriore analisi e condivisione.

L&#39;illustrazione seguente fornisce una panoramica di alto livello degli elementi chiave [!UICONTROL Trend] del report.

![](assets/trend_reports.png)

1. Configura le seguenti opzioni:

   **Tipo di rapporto:** Seleziona il tipo di rapporto desiderato (Caratteristica o Segmento).

   **Intervallo di date:** Specifica l&#39;intervallo di date per il rapporto (data di inizio e data di fine).

   **Intervallo di visualizzazione:** Specificare l&#39;intervallo di visualizzazione (intervalli 1, 7, 14, 30, 60 e 90 giorni).

2. Cerca una caratteristica o un segmento per nome o ID.
3. Nell&#39;elenco delle cartelle, trascina e rilascia le caratteristiche o i segmenti a destra del [!UICONTROL Selections] pannello.
4. Genera il rapporto da visualizzare nei dati in formato grafico o esporta il rapporto in formato CSV.

## Eseguire un rapporto sulle tendenze {#run-trend-report}

Questa procedura descrive come eseguire un [!UICONTROL Trend] rapporto.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Nel **[!UICONTROL Analytics]** dashboard, fate clic **[!UICONTROL Trend Reports]** su.
1. Dall&#39;elenco **[!UICONTROL Report Type]** a discesa, selezionate il tipo desiderato: **[!UICONTROL Trait]** oppure **[!UICONTROL Segment]**.
1. Fate clic sulle caselle di data per visualizzare un calendario, quindi selezionate le date di inizio e fine del rapporto.
1. Specificate l&#39;intervallo di visualizzazione: per 1, 7, 14, 30, 60 o 90 giorni.
1. Cerca una caratteristica o un segmento per nome o ID.
1. Nell&#39;elenco delle cartelle, trascina e rilascia le caratteristiche o i segmenti a destra del [!UICONTROL Selections] pannello.

   Per prestazioni ottimali, eseguite [!UICONTROL Trend] un report su meno di 20 caratteristiche o segmenti alla volta.
1. Fate clic **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, in base al tipo di rapporto che state visualizzando (Caratteristiche o Segmenti).

   Queste opzioni ignorano tutte le cartelle e i grafici solo per caratteristiche o segmenti selezionati singolarmente.

   Oppure

   Fai clic per **[!UICONTROL Export to CSV]** esportare i dati relativi a caratteristiche o segmenti e tutte le cartelle in formato CSV per ulteriori analisi e condivisione. Viene esportato l&#39; [!UICONTROL Unique Trait Realizations]intervallo di [!UICONTROL Total Trait Realizations][!UICONTROL Total Trait Population] tutti i giorni.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sono calcolate [!UICONTROL Rule-based Traits] solo per.

1. (Facoltativo) Passa il cursore su singole caratteristiche o segmenti per visualizzare il numero di visite e la data di ogni dato.

   Potete fare clic sulle intestazioni di colonna nella tabella per ordinare i risultati in ordine crescente o decrescente.

Per [!UICONTROL Trended Trait] i rapporti, gli zeri indicano che non [!DNL Audience Manager] sono state raccolte dati per quel giorno. Le voci vuote indicano che la caratteristica non esiste. L&#39;esempio seguente mostra esempi di entrambi i tipi di voci:

![](assets/trended_data.png)
