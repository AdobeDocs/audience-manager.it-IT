---
description: Un report Trend restituisce dati di tendenza su caratteristiche e segmenti.
seo-description: Un report Trend restituisce dati di tendenza su caratteristiche e segmenti.
seo-title: Rapporti sulle tendenze
solution: Audience Manager
title: Rapporti sulle tendenze
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: general & trend reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 1%

---


# Rapporti sulle tendenze{#trend-reports}

Un report Trend restituisce dati di tendenza su caratteristiche e segmenti.

## Panoramica {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utilizza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo di utenti ai [!UICONTROL Trend] rapporti. Gli utenti possono visualizzare solo le caratteristiche e i segmenti nel reporting per i quali dispongono delle autorizzazioni di visualizzazione. [!UICONTROL RBAC] consente di controllare i dati che possono essere visualizzati dai team interni.

Ad esempio, un&#39;agenzia che gestisce diversi account di inserzionisti può configurare le autorizzazioni per gruppi di utenti in modo che un team che gestisce l&#39;account dell&#39;inserzionista A non possa vedere i dati di reporting dell&#39;inserzionista B.

Esegui un [!UICONTROL Trend] report quando è necessario:

* Rivedete i dati delle tendenze per caratteristiche e segmenti.
* Consente di tenere traccia delle tendenze di intervalli di 1, 7, 14, 30, 60 e 90 giorni.
* Confronta caratteristiche e tendenze dei segmenti nel tempo.
* Identificare caratteristiche e segmenti di prestazioni forti o insufficienti.
* Esporta dati (formato CSV) per ulteriori analisi e condivisione.

L&#39;illustrazione seguente fornisce una panoramica di alto livello degli elementi chiave nel [!UICONTROL Trend] rapporto.

![](assets/trend_reports.png)

1. Configurate le seguenti opzioni:
   **Tipo di rapporto:** Selezionare il tipo di rapporto desiderato (Caratteristiche o Segmento).
   **Intervallo date:** Specifica l&#39;intervallo di date per il rapporto (data di inizio e data di fine).
   **Intervallo di visualizzazione:** Specificate l&#39;intervallo di visualizzazione (intervalli di 1, 7, 14, 30, 60 e 90 giorni).
1. Cercare una caratteristica o segmento per nome o ID.
1. Dall’elenco delle cartelle, trascinate le caratteristiche o i segmenti da includere nel rapporto sul [!UICONTROL Selections] pannello a destra.
1. Generate il rapporto per visualizzarlo in formato grafico o esportarlo in formato CSV.

## Eseguire un report di tendenze {#run-trend-report}

Questa procedura descrive come eseguire un [!UICONTROL Trend] rapporto.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Nel **[!UICONTROL Analytics]** dashboard, fate clic su **[!UICONTROL Trend Reports]**.
1. Dall’elenco a **[!UICONTROL Report Type]** discesa, selezionate il tipo desiderato: **[!UICONTROL Trait]** o **[!UICONTROL Segment]**.
1. Fai clic sulle caselle delle date per visualizzare un calendario, quindi seleziona le date di inizio e di fine del rapporto.
1. Specificate l&#39;intervallo di visualizzazione: entro 1, 7, 14, 30, 60 o 90 giorni.
1. Cercare una caratteristica o segmento per nome o ID.
1. Dall’elenco delle cartelle, trascinate le caratteristiche o i segmenti da includere nel rapporto sul [!UICONTROL Selections] pannello a destra.
   * Per ottenere prestazioni ottimali, esegui un [!UICONTROL Trend] rapporto su meno di 20 caratteristiche o segmenti alla volta.
1. Fate clic **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, a seconda del tipo di rapporto che state visualizzando (Caratteristiche o Segmenti). Queste opzioni ignorano tutte le cartelle e i grafici solo i tratti o i segmenti selezionati singolarmente.

   Oppure

   Fate clic **[!UICONTROL Export to CSV]** per esportare la caratteristica o i dati del segmento e tutte le cartelle in formato CSV per ulteriori analisi e condivisione. Questo consente di esportare gli intervalli [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]e [!UICONTROL Total Trait Population] per tutti i giorni.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sono calcolati [!UICONTROL Rule-based Traits] solo per.

1. (Facoltativo) Passa il puntatore del mouse sulle singole caratteristiche o segmenti per visualizzare il numero di visite e la data di ciascun punto dati. È possibile fare clic sulle intestazioni delle colonne nella tabella per ordinare i risultati in ordine crescente o decrescente.

## Risultati report sulle tendenze per le caratteristiche {#trend-report-results-traits}

I filtri riportati di seguito sono disponibili quando si esegue un [!UICONTROL Trend Report] e si seleziona **[!UICONTROL Trait]** come tipo di rapporto.

Quando filtrate i risultati tramite [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori anonimi del dispositivo che hanno aggiunto la caratteristica al proprio profilo entro l&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Realization] è il numero totale di realizzazioni di caratteristiche del mouse anonimo nell&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Population] è il numero di visitatori anonimi del dispositivo che hanno questa caratteristica sul loro profilo.

Quando filtrate i risultati tramite [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori autenticati che hanno aggiunto la caratteristica al proprio profilo, entro l&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Realization] è il numero totale di realizzazioni di caratteristiche autenticate nell&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Population] è il numero di visitatori autenticati che hanno questa caratteristica sul loro profilo.

![trend-report-traits](assets/trend-report-traits.png)

Gli zero indicano che [!DNL Audience Manager] non hanno raccolto i dati per quel giorno. Voci vuote indicano che la caratteristica non esisteva.

Guardate il video seguente per vedere in dettaglio come funzionano le metriche tra dispositivi.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Risultati report sulle tendenze per i segmenti {#segment-report-results-traits}

I filtri riportati di seguito sono disponibili quando si esegue un [!UICONTROL Trend Report] e si seleziona **[!UICONTROL Segments]** come tipo di rapporto.

* **[!UICONTROL Real-time Segment Population]**: il numero di visitatori idonei per il segmento nell&#39;intervallo di tempo selezionato.
* **[!UICONTROL Total Segment Population]**: il numero totale di visitatori idonei per il segmento.

![trend-report-segmenti](assets/trend-report-segments.png)