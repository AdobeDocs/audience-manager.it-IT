---
description: Descrive come creare segmenti con il Generatore di segmenti.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Generatore di segmenti
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Descrive i passaggi obbligatori e facoltativi per la creazione di un segmento in [!UICONTROL Segment Builder].

## Dimostrazione video

Per iniziare, guarda [Video sulla creazione di segmenti in un Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). Il video illustra il processo di creazione dei segmenti. Per ulteriori informazioni, consulta le sezioni seguenti.

## Creare un [!UICONTROL Segment] {#create-segment}

### Sezione Generatore di segmenti

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] è costituito da 3 sezioni separate: [!UICONTROL Basic Information], [!UICONTROL Traits], e [!UICONTROL Destinations Mapping]. Per creare un [!UICONTROL segment], compila i campi obbligatori nella sezione [!UICONTROL Basic Information] e [!UICONTROL Traits] sezioni. [!UICONTROL Destinations Mapping] Le impostazioni sono facoltative. Per ulteriori informazioni, consulta le istruzioni di seguito.

1. In [Informazioni di base](../../features/segments/segment-builder.md#segment-builder-controls-basics) sezione:

   ![create-segment](assets/create-segment.png)

   * Denomina il [!UICONTROL segment]. La lunghezza massima di un [!UICONTROL segment] il nome è composto da 255 caratteri.
   * Imposta il [!UICONTROL segment] stato (il valore predefinito è attivo).
   * Scegli un [!UICONTROL data source]. Utilizza il primo menu a discesa per filtrare tra gli Audienci Manager [!UICONTROL data sources], suite di rapporti di Adobe Analytics o entrambe. Quindi, utilizza il secondo menu a discesa per scegliere il [!UICONTROL data source]. Se non utilizzi le suite di rapporti di Adobe Analytics, il [!UICONTROL data source] il selettore di tipo è disattivato e l&#39;impostazione predefinita prevede solo l&#39;Audience Manager delle origini dati.
   * Seleziona un [!UICONTROL profile merge rule] da utilizzare per [!UICONTROL segment] qualificazione.
   * Assegna la [!UICONTROL segment] in una cartella di archiviazione.

1. In [Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits) sezione:
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Cerca [!UICONTROL trait] desideri aggiungere a un segmento e fai clic su **[!UICONTROL Add Trait]**. Aggiungi un altro [!UICONTROL trait] per creare un [!UICONTROL trait] gruppo.
   * Visualizza il [!UICONTROL Advanced Search] modale facendo clic su **[!UICONTROL Browse All Traits]**. Cerca [!UICONTROL traits] per nome, ID, descrizione o [!UICONTROL data source]. Durante la ricerca, fai clic su una cartella per limitare i risultati a tale cartella e alle relative sottocartelle. Puoi anche filtrare [!UICONTROL traits] da [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], e [!UICONTROL Algorithmic]) o tipo di popolazione ([ID dispositivo](../../reference/ids-in-aam.md) e [ID multi-dispositivo](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Lettura [consigli sulle caratteristiche](trait-recommendations.md) durante la creazione di [!UICONTROL segment].
   * Fai clic e trascina [!UICONTROL traits] per creare gruppi separati.
   * Passaggio del mouse tra gruppi per impostare relazioni con un valore booleano [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] valori.
   * Passa il puntatore sull&#39;icona dell&#39;orologio per aggiungere [attualità e frequenza](../../features/segments/recency-and-frequency.md) regole per [!UICONTROL trait].
   * Visualizzare i dati di popolazione del segmento durante l’aggiunta o la rimozione [!UICONTROL traits]. Clic **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati. Ulteriori informazioni su [dati sulla popolazione del segmento](../../features/segments/segment-builder-data.md#segment-populations) nel [!UICONTROL Segment Builder].
   * Clic **[!UICONTROL Save]** al termine.

1. *(Facoltativo)* Mappa a [!UICONTROL segment] a un [!UICONTROL destination] nel [Mappatura delle destinazioni](../../features/segments/segment-builder.md#segment-builder-controls-destinations) sezione:
   * Cerca [!UICONTROL destination] e fai clic su **[!UICONTROL Add Destination]**. Nota: [!UICONTROL destination] deve esistere già prima di poterlo aggiungere a una [!UICONTROL segment].
   * Clic **[!UICONTROL Save]** al termine.

Guarda il video seguente per uno sguardo dettagliato al funzionamento delle metriche tra dispositivi.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Controlli: [!UICONTROL Basic Information] Sezione {#segment-builder-controls-basics}

In entrata [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] Le impostazioni consentono di creare o modificare caratteristiche nuove o esistenti. Per creare un nuovo [!UICONTROL segment], fornisci un nome, un [!UICONTROL data source]e selezionare una cartella di archiviazione. Tutti gli altri campi sono facoltativi. Passare alla [!UICONTROL Traits] al termine.

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| Campo | Descrizione |
---------|----------
| **[!UICONTROL Name]** | Assegna al segmento un nome breve e logico che ne descriva la funzione o lo scopo. Evita abbreviazioni e caratteri speciali. La lunghezza massima del nome di un segmento è di 255 caratteri. |
| **[!UICONTROL Description]** | Un campo per informazioni descrittive aggiuntive sul segmento. |
| **[!UICONTROL Integration Code]** | Un campo per un ID definito dall’utente o per altre informazioni specifiche per l’azienda. |
| **[!UICONTROL Data Source]** | Associa il segmento a un provider di dati specifico. <br> Utilizza il primo menu a discesa per filtrare tra origini dati di Audience Manager, suite di rapporti di Adobe Analytics o entrambe. Quindi, utilizza il secondo menu a discesa per scegliere l’origine dati. <br> Se non utilizzi le suite di rapporti di Adobe Analytics, il selettore del tipo di origine dati è disattivato e per impostazione predefinita viene utilizzato solo l’Audience Manager delle origini dati. |
| **[!UICONTROL Profile Merge Rule]** | Seleziona la Regola di unione profili da utilizzare per la qualificazione dei segmenti. |
| **[!UICONTROL Status]** | Attiva o disattiva il segmento (attivo per impostazione predefinita). |
| **Archiviazione cartella** | Determina la cartella di archiviazione a cui appartiene il segmento. |

## [!UICONTROL Segment Builder] Controlli: [!UICONTROL Traits] Sezione {#segment-builder-controls-traits}

In entrata [!UICONTROL Segment Builder], il [!UICONTROL Traits] consente di gestire [!UICONTROL traits] in un [!UICONTROL segment], creare [!UICONTROL trait] e impostare i criteri di qualifica. Per aggiungere una [!UICONTROL trait] a un [!UICONTROL segment], digita il [!UICONTROL trait] nome nel campo di ricerca e fai clic su [!UICONTROL Add Trait]. Salva il [!UICONTROL trait] (se terminato) o passa a [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Prerequisiti:** Compila i campi obbligatori nella sezione [!UICONTROL Basic Information] sezione.

| Campo | Descrizione |
|--- |--- |
| **[!UICONTROL Basic View]** | Questa sezione fornisce controlli visivi che consentono di: <ul><li>Crea nuovo e gestisci esistente [!UICONTROL segments].</li><li>Rimuovi [!UICONTROL traits] da un [!UICONTROL segment].</li><li>Aggiungi fino a 50 (massimo) [!UICONTROL traits] a un [!UICONTROL segment].</li><li>Trascina [!UICONTROL traits] per creare nuovi gruppi.</li><li>Visualizza [!UICONTROL traits] e [!UICONTROL trait] gruppi in una [!UICONTROL segment].</li><li>Imposta i criteri di qualificazione con espressioni booleane, operatori di confronto e impostazioni di recency/frequenza.</li></ul> |
| **[!UICONTROL Code View]** | Apre un ambiente di sviluppo che consente di creare e gestire [!UICONTROL traits], i gruppi e i requisiti di qualifica con codice anziché con l’interfaccia visiva. La vista Codice è utile se [!UICONTROL segments]: <ul><li>Contenere più di 50 [!UICONTROL traits] in un singolo utente [!UICONTROL segment]. Nota: [!UICONTROL Segments] sono limitati a 5000 [!UICONTROL traits] (massimo).</li><li>Contengono molti [!UICONTROL trait] gruppi.</li><li>Avere requisiti di qualifica complessi.</li></ul> |
| Cerca | Ti aiuta a trovare [!UICONTROL traits] per aggiungere a una [!UICONTROL segment]. |
| Consigli | Ottieni consigli live per elementi simili [!UICONTROL traits], dalla prima parte [!UICONTROL traits] e [!UICONTROL Audience Marketplace] feed di dati a cui sei abbonato. Aggiungi questi consigli alla [!UICONTROL segment] per espandere il pubblico. Ulteriori informazioni in [Recommendations delle caratteristiche](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Ottieni consigli live per elementi simili [!UICONTROL traits], da [!UICONTROL Audience Marketplace] feed di dati a cui non sei abbonato. Ulteriori informazioni in [Recommendations delle caratteristiche](trait-recommendations.md). |
| Reale e stimato [!UICONTROL Segment] Dimensione dati | Consulta [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Rimuovi [!UICONTROL Traits] da un [!UICONTROL Segment] {#remove-traits}

Gestione di [!UICONTROL traits] nel tuo [!UICONTROL segments] è una parte importante del mantenimento [!UICONTROL segments] fattibile. Segui questi passaggi se devi rimuovere [!UICONTROL traits] da un [!UICONTROL segment].

Da rimuovere [!UICONTROL traits] da un [!UICONTROL segment]:

1. Vai a **[!UICONTROL Audience Data > Segments]**. Scorri l’elenco o utilizza la funzione di ricerca per trovare [!UICONTROL segment] vuoi lavorare con.
2. Fai clic su [!UICONTROL segment] nome per aprire [!UICONTROL segment] nella schermata dei dettagli.
3. Clic **Modifica** per aprire [!UICONTROL Segment Builder] e quindi fare clic su **Caratteristiche** per aprire [!UICONTROL traits] pannello.
4. Passa il puntatore del mouse sopra [!UICONTROL trait] si desidera eliminare e quindi fare clic sulla X. Questa azione rimuove immediatamente [!UICONTROL trait] dal tuo [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controlli: [!UICONTROL Destinations Mappings] Sezione {#segment-builder-controls-destinations}

In entrata [!UICONTROL Segment Builder], l&#39;opzione [!UICONTROL Destinations Mapping] sezione ti consente di inviare [!UICONTROL segment] dati a terzi [!DNL cookie], [!DNL URL], o [!UICONTROL server-to-server destination]. Per aggiungere una [!UICONTROL destination], cerca (o sfoglia) per [!UICONTROL destination], fornire [!UICONTROL destination] informazioni specifiche e fai clic su **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Prerequisiti

Compila i campi obbligatori nella sezione [!UICONTROL Basic Information] e [!UICONTROL Traits] sezioni. Inoltre, la destinazione deve già esistere.

### [!UICONTROL Destination Mappings] Strumenti di ricerca

Il **[!UICONTROL Destination Mappings]** Il pannello contiene gli strumenti di ricerca descritti nella tabella seguente.

| Tipo di ricerca | Descrizione |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Consente di cercare un [!UICONTROL destination] per nome. Per eseguire la ricerca, inizia a digitare. Il campo viene completato automaticamente in base ai termini di ricerca. Clic **[!UICONTROL Add Destination]** al termine. |
| **[!UICONTROL Browse All Destinations]** | Sfoglia un elenco di *tutto* [!UICONTROL destinations] disponibili. Seleziona e aggiungi [!UICONTROL destinations] al tuo [!UICONTROL segment] dall&#39;elenco a comparsa. |

## Campi in [!UICONTROL Destination Mappings] Finestre popup {#fields-in-dest-mappings}

In entrata [!UICONTROL Segment Builder], il [!UICONTROL Add Destination] viene visualizzata dopo aver selezionato un [!UICONTROL destination]. In questa finestra vengono visualizzate informazioni statiche relative al [!UICONTROL destination] e campi che variano a seconda della [!UICONTROL destination] tipo. Fornisci le informazioni richieste nei campi vuoti per impostare una [!UICONTROL destination mapping].

>[!NOTE]
>
>Le date di pubblicazione sono facoltative. Se questo campo viene lasciato vuoto, la destinazione diventa attiva e non scade mai.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campi

In [!UICONTROL Destination Mapping] campi, specifica le coppie chiave-valore utilizzate per inviare dati al [!UICONTROL destination]. Immetti la chiave nel primo campo e i valori nel secondo. Il tuo [!UICONTROL cookie destination] pop potrebbe assomigliare a questo:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campi

In [!UICONTROL URL] e [!UICONTROL Secure URL] , specificare l&#39;indirizzo standard o sicuro completo utilizzato per inviare i dati al [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campi

In [!UICONTROL Destination Value] specifica il valore (parte di una coppia chiave-valore) utilizzato per inviare dati al [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)
>* [Creare una destinazione URL](../../features/destinations/create-url-destination.md)

