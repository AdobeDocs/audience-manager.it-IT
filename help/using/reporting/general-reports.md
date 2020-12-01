---
description: Un rapporto Generale restituisce dati sulle prestazioni su caratteristiche, segmenti e destinazioni.
seo-description: Un rapporto Generale in  Audience Manager restituisce dati sulle prestazioni su caratteristiche, segmenti e destinazioni.
seo-title: Rapporti generali in  Audience Manager
solution: Audience Manager
title: Rapporti generali
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: general & trend reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 0%

---


# Rapporti generali{#general-reports}

Un report [!UICONTROL General] restituisce dati sulle prestazioni su caratteristiche, segmenti e destinazioni.

## Panoramica {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utilizza  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo di utenti ai  [!UICONTROL General] rapporti. Gli utenti possono visualizzare solo le caratteristiche e i segmenti nel reporting per i quali dispongono delle autorizzazioni di visualizzazione. [!UICONTROL RBAC] consente di controllare i dati che possono essere visualizzati dai team interni. Ad esempio, un&#39;agenzia che gestisce diversi account di inserzionisti può configurare le autorizzazioni per gruppi di utenti in modo che un team che gestisce l&#39;account dell&#39;inserzionista A non possa vedere i dati di reporting dell&#39;inserzionista B.

Eseguire un report [!UICONTROL General] quando è necessario:

* Verifica le prestazioni per caratteristica, segmento o destinazione.
* Tieni traccia delle impression (totali e univoci) a intervalli di 1, 7, 14, 30, 60 e 90 giorni.
* Rivedete i conteggi totali e unici dei carichi.
* Confronta caratteristiche e prestazioni del segmento.
* Identificazione di caratteristiche e segmenti di prestazioni forti o insufficienti, analisi della domanda o confronto di dati di carico/incendio con report di terze parti.
* Esporta dati (formato CSV) per ulteriori analisi e condivisione.

L&#39;illustrazione seguente fornisce una panoramica di alto livello degli elementi chiave nel report [!UICONTROL General].

![](assets/general_reports.png)

1. Configurate le seguenti opzioni:

   * **Tipo di rapporto:** selezionate il tipo di rapporto desiderato (Caratteristiche, Segmento o Destinazione).

   * **Per Date Through:** specifica l&#39;intervallo di date per il rapporto.

2. Cerca una caratteristica, un segmento o una destinazione per nome o ID.
3. Dall&#39;elenco delle cartelle, trascina e rilascia le caratteristiche, i segmenti o le destinazioni che desideri segnalare al pannello [!UICONTROL Selections] a destra.
4. Generare il rapporto da visualizzare in una tabella esportabile.

## Eseguire un report generale {#run-general-report}

Questa sezione descrive come eseguire un report [!UICONTROL General] e impostare l&#39;ora e altre opzioni di prestazioni.

<!-- 

t_run_general_report.xml

 -->

1. Nel dashboard **[!UICONTROL Analytics]**, fare clic su **[!UICONTROL General Reports]**.
1. Dall&#39;elenco a discesa **[!UICONTROL Report Type]**, selezionate il tipo desiderato: Caratteristiche, segmento o destinazione.
1. ** CondizionaleFare clic sulla casella della data per visualizzare un calendario, quindi selezionare la data di fine del rapporto se si desidera specificare una data diversa da quella odierna.
1. Cerca una caratteristica, un segmento o una destinazione per nome o ID.
1. Dall&#39;elenco delle cartelle, trascina e rilascia le caratteristiche, i segmenti o le destinazioni che desideri segnalare al pannello [!UICONTROL Selections] a destra.
1. Clic **[!UICONTROL Run Report]**.

   I risultati vengono visualizzati in una tabella esportabile. Fate clic sulle intestazioni delle colonne per ordinare i risultati in ordine crescente o decrescente.
1. Selezionare il pulsante di opzione desiderato nella parte superiore del rapporto per filtrare i dati in base alle prestazioni ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] o [!UICONTROL Total Trait Population]) o per ora (intervallo di 1, 7, 14, 30, 60 o 90 giorni).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sono calcolati  [!UICONTROL Rule-based Traits] solo per.

1. ** FacoltativoFare clic  **[!UICONTROL Export to CSV]**. In questo modo vengono esportati i formati [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] e [!UICONTROL Total Trait Population] per tutti gli intervalli di giorni.

## Risultati generali report spiegati {#general-reports-explained}

I numeri nella [!UICONTROL General Reports] vengono generati direttamente dalla [!UICONTROL User Profile Store]. I risultati riflettono il numero di utenti contenuti nel backend [!DNL Audience Manager] al momento della generazione di tali numeri di rapporto.

* Questi numeri non includono gli ID visitatore con traffico eccessivo. Il traffico dai robot viene filtrato prima di raggiungere il nostro sistema di back-end. Inoltre, il traffico bot viene scartato durante un processo di pulizia settimanale eseguito nel backend.
* Se durante l&#39;elaborazione in ingresso i dati sono stati cancellati dall&#39;UUID [!DNL Audience Manager] e questi ID includono utenti che non sono più attivi nel nostro sistema, questi [!DNL Audience Manager] UUID inattivi non raggiungono mai l&#39;[!UICONTROL User Profile Store] e non vengono segnalati.
* [!UICONTROL Total Trait Realizations] sono calcolati  [!UICONTROL Rule-based Traits] solo per.

## Risultati dei report generali per le caratteristiche {#general-report-results-traits}

I filtri seguenti sono disponibili quando si esegue un rapporto Generale e si seleziona **[!UICONTROL Trait]** come tipo di rapporto.

Durante il filtraggio dei risultati per [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori anonimi del dispositivo che hanno aggiunto la caratteristica al proprio profilo entro l&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Realization] è il numero totale di realizzazioni di caratteristiche anonime all&#39;interno dell&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Population] è il numero di visitatori anonimi del dispositivo che hanno questa caratteristica sul loro profilo.

![generale-report-traits-device](assets/general-report-traits-deviceid.png)

Durante il filtraggio dei risultati per [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] è il numero di visitatori autenticati che hanno aggiunto la caratteristica al proprio profilo, entro l&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Realization] è il numero totale di realizzazioni di caratteristiche autenticate nell&#39;intervallo di tempo selezionato.
* [!UICONTROL Total Trait Population] è il numero di visitatori autenticati che hanno questa caratteristica sul loro profilo.

![generale-report-traits-cross-device](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## Risultati dei report generali per segmenti {#general-report-results-segments}

Le metriche riportate di seguito sono disponibili quando si esegue un rapporto Generale e si seleziona **[!UICONTROL Segment]** come tipo di rapporto:

### Popolazione segmenti in tempo reale

Questa metrica rappresenta il numero effettivo di visitatori univoci visti in tempo reale per l&#39;intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti dal Audience Manager .

### Popolazione segmento totale

Questa metrica rappresenta il numero totale di UUID Audience Manager  qualificati per il segmento nel periodo di look-back selezionato. La popolazione totale di segmenti di 1 giorno rappresenta la base utente più precisa per il targeting.

>[!NOTE]
>
>Selezionare **[!UICONTROL Include Destination Mappings]** per visualizzare una suddivisione della popolazione del segmento per le destinazioni attivate.

L&#39;illustrazione seguente mostra i risultati dell&#39;esecuzione di un rapporto generale per il tipo di rapporto Segmento.

![](assets/general_reports_segment_metrics.png)

## Risultati dei report generali per le destinazioni {#general-report-results-destinations}

Le metriche riportate di seguito sono disponibili quando si esegue un rapporto Generale e si seleziona **[!UICONTROL Destination]** come tipo di rapporto:

**Popolazione segmenti in tempo reale**

Questa metrica rappresenta il numero effettivo di visitatori univoci visti in tempo reale per l&#39;intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti dal Audience Manager .

**Popolazione segmento totale**

Questa metrica rappresenta il numero totale di UUID Audience Manager  appartenenti a un segmento nel periodo di look-back, che sono stati inviati a una destinazione.

L&#39;illustrazione seguente mostra i risultati dell&#39;esecuzione di un rapporto generale per il tipo di rapporto Destinazioni.

![](assets/general_reports_destinations.png)
