---
description: La funzione di reporting dell’utilizzo delle attività ti consente di visualizzare e monitorare l’utilizzo delle attività per l’istanza di Audience Manager, in modo da poter confrontare l’utilizzo effettivo rispetto all’impegno contrattuale.
keywords: attività, utilizzo, reporting, impegno
seo-description: La funzione di reporting dell’utilizzo delle attività ti consente di visualizzare e monitorare l’utilizzo delle attività per l’istanza di Audience Manager, in modo da poter confrontare l’utilizzo effettivo rispetto all’impegno contrattuale.
seo-title: Reporting sull’utilizzo delle attività
solution: Audience Manager
title: Reporting sull’utilizzo delle attività
feature: Utilizzo e fatturazione
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 6%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Panoramica {#overview}

Il [!UICONTROL Activity Usage Report] ti consente di visualizzare e monitorare l’utilizzo delle attività dell’istanza di Audience Manager, fornendoti un’idea chiara dell’utilizzo delle attività in confronto all’impegno contrattuale.

Inoltre, puoi scaricare il [!UICONTROL Activity Usage Report] ogni volta che ti serve, per la conservazione dei record e l’analisi personalizzata.

## Considerazioni {#considerations}

Il [!UICONTROL Activity Usage Report] è disponibile per tutti gli utenti di Audience Manager con [privilegi di amministratore](edit-account-settings.md).

>[!IMPORTANT]
>
>La sezione [!UICONTROL Activity Usage Report] mostra le statistiche di utilizzo dell’attività dell’istanza di Audience Manager. Per qualsiasi richiesta di fatturazione relativa all’utilizzo dell’attività, contatta il tuo rappresentante di Adobe.

## Casi d&#39;uso {#use-cases}

Esistono due casi d’uso principali di [!UICONTROL Activity Usage Report]:

* **Tracciamento dell’utilizzo effettivo dell’attività dell’istanza rispetto all’impegno** di utilizzo dell’attività: La maggior parte dei clienti dispone di un impegno di attività stimato mensilmente per istanza di Audience Manager, che viene quindi cumulato in un impegno di attività annuale in tutte le istanze. Anche se questo rapporto non è un rapporto di fatturazione, può fornire utili indicazioni sul fatto che stai superando l’utilizzo dell’attività impegnata.
* **Convalida per le modifiche** di implementazione: Se hai recentemente aggiornato l’implementazione, ad esempio l’impostazione dell’inoltro lato  [!DNL Adobe Analytics] server o la modifica delle impostazioni di chiamata al  [!DNL Adobe Target] server, questo rapporto può essere utile per verificare se il nuovo volume di attività è in linea con il volume di attività previsto.

## L&#39;uso dell&#39;identificazione [!UICONTROL Activity Usage Report] {#using}

Per visualizzare il [!UICONTROL Activity Usage Report], accedi al tuo account di Audience Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Quindi, utilizza il filtro **[!UICONTROL Reporting Interval]** per selezionare l&#39;intervallo di tempo per il quale generare il rapporto. Puoi scegliere tra 30, 60, 90 giorni o un intervallo di date personalizzato.

Una volta caricato il rapporto, puoi visualizzare una suddivisione del [!UICONTROL Activities] per il periodo selezionato.

[!UICONTROL Activities] definisci il totale aggregato di tutte le interazioni in sito e fuori sito con Audience Manager, suddiviso nelle seguenti categorie:

* **[!UICONTROL Server Calls]**: Qualsiasi evento di raccolta o recupero dati inviato ad Audience Manager da siti web, server, e-mail, applicazioni mobili o altri sistemi.
* **[!UICONTROL Pixel Calls](precedentemente noto come  [!UICONTROL Impression Server Calls])**: Dati raccolti dagli annunci (come il volume di impression da una piattaforma di targeting) o chiamate di impression via e-mail effettuate ad Audience Manager. Questi richiedono la presenza del parametro `d_event` nella stringa query.
* **[!UICONTROL On-Boarded Records]**: Record univoci acquisiti dal sistema di gestione delle relazioni con i clienti (CRM) o da altri file di dati offline, come record del call center, ID dispositivo e feed di dati personalizzati da fornitori di dati esterni.
* **[!UICONTROL Log File Records]**: Record univoci da file di registro acquisiti in Audience Manager da una piattaforma di targeting.

>[!NOTE]
>
>Un record univoco definisce ogni singolo record di dati in un file memorizzato da un Adobe per conto di un cliente Audience Manager.

Inoltre, puoi utilizzare i tipi di grafico [!UICONTROL Activity Usage Trends] per passare da un tipo di grafico all’altro.

![aur-ui-graph](assets/aur-ui-graphs.png)

Puoi anche passare il cursore su una data specifica nella timeline per visualizzare l’utilizzo dettagliato di tale data.

![passaggio del mouse](assets/aur-hover.png)

## Esportazione di [!UICONTROL Activity Usage Reports] {#export}

Per una migliore panoramica del livello di utilizzo dell’attività di Audience Manager, puoi esportare il file [!UICONTROL Activity Usage Report] in base al tipo di record che desideri includere.

![aur-export](assets/aur-export.png)

I rapporti **[!UICONTROL Onboarded Records Breakdown]** e **[!UICONTROL Onsite Server Calls Breakdown]** forniscono informazioni dettagliate sui dati di origine disponibili per queste attività. Il volume attribuito a queste suddivisioni è basato sull’implementazione.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Questo rapporto contiene record caricati suddivisi per origine dati.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Questo rapporto contiene un raggruppamento delle chiamate server da tre origini: [!UICONTROL Analytics], [!UICONTROL Target] e [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Si tratta di chiamate server fatturabili passate da tutte  [!UICONTROL Adobe Analytics] le istanze all’Audience Manager, incluso l’inoltro lato server. Le chiamate server secondarie o le chiamate server duplicate (come nel caso dell&#39;inoltro lato server da più suite di rapporti) non sono attività fatturabili, pertanto non sono incluse in questa suddivisione.
* **[!UICONTROL Target]**: Si tratta di chiamate lato server da  [!UICONTROL Adobe Target] ad Audience Manager, per recuperare i dati dei segmenti di Audience Manager come parte di un’integrazione server-to-server.
* **[!UICONTROL Other]**: Include le chiamate da qualsiasi altro sito web o sistema (siti partner, chiamate server dirette, ecc.), browser mobile/chiamate app tramite  [!DNL SDK],  [!DNL DIL], chiamate evento e  [!DNL DCS] chiamate. Sono incluse anche le chiamate da [!DNL Target] se impostate come integrazione dei cookie (anziché da server a server).
