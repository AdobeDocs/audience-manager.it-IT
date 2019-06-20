---
description: Un file di metadati collega gli ID numerici con i nomi che è possibile leggere e comprendere. I rapporti sull'ottimizzazione dell'audience visualizzano nomi leggibili nei vari menu delle opzioni del rapporto.
seo-description: Un file di metadati collega gli ID numerici con i nomi che è possibile leggere e comprendere. I rapporti sull'ottimizzazione dell'audience visualizzano nomi leggibili nei vari menu delle opzioni del rapporto.
seo-title: Panoramica e mappature per i file di metadati
solution: Audience Manager
title: Panoramica e mappature per i file di metadati
uuid: 70 df 7 f 11-69 c 5-4873-a 69 d -8 f 93 f 94 e 9837
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Panoramica e mappature per i file di metadati{#overview-and-mappings-for-metadata-files}

Un file di metadati collega gli ID numerici con i nomi che è possibile leggere e comprendere. I rapporti sull&#39;ottimizzazione dell&#39;audience visualizzano nomi leggibili nei vari menu delle opzioni del rapporto.

## Panoramica {#overview}

Una revisione dei metadati e la modalità di utilizzo. Un file di metadati deve essere accompagnato da un file di dati. I contenuti dei file di metadati corrispondono alle informazioni sui file di dati per etichette pertinenti e comprensibili all&#39;utente nei menu dei rapporti. Per ulteriori informazioni, vedi [File di dati per report di ottimizzazione pubblico](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### I file di metadati contengono dati su altri dati

Un file di metadati contiene informazioni su altri tipi di dati. Per capire come funziona, vediamo come [!DNL Audience Manager] ricevere i dati.

Durante un evento impression o clic [!DNL Audience Manager] , riceve i dati in una stringa URL nota come chiamata *dell&#39;evento*.

La chiamata evento organizza le informazioni in set di coppie chiave-valore definite. I valori in una coppia chiave-valore contengono dati numerici. Il file di metadati contiene nomi e altre informazioni leggibili corrispondenti all&#39;ID in ciascuna coppia chiave-valore.

### ID collegamenti metadati a nomi leggibili

Il file di metadati è richiesto per collegare un ID numerico a un nome leggibile. Ad esempio, supponiamo che una chiamata all&#39;evento contenga un ID creativo in una coppia chiave-valore come questa: `d_creative:1234`. Senza un file di metadati, questa creativa viene visualizzata come 1234 in un menu delle opzioni.

Tuttavia, un file di metadati formattato correttamente può collegare questo elemento creativo a un nome reale come «Inserzionista A», un nome che potete leggere e riconoscere in un rapporto.

### Quando è necessario un file di metadati

Innanzitutto, un file di metadati e tutti i parametri elencati di seguito sono obbligatori in una chiamata dell&#39;evento quando si desidera utilizzare i report di ottimizzazione [dell&#39;audience](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

In secondo luogo, è necessario un file di metadati se si inviano dati personalizzati o [!DNL Audience Manager] se si desidera visualizzare i dati nei report di altri fornitori con i quali non siamo integrati. Ad esempio, [!DNL Audience Manager] con un&#39;integrazione con [il DCM (Campaign Manager, Gestione campagne)](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) di Google. A causa di questa relazione, [!DNL Audience Manager] può associare ID con nomi e descrizioni utilizzate dalle opzioni del report. Senza un&#39;integrazione, possiamo comunque assimilare i dati, ma le opzioni del rapporto mostreranno ID numerici invece di nomi descrittivi.

![](assets/metadata_menu.png)

## Mappature file {#file-mappings}

Nella tabella seguente sono elencate le coppie chiave-valore che contengono i dati utilizzati dai [!UICONTROL Audience Optimization] report. Se è necessario utilizzare un file di metadati, contiene informazioni leggibili dall&#39;uomo corrispondenti ai valori in queste coppie chiave-valore. I valori di queste chiavi accettano solo i numeri interi (tipo di dati INT). Nota, *il corsivo* indica un segnaposto variabile. Altri elementi sono costanti o chiavi e non cambiano.

>[!IMPORTANT]
>
>Se utilizzate [!UICONTROL Audience Optimization] i rapporti, *tutti* questi valori sono obbligatori nella chiamata dell&#39;evento.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione Rapporto </th> 
   <th colname="col2" class="entry"> Coppie chiave-valore </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Inserzionista </p> </td> 
   <td colname="col2"> <p> <code>d_ adsrc = <i>ID origine dati o codice integrazione</i></code> </p> <p>Si tratta dell'ID di origine dati dell'inserzionista o del codice di integrazione fornito durante la creazione di un'origine dati. Consultate <a href="../../../features/manage-datasources.md#create-data-source"> Creare un'origine dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Business Unit (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_ bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campagna </p> </td> 
   <td colname="col2"> <p> <code>d_ campaign = <i>ID campagna</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_ creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Accetta due coppie chiave-valore diverse: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_ exchange = <i>ID per lo scambio che ha servito l'annuncio</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_ site = <i>ID per il sito un annuncio attivato</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordine di inserimento (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_ io = <i>ID ordine di inserimento</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Piattaforma </p> </td> 
   <td colname="col2"> <p> <code>d_ src = <i>ID origine dati</i></code> </p> <p>Si tratta dell' <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> ID di origine</a> dati per la piattaforma che fornisce informazioni sui metadati (ad es. DFA, Atlas, GBM, mediamath ecc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic </p> </td> 
   <td colname="col2"> <p> <code>d_ tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verticale </p> </td> 
   <td colname="col2"> <p> <code>d_ vert = <i>ID verticale</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come denominare i nomi dei file, i contenuti e i percorsi di consegna della forma degli eventi {#how-ids-shape-file-names}

Gli ID passati da queste coppie chiave-valore contribuiscono a creare il nome del file di metadati e il relativo contenuto. Le sezioni e le illustrazioni seguenti spiegano come funziona. Questi esempi creano un file che contiene il nome di un elemento creativo in una campagna, ma sono possibili altre combinazioni.

### Chiamata evento

In questo esempio creeremo un file di metadati che porta i nomi creativi in un [!UICONTROL Audience Optimization] report. A tal fine, è necessario estrarre gli ID creativi, campagna e dati di dati da una chiamata evento.

![](assets/metadata_file_event.png)

### Nome file

Il nome del file è basato sugli ID creativi, di campagna e di dati. In questo caso, confrontate le differenze tra i dati chiave-valore in una chiamata dell&#39;evento e come viene utilizzato nel nome di un file.

Nel nome di un file:

* La chiave di origine dati cambia a `dpid` partire `d_src`da.

* Gli ID creativi e delle campagne rappresentano una categoria piuttosto che un identificatore effettivo.

![](assets/metadata_file_name.png)

Consultate [Convenzioni di denominazione per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Contenuto file

In questo esempio, il contenuto del file riflette gli ID creativi e campagna passati sulla chiamata dell&#39;evento. Il nuovo elemento è leggibile. Una volta elaborati, il nome in questo file verrà visualizzato come opzione nel menu Creativo di un [!UICONTROL Audience Optimization] report.

![](assets/metadata_file_contents.png)

Consultate [Formato contenuto per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Consegna file

Dopo aver assegnato un nome e aggiunto dati a un file, lo potete inviare a una directory di archiviazione Amazon S 3 fornita da [!DNL Audience Manager]. Consultate [Metodi di consegna per file metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md) e [aggiornamenti dello stato per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md).

>[!MORE_ LIKE_ THIS]
>
>* [File di dati per report di ottimizzazione pubblico](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Acquisizione di dati su una campagna tramite chiamate pixel](../../../integration/media-data-integration/click-data-pixels.md)
>* [Acquisizione dei dati di impressione della campagna attraverso Pixel Calls (Chiamate pixel)](../../../integration/media-data-integration/impression-data-pixels.md)

