---
description: Descrive come creare segmenti con Segment Builder (Generatore di segmenti).
seo-description: Descrive come creare segmenti con Segment Builder (Generatore di segmenti).
seo-title: Generatore di segmenti
solution: Audience Manager
title: Generatore di segmenti
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: 4bf32099e964c421d943d9925c74dd0d4d6ee576
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 1%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Descrive i passaggi obbligatori e facoltativi per creare un segmento in [!UICONTROL Segment Builder].

## Dimostrazione video

Per iniziare, guarda il video [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Crea segmenti in  Audience Manager. Il video illustra il processo di creazione dei segmenti. Per ulteriori informazioni, consulta le sezioni riportate di seguito.

## Crea un [!UICONTROL Segment] {#create-segment}

### Sezione Generatore di segmenti

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] è costituito da 3 sezioni distinte: [!UICONTROL Basic Information], [!UICONTROL Traits]e [!UICONTROL Destinations Mapping]. Per creare un [!UICONTROL segment], completate i campi richiesti nelle [!UICONTROL Basic Information] sezioni e [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] sono facoltative. Per ulteriore assistenza, consulta le istruzioni riportate di seguito.

1. Nella sezione [Informazioni](../../features/segments/segment-builder.md#segment-builder-controls-basics) di base:

   ![create-segment](assets/create-segment.png)

   * Denominate il [!UICONTROL segment]. La lunghezza massima di un [!UICONTROL segment] nome è di 255 caratteri.
   * Impostate lo [!UICONTROL segment] stato (attivo è predefinito).
   * Scegli una [!UICONTROL data source]. Usate il primo menu a discesa per filtrare tra  Audience Manager [!UICONTROL data sources],  suite di rapporti Adobe Analytics o entrambe. Quindi, usate il secondo menu a discesa per scegliere [!UICONTROL data source]. Se non si utilizzano  suite di rapporti Adobe Analytics, il selettore [!UICONTROL data source] del tipo è disabilitato e predefinito per  solo origini dati del Audience Manager.
   * Selezionare un [!UICONTROL profile merge rule] da utilizzare per la [!UICONTROL segment] qualifica.
   * Assegnare l’ [!UICONTROL segment] oggetto a una cartella di archiviazione.

1. Nella sezione [Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Cerca il segmento da [!UICONTROL trait] aggiungere e fai clic su **[!UICONTROL Add Trait]**. Aggiungete un altro [!UICONTROL trait] per creare un [!UICONTROL trait] gruppo.
   * Aprire la [!UICONTROL Advanced Search] modale facendo clic su **[!UICONTROL Browse All Traits]**. Cercare [!UICONTROL traits] per nome, ID, descrizione o [!UICONTROL data source]. Fate clic su una cartella durante la ricerca per limitare i risultati a tale cartella e alle relative sottocartelle. Puoi anche filtrare [!UICONTROL traits] per [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based]e [!UICONTROL Onboarded]) o per tipo di popolazione (ID [!UICONTROL Algorithmic][dispositivo e ID](../../reference/ids-in-aam.md) [](../../reference/ids-in-aam.md)multi-dispositivo).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Ricevi raccomandazioni sulle [caratteristiche](trait-recommendations.md) live mentre crei le tue [!UICONTROL segment].
   * Fate clic e trascinate [!UICONTROL traits] per creare gruppi separati.
   * Passa il puntatore del mouse tra i gruppi per impostare le relazioni con i valori booleani [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] .
   * Passa il cursore del mouse sull’icona dell’orologio per aggiungere regole di [aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) al [!UICONTROL trait].
   * Visualizzare i dati sulla popolazione del segmento durante l&#39;aggiunta o la rimozione [!UICONTROL traits]. Fare clic **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati. Per ulteriori informazioni sui dati relativi alla popolazione dei [segmenti](../../features/segments/segment-builder-data.md#segment-populations) , consulta la sezione [!UICONTROL Segment Builder].
   * Al **[!UICONTROL Save]** termine, fate clic.

1. *(Facoltativo)* Mappate una [!UICONTROL segment] mappa su una [!UICONTROL destination] nella sezione Mappatura [](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destinazione:
   * Cercare il [!UICONTROL destination] e fare clic su **[!UICONTROL Add Destination]**. Nota: [!UICONTROL destination] deve già esistere prima di poter essere aggiunto a un [!UICONTROL segment].
   * Al **[!UICONTROL Save]** termine, fate clic.

Guardate il video seguente per vedere in dettaglio come funzionano le metriche tra dispositivi.

>[!VIDEO](https://video.tv.adobe.com/v/33445/)

## [!UICONTROL Segment Builder] Controlli: [!UICONTROL Basic Information] Sezione {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] le impostazioni consentono di creare caratteristiche nuove o di modificare quelle esistenti. Per creare una nuova cartella, [!UICONTROL segment]immettete un nome, una cartella [!UICONTROL data source]e selezionate una cartella di archiviazione. Tutti gli altri campi sono facoltativi. Al termine, passare alla [!UICONTROL Traits] sezione.

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

## [!UICONTROL Segment Builder] Controlli: [!UICONTROL Traits] Sezione {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], la [!UICONTROL Traits] sezione consente di gestire [!UICONTROL traits] in un [!UICONTROL segment], creare [!UICONTROL trait] gruppi e impostare criteri di qualifica. Per aggiungere un [!UICONTROL trait] nome a un [!UICONTROL segment], digitate il [!UICONTROL trait] nome nel campo di ricerca e fate clic su [!UICONTROL Add Trait]. Salvate il [!UICONTROL trait] (se completato) o passate a [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Prerequisiti:** Compila i campi richiesti nella [!UICONTROL Basic Information] sezione .

| Campo | Descrizione |
|--- |--- |
| **[!UICONTROL Basic View]** | Questa sezione contiene controlli visivi che consentono di: <ul><li>Creare nuovi modelli e gestire quelli esistenti [!UICONTROL segments].</li><li>Rimuovere [!UICONTROL traits] da un [!UICONTROL segment].</li><li>Aggiungete fino a 50 (massimo) [!UICONTROL traits] a un [!UICONTROL segment].</li><li>Trascinate e rilasciate [!UICONTROL traits] per creare nuovi gruppi.</li><li>Visualizzare [!UICONTROL traits] e [!UICONTROL trait] i gruppi in un [!UICONTROL segment].</li><li>Impostate i criteri di qualifica con espressioni booleane, operatori di confronto e impostazioni di aggiornamento/frequenza.</li></ul> |
| **[!UICONTROL Code View]** | Apre un ambiente di sviluppo che consente di creare e gestire [!UICONTROL traits]i requisiti di gruppi e qualifica con codice anziché con l&#39;interfaccia visiva. La vista codice è utile se [!UICONTROL segments]: <ul><li>Contengono più di 50 [!UICONTROL traits] in un individuo [!UICONTROL segment]. Nota: [!UICONTROL Segments] sono limitati a 5000 [!UICONTROL traits] (massimo).</li><li>Contengono molti [!UICONTROL trait] gruppi.</li><li>Avere requisiti di qualifica complessi.</li></ul> |
| Cerca | Consente di trovare [!UICONTROL traits] l’aggiunta a un [!UICONTROL segment]. |
| Consigli | Ottenete raccomandazioni live per contenuti simili [!UICONTROL traits], dai feed di dati di prime parti [!UICONTROL traits] e [!UICONTROL Audience Marketplace] ai quali siete iscritti. Aggiungete queste raccomandazioni alla [!UICONTROL segment] regola per espandere il pubblico. Ulteriori informazioni in [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Ottenete raccomandazioni live per contenuti simili [!UICONTROL traits], dai [!UICONTROL Audience Marketplace] feed di dati a cui non siete iscritti. Ulteriori informazioni in [Trait Recommendations](trait-recommendations.md). |
| Dati [!UICONTROL Segment] di dimensioni reali e stimate | Consulta [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Rimuovi [!UICONTROL Traits] da un [!UICONTROL Segment] {#remove-traits}

Gestire il [!UICONTROL traits] contenuto [!UICONTROL segments] è una parte importante per mantenere la [!UICONTROL segments] redditività. Per rimuovere [!UICONTROL traits] da un [!UICONTROL segment], effettuate le seguenti operazioni.

Per rimuovere [!UICONTROL traits] da un [!UICONTROL segment]:

1. Vai a **[!UICONTROL Audience Data > Segments]**. Scorrete l’elenco o utilizzate la funzione di ricerca per trovare il [!UICONTROL segment] tipo di oggetto da usare.
2. Fate clic sul [!UICONTROL segment] nome per aprire la schermata [!UICONTROL segment] Dettagli.
3. Fate clic su **Modifica** per aprire [!UICONTROL Segment Builder] e quindi su **Caratteristiche** per aprire il [!UICONTROL traits] pannello.
4. Passate il puntatore del mouse sopra la X da [!UICONTROL trait] eliminare, quindi fate clic sulla X. Questa azione rimuove immediatamente le [!UICONTROL trait] risorse dal [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controlli: [!UICONTROL Destinations Mappings] Sezione {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], la [!UICONTROL Destinations Mapping] sezione facoltativa consente di inviare [!UICONTROL segment] dati a terzi [!DNL cookie], [!DNL URL]o [!UICONTROL server-to-server destination]. Per aggiungere [!UICONTROL destination], cercare (o cercare) un [!UICONTROL destination], fornire [!UICONTROL destination] informazioni specifiche e fare clic su **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Prerequisiti

Compila i campi richiesti nelle sezioni [!UICONTROL Basic Information] e [!UICONTROL Traits] . Inoltre, la destinazione deve già esistere.

### [!UICONTROL Destination Mappings] Strumenti di ricerca

Il **[!UICONTROL Destination Mappings]** pannello contiene gli strumenti di ricerca come descritto nella tabella seguente.

| Tipo di ricerca | Descrizione |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Consente di cercare uno specifico [!UICONTROL destination] per nome. Per effettuare una ricerca, iniziate a digitare. Il campo verrà completato automaticamente in base ai termini di ricerca. Al **[!UICONTROL Add Destination]** termine, fate clic. |
| **[!UICONTROL Browse All Destinations]** | Sfogliate un elenco di *tutte* le risorse [!UICONTROL destinations] disponibili. Seleziona e aggiungi [!UICONTROL destinations] il tuo nome [!UICONTROL segment] dall&#39;elenco a comparsa. |

## Campi nelle finestre [!UICONTROL Destination Mappings] a comparsa {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], la [!UICONTROL Add Destination] finestra di dialogo viene visualizzata dopo la selezione di un [!UICONTROL destination]. In questa finestra sono visualizzate informazioni statiche sui campi [!UICONTROL destination] e che variano a seconda del [!UICONTROL destination] tipo. Fornire le informazioni necessarie nei campi vuoti per impostare un [!UICONTROL destination mapping].

>[!NOTE]
>
>Le date di pubblicazione sono facoltative. Quando è vuota, la destinazione diventa attiva e non scade mai.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campi

Nei [!UICONTROL Destination Mapping] campi, specificate le coppie chiave-valore utilizzate per inviare i dati al [!UICONTROL destination]. Immettere la chiave nel primo campo e i valori nel secondo. Il tuo [!UICONTROL cookie destination] pop potrebbe assomigliare a questo:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campi

Nei campi [!UICONTROL URL] e [!UICONTROL Secure URL] , specificate l&#39;indirizzo standard o protetto completo utilizzato per inviare i dati al [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campi

Nel [!UICONTROL Destination Value] campo specificare il valore (parte di una coppia chiave-valore) utilizzato per inviare i dati al [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)
>* [Creare una destinazione URL](../../features/destinations/create-url-destination.md)

