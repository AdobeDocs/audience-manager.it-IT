---
description: Descrive come creare segmenti con Segment Builder (Generatore di segmenti).
seo-description: Descrive come creare segmenti con Segment Builder (Generatore di segmenti).
seo-title: Generatore di segmenti
solution: Audience Manager
title: Generatore di segmenti
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Descrive i passaggi obbligatori e facoltativi per creare un segmento in [!UICONTROL Segment Builder].

## Dimostrazione video

Per iniziare, guardate il video [Crea segmenti in  Audience Manager ](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). Il video illustra il processo di creazione dei segmenti. Per ulteriori informazioni, consulta le sezioni riportate di seguito.

## Creare un [!UICONTROL Segment] {#create-segment}

### Sezione Generatore di segmenti

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] è costituito da 3 sezioni distinte:  [!UICONTROL Basic Information],  [!UICONTROL Traits]e  [!UICONTROL Destinations Mapping]. Per creare un [!UICONTROL segment], completare i campi richiesti nelle sezioni [!UICONTROL Basic Information] e [!UICONTROL Traits]. [!UICONTROL Destinations Mapping] sono facoltative. Per ulteriore assistenza, consulta le istruzioni riportate di seguito.

1. Nella sezione [Informazioni di base](../../features/segments/segment-builder.md#segment-builder-controls-basics):

   ![create-segment](assets/create-segment.png)

   * Denominate il simbolo [!UICONTROL segment]. La lunghezza massima di un nome [!UICONTROL segment] è di 255 caratteri.
   * Impostate lo stato [!UICONTROL segment] (attivo è il valore predefinito).
   * Scegliete un elemento [!UICONTROL data source]. Utilizzate il primo menu a discesa per filtrare tra  Audience Manager [!UICONTROL data sources],  suite di rapporti Adobe Analytics o entrambe. Quindi, utilizzate il secondo menu a discesa per scegliere il [!UICONTROL data source]. Se non si utilizzano  suite di rapporti Adobe Analytics, il selettore di tipo [!UICONTROL data source] è disabilitato e predefinito solo per  origini dati di Audience Manager.
   * Selezionare un [!UICONTROL profile merge rule] da utilizzare per la qualifica [!UICONTROL segment].
   * Assegnare l&#39;elemento [!UICONTROL segment] a una cartella di archiviazione.

1. Nella sezione [Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits):
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Cercare la [!UICONTROL trait] da aggiungere a un segmento e fare clic su **[!UICONTROL Add Trait]**. Aggiungete un altro [!UICONTROL trait] per creare un gruppo [!UICONTROL trait].
   * Aprire il modale [!UICONTROL Advanced Search] facendo clic su **[!UICONTROL Browse All Traits]**. Cercare [!UICONTROL traits] per nome, ID, descrizione o [!UICONTROL data source]. Fate clic su una cartella durante la ricerca per limitare i risultati a tale cartella e alle relative sottocartelle. Potete anche filtrare [!UICONTROL traits] per [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] e [!UICONTROL Algorithmic]) o per tipo di popolazione ([ID dispositivo](../../reference/ids-in-aam.md) e [ID multi-dispositivo](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Ricevi le [raccomandazioni sulle caratteristiche](trait-recommendations.md) live durante la creazione della [!UICONTROL segment].
   * Fate clic e trascinate [!UICONTROL traits] per creare gruppi separati.
   * Passa il puntatore del mouse tra i gruppi per impostare le relazioni con i valori booleani [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT].
   * Passa il cursore del mouse sull&#39;icona dell&#39;orologio per aggiungere le regole [recency e frequenza](../../features/segments/recency-and-frequency.md) alla [!UICONTROL trait].
   * Visualizzare i dati sulla popolazione del segmento durante l&#39;aggiunta o la rimozione di [!UICONTROL traits]. Fare clic su **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati. Per ulteriori informazioni su [dati sulla popolazione del segmento](../../features/segments/segment-builder-data.md#segment-populations), vedere [!UICONTROL Segment Builder].
   * Fare clic su **[!UICONTROL Save]** al termine.

1. *(Facoltativo)* Mappate una mappa  [!UICONTROL segment] su una  [!UICONTROL destination] nella sezione  [Destination ](../../features/segments/segment-builder.md#segment-builder-controls-destinations) Mapping (Mappatura destinazione):
   * Cercare il [!UICONTROL destination] e fare clic su **[!UICONTROL Add Destination]**. Nota: il [!UICONTROL destination] deve già esistere prima di poter essere aggiunto a un [!UICONTROL segment].
   * Fare clic su **[!UICONTROL Save]** al termine.

Guardate il video seguente per vedere in dettaglio come funzionano le metriche tra dispositivi.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] Controlli:  [!UICONTROL Basic Information] Sezione  {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], le impostazioni [!UICONTROL the Basic Information] consentono di creare caratteristiche nuove o di modificare caratteristiche esistenti. Per creare una nuova [!UICONTROL segment], immettete un nome, una [!UICONTROL data source] e selezionate una cartella di archiviazione. Tutti gli altri campi sono facoltativi. Al termine, passare alla sezione [!UICONTROL Traits].

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
| **[!UICONTROL Name]** | Assegna al segmento un nome logico breve che ne descrive funzione o finalità. Evitare abbreviazioni e caratteri speciali. La lunghezza massima del nome di un segmento è di 255 caratteri. |
| **[!UICONTROL Description]** | Campo per ulteriori informazioni descrittive sul segmento. |
| **[!UICONTROL Integration Code]** | Campo per un ID definito dall’utente o altre informazioni specifiche per la società. |
| **[!UICONTROL Data Source]** | Associa il segmento a un fornitore di dati specifico. <br> Utilizzate il primo menu a discesa per filtrare tra origini dati  Audience Manager,  suite di rapporti Adobe Analytics o entrambe. Quindi, utilizzare il secondo menu a discesa per scegliere l&#39;origine dati. <br> Se non si utilizzano  suite di rapporti Adobe Analytics, il selettore del tipo di origine dati è disabilitato e predefinito per  solo origini dati Audienci Manager. |
| **[!UICONTROL Profile Merge Rule]** | Seleziona la regola di unione profilo da utilizzare per la qualifica del segmento. |
| **[!UICONTROL Status]** | Attiva o disattiva il segmento (attivo per impostazione predefinita). |
| **Memorizzazione delle cartelle** | Stabilisce a quale cartella di archiviazione appartiene il segmento. |

## [!UICONTROL Segment Builder] Controlli:  [!UICONTROL Traits] Sezione  {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], la sezione [!UICONTROL Traits] consente di gestire [!UICONTROL traits] in [!UICONTROL segment], creare gruppi [!UICONTROL trait] e impostare criteri di qualifica. Per aggiungere un [!UICONTROL trait] a un [!UICONTROL segment], digitare il nome [!UICONTROL trait] nel campo di ricerca e fare clic su [!UICONTROL Add Trait]. Salvate il [!UICONTROL trait] (se completato) o passate a [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Prerequisiti:** completa i campi richiesti nella  [!UICONTROL Basic Information] sezione.

| Campo | Descrizione |
|--- |--- |
| **[!UICONTROL Basic View]** | Questa sezione contiene controlli visivi che consentono di: <ul><li>Creare nuovi elementi e gestire [!UICONTROL segments] esistenti.</li><li>Rimuovere [!UICONTROL traits] da un [!UICONTROL segment].</li><li>Aggiungere fino a 50 (massimo) [!UICONTROL traits] a un [!UICONTROL segment].</li><li>Trascinare [!UICONTROL traits] per creare nuovi gruppi.</li><li>Visualizzare i gruppi [!UICONTROL traits] e [!UICONTROL trait] in un [!UICONTROL segment].</li><li>Impostate i criteri di qualifica con espressioni booleane, operatori di confronto e impostazioni di aggiornamento/frequenza.</li></ul> |
| **[!UICONTROL Code View]** | Apre un ambiente di sviluppo che consente di creare e gestire [!UICONTROL traits], gruppi e requisiti di qualifica con codice anziché con l&#39;interfaccia visiva. La vista del codice è utile se [!UICONTROL segments]: <ul><li>Contiene più di 50 [!UICONTROL traits] in un singolo [!UICONTROL segment]. Nota: [!UICONTROL Segments] sono limitati a 5000 [!UICONTROL traits] (massimo).</li><li>Contiene molti gruppi [!UICONTROL trait].</li><li>Avere requisiti di qualifica complessi.</li></ul> |
| Cerca | Consente di trovare [!UICONTROL traits] da aggiungere a [!UICONTROL segment]. |
| Consigli | Ottenete raccomandazioni live per [!UICONTROL traits] simili dai feed di dati di prime parti [!UICONTROL traits] e [!UICONTROL Audience Marketplace] ai quali siete iscritti. Aggiungete queste raccomandazioni alla regola [!UICONTROL segment] per espandere il pubblico. Leggi tutto in [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Ottenete raccomandazioni live per [!UICONTROL traits] simili dai feed di dati [!UICONTROL Audience Marketplace] a cui non siete iscritti. Leggi tutto in [Trait Recommendations](trait-recommendations.md). |
| Dati di dimensioni reali e stimati[!UICONTROL Segment] | Consulta [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Rimuovere [!UICONTROL Traits] da un [!UICONTROL Segment] {#remove-traits}

Gestire la [!UICONTROL traits] nel [!UICONTROL segments] è una parte importante per mantenere la [!UICONTROL segments] redditività. Per rimuovere [!UICONTROL traits] da un [!UICONTROL segment], eseguite i seguenti passaggi.

Per rimuovere [!UICONTROL traits] da un [!UICONTROL segment]:

1. Vai a **[!UICONTROL Audience Data > Segments]**. Scorrete l&#39;elenco o utilizzate la funzione di ricerca per trovare la [!UICONTROL segment] con cui desiderate lavorare.
2. Fare clic sul nome [!UICONTROL segment] per aprire la schermata dei dettagli [!UICONTROL segment].
3. Fare clic su **Modifica** per aprire [!UICONTROL Segment Builder], quindi fare clic su **Caratteristiche** per aprire il pannello [!UICONTROL traits].
4. Passate il puntatore del mouse sulla [!UICONTROL trait] da eliminare, quindi fate clic sulla X. Questa azione rimuove immediatamente la [!UICONTROL trait] dal [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controlli:  [!UICONTROL Destinations Mappings] Sezione  {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], la sezione opzionale [!UICONTROL Destinations Mapping] consente di inviare dati [!UICONTROL segment] a terzi [!DNL cookie], [!DNL URL] o [!UICONTROL server-to-server destination]. Per aggiungere un [!UICONTROL destination], cercare (o cercare) un [!UICONTROL destination], fornire [!UICONTROL destination] informazioni specifiche e fare clic su **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Prerequisiti

Completare i campi richiesti nelle sezioni [!UICONTROL Basic Information] e [!UICONTROL Traits]. Inoltre, la destinazione deve già esistere.

### [!UICONTROL Destination Mappings] Strumenti di ricerca

Il pannello **[!UICONTROL Destination Mappings]** contiene strumenti di ricerca come descritto nella tabella seguente.

| Tipo di ricerca | Descrizione |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Consente di cercare un [!UICONTROL destination] specifico per nome. Per effettuare una ricerca, iniziate a digitare. Il campo verrà completato automaticamente in base ai termini di ricerca. Fare clic su **[!UICONTROL Add Destination]** al termine. |
| **[!UICONTROL Browse All Destinations]** | Sfogliate un elenco di *all* [!UICONTROL destinations] disponibili. Seleziona e aggiungi [!UICONTROL destinations] al [!UICONTROL segment] dall&#39;elenco a comparsa. |

## Campi nella [!UICONTROL Destination Mappings] finestra a comparsa {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], dopo aver selezionato un [!UICONTROL destination] viene visualizzata la finestra di dialogo [!UICONTROL Add Destination]. In questa finestra sono visualizzate informazioni statiche sui campi [!UICONTROL destination] e che variano a seconda del tipo [!UICONTROL destination]. Fornire le informazioni necessarie nei campi vuoti per impostare un [!UICONTROL destination mapping].

>[!NOTE]
>
>Le date di pubblicazione sono facoltative. Quando è vuota, la destinazione diventa attiva e non scade mai.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campi

Nei campi [!UICONTROL Destination Mapping], specificate le coppie chiave-valore utilizzate per inviare i dati a [!UICONTROL destination]. Immettere la chiave nel primo campo e i valori nel secondo. Il [!UICONTROL cookie destination] pop potrebbe essere simile al seguente:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campi

Nei campi [!UICONTROL URL] e [!UICONTROL Secure URL], specificare l&#39;indirizzo standard o protetto completo utilizzato per inviare i dati a [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campi

Nel campo [!UICONTROL Destination Value] specificare il valore (parte di una coppia chiave-valore) utilizzato per inviare i dati a [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)
>* [Creare una destinazione URL](../../features/destinations/create-url-destination.md)

