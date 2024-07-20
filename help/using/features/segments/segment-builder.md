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
source-wordcount: '1048'
ht-degree: 1%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Descrive i passaggi obbligatori e facoltativi per la creazione di un segmento in [!UICONTROL Segment Builder].

## Dimostrazione video

Inizia guardando [Creare segmenti nel video di Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). Il video illustra il processo di creazione dei segmenti. Per ulteriori informazioni, consulta le sezioni seguenti.

## Crea un [!UICONTROL Segment] {#create-segment}

### Sezione Generatore di segmenti

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] è costituito da 3 sezioni separate: [!UICONTROL Basic Information], [!UICONTROL Traits] e [!UICONTROL Destinations Mapping]. Per creare un [!UICONTROL segment], completare i campi obbligatori nelle sezioni [!UICONTROL Basic Information] e [!UICONTROL Traits]. Le impostazioni di [!UICONTROL Destinations Mapping] sono facoltative. Per ulteriori informazioni, consulta le istruzioni di seguito.

1. Nella sezione [Informazioni di base](../../features/segments/segment-builder.md#segment-builder-controls-basics):

   ![create-segment](assets/create-segment.png)

   * Denomina [!UICONTROL segment]. La lunghezza massima di un nome [!UICONTROL segment] è di 255 caratteri.
   * Imposta lo stato [!UICONTROL segment] (attivo è predefinito).
   * Scegli un [!UICONTROL data source]. Utilizza il primo menu a discesa per filtrare tra le suite di rapporti Audience Manager [!UICONTROL data sources], Adobe Analytics o entrambe. Quindi, utilizzare il secondo menu a discesa per scegliere [!UICONTROL data source]. Se non utilizzi le suite di rapporti di Adobe Analytics, il selettore di tipo [!UICONTROL data source] è disabilitato e per impostazione predefinita viene utilizzato solo l&#39;Audience Manager di origini dati.
   * Selezionare [!UICONTROL profile merge rule] da utilizzare per la qualifica [!UICONTROL segment].
   * Assegnare [!UICONTROL segment] a una cartella di archiviazione.

1. Nella sezione [Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits):
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Cercare [!UICONTROL trait] da aggiungere a un segmento e fare clic su **[!UICONTROL Add Trait]**. Aggiungi un altro [!UICONTROL trait] per creare un gruppo [!UICONTROL trait].
   * Visualizzare il modale [!UICONTROL Advanced Search] facendo clic su **[!UICONTROL Browse All Traits]**. Cerca [!UICONTROL traits] per nome, ID, descrizione o [!UICONTROL data source]. Durante la ricerca, fai clic su una cartella per limitare i risultati a tale cartella e alle relative sottocartelle. È inoltre possibile filtrare [!UICONTROL traits] per [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] e [!UICONTROL Algorithmic]) o per tipo di popolazione ([ID dispositivo](../../reference/ids-in-aam.md) e [ID multi-dispositivo](../../reference/ids-in-aam.md)).
     ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Ottieni le [raccomandazioni sulle caratteristiche](trait-recommendations.md) durante la creazione di [!UICONTROL segment].
   * Fai clic e trascina [!UICONTROL traits] per creare gruppi separati.
   * Passare il mouse tra i gruppi per impostare le relazioni con i valori booleani [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT].
   * Passa il puntatore sull&#39;icona dell&#39;orologio per aggiungere [regole di aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) a [!UICONTROL trait].
   * Visualizzare i dati del gruppo di segmenti durante l&#39;aggiunta o la rimozione di [!UICONTROL traits]. Fai clic su **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati. Ulteriori informazioni sui [dati di popolazione del segmento](../../features/segments/segment-builder-data.md#segment-populations) in [!UICONTROL Segment Builder].
   * Al termine, fai clic su **[!UICONTROL Save]**.

1. *(Facoltativo)* Mappa un [!UICONTROL segment] a un [!UICONTROL destination] nella sezione [Mappatura destinazione](../../features/segments/segment-builder.md#segment-builder-controls-destinations):
   * Cercare [!UICONTROL destination] e fare clic su **[!UICONTROL Add Destination]**. Nota: [!UICONTROL destination] deve esistere già prima di poterlo aggiungere a [!UICONTROL segment].
   * Al termine, fai clic su **[!UICONTROL Save]**.

Guarda il video seguente per uno sguardo dettagliato al funzionamento delle metriche tra dispositivi.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## Controlli [!UICONTROL Segment Builder]: sezione [!UICONTROL Basic Information] {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], le impostazioni di [!UICONTROL the Basic Information] ti consentono di creare o modificare caratteristiche nuove o esistenti. Per creare un nuovo [!UICONTROL segment], specificare un nome, un [!UICONTROL data source] e selezionare una cartella di archiviazione. Tutti gli altri campi sono facoltativi. Al termine, passa alla sezione [!UICONTROL Traits].

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
| **[!UICONTROL Data Source]** | Associa il segmento a un provider di dati specifico. <br> Utilizza il primo menu a discesa per filtrare tra origini dati di Audience Manager, suite di rapporti di Adobe Analytics o entrambe. Quindi, utilizza il secondo menu a discesa per scegliere l’origine dati. <br> Se non utilizzi le suite di rapporti di Adobe Analytics, il selettore del tipo di origine dati è disabilitato e per impostazione predefinita viene utilizzato solo l&#39;Audience Manager delle origini dati. |
| **[!UICONTROL Profile Merge Rule]** | Seleziona la Regola di unione profili da utilizzare per la qualificazione dei segmenti. |
| **[!UICONTROL Status]** | Attiva o disattiva il segmento (attivo per impostazione predefinita). |
| **Archiviazione cartelle** | Determina la cartella di archiviazione a cui appartiene il segmento. |

## Controlli [!UICONTROL Segment Builder]: sezione [!UICONTROL Traits] {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], la sezione [!UICONTROL Traits] consente di gestire [!UICONTROL traits] in un [!UICONTROL segment], creare [!UICONTROL trait] gruppi e impostare criteri di qualifica. Per aggiungere un [!UICONTROL trait] a un [!UICONTROL segment], digitare il nome [!UICONTROL trait] nel campo di ricerca e fare clic su [!UICONTROL Add Trait]. Salvare [!UICONTROL trait] (se terminato) o passare a [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Prerequisiti:** Completare i campi obbligatori nella sezione [!UICONTROL Basic Information].

| Campo | Descrizione |
|--- |--- |
| **[!UICONTROL Basic View]** | Questa sezione fornisce controlli visivi che consentono di: <ul><li>Crea nuovo/i e gestisci [!UICONTROL segments] esistente/i.</li><li>Rimuovi [!UICONTROL traits] da [!UICONTROL segment].</li><li>Aggiungere fino a 50 (massimo) [!UICONTROL traits] a [!UICONTROL segment].</li><li>Trascina [!UICONTROL traits] per creare nuovi gruppi.</li><li>Visualizza [!UICONTROL traits] e [!UICONTROL trait] gruppi in un [!UICONTROL segment].</li><li>Imposta i criteri di qualificazione con espressioni booleane, operatori di confronto e impostazioni di recency/frequenza.</li></ul> |
| **[!UICONTROL Code View]** | Apre un ambiente di sviluppo che consente di creare e gestire [!UICONTROL traits], gruppi e requisiti di qualificazione con il codice anziché con l&#39;interfaccia visiva. La visualizzazione del codice è utile se [!UICONTROL segments]: <ul><li>Contenere più di 50 [!UICONTROL traits] in un singolo [!UICONTROL segment]. Nota: [!UICONTROL Segments] sono limitati a 5000 [!UICONTROL traits] (massimo).</li><li>Contengono molti [!UICONTROL trait] gruppi.</li><li>Avere requisiti di qualifica complessi.</li></ul> |
| Cerca | Consente di trovare [!UICONTROL traits] da aggiungere a [!UICONTROL segment]. |
| Consigli | Ricevi consigli live per [!UICONTROL traits] simili dai tuoi feed di dati di prime parti [!UICONTROL traits] e [!UICONTROL Audience Marketplace] a cui sei abbonato. Aggiungi questi consigli alla regola [!UICONTROL segment] per espandere il pubblico. Ulteriori informazioni in [Caratteristiche Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Ricevi consigli live per [!UICONTROL traits] simili dai feed di dati di [!UICONTROL Audience Marketplace] ai quali non sei abbonato. Ulteriori informazioni in [Caratteristiche Recommendations](trait-recommendations.md). |
| Dati reali e delle dimensioni stimate di [!UICONTROL Segment] | Consulta [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Rimuovi [!UICONTROL Traits] da [!UICONTROL Segment] {#remove-traits}

La gestione di [!UICONTROL traits] in [!UICONTROL segments] è importante per mantenere [!UICONTROL segments] attivo. Segui questi passaggi se devi rimuovere [!UICONTROL traits] da un [!UICONTROL segment].

Per rimuovere [!UICONTROL traits] da un [!UICONTROL segment]:

1. Vai a **[!UICONTROL Audience Data > Segments]**. Scorrere l&#39;elenco o utilizzare la funzionalità di ricerca per trovare i [!UICONTROL segment] che si desidera utilizzare.
2. Fare clic sul nome [!UICONTROL segment] per aprire la schermata dei dettagli [!UICONTROL segment].
3. Fai clic su **Modifica** per aprire [!UICONTROL Segment Builder], quindi su **Caratteristiche** per aprire il pannello [!UICONTROL traits].
4. Passa il puntatore del mouse su [!UICONTROL trait] da eliminare, quindi fai clic sulla X. Questa azione rimuove immediatamente [!UICONTROL trait] dal tuo [!UICONTROL segment].

## Controlli [!UICONTROL Segment Builder]: sezione [!UICONTROL Destinations Mappings] {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], la sezione facoltativa [!UICONTROL Destinations Mapping] ti consente di inviare dati [!UICONTROL segment] a una terza parte [!DNL cookie], [!DNL URL] o [!UICONTROL server-to-server destination]. Per aggiungere un [!UICONTROL destination], cercare un [!UICONTROL destination], fornire [!UICONTROL destination] informazioni specifiche e fare clic su **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Prerequisiti

Completare i campi obbligatori nelle sezioni [!UICONTROL Basic Information] e [!UICONTROL Traits]. Inoltre, la destinazione deve già esistere.

### Strumenti di ricerca [!UICONTROL Destination Mappings]

Il pannello **[!UICONTROL Destination Mappings]** contiene gli strumenti di ricerca descritti nella tabella seguente.

| Tipo di ricerca | Descrizione |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Consente di cercare un [!UICONTROL destination] specifico per nome. Per eseguire la ricerca, inizia a digitare. Il campo viene completato automaticamente in base ai termini di ricerca. Al termine, fai clic su **[!UICONTROL Add Destination]**. |
| **[!UICONTROL Browse All Destinations]** | Sfoglia un elenco di *tutti* [!UICONTROL destinations] disponibili. Seleziona e aggiungi [!UICONTROL destinations] al tuo [!UICONTROL segment] dall&#39;elenco a comparsa. |

## Campi nelle finestre popup [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], la finestra di dialogo [!UICONTROL Add Destination] viene visualizzata dopo aver selezionato un [!UICONTROL destination]. In questa finestra vengono visualizzate informazioni statiche sui campi [!UICONTROL destination] e variabili a seconda del tipo [!UICONTROL destination]. Fornisci le informazioni richieste nei campi vuoti per impostare un [!UICONTROL destination mapping].

>[!NOTE]
>
>Le date di pubblicazione sono facoltative. Se questo campo viene lasciato vuoto, la destinazione diventa attiva e non scade mai.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] campi

Nei campi [!UICONTROL Destination Mapping], specificare le coppie chiave-valore utilizzate per inviare dati a [!UICONTROL destination]. Immetti la chiave nel primo campo e i valori nel secondo. Il tuo elemento pop [!UICONTROL cookie destination] potrebbe essere simile al seguente:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] campi

Nei campi [!UICONTROL URL] e [!UICONTROL Secure URL], specificare l&#39;indirizzo completo standard o sicuro utilizzato per inviare i dati a [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] campi

Nel campo [!UICONTROL Destination Value] specificare il valore (parte di una coppia chiave-valore) utilizzato per inviare dati a [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Crea una destinazione cookie](../../features/destinations/create-cookie-destination.md)
>* [Crea una destinazione URL](../../features/destinations/create-url-destination.md)
