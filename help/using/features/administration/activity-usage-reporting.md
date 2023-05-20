---
description: Activity Usage Reporting (Reporting sull'utilizzo dell'attività) consente di visualizzare e monitorare l'utilizzo dell'attività per l'istanza dell'Audience Manager, in modo da poter confrontare l'utilizzo effettivo con l'impegno contrattuale.
keywords: attività, utilizzo, reporting, impegno
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: Reporting sull’utilizzo delle attività
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Panoramica {#overview}

Il [!UICONTROL Activity Usage Report] ti consente di visualizzare e monitorare l’utilizzo delle attività dell’istanza di Audience Manager, fornendoti un’idea chiara dell’utilizzo delle attività in confronto all’impegno contrattuale.

Inoltre, puoi scaricare [!UICONTROL Activity Usage Report] quando necessario, per la conservazione dei record e l&#39;analisi personalizzata.

## Considerazioni {#considerations}

Il [!UICONTROL Activity Usage Report] è disponibile per tutti gli utenti di Audience Manager con [privilegi di amministratore](edit-account-settings.md).

>[!IMPORTANT]
>
>Il [!UICONTROL Activity Usage Report] mostra le statistiche di utilizzo dell’attività dell’istanza Audience Manager. Per qualsiasi richiesta di informazioni sulla fatturazione relativa all’utilizzo dell’attività, contatta il rappresentante del tuo Adobe.

## Casi d&#39;uso {#use-cases}

Esistono due casi d’uso principali del [!UICONTROL Activity Usage Report]:

* **Tracciamento dell’utilizzo effettivo dell’attività dell’istanza rispetto all’impegno di utilizzo dell’attività**: la maggior parte dei clienti ha un impegno mensile stimato per ogni istanza di Audience Manager, che viene poi cumulato in un impegno annuale per tutte le istanze. Anche se non si tratta di un rapporto di fatturazione, può fornire indicazioni utili per stabilire se l’utilizzo dell’attività impegnata è stato superato.
* **Convalida per le modifiche di implementazione**: se hai aggiornato di recente l’implementazione, ad esempio la configurazione di [!DNL Adobe Analytics] inoltro lato server o modifica [!DNL Adobe Target] impostazioni delle chiamate al server, questo rapporto può aiutarti a verificare se il nuovo volume di attività è in linea con il volume di attività previsto.

## L&#39;uso dell&#39;identificazione [!UICONTROL Activity Usage Report] {#using}

Per visualizzare [!UICONTROL Activity Usage Report], accedi al tuo account di Audience Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Quindi, utilizza **[!UICONTROL Reporting Interval]** per selezionare l’intervallo di tempo per il quale generare il rapporto. Puoi scegliere tra 30, 60, 90 giorni o un intervallo di date personalizzato.

Una volta caricato il rapporto, puoi vedere un raggruppamento del tuo [!UICONTROL Activities] per il periodo selezionato.

[!UICONTROL Activities] definisci il totale aggregato di tutte le interazioni nel sito e fuori dal sito con Audience Manager, suddiviso nelle seguenti categorie:

* **[!UICONTROL Server Calls]**: qualsiasi evento di raccolta o recupero di dati inviato ad Audience Manager da siti web, server, e-mail, app mobili o altri sistemi.
* **[!UICONTROL Pixel Calls](precedentemente noto come [!UICONTROL Impression Server Calls])**: dati raccolti dagli annunci (come il volume di impression da una piattaforma di targeting) o chiamate di impression e-mail effettuate su Audience Manager. Questi richiedono la presenza di `d_event` parametro nella stringa query.
* **[!UICONTROL On-Boarded Records]**: record univoci acquisiti dal tuo sistema CRM (Customer Relationship Management System) o altri file di dati offline, come record di call center, ID dispositivo e feed di dati personalizzati da fornitori di dati esterni.
* **[!UICONTROL Log File Records]**: record univoci dai file di registro acquisiti in Audience Manager da una piattaforma di targeting.

>[!NOTE]
>
>Un record univoco definisce ogni singolo record di dati in un file memorizzato da Adobe per conto di un cliente Audience Manager.

Inoltre, è possibile utilizzare [!UICONTROL Activity Usage Trends] tipi di grafico per passare da un tipo di grafico all’altro.

![aur-ui-graphs](assets/aur-ui-graphs.png)

Puoi anche passare il cursore su una data specifica nella timeline per visualizzarne l’utilizzo dettagliato.

![aur-hover](assets/aur-hover.png)

## Esportazione [!UICONTROL Activity Usage Reports] {#export}

Per una migliore panoramica del livello di utilizzo dell’attività di Audience Manager, puoi esportare la [!UICONTROL Activity Usage Report] in base al tipo di record che si desidera includere.

![aur-export](assets/aur-export.png)

Il **[!UICONTROL Onboarded Records Breakdown]** e **[!UICONTROL Onsite Server Calls Breakdown]** I rapporti forniscono informazioni dettagliate sui dati di origine disponibili per queste attività. Il volume attribuito a queste suddivisioni si basa sull’implementazione.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Questo report contiene record onboarded suddivisi per origine dati.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Questo rapporto contiene un raggruppamento delle chiamate al server provenienti da tre origini: [!UICONTROL Analytics], [!UICONTROL Target], e [!UICONTROL Other].

* **[!UICONTROL Analytics]**: si tratta di chiamate server fatturabili passate da tutti [!UICONTROL Adobe Analytics] istanze da Audience Manager, incluso l’inoltro lato server. Le chiamate server secondarie o le chiamate server duplicate (come nel caso dell’inoltro lato server da più suite di rapporti) non sono attività fatturabili, pertanto non sono incluse in questo raggruppamento.
* **[!UICONTROL Target]**: si tratta di chiamate lato server da [!UICONTROL Adobe Target] ad Audience Manager, per recuperare i dati dei segmenti Audience Manager come parte di un’integrazione server-to-server.
* **[!UICONTROL Other]**: include chiamate da qualsiasi altro sito web o sistema (siti partner, chiamate server dirette, ecc.), chiamate browser/app mobili tramite [!DNL SDK], [!DNL DIL], chiamate evento e [!DNL DCS] chiamate. Include anche le chiamate da [!DNL Target] se è configurato come integrazione di cookie (anziché server-to-server).
