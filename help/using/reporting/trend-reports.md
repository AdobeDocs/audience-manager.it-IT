---
description: Un rapporto di tendenze restituisce dati di tendenza su caratteristiche e segmenti.
seo-description: Un rapporto di tendenze restituisce dati di tendenza su caratteristiche e segmenti.
seo-title: Rapporti sulle tendenze
solution: Audience Manager
title: Rapporti sulle tendenze
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: Rapporti generali e sulle tendenze
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# Rapporti sulle tendenze{#trend-reports}

Un rapporto di tendenze restituisce dati di tendenza su caratteristiche e segmenti.

## Panoramica {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utilizza  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo di utenti ai  [!UICONTROL Trend] rapporti. Gli utenti possono visualizzare solo le caratteristiche e i segmenti nel reporting che dispongono delle autorizzazioni di visualizzazione. [!UICONTROL RBAC] consente di controllare quali dati possono essere visualizzati dai team interni.

Ad esempio, un’agenzia che gestisce diversi account inserzionista può configurare le autorizzazioni per i gruppi di utenti in modo che un team che gestisce l’account dell’inserzionista A non possa visualizzare i dati di reporting dell’inserzionista B.

Esegui un rapporto [!UICONTROL Trend] quando devi:

* Esamina i dati delle tendenze per caratteristiche e segmenti.
* Monitora le tendenze di intervalli di 1, 7, 14, 30, 60 e 90 giorni.
* Confronta le tendenze di caratteristiche e segmenti nel tempo.
* Identifica caratteristiche e segmenti dalle prestazioni forti o scarsi.
* Esporta dati (formato .csv) per ulteriori analisi e condivisione.

La figura seguente fornisce una panoramica di alto livello degli elementi chiave del rapporto [!UICONTROL Trend] .

![](assets/trend_reports.png)

1. Configura le seguenti opzioni:
   **Tipo di rapporto:** seleziona il tipo di rapporto desiderato (caratteristica o segmento).
   **Intervallo di date:** specifica l’intervallo di date per il rapporto (data di inizio e data di fine).
   **Intervallo di visualizzazione:** specifica l’intervallo di visualizzazione (intervalli di 1, 7, 14, 30, 60 e 90 giorni).
1. Cerca una caratteristica o un segmento per nome o ID.
1. Dall’elenco delle cartelle, trascina e rilascia le caratteristiche o i segmenti che desideri includere nel rapporto nel pannello [!UICONTROL Selections] a destra.
1. Genera il rapporto da visualizzare in formato grafico o esporta il rapporto in formato CSV.

## Eseguire un rapporto sulle tendenze {#run-trend-report}

Questa procedura descrive come eseguire un rapporto [!UICONTROL Trend].

<!-- 

t_working_with_trend_reports.xml

 -->

1. Nel dashboard **[!UICONTROL Analytics]**, fai clic su **[!UICONTROL Trend Reports]**.
1. Dall’elenco a discesa **[!UICONTROL Report Type]** , seleziona il tipo desiderato: **[!UICONTROL Trait]** o **[!UICONTROL Segment]**.
1. Fai clic sulle caselle della data per visualizzare un calendario, quindi seleziona le date di inizio e di fine del rapporto.
1. Specifica l&#39;intervallo di visualizzazione: entro 1, 7, 14, 30, 60 o 90 giorni.
1. Cerca una caratteristica o un segmento per nome o ID.
1. Dall’elenco delle cartelle, trascina e rilascia le caratteristiche o i segmenti che desideri includere nel rapporto nel pannello [!UICONTROL Selections] a destra.
   * Per ottenere le migliori prestazioni, esegui un rapporto [!UICONTROL Trend] su meno di 20 caratteristiche o segmenti alla volta.
1. Fai clic su **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, a seconda del tipo di rapporto che stai visualizzando (Caratteristiche o Segmenti). Queste opzioni ignorano tutte le cartelle e i grafici solo le caratteristiche o i segmenti selezionati singolarmente.

   Oppure

   Fai clic su **[!UICONTROL Export to CSV]** per esportare i dati delle caratteristiche o dei segmenti e tutte le cartelle in formato CSV per ulteriori analisi e condivisione. Vengono esportati i valori [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] e [!UICONTROL Total Trait Population] per tutti gli intervalli di giorni.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sono calcolati  [!UICONTROL Rule-based Traits] solo per .

1. (Facoltativo) Passa il puntatore del mouse su singole caratteristiche o segmenti per visualizzare il numero di visite e la data di ciascun punto dati. Puoi fare clic sulle intestazioni di colonna nella tabella per ordinare i risultati in ordine crescente o decrescente.

## Risultati dei report sulle tendenze per le caratteristiche {#trend-report-results-traits}

I filtri seguenti sono disponibili quando si esegue un [!UICONTROL Trend Report] e si seleziona **[!UICONTROL Trait]** come tipo di rapporto.

Durante il filtraggio dei risultati per [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori anonimi del dispositivo che hanno aggiunto la caratteristica al profilo entro l’intervallo di tempo selezionato.
* [!UICONTROL Total Trait Realization] è il numero totale di realizzazioni di caratteristiche del mouse anonimo all’interno dell’intervallo di tempo selezionato.
* [!UICONTROL Total Trait Population] è il numero di visitatori del tuo dispositivo anonimi che hanno questa caratteristica sul loro profilo.

Durante il filtraggio dei risultati per [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori autenticati che hanno aggiunto la caratteristica al loro profilo, entro l’intervallo di tempo selezionato.
* [!UICONTROL Total Trait Realization] è il numero totale di realizzazioni di caratteristiche autenticate nell’intervallo di tempo selezionato.
* [!UICONTROL Total Trait Population] è il numero di visitatori autenticati che hanno questa caratteristica sul loro profilo.

![trend-report-traits](assets/trend-report-traits.png)

Gli zero indicano che [!DNL Audience Manager] non ha raccolto i dati per quel giorno. Le voci vuote indicano che la caratteristica non esisteva.

Guarda il video seguente per vedere in dettaglio come funzionano le metriche per dispositivi diversi.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Risultati dei report sulle tendenze per i segmenti {#segment-report-results-traits}

I filtri seguenti sono disponibili quando si esegue un [!UICONTROL Trend Report] e si seleziona **[!UICONTROL Segments]** come tipo di rapporto.

* **[!UICONTROL Real-time Segment Population]**: il numero di visitatori qualificati per il segmento nell’intervallo di tempo selezionato.
* **[!UICONTROL Total Segment Population]**: il numero totale di visitatori qualificati per il segmento.

![segmenti di trend-report](assets/trend-report-segments.png)
