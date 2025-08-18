---
description: Un rapporto sulle tendenze restituisce dati sulle tendenze per caratteristiche e segmenti.
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: Report tendenze
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Report tendenze{#trend-reports}

Un rapporto sulle tendenze restituisce dati sulle tendenze per caratteristiche e segmenti.

## Panoramica {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utilizza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo utenti ai report [!UICONTROL Trend]. Gli utenti possono visualizzare solo le caratteristiche e i segmenti per i rapporti che dispongono delle autorizzazioni di visualizzazione. La funzionalità [!UICONTROL RBAC] consente di controllare i dati di reporting che i team interni possono visualizzare.

Ad esempio, un’agenzia che gestisce account pubblicitari diversi può configurare le autorizzazioni per i gruppi di utenti in modo che un team che gestisce l’account dell’inserzionista A non possa visualizzare i dati di reporting dell’inserzionista B.

Eseguire un report [!UICONTROL Trend] quando è necessario:

* Rivedi i dati di tendenza per caratteristiche e segmenti.
* Tracciare le tendenze con intervalli di 1, 7, 14, 30, 60 e 90 giorni.
* Confrontare le tendenze di caratteristiche e segmenti nel tempo.
* Identifica caratteristiche e segmenti con prestazioni potenti o insoddisfacenti.
* Esporta i dati (formato .csv) per ulteriori analisi e condivisioni.

Nella figura seguente viene fornita una panoramica di alto livello degli elementi chiave nel report [!UICONTROL Trend].

![](assets/trend_reports.png)

1. Configura le seguenti opzioni:
   **Tipo di rapporto:** Selezionare il tipo di rapporto desiderato (caratteristica o segmento).
   **Intervallo date:** Specificare l&#39;intervallo di date per il report (data di inizio e data di fine).
   **Intervallo di visualizzazione:** Specificare l&#39;intervallo di visualizzazione (intervalli di 1, 7, 14, 30, 60 e 90 giorni).
1. Cerca una caratteristica o un segmento per nome o ID.
1. Dall&#39;elenco delle cartelle, trascina e rilascia le caratteristiche o i segmenti che desideri segnalare al pannello [!UICONTROL Selections] sul lato destro.
1. Genera il rapporto da visualizzare in formato grafico oppure esportalo in formato CSV.

## Eseguire un rapporto sulle tendenze {#run-trend-report}

Questa procedura descrive come eseguire un report [!UICONTROL Trend].

<!-- 

t_working_with_trend_reports.xml

 -->

1. Nel dashboard **[!UICONTROL Analytics]**, fare clic su **[!UICONTROL Trend Reports]**.
1. Dall&#39;elenco a discesa **[!UICONTROL Report Type]**, selezionare il tipo desiderato: **[!UICONTROL Trait]** o **[!UICONTROL Segment]**.
1. Fare clic sulle caselle delle date per visualizzare un calendario, quindi selezionare le date di inizio e di fine per il report.
1. Specificare l&#39;intervallo di visualizzazione: 1, 7, 14, 30, 60 o 90 giorni.
1. Cerca una caratteristica o un segmento per nome o ID.
1. Dall&#39;elenco delle cartelle, trascina e rilascia le caratteristiche o i segmenti che desideri segnalare al pannello [!UICONTROL Selections] sul lato destro.
   * Per ottenere prestazioni ottimali, eseguire un report [!UICONTROL Trend] su meno di 20 caratteristiche o segmenti alla volta.
1. Fare clic su **[!UICONTROL Graph Traits]** o **[!UICONTROL Graph Segments]**, a seconda del tipo di report che si sta visualizzando (Caratteristiche o Segmenti). Queste opzioni ignorano tutte le cartelle e i grafici solo per singoli segmenti o caratteristiche selezionati.

   Oppure

   Fai clic su **[!UICONTROL Export to CSV]** per esportare i dati di caratteristiche o segmenti e tutte le cartelle in formato CSV per ulteriori analisi e condivisioni. Esporta [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] e [!UICONTROL Total Trait Population] per tutti gli intervalli di giorni.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sono calcolati solo per [!UICONTROL Rule-based Traits].

1. (Facoltativo) Passa il puntatore del mouse su singole caratteristiche o segmenti per visualizzare il numero di visite e la data di ogni punto dati. Puoi fare clic sulle intestazioni di colonna nella tabella per ordinare i risultati in ordine crescente o decrescente.

## Risultati report tendenze per caratteristiche {#trend-report-results-traits}

I filtri seguenti sono disponibili quando si esegue [!UICONTROL Trend Report] e si seleziona **[!UICONTROL Trait]** come tipo di report.

Quando si filtrano i risultati per [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori anonimi del dispositivo che hanno aggiunto la caratteristica al loro profilo entro l&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Realization] è il numero totale di realizzazioni delle caratteristiche del mouse anonimo nell&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Population] è il numero di visitatori anonimi del tuo dispositivo che hanno questa caratteristica sul loro profilo.

Quando si filtrano i risultati per [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori autenticati che hanno aggiunto la caratteristica al loro profilo, entro l&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Realization] è il numero totale di realizzazioni di caratteristiche autenticate nell&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Population] è il numero di visitatori autenticati che hanno questa caratteristica sul loro profilo.

![trend-report-traits](assets/trend-report-traits.png)

Gli zeri indicano che [!DNL Audience Manager] non ha raccolto dati per quel giorno. Le voci vuote indicano che la caratteristica non esiste.

Guarda il video seguente per uno sguardo dettagliato al funzionamento delle metriche tra dispositivi.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=it)

## Risultati dei rapporti sulle tendenze per i segmenti {#segment-report-results-traits}

I filtri seguenti sono disponibili quando si esegue [!UICONTROL Trend Report] e si seleziona **[!UICONTROL Segments]** come tipo di report.

* **[!UICONTROL Real-time Segment Population]**: il numero di visitatori qualificati per il segmento all&#39;interno dell&#39;intervallo di tempo selezionato.
* **[!UICONTROL Total Segment Population]**: numero totale di visitatori qualificati per il segmento.

![trend-report-segments](assets/trend-report-segments.png)
