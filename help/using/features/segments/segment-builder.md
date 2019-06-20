---
description: Descrive come creare segmenti con Segment Builder (Generatore di segmenti).
seo-description: Descrive come creare segmenti con Segment Builder (Generatore di segmenti).
seo-title: Generatore di segmenti
solution: Audience Manager
title: Generatore di segmenti
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: b346dbe500f1e662c7b121a18c6cc0704ef3cfac

---


# Generatore di segmenti {#segment-builder}

Descrive i passaggi obbligatori e facoltativi che creano un segmento in [!UICONTROL Segment Builder].

## Crea un segmento {#create-segment}

### Sezione Generatore di segmenti

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] consiste di 3 sezioni separate: [!UICONTROL Basic Information], [!UICONTROL Traits]e [!UICONTROL Destinations Mapping]. Per creare un segmento, completa i campi obbligatori nelle [!UICONTROL Basic Information][!UICONTROL Traits] sezioni e. [!UICONTROL Destinations Mapping] sono facoltative. Per ulteriore assistenza, consultate le istruzioni riportate di seguito.

1. Nella [sezione Informazioni](../../features/segments/segment-builder.md#segment-builder-controls-basics) di base:
   * Denominate il segmento. La lunghezza massima del nome di un segmento è 255 caratteri.
   * Imposta lo stato del segmento (attivo, è predefinito).
   * Scegliete un&#39;origine dati.
   * Seleziona una regola di unione profilo da usare per la qualifica del segmento.
   * Assegna il segmento a una cartella di archiviazione.
1. Nella sezione [Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Cerca la caratteristica da aggiungere a un segmento e fai clic **[!UICONTROL Add Trait]** su. Aggiungete un&#39;altra caratteristica per creare un gruppo di caratteristiche.
   * Visualizzate il modale della ricerca avanzata facendo clic **[!UICONTROL Browse All Traits]** su. Cerca caratteristiche per nome, ID, descrizione o origine dati. Fate clic su una cartella durante la ricerca per limitare i risultati a quella cartella e alle relative sottocartelle. Potete anche filtrare le caratteristiche per tipo di caratteristica.
   * Ottenete suggerimenti sulle [caratteristiche live](trait-recommendations.md) durante la creazione del segmento.
   * Fate clic e trascinate le caratteristiche per creare gruppi separati.
   * Passa il cursore tra i gruppi per impostare le relazioni con i valori booleani [!UICONTROL AND], [!UICONTROL OR]o [!UICONTROL AND NOT] .
   * Passa il cursore sull&#39;icona dell&#39;orologio per aggiungere [al tratto](../../features/segments/recency-and-frequency.md) regole di aggiornamento e frequenza.
   * Visualizza i dati della popolazione del segmento quando aggiungi o rimuovi caratteristiche. Fate clic per **[!UICONTROL Calculate Estimates]** visualizzare (o aggiornare) i numeri stimati della popolazione. Scopri ulteriori informazioni sui [dati relativi alla popolazione del segmento](../../features/segments/segment-builder-data.md#segment-populations) in Segment Builder (Generatore segmenti).
   * Fate clic **[!UICONTROL Save]** su di essa.
1. *(Facoltativo)* Mappate un segmento su una destinazione nella [sezione Mappatura](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destinazione:
   * Cercare la destinazione e fare clic **[!UICONTROL Add Destination]**. Nota, la destinazione deve già esistere prima di aggiungerla a un segmento.
   * Fate clic **[!UICONTROL Save]** su di essa.

## Controlli del Generatore di segmenti: Sezione Informazioni di base {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder][!UICONTROL the Basic Information] , le impostazioni consentono di creare nuove caratteristiche o di modificare le caratteristiche esistenti. Per creare un nuovo segmento, fornisci un nome, un&#39;origine dati e seleziona una cartella di archiviazione. Tutti gli altri campi sono facoltativi. Passate alla [!UICONTROL Traits] sezione al termine.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Nome</b> </td> 
   <td colname="col2"> <p>Assegna al segmento un nome breve e logico che descrive la funzione o lo scopo. Evitare abbreviazioni e caratteri speciali. La lunghezza massima del nome di un segmento è 255 caratteri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Descrizione</b> </td> 
   <td colname="col2"> <p>Campo per ulteriori informazioni descrittive sul segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Codice integrazione</b> </td> 
   <td colname="col2"> <p>Campo per un ID definito dall'utente o altre informazioni specifiche della società. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Origine dati</b> </td> 
   <td colname="col2"> <p>Associa il segmento a un provider di dati specifico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regola unione profilo</b> </td> 
   <td colname="col2"> <p>Seleziona la Regola unione profilo da usare per la qualifica del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Stato</b> </td> 
   <td colname="col2"> <p>Attiva o disattiva il segmento (attivo per impostazione predefinita). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Archiviazione cartella</b> </td> 
   <td colname="col2"> <p>Determina la cartella di memorizzazione a cui appartiene il segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controlli del Generatore di segmenti: Sezione Caratteristiche {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], la [!UICONTROL Traits] sezione consente di gestire le caratteristiche in un segmento, creare gruppi di caratteristiche e impostare criteri di qualifica. Per aggiungere una caratteristica a un segmento, digita il nome della caratteristica nel campo di ricerca e fai clic [!UICONTROL Add Trait]su. Salvate la caratteristica (se effettuata) o passate [!UICONTROL Destinations Mapping]a.

<!-- r_segment_traits_section.xml -->

**Prerequisiti:** Compila i campi richiesti nella [!UICONTROL Basic Information] sezione.

| Campo | Descrizione |
|--- |--- |
| Visualizzazione di base | Questa sezione fornisce controlli visivi che consentono di: <ul><li>Crea nuovi segmenti e gestisci i segmenti esistenti.</li><li>Rimuovi caratteristiche da un segmento.</li><li>Aggiungete fino a 50 caratteristiche al segmento.</li><li>Trascinate le caratteristiche per creare nuovi gruppi.</li><li>Visualizza caratteristiche e gruppi di caratteristiche in un segmento.</li><li>Impostate criteri di qualifica con espressioni booleane, operatori di confronto e impostazioni recency/frequenza.</li></ul> |
| Vista Codice | Apre un ambiente di sviluppo che consente di creare e gestire caratteristiche, gruppi e requisiti di qualifica con codice anziché l&#39;interfaccia visiva. La vista Codice è utile se i segmenti sono: <ul><li>Contiene più di 50 caratteristiche in un singolo segmento. Nota: I segmenti sono limitati a 5000 caratteristiche (massimo).</li><li>Contiene molti gruppi di caratteristiche.</li><li>Requisiti di qualificazione complessi.</li></ul> |
| Cerca | Consente di trovare caratteristiche da aggiungere a un segmento. |
| Consigli | Ottenete consigli live per caratteristiche simili da aggiungere alla regola del segmento. Ulteriori informazioni in [Recommendations](trait-recommendations.md)(Raccomandazioni). |
| Dati Dimensione segmento reale e stimati | Consulta [Caratteristiche e dati demografici segmenti in Segment Builder](segment-builder-data.md)(Generatore segmenti). |

## Rimuovi caratteristiche da un segmento {#remove-traits}

La gestione delle caratteristiche nei segmenti è una fase importante per mantenere i segmenti validi. Per rimuovere tratti da un segmento, effettuate le seguenti operazioni.

Per rimuovere tratti da un segmento:

1. Vai a **Dati audience &gt; Segmenti**. Scorri l&#39;elenco o usa la funzione di ricerca per trovare il segmento con cui vuoi lavorare.
2. Fai clic sul nome del segmento per aprire la schermata dei dettagli del segmento.
3. Fai clic su **Modifica** per aprire Segment Builder (Generatore segmenti), quindi fai clic su **Traits (Caratteristiche)** per aprire il pannello delle caratteristiche.
4. Passate il puntatore del mouse sulla caratteristica da eliminare, quindi fate clic sulla X. Questa azione rimuove immediatamente la caratteristica dal segmento.

## Controlli del Generatore di segmenti: Sezione Mappature destinazioni {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], la sezione opzionale [!UICONTROL Destinations Mapping] consente di inviare dati di segmento a una destinazione di terze parti [!DNL cookie], [!DNL URL]o server-to-server. Per aggiungere una destinazione, cercare (o sfogliare) una destinazione, fornire informazioni specifiche sulla destinazione e fare clic **[!UICONTROL Add Destination]** su.

<!-- r_segment_destinations_map.xml -->

### Prerequisiti

Compila i campi richiesti nelle [!UICONTROL Basic Information][!UICONTROL Traits] sezioni e. Inoltre, la destinazione deve già esistere.

### Strumenti di ricerca delle mappature di destinazione

**[!UICONTROL Destination Mappings]** Il pannello contiene strumenti di ricerca come descritto nella tabella seguente.

| Tipo di ricerca | Descrizione |
|---|---|
| **Ricerca per nome destinazione** | Consente di cercare una destinazione specifica per nome. Per eseguire la ricerca, iniziate a digitare. Il campo viene compilato automaticamente in base ai termini di ricerca. Fate clic **[!UICONTROL Add Destination]** su di essa. |
| **Sfoglia tutte le destinazioni** | Sfogliate un elenco di *tutte* le destinazioni disponibili. Seleziona e aggiungi le destinazioni al tuo segmento dall&#39;elenco a comparsa. |

## Campi nella finestra a comparsa Mappature di destinazione {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], la [!UICONTROL Add Destination] finestra di dialogo viene visualizzata dopo la selezione di una destinazione. Questa finestra visualizza informazioni statiche sulla destinazione e sui campi che variano a seconda del tipo di destinazione. Fornite le informazioni richieste nei campi vuoti per impostare una mappatura di destinazione.

>[!NOTE]
>
>Le date di pubblicazione sono facoltative. Se vuota, la destinazione diventa attiva e non scade mai.

<!-- r_add_mappings_pop.xml -->

### Campi di destinazione cookie

Nei [!UICONTROL Destination Mapping] campi, specificate le coppie chiave-valore utilizzate per inviare i dati alla destinazione. Immettere la chiave nel primo campo e i valori della seconda. La destinazione del cookie potrebbe essere simile a quella riportata di seguito:

![](assets/cookie_modal.PNG)

### Campi destinazione URL

Nei campi [!UICONTROL URL] e [!UICONTROL Secure URL] specificate l&#39;indirizzo standard o protetto completo utilizzato per inviare i dati alla destinazione.

![](assets/url_modal.PNG)

### Campi di destinazione server-to-server

Nel [!UICONTROL Destination Value] campo specificare il valore (parte di una coppia chiave-valore) usato per inviare dati alla destinazione.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Creare una destinazione cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [Creare una destinazione URL](../../features/destinations/manage-destinations.md#configure-url-destination)

