---
description: Un rapporto Generale restituisce dati sulle prestazioni su caratteristiche, segmenti e destinazioni.
seo-description: Un rapporto Generale in Audience Manager restituisce dati sulle prestazioni su caratteristiche, segmenti e destinazioni.
seo-title: Report generali in Audience Manager
solution: Audience Manager
title: Rapporti generali
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Rapporti generali{#general-reports}

Un [!UICONTROL General] rapporto restituisce dati sulle prestazioni su caratteristiche, segmenti e destinazioni.

## Panoramica {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utilizza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo di utenti ai [!UICONTROL General] rapporti. Gli utenti possono visualizzare solo le caratteristiche e i segmenti nel reporting per i quali dispongono delle autorizzazioni di visualizzazione. [!UICONTROL RBAC] consente di controllare i dati che possono essere visualizzati dai team interni. Ad esempio, un&#39;agenzia che gestisce diversi account di inserzionisti può configurare le autorizzazioni per gruppi di utenti in modo che un team che gestisce l&#39;account dell&#39;inserzionista A non possa vedere i dati di reporting dell&#39;inserzionista B.

Esegui un [!UICONTROL General] report quando è necessario:

* Verifica le prestazioni per caratteristica, segmento o destinazione.
* Tieni traccia delle impression (totali e univoci) a intervalli di 1, 7, 14, 30, 60 e 90 giorni.
* Rivedete i conteggi totali e unici dei carichi.
* Confronta caratteristiche e prestazioni del segmento.
* Identificazione di caratteristiche e segmenti di prestazioni forti o insufficienti, analisi della domanda o confronto di dati di carico/incendio con report di terze parti.
* Esporta dati (formato CSV) per ulteriori analisi e condivisione.

L&#39;illustrazione seguente fornisce una panoramica di alto livello degli elementi chiave nel [!UICONTROL General] rapporto.

![](assets/general_reports.png)

1. Configurate le seguenti opzioni:

   * **Tipo di rapporto:** Seleziona il tipo di rapporto desiderato (Caratteristiche, Segmento o Destinazione).

   * **Per le date fino a:** Specifica l&#39;intervallo di date per il rapporto.

2. Cerca una caratteristica, un segmento o una destinazione per nome o ID.
3. Dall’elenco delle cartelle, trascina e rilascia le caratteristiche, i segmenti o le destinazioni da includere nel rapporto sul [!UICONTROL Selections] pannello a destra.
4. Generare il rapporto da visualizzare in una tabella esportabile.

## Eseguire un report generale {#run-general-report}

Questa sezione descrive come eseguire un [!UICONTROL General] rapporto e impostare l&#39;ora e altre opzioni di prestazioni.

<!-- 

t_run_general_report.xml

 -->

1. Nel **[!UICONTROL Analytics]** dashboard, fate clic su **[!UICONTROL General Reports]**.
1. Dall’elenco a **[!UICONTROL Report Type]** discesa, selezionate il tipo desiderato: Caratteristiche, segmento o destinazione.
1. *Condizionale* Fare clic sulla casella della data per visualizzare un calendario, quindi selezionare la data di fine del rapporto se si desidera specificare una data diversa da quella odierna.
1. Cerca una caratteristica, un segmento o una destinazione per nome o ID.
1. Dall’elenco delle cartelle, trascina e rilascia le caratteristiche, i segmenti o le destinazioni da includere nel rapporto sul [!UICONTROL Selections] pannello a destra.
1. Clic **[!UICONTROL Run Report]**.

   I risultati vengono visualizzati in una tabella esportabile. Fate clic sulle intestazioni delle colonne per ordinare i risultati in ordine crescente o decrescente.
1. Selezionate il pulsante di opzione desiderato nella parte superiore del rapporto per filtrare i dati in base alle prestazioni ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]o [!UICONTROL Total Trait Population]) o per ora (intervallo di 1, 7, 14, 30, 60 o 90 giorni).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sono calcolati [!UICONTROL Rule-based Traits] solo per.

1. *Facoltativo* Fare clic **[!UICONTROL Export to CSV]**. Questo consente di esportare gli intervalli [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]e [!UICONTROL Total Trait Population] per tutti i giorni.

## Spiegati i risultati generali dei report {#general-reports-explained}

I numeri nel [!UICONTROL General Reports] vengono generati direttamente dal nostro [!UICONTROL User Profile Store]. I risultati riflettono il numero di utenti [!DNL Audience Manager] contenuti nel backend al momento della generazione di tali numeri di rapporto.

* Questi numeri non includono gli ID visitatore con traffico eccessivo. Il traffico dai robot viene filtrato prima di raggiungere il nostro sistema di back-end. Inoltre, il traffico bot viene scartato durante un processo di pulizia settimanale eseguito nel backend.
* Se a bordo dei dati tramite l&#39;elaborazione in ingresso è stato disattivato l&#39; [!DNL Audience Manager] UUID e questi ID includono utenti che non sono più attivi nel nostro sistema, questi [!DNL Audience Manager] UUID inattivi non raggiungono mai l&#39;UUID [!UICONTROL User Profile Store] e non vengono segnalati.
* [!UICONTROL Total Trait Realizations] sono calcolati [!UICONTROL Rule-based Traits] solo per.

## Risultati dei report generali per le caratteristiche {#general-report-results-traits}

Le metriche riportate di seguito sono disponibili quando si esegue un rapporto Generale e si seleziona **[!UICONTROL Trait]** come tipo di rapporto:

**Realizzazioni di caratteristiche univoche**

Questa metrica rappresenta il numero univoco di ID utente univoci di [Audience Manager (UUID)](../reference/ids-in-aam.md) qualificati per la caratteristica nell’intervallo di tempo selezionato. Ad esempio, se un utente ha visitato la pagina principale tre volte il 10/1, viene visualizzata una sola realizzazione di caratteristica univoca.

**Totale realizzazioni caratteristiche**

Questa metrica rappresenta la quantità totale di attivazioni di caratteristiche per la caratteristica nell&#39;intervallo di tempo selezionato. Ad esempio, se un utente ha visitato la tua homepage, poi è passato alle tue notizie tecniche e alle tue sezioni di notizie sportive, apparirebbero nel Report generale come tre realizzazioni totali delle caratteristiche e una realizzazione unica.

**Totale popolazione caratteristiche**

Questa metrica rappresenta la quantità totale di UUID Audience Manager attualmente idonei per la caratteristica. Utilizzate questo numero per comprendere la quantità totale di utenti che potete utilizzare per la segmentazione e il targeting. In genere, gli utenti restano parte di una caratteristica per [120 giorni](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Ad esempio, un utente che visita la tua homepage tre volte oggi e non ritorna mai dopo, rimarrà come utente in questa popolazione ogni giorno fino a 120 giorni da ora. A 120 giorni, sarebbero stati rimossi dalla popolazione. Per ulteriori esempi sulla differenza tra le realizzazioni di caratteristiche univoche e la popolazione di caratteristiche totali, consulta la Guida di riferimento [per le qualifiche di](../features/traits/trait-and-segment-qualification-reference.md) caratteristiche e segmenti.

L&#39;illustrazione seguente mostra i risultati dell&#39;esecuzione di un rapporto generale per il tipo di rapporto Caratteristiche.

![](assets/general_reports_metrics.png)

## Risultati dei report generali per i segmenti {#general-report-results-segments}

Le metriche riportate di seguito sono disponibili quando si esegue un rapporto Generale e si seleziona **[!UICONTROL Segment]** come tipo di rapporto:

**Popolazione segmenti in tempo reale**

Questa metrica rappresenta il numero effettivo di visitatori univoci visti in tempo reale per l’intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti da Audience Manager.

**Popolazione segmento totale**

Questa metrica rappresenta il numero totale di UUID Audience Manager qualificati per il segmento nel periodo di look-back selezionato. La popolazione totale di segmenti di 1 giorno rappresenta la base utente più precisa per il targeting.

>[!NOTE]
>
>Selezionate **[!UICONTROL Include Destination Mappings]** per visualizzare una suddivisione della popolazione del segmento per le destinazioni attivate.

L&#39;illustrazione seguente mostra i risultati dell&#39;esecuzione di un rapporto generale per il tipo di rapporto Segmento.

![](assets/general_reports_segment_metrics.png)

## Risultati report generali per le destinazioni {#general-report-results-destinations}

Le metriche riportate di seguito sono disponibili quando si esegue un rapporto Generale e si seleziona **[!UICONTROL Destination]** come tipo di rapporto:

**Popolazione segmenti in tempo reale**

Questa metrica rappresenta il numero effettivo di visitatori univoci visti in tempo reale per l’intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti da Audience Manager.

**Popolazione segmento totale**

Questa metrica rappresenta il numero totale di UUID Audience Manager appartenenti a un segmento nel periodo di look-back, che sono stati inviati a una destinazione.

L&#39;illustrazione seguente mostra i risultati dell&#39;esecuzione di un rapporto generale per il tipo di rapporto Destinazioni.

![](assets/general_reports_destinations.png)
