---
description: Descrive come creare segmenti con Generatore di segmenti.
seo-description: Descrive come creare segmenti con Generatore di segmenti.
seo-title: Generatore di segmenti
solution: Audience Manager
title: Generatore di segmenti
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: 'Segmenti '
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Descrive i passaggi richiesti e facoltativi per creare un segmento in [!UICONTROL Segment Builder].

## Dimostrazione video

Per iniziare, guarda il video [Crea segmenti in Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). Il video illustra il processo di creazione dei segmenti. Per ulteriori informazioni, consulta le sezioni seguenti.

## Crea un [!UICONTROL Segment] {#create-segment}

### Sezione Segment Builder

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] è costituito da 3 sezioni distinte:  [!UICONTROL Basic Information],  [!UICONTROL Traits] e  [!UICONTROL Destinations Mapping]. Per creare un [!UICONTROL segment], completa i campi richiesti nelle sezioni [!UICONTROL Basic Information] e [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] Le impostazioni sono facoltative. Per ulteriore assistenza, consulta le istruzioni riportate di seguito.

1. Nella sezione [Informazioni di base](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![creare un segmento](assets/create-segment.png)

   * Denomina il simbolo [!UICONTROL segment]. La lunghezza massima di un nome [!UICONTROL segment] è di 255 caratteri.
   * Imposta lo stato [!UICONTROL segment] (attivo è predefinito).
   * Scegli un [!UICONTROL data source]. Usa il primo menu a discesa per filtrare tra Audience Manager [!UICONTROL data sources], suite di rapporti Adobe Analytics o entrambe. Quindi, utilizza il secondo menu a discesa per scegliere il tuo [!UICONTROL data source]. Se non usi le suite di rapporti di Adobe Analytics, il selettore di tipo [!UICONTROL data source] è disabilitato e predefinito solo per le origini dati di Audience Manager.
   * Seleziona un [!UICONTROL profile merge rule] da utilizzare per la qualifica [!UICONTROL segment].
   * Assegna il [!UICONTROL segment] a una cartella di archiviazione.

1. Nella sezione [Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Cerca il [!UICONTROL trait] da aggiungere a un segmento e fai clic su **[!UICONTROL Add Trait]**. Aggiungi un altro [!UICONTROL trait] per creare un gruppo [!UICONTROL trait].
   * Visualizza il modale [!UICONTROL Advanced Search] facendo clic su **[!UICONTROL Browse All Traits]**. Cerca [!UICONTROL traits] per nome, ID, descrizione o [!UICONTROL data source]. Fai clic su una cartella durante la ricerca per limitare i risultati a tale cartella e alle relative sottocartelle. Puoi anche filtrare [!UICONTROL traits] per [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] e [!UICONTROL Algorithmic]) o per tipo di popolazione ([ID dispositivo](../../reference/ids-in-aam.md) e [ID multidispositivo](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Ricevi le [raccomandazioni sulle caratteristiche](trait-recommendations.md) in tempo reale durante la generazione del [!UICONTROL segment].
   * Fai clic su e trascina [!UICONTROL traits] per creare gruppi separati.
   * Passa il puntatore del mouse tra i gruppi per impostare le relazioni con i valori booleani [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT].
   * Passa il puntatore sull&#39;icona dell&#39;orologio per aggiungere le regole [recency e frequenza](../../features/segments/recency-and-frequency.md) al percorso [!UICONTROL trait].
   * Visualizza i dati della popolazione del segmento durante l&#39;aggiunta o la rimozione di [!UICONTROL traits]. Fai clic su **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati. Ulteriori informazioni su [dati sulla popolazione del segmento](../../features/segments/segment-builder-data.md#segment-populations) in [!UICONTROL Segment Builder].
   * Al termine, fai clic su **[!UICONTROL Save]** .

1. *(Facoltativo)* Mappa un  [!UICONTROL segment] su un  [!UICONTROL destination] nella sezione  [Destination ](../../features/segments/segment-builder.md#segment-builder-controls-destinations) Mapping (Mappatura destinazione) :
   * Cerca il [!UICONTROL destination] e fai clic su **[!UICONTROL Add Destination]**. Nota: il [!UICONTROL destination] deve esistere già prima di poter essere aggiunto a un [!UICONTROL segment].
   * Al termine, fai clic su **[!UICONTROL Save]** .

Guarda il video seguente per vedere in dettaglio come funzionano le metriche per dispositivi diversi.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Controlli:  [!UICONTROL Basic Information] Sezione  {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], le impostazioni [!UICONTROL the Basic Information] consentono di creare o modificare caratteristiche nuove o esistenti. Per creare un nuovo [!UICONTROL segment], fornisci un nome, un [!UICONTROL data source] e seleziona una cartella di archiviazione. Tutti gli altri campi sono facoltativi. Al termine, passa alla sezione [!UICONTROL Traits].

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
| **[!UICONTROL Name]** | Assegna al segmento un nome logico breve che ne descrive la funzione o lo scopo. Evitare abbreviazioni e caratteri speciali. La lunghezza massima del nome di un segmento è di 255 caratteri. |
| **[!UICONTROL Description]** | Campo per ulteriori informazioni descrittive sul segmento. |
| **[!UICONTROL Integration Code]** | Campo per un ID definito dall’utente o per altre informazioni specifiche per l’azienda. |
| **[!UICONTROL Data Source]** | Associa il segmento a un provider di dati specifico. <br> Utilizza il primo menu a discesa per filtrare tra origini dati di Audience Manager, suite di rapporti Adobe Analytics o entrambe. Quindi, utilizza il secondo menu a discesa per scegliere l’origine dati. <br> Se non usi le suite di rapporti di Adobe Analytics, il selettore del tipo di origine dati è disabilitato e viene impostato come impostazione predefinita solo per le origini dati di Audience Manager. |
| **[!UICONTROL Profile Merge Rule]** | Seleziona la regola di unione profili da utilizzare per la qualifica dei segmenti. |
| **[!UICONTROL Status]** | Attiva o disattiva il segmento (attivo per impostazione predefinita). |
| **Archiviazione cartelle** | Determina la cartella di archiviazione a cui appartiene il segmento. |

## [!UICONTROL Segment Builder] Controlli:  [!UICONTROL Traits] Sezione  {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], la sezione [!UICONTROL Traits] ti consente di gestire [!UICONTROL traits] in un [!UICONTROL segment], creare gruppi [!UICONTROL trait] e impostare criteri di qualificazione. Per aggiungere un [!UICONTROL trait] a un [!UICONTROL segment], digita il nome [!UICONTROL trait] nel campo di ricerca e fai clic su [!UICONTROL Add Trait]. Salva il [!UICONTROL trait] (se completato) o passa a [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Prerequisiti:** completa i campi richiesti nella  [!UICONTROL Basic Information] sezione .

| Campo | Descrizione |
|--- |--- |
| **[!UICONTROL Basic View]** | Questa sezione fornisce controlli visivi che consentono di: <ul><li>Crea nuovi e gestisci i [!UICONTROL segments] esistenti.</li><li>Rimuovere [!UICONTROL traits] da un [!UICONTROL segment].</li><li>Aggiungi fino a 50 (massimo) [!UICONTROL traits] a [!UICONTROL segment].</li><li>Trascina [!UICONTROL traits] per creare nuovi gruppi.</li><li>Visualizzare i gruppi [!UICONTROL traits] e [!UICONTROL trait] in un [!UICONTROL segment].</li><li>Imposta i criteri di qualificazione con espressioni booleane, operatori di confronto e impostazioni di aggiornamento/frequenza.</li></ul> |
| **[!UICONTROL Code View]** | Apre un ambiente di sviluppo che consente di creare e gestire [!UICONTROL traits], gruppi e requisiti di qualificazione con codice anziché con l’interfaccia visiva. La vista Codice è utile se il tuo [!UICONTROL segments]: <ul><li>Contenere più di 50 [!UICONTROL traits] in un singolo [!UICONTROL segment]. Nota: [!UICONTROL Segments] sono limitati a 5000 [!UICONTROL traits] (massimo).</li><li>Contenere molti gruppi [!UICONTROL trait].</li><li>Avere requisiti di qualificazione complessi.</li></ul> |
| Cerca | Consente di trovare [!UICONTROL traits] da aggiungere a [!UICONTROL segment]. |
| Consigli | Ottieni consigli live per [!UICONTROL traits] simili dai feed di dati di prime parti [!UICONTROL traits] e [!UICONTROL Audience Marketplace] a cui sei abbonato. Aggiungi questi consigli alla regola [!UICONTROL segment] per espandere il pubblico. Ulteriori informazioni sono disponibili in [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Ottieni consigli live per [!UICONTROL traits] simili, dai [!UICONTROL Audience Marketplace] feed di dati a cui non sei iscritto. Ulteriori informazioni sono disponibili in [Trait Recommendations](trait-recommendations.md). |
| Dati reali e stimati [!UICONTROL Segment] sulle dimensioni | Consulta [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Rimuovi [!UICONTROL Traits] da un [!UICONTROL Segment] {#remove-traits}

La gestione di [!UICONTROL traits] nel [!UICONTROL segments] è una parte importante del mantenimento della redditività di [!UICONTROL segments]. Segui questi passaggi se devi rimuovere [!UICONTROL traits] da un [!UICONTROL segment].

Per rimuovere [!UICONTROL traits] da un elemento [!UICONTROL segment]:

1. Vai a **[!UICONTROL Audience Data > Segments]**. Scorri l’elenco o utilizza la funzione di ricerca per trovare il [!UICONTROL segment] con cui desideri lavorare.
2. Fai clic sul nome [!UICONTROL segment] per aprire la schermata dei dettagli [!UICONTROL segment] .
3. Fai clic su **Modifica** per aprire [!UICONTROL Segment Builder], quindi fai clic su **Caratteristiche** per aprire il pannello [!UICONTROL traits].
4. Passa il puntatore del mouse sulla [!UICONTROL trait] da eliminare, quindi fai clic sulla X. Questa azione rimuove immediatamente la [!UICONTROL trait] dal [!UICONTROL segment].

## [!UICONTROL Segment Builder] Controlli:  [!UICONTROL Destinations Mappings] Sezione  {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], la sezione opzionale [!UICONTROL Destinations Mapping] consente di inviare dati [!UICONTROL segment] a terze parti [!DNL cookie], [!DNL URL] o [!UICONTROL server-to-server destination]. Per aggiungere un [!UICONTROL destination], cerca (o sfoglia) un [!UICONTROL destination], fornisci informazioni specifiche [!UICONTROL destination] e fai clic su **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Prerequisiti

Compila i campi richiesti nelle sezioni [!UICONTROL Basic Information] e [!UICONTROL Traits] . Inoltre, la destinazione deve esistere già.

### [!UICONTROL Destination Mappings] Strumenti di ricerca

Il pannello **[!UICONTROL Destination Mappings]** contiene gli strumenti di ricerca descritti nella tabella seguente.

| Tipo di ricerca | Descrizione |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Consente di cercare un [!UICONTROL destination] specifico per nome. Per eseguire la ricerca, inizia a digitare. Il campo verrà compilato automaticamente in base ai termini di ricerca. Al termine, fai clic su **[!UICONTROL Add Destination]** . |
| **[!UICONTROL Browse All Destinations]** | Sfoglia un elenco di *tutto* [!UICONTROL destinations] disponibile. Seleziona e aggiungi [!UICONTROL destinations] al tuo [!UICONTROL segment] dall&#39;elenco a comparsa. |

## Campi nel [!UICONTROL Destination Mappings] Windows pop-up {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], dopo aver selezionato un [!UICONTROL destination] viene visualizzata la finestra di dialogo [!UICONTROL Add Destination]. Questa finestra visualizza informazioni statiche sui campi [!UICONTROL destination] e che variano a seconda del tipo [!UICONTROL destination]. Fornisci le informazioni richieste nei campi vuoti per impostare un [!UICONTROL destination mapping].

>[!NOTE]
>
>Le date di pubblicazione sono facoltative. Quando viene lasciato vuoto, la destinazione diventa attiva e non scade mai.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Campi

Nei campi [!UICONTROL Destination Mapping] , specifica le coppie chiave-valore utilizzate per inviare i dati a [!UICONTROL destination]. Immetti la chiave nel primo campo e i valori nel secondo. Il tuo [!UICONTROL cookie destination] pop potrebbe essere simile al seguente:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Campi

Nei campi [!UICONTROL URL] e [!UICONTROL Secure URL] , specifica l’indirizzo standard o sicuro completo utilizzato per inviare i dati a [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Campi

Nel campo [!UICONTROL Destination Value] specifica il valore (parte di una coppia chiave-valore) utilizzato per inviare i dati a [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)
* [Creare una destinazione URL](../../features/destinations/create-url-destination.md)

