---
description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-title: ' Configurare una destinazione Analytics'
solution: Audience Manager
title: Configurare una destinazione Analytics
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Configurare una destinazione Analytics

## Requisiti {#requirements}

Consulta [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Destinazioni Analytics predefinite e nuove destinazioni Analytics

| Tipo di destinazione Analytics | Descrizione |
|---|---|
| impostazione predefinita | Il nome di questa destinazione predefinita è "Adobe Analytics", che puoi modificare. Gli ID suite di rapporti mappati vengono visualizzati nell'archivio delle cartelle per le caratteristiche e i segmenti di Audience Manager. <br>  Audience Manager crea automaticamente una destinazione se l'account dispone di: <br>  <ul><li>Soddisfa i requisiti descritti nella documentazione di [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) .</li><li>Una suite [di](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) rapporti in Analytics.</li><li>[Mappata una suite di rapporti a un'organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Nuovo | Per creare nuove destinazioni Analytics, vai a Dati audience &gt; Destinazioni &gt; Crea nuova destinazione e segui i passaggi per ciascuna sezione descritta di seguito. |

## Passaggio 1: Informazioni di base

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione di Analytics. Per completare questa sezione:

1. Fate clic su Informazioni **di** base per esporre i controlli.
1. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
1. *(Facoltativo)* Descrivere la destinazione. Una descrizione sintetica è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
1. *(Facoltativo)* Nell'elenco **Piattaforma** , lasciare il valore predefinito impostato su **Tutto**. Attualmente, queste opzioni non fanno nulla. Sono progettati per supportare funzioni che possono essere aggiunte in un secondo momento.
1. Nell'elenco **Categoria** , seleziona **Adobe Experience Cloud**.
1. Nell'elenco **Tipo** , seleziona **Adobe Analytics**.
1. Fare clic su **Salva** per accedere alle impostazioni di configurazione o su Etichette **esportazione** dati per applicare i controlli di esportazione alla destinazione.

>[!NOTE]
>
>Per una destinazione Analytics, la casella di controllo Mappatura **destinazione di riempimento** automatico e l'opzione ID **** segmento sono selezionate per impostazione predefinita. Non potete modificare queste impostazioni.

![informazioni di base](assets/basicinformation.png)

## Passaggio 2: Configurare i controlli di esportazione dei dati

Questa sezione contiene opzioni che applicano i controlli [di esportazione dei](/help/using/features/data-export-controls.md) dati a una destinazione Analytics. Salta questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fate clic su Controlli **esportazione** dati per esporre i controlli.
1. Selezionare un'etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (vedere [Aggiungi etichette di esportazione dati a una destinazione](/help/using/features/destinations/add-data-export-labels.md) ). Per le destinazioni Analytics, la casella di controllo PII è selezionata per impostazione predefinita.
1. Fai clic su **Salva**.

![controlli di esportazione](assets/exportControls.png)

## Passaggio 3: Mappa suite di rapporti

Nella sezione Configurazione sono elencate le suite di rapporti di Analytics che sono state abilitate per l'inoltro lato server. Se hai più destinazioni Analytics, le suite di rapporti assegnate a tali destinazioni si escluderanno a vicenda e saranno applicate da Audience Manager. Per completare questa sezione:

1. Fate clic su **Configurazione** per esporre i controlli.
1. Seleziona una (o più) suite di rapporti a cui vuoi inviare i segmenti.
1. Fai clic su **Salva**.

![reportsuites](assets/reportSuites.png)

## Passaggio 4: Mappature segmenti

Questa sezione offre opzioni che consentono di mappare i segmenti automaticamente o manualmente.

| Opzione mapping | Descrizione |
|---|---|
| Mappa automaticamente tutti i segmenti attuali e futuri | Selezionata per impostazione predefinita, questa funzione invia ad Analytics tutti i segmenti per i quali un visitatore si qualifica, in base all’hit. <br>  Se un visitatore appartiene a più di 150 segmenti di Audience Manager per un singolo hit, vengono inviati ad Analytics solo i 150 segmenti qualificati più di recente, mentre il resto dell’elenco viene troncato. Viene inviato un flag aggiuntivo ad Analytics per indicare che l’elenco dei segmenti è stato troncato. Questa azione viene visualizzata come "Limite pubblico raggiunto" nella dimensione Nome pubblico e come "1" nella dimensione ID pubblico. Per informazioni dettagliate, consultate le [domande frequenti](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) . <br>  Inoltre, questa opzione influisce sulla disponibilità di destinazione in [Segment Builder](/help/using/features/segments/segment-builder.md). Ad esempio, se un segmento viene mappato automaticamente a una destinazione Analytics, tale destinazione non è disponibile per la selezione nella sezione Mappature [di](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) destinazione di Segment Builder. La destinazione Analytics viene visualizzata in grigio e viene visualizzata l'opzione "Analytics" nella colonna Tipo del browser Destinazione. |
| Mappatura manuale dei segmenti | Questa opzione espone i controlli di ricerca e ricerca che consentono di scegliere quali segmenti inviare ad Analytics. <br>  Per cercare un segmento: <br>  <ol><li>Digita il nome del segmento o l’ID nel campo di ricerca.</li><li>Fai clic su <b>Aggiungi.</b></li><li>Continua a cercare e aggiungere segmenti o fai clic su <b>Fine</b>.</li></ol><br>  Per cercare un segmento: <ol><li>Fai clic su <b>Sfoglia tutti i segmenti</b>. Viene visualizzato un elenco di segmenti disponibili.</li><li>Dall’elenco, selezionate la casella di controllo del segmento da utilizzare e fate clic su <b>Aggiungi segmenti</b>selezionati.</li><li>Fate clic su <b>Salva</b> nella finestra Aggiungi mappature. Non puoi modificare le mappature, le date di inizio o di fine durante la versione beta.</li><li>Continua a cercare e aggiungere segmenti o fai clic su <b>Fine</b>.</li></ol> ![mapsegmenti](assets/mapSegments.png) |

## Passaggi successivi

Dopo aver creato e salvato una destinazione, puoi lavorare con tali dati in Analytics. Tuttavia, potrebbero essere necessarie alcune ore prima che i dati siano disponibili nelle suite di rapporti selezionate. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
