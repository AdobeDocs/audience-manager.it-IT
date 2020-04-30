---
description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-description: Audience Analytics consente di inviare segmenti Audience Manager ad Analytics. Per utilizzare questa funzione è necessario creare una destinazione Analytics e mappare i segmenti su tale destinazione in Audience Manager.
seo-title: Configurare una destinazione Analytics
solution: Audience Manager
title: Configurare una destinazione Analytics
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Configurare una destinazione Analytics

## Requisiti {#requirements}

Per configurare una destinazione Analytics, l&#39;utente Audience Manager deve disporre delle autorizzazioni di amministratore. Consultate [Creare utenti](/help/using/features/administration/administration-overview.md#create-users) nella guida all&#39;amministrazione. Tenere presente che disporre dell&#39;autorizzazione `CREATE_DESTINATIONS` per il [](/help/using/features/administration/administration-overview.md#wild-card-permissions) carattere jolly non è sufficiente per creare le destinazioni Analytics.
Per ulteriori requisiti, consulta Prerequisiti in [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Destinazioni Analytics predefinite e nuove destinazioni Analytics

| Tipo di destinazione Analytics | Descrizione |
|---|---|
| impostazione predefinita | Il nome di questa destinazione predefinita è &quot;Adobe Analytics&quot;, che puoi modificare. Gli ID suite di rapporti mappati vengono visualizzati nell&#39;archivio delle cartelle per le caratteristiche e i segmenti di Audience Manager. <br>  Audience Manager crea automaticamente una destinazione se l&#39;account dispone di: <br>  <ul><li>Soddisfa i requisiti descritti nella documentazione di [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) .</li><li>Una suite [di](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) rapporti in Analytics.</li><li>[Mappata una suite di rapporti a un&#39;organizzazione](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).</li></ul> |
| Nuovo | Per creare nuove destinazioni Analytics, vai a Dati audience > Destinazioni > Crea nuova destinazione e segui i passaggi per ciascuna sezione descritta di seguito. |

## Passaggio 1: Informazioni di base

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione di Analytics. Per completare questa sezione:

1. Fate clic su Informazioni **di** base per esporre i controlli.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivere la destinazione. Una descrizione sintetica è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. *(Facoltativo)* Nell&#39;elenco **Piattaforma** , lasciare il valore predefinito impostato su **Tutto**. Attualmente, queste opzioni non fanno nulla. Sono progettati per supportare funzioni che possono essere aggiunte in un secondo momento.
5. Nell&#39;elenco **Categoria** , seleziona **Adobe Experience Cloud**.
6. Nell&#39;elenco **Tipo** , seleziona **Adobe Analytics**.
7. Fare clic su **Salva** per accedere alle impostazioni di configurazione o su Etichette **esportazione** dati per applicare i controlli di esportazione alla destinazione.

>[!NOTE]
>
>Per una destinazione Analytics, la casella di controllo Mappatura **destinazione di riempimento** automatico e l&#39;opzione ID **** segmento sono selezionate per impostazione predefinita. Non è possibile modificare queste impostazioni.

![informazioni di base](assets/basicinformation.png)

## Passaggio 2: Configurare i controlli di esportazione dei dati

Questa sezione contiene opzioni che applicano i controlli [di esportazione dei](/help/using/features/data-export-controls.md) dati a una destinazione Analytics. Salta questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fate clic su Controlli **esportazione** dati per esporre i controlli.
1. Selezionare un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (vedere [Aggiungi etichette di esportazione dati a una destinazione](/help/using/features/destinations/add-data-export-labels.md) ). Per le destinazioni Analytics, la casella di controllo PII è selezionata per impostazione predefinita.
1. Fai clic su **Salva**.

![controlli di esportazione](assets/exportControls.png)

## Passaggio 3: Mappa suite di rapporti

Nella sezione Configurazione sono elencate le suite di rapporti di Analytics che sono state abilitate per l&#39;inoltro lato server. Se hai più destinazioni Analytics, le suite di rapporti assegnate a tali destinazioni si escluderanno a vicenda e saranno applicate da Audience Manager. Per completare questa sezione:

1. Fate clic su **Configurazione** per esporre i controlli.
1. Seleziona una (o più) suite di rapporti a cui vuoi inviare i segmenti.
1. Fai clic su **Salva**.

![reportsuites](assets/reportSuites.png)

## Passaggio 4: Mappature dei segmenti

Questa sezione offre opzioni che consentono di mappare i segmenti automaticamente o manualmente.

| Opzione di mapping | Descrizione |
|---|---|
| Mappa automaticamente tutti i segmenti attuali e futuri | Selezionata per impostazione predefinita, questa funzione invia ad Analytics tutti i segmenti per i quali un visitatore si qualifica, in base all’hit. <br>  Se un visitatore appartiene a più di 150 segmenti di Audience Manager su un singolo hit, vengono inviati ad Analytics solo i 150 segmenti qualificati più di recente, mentre il resto dell’elenco viene troncato. Viene inviato un flag aggiuntivo ad Analytics per indicare che l’elenco dei segmenti è stato troncato. Questa azione viene visualizzata come &quot;Limite pubblico raggiunto&quot; nella dimensione Nome pubblico e come &quot;1&quot; nella dimensione ID pubblico. Per informazioni dettagliate, consultate le [domande frequenti](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) . <br>  Inoltre, questa opzione influisce sulla disponibilità di destinazione in [Segment Builder](/help/using/features/segments/segment-builder.md). Ad esempio, se un segmento viene mappato automaticamente a una destinazione Analytics, tale destinazione non è disponibile per la selezione nella sezione Mappature [di](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) destinazione di Segment Builder. La destinazione Analytics viene visualizzata in grigio e viene visualizzata l&#39;opzione &quot;Analytics&quot; nella colonna Tipo del browser Destinazione. |
| Mappatura manuale dei segmenti | Questa opzione espone i controlli di ricerca e ricerca che consentono di scegliere quali segmenti inviare ad Analytics. <br>  Per cercare un segmento: <br>  <ol><li>Digita il nome del segmento o l’ID nel campo di ricerca.</li><li>Fai clic su <b>Aggiungi.</b></li><li>Continua a cercare e aggiungere segmenti o fai clic su <b>Fine</b>.</li></ol><br>  Per cercare un segmento: <ol><li>Fai clic su <b>Sfoglia tutti i segmenti</b>. Viene visualizzato un elenco di segmenti disponibili.</li><li>Dall’elenco, selezionate la casella di controllo del segmento da utilizzare e fate clic su <b>Aggiungi segmenti</b>selezionati.</li><li>Fate clic su <b>Salva</b> nella finestra Aggiungi mappature. Non puoi modificare le mappature, le date di inizio o di fine durante la versione beta.</li><li>Continua a cercare e aggiungere segmenti o fai clic su <b>Fine</b>.</li></ol> ![mapsegmenti](assets/mapSegments.png) |

## Passaggi successivi

Dopo aver creato e salvato una destinazione, puoi lavorare con tali dati in Analytics. Tuttavia, potrebbero essere necessarie alcune ore prima che i dati siano disponibili nelle suite di rapporti selezionate. See [Use the Audience Data in Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
