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
source-wordcount: '638'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Panoramica {#overview}

Il [!UICONTROL Activity Usage Report] ti consente di visualizzare e monitorare l’utilizzo delle attività dell’istanza di Audience Manager, fornendoti un’idea chiara dell’utilizzo delle attività in confronto all’impegno contrattuale.

È inoltre possibile scaricare [!UICONTROL Activity Usage Report] in qualsiasi momento, per la conservazione dei record e l&#39;analisi personalizzata.

## Considerazioni {#considerations}

[!UICONTROL Activity Usage Report] è disponibile per tutti gli utenti Audienci Manager con [privilegi di amministratore](edit-account-settings.md).

>[!IMPORTANT]
>
>[!UICONTROL Activity Usage Report] mostra le statistiche di utilizzo delle attività dell&#39;istanza Audience Manager. Per qualsiasi richiesta di informazioni sulla fatturazione relativa all’utilizzo dell’attività, contatta il rappresentante del tuo Adobe.

## Casi d&#39;uso {#use-cases}

Esistono due casi d&#39;uso principali di [!UICONTROL Activity Usage Report]:

* **Monitoraggio dell&#39;utilizzo effettivo dell&#39;attività dell&#39;istanza rispetto all&#39;impegno di utilizzo dell&#39;attività**: la maggior parte dei clienti ha un impegno di attività stimato mensile per ogni istanza di Audience Manager, che viene poi cumulato in un impegno di attività annuale in tutte le istanze. Anche se non si tratta di un rapporto di fatturazione, può fornire indicazioni utili per stabilire se l’utilizzo dell’attività impegnata è stato superato.
* **Convalida per modifiche all&#39;implementazione**: se l&#39;implementazione è stata aggiornata di recente, ad esempio impostando l&#39;inoltro lato server [!DNL Adobe Analytics] o modificando le impostazioni delle chiamate al server [!DNL Adobe Target], questo report può aiutarti a verificare se il nuovo volume di attività è in linea con il volume di attività previsto.

## Utilizzo di [!UICONTROL Activity Usage Report] {#using}

Per visualizzare [!UICONTROL Activity Usage Report], accedi al tuo account Audience Manager e passa a **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Quindi, utilizzare il filtro **[!UICONTROL Reporting Interval]** per selezionare l&#39;intervallo di tempo per il quale generare il report. Puoi scegliere tra 30, 60, 90 giorni o un intervallo di date personalizzato.

Una volta caricato il report, puoi visualizzare un raggruppamento di [!UICONTROL Activities] per il periodo selezionato.

[!UICONTROL Activities] definire il totale aggregato di tutte le interazioni nel sito e fuori dal sito con Audience Manager, suddiviso nelle seguenti categorie:

* **[!UICONTROL Server Calls]**: qualsiasi evento di raccolta o recupero dati inviato ad Audience Manager da siti Web, server, e-mail, app mobili o altri sistemi.
* **[!UICONTROL Pixel Calls] (precedentemente noto come [!UICONTROL Impression Server Calls])**: dati raccolti dagli annunci (ad esempio il volume di impression da una piattaforma di targeting) o chiamate di impression e-mail effettuate a Audience Manager. Questi richiedono la presenza del parametro `d_event` nella stringa query.
* **[!UICONTROL On-Boarded Records]**: record univoci acquisiti dal sistema CRM o da altri file di dati offline, ad esempio record di call center, ID dispositivo e feed di dati personalizzati da provider di dati esterni.
* **[!UICONTROL Log File Records]**: record univoci dai file di registro acquisiti in Audience Manager da una piattaforma di targeting.

>[!NOTE]
>
>Un record univoco definisce ogni singolo record di dati in un file memorizzato da Adobe per conto di un cliente Audience Manager.

È inoltre possibile utilizzare i tipi di grafico [!UICONTROL Activity Usage Trends] per passare da un tipo di grafico all&#39;altro.

![aur-ui-graphs](assets/aur-ui-graphs.png)

Puoi anche passare il cursore su una data specifica nella timeline per visualizzarne l’utilizzo dettagliato.

![aur-hover](assets/aur-hover.png)

## Esportazione di [!UICONTROL Activity Usage Reports] {#export}

Per una migliore panoramica del livello di utilizzo dell&#39;attività di Audience Manager, è possibile esportare [!UICONTROL Activity Usage Report] in base al tipo di record che si desidera includere.

![aur-export](assets/aur-export.png)

I report **[!UICONTROL Onboarded Records Breakdown]** e **[!UICONTROL Onsite Server Calls Breakdown]** forniscono informazioni dettagliate sui dati di origine disponibili per queste attività. Il volume attribuito a queste suddivisioni si basa sull’implementazione.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Questo report contiene record onboarded suddivisi per origine dati.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Questo report contiene un raggruppamento delle chiamate server da tre origini: [!UICONTROL Analytics], [!UICONTROL Target] e [!UICONTROL Other].

* **[!UICONTROL Analytics]**: si tratta di chiamate server fatturabili passate da tutte le [!UICONTROL Adobe Analytics] istanze all&#39;Audience Manager, incluso l&#39;inoltro lato server. Le chiamate server secondarie o le chiamate server duplicate (come nel caso dell’inoltro lato server da più suite di rapporti) non sono attività fatturabili, pertanto non sono incluse in questo raggruppamento.
* **[!UICONTROL Target]**: si tratta di chiamate lato server da [!UICONTROL Adobe Target] a Audience Manager per recuperare i dati del segmento Audience Manager come parte di un&#39;integrazione server-to-server.
* **[!UICONTROL Other]**: include chiamate da qualsiasi altro sito Web o sistema (siti partner, chiamate server dirette e così via), chiamate browser/app mobile tramite [!DNL SDK], [!DNL DIL], chiamate evento e [!DNL DCS] chiamate. Include anche le chiamate da [!DNL Target] se configurato come integrazione cookie (anziché server-to-server).
