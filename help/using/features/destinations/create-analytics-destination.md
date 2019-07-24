---
description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-title: Configurare una destinazione di Analytics
solution: Audience Manager
title: Configurare una destinazione di Analytics
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# Configurare una destinazione di Analytics

## Requisiti {#requirements}

See [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Destinazioni di Analytics predefinite e nuove destinazioni di Analytics

| Tipo di destinazione di Analytics | Descrizione |
|---|---|
| impostazione predefinita | Il nome di questa destinazione predefinita è "Adobe Analytics", che potete modificare. Gli ID di suite di rapporti mappati vengono visualizzati nella memorizzazione delle cartelle per le caratteristiche e i segmenti di Audience Manager. <br>Audience Manager crea automaticamente una destinazione se l'account ha: <br> <ul><li>Met the requirements described in the [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) documentation.</li><li>A [report suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[È stata mappata una suite di rapporti su un'organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Nuovo | Per creare nuove destinazioni Analytics, vai a Audience Data &gt; Destinazioni &gt; Crea nuova destinazione e segui i passaggi descritti di seguito. |

## Passaggio 1: Fornire informazioni di base

Questa sezione contiene campi e opzioni che avviano il processo di creazione di destinazione di Analytics. Per completare questa sezione:

1. Click **Basic Information** to expose the controls.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivete la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. *(Facoltativo)* Nell'elenco **Piattaforma** , lasciate il set predefinito **su Tutti**. Al momento, queste opzioni non eseguono alcuna operazione. Sono progettati per supportare funzioni che possono essere aggiunte in un secondo momento.
5. In the **Category** list, select **Adobe Experience Cloud**.
6. In the **Type** list, select **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. Non potete modificare queste impostazioni.

![informazioni di base](assets/basicinformation.png)

## Passaggio 2: Configurare i controlli sull'esportazione dei dati

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Ignorate questo passaggio se non utilizzate i controlli di esportazione dei dati. Per completare questa sezione:

1. Click **Data Export Controls** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). Per le destinazioni di Analytics, la casella di controllo PII è selezionata per impostazione predefinita.
3. Fai clic su **Salva**.

![exportcontrolli](assets/exportControls.png)

## Passaggio 3: Mappa suite di rapporti

Nella sezione Configurazione sono elencate le suite di rapporti di Analytics abilitate per l'inoltro lato server. Se hai più destinazioni Analytics, le suite di rapporti assegnate a queste destinazioni saranno mutualmente esclusive e applicate da Audience Manager. Per completare questa sezione:

1. Click **Configuration** to expose the controls.
2. Seleziona una o più suite di rapporti a cui vuoi inviare segmenti.
3. Fai clic su **Salva**.

![suite di rapporti](assets/reportSuites.png)

## Passaggio 4: Mappature segmento

Questa sezione fornisce opzioni che consentono di mappare i segmenti automaticamente o manualmente.

| Opzione di mapping | Descrizione |
|---|---|
| Mappa automaticamente tutti i segmenti correnti e futuri | Selezionato per impostazione predefinita, questa funzione invia tutti i segmenti che un visitatore qualifica, su base giornaliera, ad Analytics. <br>Se un visitatore appartiene a più di 150 segmenti Audience Manager su un unico hit, vengono inviati ad Analytics solo i 150 segmenti idonei più recenti, mentre l'elenco rimanente viene troncato. Ad Analytics viene inviato un flag aggiuntivo che indica che l'elenco dei segmenti è stato troncato. Questa azione viene visualizzata come «Limite pubblico raggiunto» nella dimensione Nome pubblico e «1» nella dimensione ID audience. See the [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) for details. <br>Inoltre, questa opzione influisce sulla disponibilità di destinazione in [Segment Builder](/help/using/features/segments/segment-builder.md)(Generatore segmenti). For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. La destinazione Analisi appare disattivata e mostra "Analytics" nella colonna Tipo del browser Destinazione. |
| Mappare manualmente i segmenti | Questa opzione espone i controlli di ricerca e ricerca che consentono di scegliere i segmenti da inviare ad Analytics. <br>Per cercare un segmento: <br> <ol><li>Digita il nome o l'ID del segmento nel campo di ricerca.</li><li>Fai clic su <b>Aggiungi.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>Per cercare un segmento: <ol><li>Click <b>Browse all segments</b>. Viene visualizzato un elenco dei segmenti disponibili.</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. Non puoi cambiare le mappature, l'inizio o le date di fine durante la versione beta.</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> |

![mapsegments](assets/mapSegments.png)

## Passaggi successivi

Dopo aver creato e salvato una destinazione, puoi lavorare con quei dati in Analytics. Tuttavia, potrebbero essere necessarie alcune ore prima che i dati siano disponibili nelle suite di rapporti selezionate. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).



