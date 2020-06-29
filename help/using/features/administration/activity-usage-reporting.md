---
description: La funzione di generazione dei rapporti sull'uso dell'attività consente di visualizzare e monitorare l'utilizzo dell'attività per l'istanza Audience Manager , in modo da poter confrontare l'utilizzo effettivo con l'impegno contrattuale.
keywords: activity, usage, reporting, commitment
seo-description: La funzione di generazione dei rapporti sull'uso dell'attività consente di visualizzare e monitorare l'utilizzo dell'attività per l'istanza Audience Manager , in modo da poter confrontare l'utilizzo effettivo con l'impegno contrattuale.
seo-title: Report sull'utilizzo dell'attività
solution: Audience Manager
title: Report sull'utilizzo dell'attività
topic: Activity Usage Reporting
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---


# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Panoramica {#overview}

Questo [!UICONTROL Activity Usage Report] consente di visualizzare e monitorare l&#39;utilizzo dell&#39;attività dell&#39;istanza Audience Manager , fornendo un&#39;idea chiara di come l&#39;utilizzo dell&#39;attività rispetto all&#39;impegno contrattuale.

Inoltre, puoi scaricare il file [!UICONTROL Activity Usage Report] ogni volta che ti serve, per la conservazione dei record e l&#39;analisi personalizzata.

## Considerazioni {#considerations}

L’ [!UICONTROL Activity Usage Report] opzione è disponibile per tutti  utenti Audience Manager con privilegi di [amministratore](edit-account-settings.md).

>[!IMPORTANT]
>
>Vengono [!UICONTROL Activity Usage Report] visualizzate le statistiche di utilizzo dell&#39;attività dell&#39;istanza di Audience Manager . Per qualsiasi richiesta di fatturazione relativa all&#39;utilizzo dell&#39;attività, contattate il vostro rappresentante Adobe.

## Casi d&#39;uso {#use-cases}

Esistono due casi d’uso principali di [!UICONTROL Activity Usage Report]:

* **Tracciamento dell’utilizzo effettivo dell’attività dell’istanza rispetto all’impegno** di utilizzo dell’attività: La maggior parte dei clienti ha un impegno di attività stimato mensilmente per &#39;istanza di Audience Manager, che viene poi cumulato in un impegno di attività annuale in tutti i casi. Anche se questo rapporto non è un rapporto di fatturazione, può fornire utili indicazioni sul fatto che si stia superando l&#39;utilizzo dell&#39;attività impegnata.
* **Convalida per le modifiche** di implementazione: Se avete aggiornato di recente l&#39;implementazione, ad esempio impostando l&#39;inoltro lato [!DNL Adobe Analytics] server o modificando le impostazioni delle chiamate al [!DNL Adobe Target] server, questo rapporto può essere utile per verificare se il nuovo volume di attività è in linea con il volume di attività previsto.

## L&#39;uso dell&#39;identificazione [!UICONTROL Activity Usage Report] {#using}

Per visualizzare il [!UICONTROL Activity Usage Report]collegamento, accedete al vostro account Audience Manager  e andate a **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Quindi, utilizzate il **[!UICONTROL Reporting Interval]** filtro per selezionare l&#39;intervallo di tempo per il quale generare il rapporto. Puoi scegliere tra 30, 60, 90 giorni o un intervallo di date personalizzato.

Una volta caricato il rapporto, potete visualizzare una suddivisione del periodo [!UICONTROL Activities] selezionato.

[!UICONTROL Activities] definire il totale complessivo di tutte le interazioni onsite e offsite con  Audience Manager, suddivise nelle seguenti categorie:

* **[!UICONTROL Server Calls]**: Qualsiasi evento di raccolta o recupero dei dati inviato a  Audience Manager da siti Web, server, e-mail, applicazioni mobili o altri sistemi.
* **[!UICONTROL Pixel Calls](precedentemente noto come[!UICONTROL Impression Server Calls])**: Dati raccolti da annunci (come volume di impression da una piattaforma di targeting) o chiamate di impression e-mail effettuate a  Audience Manager. Questi richiedono la presenza del`d_event`parametro nella stringa di query.
* **[!UICONTROL On-Boarded Records]**: Record univoci acquisiti dal sistema CRM (Customer Relationship Management System) o da altri file di dati offline, come record del call center, ID dispositivo e feed di dati personalizzati da fornitori di dati esterni.
* **[!UICONTROL Log File Records]**: Record univoci dai file di registro trasferiti  Audience Manager da una piattaforma di destinazione.

>[!NOTE]
>
>Un record univoco definisce ciascun record singolo di dati in un file memorizzato da Adobe per conto di un cliente Audience Manager .

Inoltre, potete usare i tipi di [!UICONTROL Activity Usage Trends] grafico per passare da un tipo di grafico all’altro.

![aur-ui-graph](assets/aur-ui-graphs.png)

Puoi anche passare il cursore su una data specifica nella timeline per visualizzare l’utilizzo dettagliato di tale data.

![passaggio del mouse](assets/aur-hover.png)

## Esportazione [!UICONTROL Activity Usage Reports] {#export}

Per una migliore panoramica del livello di utilizzo  attività Audience Manager, potete esportare i record [!UICONTROL Activity Usage Report] in base al tipo di record da includere.

![aur-export](assets/aur-export.png)

I **[!UICONTROL Onboarded Records Breakdown]** rapporti e **[!UICONTROL Onsite Server Calls Breakdown]** le informazioni più dettagliate sui dati di origine disponibili per queste attività. Il volume attribuito a queste suddivisioni è basato sull&#39;implementazione.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Questo rapporto contiene record caricati suddivisi per origine dati.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Questo rapporto contiene una suddivisione delle chiamate server da tre origini: [!UICONTROL Analytics], [!UICONTROL Target]e [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Si tratta di chiamate server fatturabili passate da tutte [!UICONTROL Adobe Analytics] le istanze a  Audience Manager, incluso l&#39;inoltro lato server. Le chiamate server secondarie o le chiamate server duplicate (come nel caso dell&#39;inoltro lato server da più suite di rapporti) non sono attività fatturabili, pertanto non sono incluse in questa suddivisione.
* **[!UICONTROL Target]**: Si tratta di chiamate lato server da [!UICONTROL Adobe Target] a  Audience Manager, per recuperare  dati del segmento Audience Manager come parte di un&#39;integrazione tra server.
* **[!UICONTROL Other]**: Include le chiamate da qualsiasi altro sito Web o sistema (siti partner, chiamate server dirette, ecc.), browser mobile/chiamate app tramite [!DNL SDK], [!DNL DIL], chiamate evento e [!DNL DCS] chiamate. Include anche le chiamate da [!DNL Target] se configurate come integrazione dei cookie (anziché da server a server).
