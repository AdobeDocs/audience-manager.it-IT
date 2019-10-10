---
description: Descrive come creare segmenti con Segment Builder (Generatore di segmenti).
seo-description: Descrive come creare segmenti con Segment Builder (Generatore di segmenti).
seo-title: Generatore di segmenti
solution: Audience Manager
title: Generatore di segmenti
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: c7efca0cd13f0ca05d926e6675b74ef0170cbce1

---


# Generatore di segmenti {#segment-builder}

Descrive i passaggi obbligatori e facoltativi per creare un segmento in [!UICONTROL Segment Builder].

## Dimostrazione video

Per iniziare, guarda il video [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Crea segmenti in Audience Manager. Il video illustra il processo di creazione dei segmenti. Per ulteriori informazioni, consulta le sezioni riportate di seguito.

## Crea un segmento {#create-segment}

### Sezione Generatore di segmenti

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] è costituito da 3 sezioni distinte: [!UICONTROL Basic Information], [!UICONTROL Traits], e [!UICONTROL Destinations Mapping]. Per creare un segmento, completa i campi richiesti nelle [!UICONTROL Basic Information] sezioni e [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] sono facoltative. Per ulteriore assistenza, consulta le istruzioni riportate di seguito.

![create-segment](assets/create-segment.png)

1. Nella sezione [Informazioni](../../features/segments/segment-builder.md#segment-builder-controls-basics) di base:
   * Denominate il segmento. La lunghezza massima del nome di un segmento è di 255 caratteri.
   * Imposta lo stato del segmento (attivo è predefinito).
   * Scegliere un'origine dati. Usate il primo menu a discesa per filtrare tra le origini dati di Audience Manager, le suite di rapporti di Adobe Analytics o entrambe. Quindi, utilizzare il secondo menu a discesa per scegliere l'origine dati. Se non hai suite di rapporti Adobe Analytics, il selettore del tipo di origine dati è disabilitato e puoi visualizzare solo le tue origini dati Audience Manager.
   * Selezionare una regola di unione dei profili da utilizzare per la qualifica del segmento.
   * Assegnare il segmento a una cartella di archiviazione.
2. Nella sezione [Caratteristiche](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Cerca la caratteristica che desideri aggiungere a un segmento e fai clic su **[!UICONTROL Add Trait]**. Aggiungete un’altra caratteristica per creare un gruppo di caratteristiche.
   * Visualizzate la modalità Ricerca avanzata facendo clic su **[!UICONTROL Browse All Traits]**. Cerca caratteristiche per nome, ID, descrizione o origine dati. Fate clic su una cartella durante la ricerca per limitare i risultati a tale cartella e alle relative sottocartelle. Potete anche filtrare le caratteristiche per tipo di caratteristica.
   * Ricevi raccomandazioni sulle [caratteristiche](trait-recommendations.md) live mentre crei il tuo segmento.
   * Fate clic e trascinate le caratteristiche per creare gruppi separati.
   * Passa il puntatore del mouse tra i gruppi per impostare le relazioni con i valori booleani [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] .
   * Passa il cursore del mouse sull’icona dell’orologio per aggiungere regole di [aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) alla caratteristica.
   * Visualizzare i dati sulla popolazione del segmento quando si aggiungono o si rimuovono caratteristiche. Fare clic **[!UICONTROL Calculate Estimates]** per visualizzare (o aggiornare) i numeri di popolazione stimati. Ulteriori informazioni sui dati relativi alla popolazione dei [segmenti](../../features/segments/segment-builder-data.md#segment-populations) nel Generatore di segmenti.
   * Click **[!UICONTROL Save]** when done.
3. *(Facoltativo)* Mappare un segmento a una destinazione nella sezione Mappatura [](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destinazione:
   * Cerca la destinazione e fai clic su **[!UICONTROL Add Destination]**. Nota: la destinazione deve già esistere prima di poter essere aggiunta a un segmento.
   * Click **[!UICONTROL Save]** when done.

## Controlli Generatore di segmenti: Sezione Informazioni di base {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] le impostazioni consentono di creare caratteristiche nuove o di modificare quelle esistenti. Per creare un nuovo segmento, immetti un nome, un'origine dati e seleziona una cartella di archiviazione. Tutti gli altri campi sono facoltativi. Al termine, passare alla [!UICONTROL Traits] sezione.

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
   <td colname="col2"> <p>Assegna al segmento un nome logico breve che ne descrive funzione o finalità. Evitare abbreviazioni e caratteri speciali. La lunghezza massima del nome di un segmento è di 255 caratteri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Descrizione</b> </td> 
   <td colname="col2"> <p>Campo per ulteriori informazioni descrittive sul segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Codice integrazione</b> </td> 
   <td colname="col2"> <p>Campo per un ID definito dall’utente o altre informazioni specifiche per la società. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Origine dati</b> </td> 
   <td colname="col2"> <p>Associa il segmento a un fornitore di dati specifico. <p>Usate il primo menu a discesa per filtrare tra le origini dati di Audience Manager, le suite di rapporti di Adobe Analytics o entrambe. Quindi, utilizzare il secondo menu a discesa per scegliere l'origine dati.</p><p> Se non hai suite di rapporti Adobe Analytics, il selettore del tipo di origine dati è disabilitato e puoi visualizzare solo le tue origini dati Audience Manager.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regola di unione profilo</b> </td> 
   <td colname="col2"> <p>Seleziona la regola di unione profilo da utilizzare per la qualifica del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Stato</b> </td> 
   <td colname="col2"> <p>Attiva o disattiva il segmento (attivo per impostazione predefinita). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memorizzazione delle cartelle</b> </td> 
   <td colname="col2"> <p>Determina a quale cartella di archiviazione appartiene il segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controlli Generatore di segmenti: Sezione Caratteristiche {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], la [!UICONTROL Traits] sezione consente di gestire le caratteristiche di un segmento, creare gruppi di caratteristiche e impostare criteri di qualifica. Per aggiungere una caratteristica a un segmento, digita il nome della caratteristica nel campo di ricerca e fai clic [!UICONTROL Add Trait]. Salvate la caratteristica (se completata) o passate a [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**** Prerequisiti: Compila i campi richiesti nella [!UICONTROL Basic Information] sezione .

| Campo | Descrizione |
|--- |--- |
| Visualizzazione di base | Questa sezione contiene controlli visivi che consentono di: <ul><li>Crea nuovi segmenti e gestisci quelli esistenti.</li><li>Rimuove le caratteristiche da un segmento.</li><li>Aggiungi fino a 50 (massimo) caratteristiche a un segmento.</li><li>Trascinate le caratteristiche per creare nuovi gruppi.</li><li>Visualizzare caratteristiche e gruppi di caratteristiche in un segmento.</li><li>Impostate i criteri di qualifica con espressioni booleane, operatori di confronto e impostazioni di aggiornamento/frequenza.</li></ul> |
| Vista Codice | Apre un ambiente di sviluppo che consente di creare e gestire caratteristiche, gruppi e requisiti di qualifica con codice invece dell'interfaccia visiva. La vista Codice è utile se i segmenti: <ul><li>Contiene più di 50 caratteristiche in un singolo segmento. Nota: I segmenti sono limitati a 5000 caratteristiche (massimo).</li><li>Contiene molti gruppi di caratteristiche.</li><li>Avere requisiti di qualifica complessi.</li></ul> |
| Cerca | Consente di trovare caratteristiche da aggiungere a un segmento. |
| Consigli | Ottieni raccomandazioni live per caratteristiche simili da aggiungere alla regola del segmento. Ulteriori informazioni in [Recommendations](trait-recommendations.md)sulle caratteristiche. |
| Dati reali e stimati sulle dimensioni dei segmenti | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Rimozione di caratteristiche da un segmento {#remove-traits}

Gestire le caratteristiche nei segmenti è importante per mantenere i segmenti vitali. Per rimuovere le caratteristiche da un segmento, effettuate le seguenti operazioni.

Per rimuovere caratteristiche da un segmento:

1. Vai a Dati **audience &gt; Segmenti**. Scorrete l’elenco o utilizzate la funzione di ricerca per individuare il segmento con cui desiderate lavorare.
2. Fate clic sul nome del segmento per aprire la schermata dei dettagli del segmento.
3. Fai clic su **Modifica** per aprire Segment Builder (Generatore di segmenti), quindi fai clic su **Traits (Caratteristiche)** per aprire il pannello Traits (Caratteristiche).
4. Passate il puntatore del mouse sulla caratteristica da eliminare, quindi fate clic sulla X. Questa azione rimuove immediatamente la caratteristica dal segmento.

## Controlli Generatore di segmenti: Sezione Mappature destinazioni {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], la [!UICONTROL Destinations Mapping] sezione facoltativa consente di inviare i dati del segmento a una destinazione di terze parti [!DNL cookie], [!DNL URL]o da server a server. Per aggiungere una destinazione, cercare (o sfogliare), fornire informazioni specifiche sulla destinazione e fare clic **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Prerequisiti

Compila i campi richiesti nelle sezioni [!UICONTROL Basic Information] e [!UICONTROL Traits] . Inoltre, la destinazione deve già esistere.

### Strumenti di ricerca Mappature di destinazione

Il **[!UICONTROL Destination Mappings]** pannello contiene gli strumenti di ricerca come descritto nella tabella seguente.

| Tipo di ricerca | Descrizione |
|---|---|
| **Ricerca per nome destinazione** | Consente di cercare una destinazione specifica per nome. Per effettuare una ricerca, iniziate a digitare. Il campo verrà completato automaticamente in base ai termini di ricerca. Click **[!UICONTROL Add Destination]** when done. |
| **Sfoglia tutte le destinazioni** | Sfoglia un elenco di *tutte* le destinazioni disponibili. Seleziona e aggiungi destinazioni al segmento dall’elenco a comparsa. |

## Campi nelle finestre a comparsa Mappature di destinazione {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], dopo aver selezionato una destinazione viene visualizzata [!UICONTROL Add Destination] la finestra di dialogo. Questa finestra visualizza informazioni statiche sulla destinazione e sui campi che variano a seconda del tipo di destinazione. Fornire le informazioni richieste nei campi vuoti per impostare una mappatura di destinazione.

>[!NOTE]
>
>Le date di pubblicazione sono facoltative. Quando è vuota, la destinazione diventa attiva e non scade mai.

<!-- r_add_mappings_pop.xml -->

### Campi di destinazione cookie

Nei [!UICONTROL Destination Mapping] campi, specificare le coppie chiave-valore utilizzate per inviare i dati alla destinazione. Immettere la chiave nel primo campo e i valori nel secondo. Il pop di destinazione dei cookie potrebbe essere simile al seguente:

![](assets/cookie_modal.PNG)

### Campi di destinazione URL

Nei campi [!UICONTROL URL] e [!UICONTROL Secure URL] , specificare l'indirizzo standard o protetto completo utilizzato per inviare i dati alla destinazione.

![](assets/url_modal.PNG)

### Campi di destinazione da server a server

Nel [!UICONTROL Destination Value] campo specificare il valore (parte di una coppia chiave-valore) utilizzato per inviare i dati alla destinazione.

![](assets/s2s_modal.PNG)

>[!MORE_LIKE_this]
>
>* [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md)
>* [Creare una destinazione URL](../../features/destinations/create-url-destination.md)

