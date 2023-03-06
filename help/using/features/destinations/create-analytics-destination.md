---
description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Configurare una destinazione di Analytics
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 5%

---

# Configurare una destinazione di Analytics

## Requisiti {#requirements}

Per configurare una destinazione Analytics, l’utente Audience Manager deve disporre delle autorizzazioni di amministratore. Consulta [Crea utenti](/help/using/features/administration/administration-overview.md#create-users) nella Guida all’amministrazione. Tieni presente che avere `CREATE_DESTINATIONS` [autorizzazione caratteri jolly](/help/using/features/administration/administration-overview.md#wild-card-permissions) non è sufficiente per creare delle destinazioni Analytics.
Per ulteriori requisiti, consulta Prerequisiti in [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

## La destinazione Analytics predefinita e le nuove destinazioni Analytics

| Tipo di destinazione di Analytics | Descrizione |
|---|---|
| impostazione predefinita | Il nome di questa destinazione predefinita è &quot;Adobe Analytics&quot;, che puoi modificare. Gli ID delle suite di rapporti mappati vengono visualizzati nell’archiviazione delle cartelle per le caratteristiche e i segmenti Audienci Manager. <br>  In Audience Manager, viene creata automaticamente una destinazione se l’account presenta: <br>  <ul><li>Soddisfa i requisiti descritti nella [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) documentazione.</li><li>A [suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) in Analytics.</li></ul> |
| Nuovo | Per creare nuove destinazioni Analytics, vai a Dati pubblico > Destinazioni > Crea nuova destinazione e segui i passaggi per ciascuna sezione descritta di seguito. |

## Audience Manager di qualifiche dei segmenti in Adobe Analytics {#segment-qualifications}

Quando invii informazioni sui segmenti a una destinazione Analytics, Audience Manager invia solo i segmenti per i quali il visitatore è qualificato. Se un visitatore non si qualifica più per un segmento, queste informazioni sono _non_ inoltrato ad Adobe Analytics.

Ad esempio, considera le regole del segmento di seguito:

* Segmento A: caratteristica 1 E caratteristica 2
* Segmento B: caratteristica 1 E NON caratteristica 2

Nei rapporti di Analytics, un profilo può essere visualizzato come qualificato per entrambi i segmenti, anche se non si qualifica più per il segmento B.

## Passaggio 1: fornire informazioni di base

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione Analytics. Per completare questa sezione:

1. Clic **Informazioni di base** per esporre i controlli.
2. Denomina la destinazione. Evita abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivi la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. *(Facoltativo)* In **Piattaforma** , lasciare l&#39;impostazione predefinita su **Tutti**. Al momento, queste opzioni non funzionano. Sono progettate per supportare funzioni che possono essere aggiunte in un secondo momento.
5. In **Categoria** elenco, seleziona **Adobe Experience Cloud**.
6. In **Tipo** elenco, seleziona **Adobe Analytics**.
7. Clic **Salva** per passare alle impostazioni di configurazione o fare clic su **Etichette esportazione dati** per applicare i controlli sulle esportazioni alla destinazione.

>[!NOTE]
>
>Per una destinazione di Analytics, la **Mappatura destinazione riempimento automatico** e **ID segmento** sono selezionate per impostazione predefinita. Impossibile modificare queste impostazioni.

![informazioni di base](assets/basicinformation.png)

## Passaggio 2: configurare i controlli di esportazione dei dati

Questa sezione contiene le opzioni applicabili [Controlli sull’esportazione dei dati](/help/using/features/data-export-controls.md) a una destinazione Analytics. Ignora questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Clic **Controlli sull’esportazione dei dati** per esporre i controlli.
1. Selezionare un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (vedere [Aggiungere etichette di esportazione dei dati a una destinazione](/help/using/features/destinations/add-data-export-labels.md) ). Per le destinazioni di Analytics, la casella di controllo PII è selezionata per impostazione predefinita.
1. Fai clic su **Salva**.

![controlli esportazione](assets/exportControls.png)

## Passaggio 3: mappare le suite di rapporti

Nella sezione Configurazione sono elencate le suite di rapporti di Analytics abilitate per l’inoltro lato server. Se disponi di più destinazioni di Analytics, le suite di rapporti assegnate a tali destinazioni si escluderanno a vicenda e verranno applicate da Audience Manager. Per completare questa sezione:

1. Clic **Configurazione** per esporre i controlli.
1. Seleziona una (o più) suite di rapporti a cui desideri inviare i segmenti.
1. Fai clic su **Salva**.

![suite di rapporti](assets/reportSuites.png)

## Passaggio 4: mappature dei segmenti

In questa sezione sono disponibili opzioni che consentono di mappare i segmenti automaticamente o manualmente.

| Opzione di mappatura | Descrizione |
|---|---|
| Mappa automaticamente tutti i segmenti correnti e futuri | Selezionata per impostazione predefinita, questa funzione invia ad Analytics tutti i segmenti per i quali un visitatore si qualifica, in base all’hit. <br>  Se un visitatore appartiene a più di 150 segmenti di Audience Manager su un singolo hit, solo i 150 segmenti qualificati più di recente vengono inviati ad Analytics, mentre l’elenco rimanente viene troncato. Ad Analytics viene inviato un flag aggiuntivo che indica che l’elenco dei segmenti è stato troncato. Questa azione viene visualizzata come &quot;Limite di pubblico raggiunto&quot; nella dimensione Nome pubblico e &quot;1&quot; nella dimensione ID pubblico. Consulta la [Domande frequenti](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) per i dettagli. <br>  Inoltre, questa opzione influisce sulla disponibilità della destinazione in [Generatore di segmenti](/help/using/features/segments/segment-builder.md). Ad esempio, se un segmento viene mappato automaticamente a una destinazione Analytics, tale destinazione non è disponibile per la selezione nel [mappature di destinazione](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) sezione di Segment Builder. La destinazione Analytics appare in grigio e mostra &quot;Analytics&quot; nella colonna Tipo del browser Destinazioni. |
| Mappare manualmente i segmenti | Questa opzione espone i controlli di ricerca e navigazione che consentono di scegliere quali segmenti inviare ad Analytics. <br>  Per cercare un segmento: <br>  <ol><li>Digita il nome o l’ID del segmento nel campo di ricerca.</li><li>Fai clic su <b>Aggiungi.</b></li><li>Continua a cercare e aggiungere segmenti o fai clic su <b>Fine</b>.</li></ol><br>  Per cercare un segmento: <ol><li>Clic <b>Sfoglia tutti i segmenti</b>. Questo espone un elenco dei segmenti disponibili.</li><li>Dall’elenco, seleziona la casella di controllo del segmento da utilizzare e fai clic su <b>Aggiungi segmenti selezionati</b>.</li><li>Clic <b>Salva</b> nella finestra Aggiungi mappature. Non puoi modificare le mappature, le date di inizio o di fine durante il rilascio della versione beta.</li><li>Continua a sfogliare e aggiungere segmenti o fai clic su <b>Fine</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Passaggi successivi

Dopo aver creato e salvato una destinazione, puoi utilizzarla in Analytics. Tuttavia, possono essere necessarie alcune ore prima che i dati siano disponibili nelle suite di rapporti selezionate. Consulta [Utilizzare i dati sul pubblico in Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
