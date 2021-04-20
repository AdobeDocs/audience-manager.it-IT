---
description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-title: Configurare una destinazione di Analytics
solution: Audience Manager
title: Configurare una destinazione di Analytics
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 9%

---

# Configurare una destinazione di Analytics

## Requisiti {#requirements}

Per configurare una destinazione Analytics, l’utente Audience Manager deve disporre delle autorizzazioni di amministratore. Consulta [Creare utenti](/help/using/features/administration/administration-overview.md#create-users) nella Guida all&#39;amministrazione. Tieni presente che disporre dell’ `CREATE_DESTINATIONS` [autorizzazione per i caratteri jolly](/help/using/features/administration/administration-overview.md#wild-card-permissions) non è sufficiente per creare le destinazioni Analytics.
Per ulteriori requisiti, consulta Prerequisiti in [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Destinazioni Analytics predefinite e nuove destinazioni Analytics

| Tipo di destinazione di Analytics | Descrizione |
|---|---|
| impostazione predefinita | Il nome di questa destinazione predefinita è &quot;Adobe Analytics&quot;, che puoi modificare. Gli ID suite di rapporti mappati vengono visualizzati nell’archivio cartelle per le caratteristiche e i segmenti di Audience Manager. <br>  Audience Manager crea automaticamente una destinazione se il tuo account dispone di:  <br>  <ul><li>Soddisfare i requisiti descritti nella documentazione [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) .</li><li>Una [suite di rapporti](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) in Analytics.</li><li>[Mappata una suite di rapporti a un&#39;organizzazione](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).</li></ul> |
| Nuovo | Per creare nuove destinazioni di Analytics, vai a Audience Data > Destinazioni > Crea nuova destinazione e segui i passaggi per ciascuna sezione descritta di seguito. |

## Passaggio 1: Informazioni di base

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione di Analytics. Per completare questa sezione:

1. Fare clic su **Informazioni di base** per esporre i controlli.
2. Denomina la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivi la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. *(Facoltativo)* Nell’elenco  **** Piattaforma, lascia l’impostazione predefinita su  **Tutto**. Attualmente, queste opzioni non fanno nulla. Sono progettati per supportare funzioni che possono essere aggiunte in un secondo momento.
5. Nell&#39;elenco **Categoria**, selezionare **Adobe Experience Cloud**.
6. Nell&#39;elenco **Tipo**, selezionare **Adobe Analytics**.
7. Fai clic su **Salva** per passare alle impostazioni di configurazione oppure fai clic su **Etichette di esportazione dati** per applicare i controlli di esportazione alla destinazione.

>[!NOTE]
>
>Per una destinazione Analytics, le caselle di controllo **Mappatura automatica della destinazione di riempimento** e **ID segmento** sono selezionate per impostazione predefinita. Non è possibile modificare queste impostazioni.

![informazioni di base](assets/basicinformation.png)

## Passaggio 2: Configurare i controlli di esportazione dei dati

Questa sezione contiene opzioni che applicano [Controlli sull&#39;esportazione dei dati](/help/using/features/data-export-controls.md) a una destinazione Analytics. Ignora questo passaggio se non utilizzi i controlli di esportazione dati. Per completare questa sezione:

1. Fare clic su **Controlli sull&#39;esportazione dei dati** per esporre i controlli.
1. Seleziona un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (vedi [Aggiungi etichette di esportazione dei dati a una destinazione](/help/using/features/destinations/add-data-export-labels.md) ). Per le destinazioni di Analytics, la casella di controllo PII è selezionata per impostazione predefinita.
1. Fai clic su **Salva**.

![controlli all&#39;esportazione](assets/exportControls.png)

## Passaggio 3: Mappa suite di rapporti

Nella sezione Configurazione sono elencate le suite di rapporti di Analytics che sono state abilitate per l’inoltro lato server. Se disponi di più destinazioni Analytics, le suite di rapporti assegnate a queste destinazioni si escluderanno a vicenda e saranno applicate in base all’Audience Manager. Per completare questa sezione:

1. Fare clic su **Configurazione** per esporre i controlli.
1. Seleziona una (o più) suite di rapporti a cui desideri inviare i segmenti.
1. Fai clic su **Salva**.

![suite di rapporti](assets/reportSuites.png)

## Passaggio 4: Mappature dei segmenti

Questa sezione fornisce opzioni che consentono di mappare i segmenti automaticamente o manualmente.

| Opzione di mappatura | Descrizione |
|---|---|
| Mappa automaticamente tutti i segmenti attuali e futuri | Selezionata per impostazione predefinita, questa funzione invia ad Analytics tutti i segmenti per i quali un visitatore si qualifica, in base all’hit. <br>  Se un visitatore appartiene a più di 150 segmenti di Audience Manager su un singolo hit, solo i 150 segmenti qualificati più di recente vengono inviati ad Analytics, mentre il rimanente elenco viene troncato. Viene inviato un flag aggiuntivo ad Analytics per indicare che l’elenco dei segmenti è stato troncato. Questa azione viene visualizzata come &quot;Limite pubblico raggiunto&quot; nella dimensione Nome pubblico e come &quot;1&quot; nella dimensione ID pubblico. Per ulteriori informazioni, consulta le [Domande frequenti](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) . <br>  Inoltre, questa opzione influisce sulla disponibilità di destinazione nel  [Generatore di segmenti](/help/using/features/segments/segment-builder.md). Ad esempio, se un segmento viene mappato automaticamente a una destinazione Analytics, tale destinazione non è disponibile per la selezione nella sezione [mappature di destinazione](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) del Generatore di segmenti. La destinazione Analytics appare in grigio e mostra &quot;Analytics&quot; nella colonna Tipo del browser Destinazione. |
| Mappare manualmente i segmenti | Questa opzione espone i controlli di ricerca e navigazione che ti consentono di scegliere quali segmenti inviare ad Analytics. <br>  Per cercare un segmento:  <br>  <ol><li>Digita il nome o l’ID del segmento nel campo di ricerca.</li><li>Fai clic su <b>Aggiungi.</b></li><li>Continua a cercare e aggiungere segmenti o fai clic su <b>Fine</b>.</li></ol><br>  Per cercare un segmento: <ol><li>Fai clic su <b>Sfoglia tutti i segmenti</b>. Mostra un elenco dei segmenti disponibili.</li><li>Dall’elenco, seleziona la casella di controllo del segmento da utilizzare e fai clic su <b>Aggiungi segmenti selezionati</b>.</li><li>Fai clic su <b>Salva</b> nella finestra Aggiungi mappature. Non puoi modificare le mappature, le date di inizio o di fine durante la versione beta.</li><li>Continua a sfogliare e aggiungere segmenti o fai clic su <b>Fine</b>.</li></ol> ![mapsegmenti](assets/mapSegments.png) |

## Passaggi successivi

Dopo aver creato e salvato una destinazione, puoi lavorare con tali dati in Analytics. Tuttavia, potrebbero essere necessarie alcune ore prima che i dati siano disponibili nelle suite di rapporti selezionate. Consulta [Utilizzare i dati sul pubblico in Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
