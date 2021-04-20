---
description: Un file di metadati collega gli ID numerici con nomi leggibili e comprensibili. Nei rapporti di Audience Optimization vengono visualizzati nomi leggibili nei menu delle varie opzioni del rapporto.
seo-description: Un file di metadati collega gli ID numerici con nomi leggibili e comprensibili. Nei rapporti di Audience Optimization vengono visualizzati nomi leggibili nei menu delle varie opzioni del rapporto.
seo-title: Panoramica e mappature dei file di metadati
solution: Audience Manager
title: Panoramica e mappature dei file di metadati
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 4%

---

# Panoramica e mappature dei file di metadati{#overview-and-mappings-for-metadata-files}

Un file di metadati collega gli ID numerici con nomi leggibili e comprensibili. Nei rapporti di Audience Optimization vengono visualizzati nomi leggibili nei menu delle varie opzioni del rapporto.

## Panoramica {#overview}

Revisione dei metadati e del loro utilizzo. Un file di metadati deve essere accompagnato da un file di dati. Il contenuto dei file di metadati corrisponde alle informazioni sui file di dati alle relative etichette leggibili dagli utenti nei menu dei rapporti. Per ulteriori informazioni, consulta [File di dati per rapporti di Audience Optimization e file di registro fruibili](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### I File Di Metadati Contengono Dati Su Altri Dati

Un file di metadati contiene informazioni su altri tipi di dati. Per comprendere come funziona, esaminiamo in che modo [!DNL Audience Manager] riceve i dati.

Durante un evento impression o clic, [!DNL Audience Manager] riceve i dati in una stringa URL nota come *chiamata evento*.

La chiamata dell&#39;evento organizza le informazioni in set di coppie chiave-valore definite. I valori di una coppia chiave-valore contengono dati numerici. Il file di metadati contiene nomi e altre informazioni leggibili corrispondenti all&#39;ID in ogni coppia chiave-valore.

### ID dei collegamenti ai metadati in nomi leggibili

Il file di metadati è necessario per collegare un ID numerico a un nome leggibile. Ad esempio, supponiamo che una chiamata evento contenga un ID creativo in una coppia chiave-valore come questa: `d_creative:1234`. Senza un file di metadati, questo creativo apparirebbe a 1234 in un menu di opzioni.

Tuttavia, un file di metadati formattato correttamente può collegare questo creativo a un nome reale come &quot;Advertiser Creative A&quot;, che è un nome che si può leggere e riconoscere in un rapporto.

### Quando è necessario un file di metadati

Innanzitutto, un file di metadati e tutti i parametri elencati di seguito sono necessari in una chiamata dell&#39;evento quando desideri utilizzare i [Report di Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

In secondo luogo, è necessario un file di metadati se invii dati personali a [!DNL Audience Manager] o se desideri visualizzare i dati nei rapporti di altri provider con cui non siamo integrati. Ad esempio, [!DNL Audience Manager] dispone di un’integrazione con Google [Fare doppio clic su Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). A causa di questa relazione, [!DNL Audience Manager] può associare gli ID con i nomi e le descrizioni utilizzati dalle opzioni del rapporto. Senza un’integrazione, possiamo comunque acquisire i dati, ma le opzioni del rapporto mostrano ID numerici invece di un nome descrittivo.

![immagine del menu metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## Mappature file {#file-mappings}

Nella tabella seguente sono elencate le coppie chiave-valore che contengono i dati utilizzati dai rapporti [!UICONTROL Audience Optimization] . Se devi utilizzare un file di metadati, questo conterrà informazioni leggibili dall’utente che corrispondono ai valori di queste coppie chiave-valore. I valori per queste chiavi accettano solo numeri interi (tipo di dati INT). Nota: *corsivo* indica un segnaposto variabile. Gli altri elementi sono costanti o chiavi e non cambiano.

>[!IMPORTANT]
>
>Se utilizzi i rapporti [!UICONTROL Audience Optimization] , nella chiamata dell’evento è richiesto *all* di questi valori.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione rapporto </th> 
   <th colname="col2" class="entry"> Coppie chiave-valore metadati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Inserzionista </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Si tratta dell’ID sorgente dati dell’inserzionista o del codice di integrazione fornito durante la creazione di un’origine dati. Consulta <a href="../../../features/manage-datasources.md#create-data-source"> Creare un'origine dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Business Unit (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campagna </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creativo </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Accetta 2 diverse coppie chiave-valore: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordine di inserimento (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Piattaforma </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Si tratta dell’ <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> origine dati</a> ID per la piattaforma che fornisce informazioni sui metadati (ad esempio, DFA, Atlas, GBM, MediaMath, ecc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tattico </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verticale </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come gli ID delle chiamate evento formano i nomi dei file, i contenuti e i percorsi di consegna {#how-ids-shape-file-names}

Gli ID trasmessi da queste coppie chiave-valore aiutano a creare il nome del file di metadati e il relativo contenuto. Le sezioni e le illustrazioni seguenti mostrano come funziona. Questi esempi creano un file che contiene il nome di un elemento creativo in una campagna, ma sono possibili altre combinazioni.

### Chiamata evento

In questo esempio creeremo un file di metadati che include nomi creativi in un rapporto [!UICONTROL Audience Optimization]. A questo scopo, è necessario estrarre ID creativi, di campagne e di origini dati da una chiamata dell’evento.

![immagine chiamata evento](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### Nome file

Il nome del file si basa sugli ID creativi, della campagna e dell’origine dati. In questo caso, confronta le differenze tra i dati chiave-valore in una chiamata evento e il modo in cui vengono utilizzati in un nome file.

In un nome file:

* La chiave dell&#39;origine dati diventa `dpid` da `d_src`.

* Gli ID creativi e di campagna rappresentano una categoria anziché un identificatore effettivo.

![come viene creato un nome file](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

Consulta [Convenzioni di denominazione per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Contenuto del file

In questo esempio, il contenuto del file riflette gli ID creativi e di campagna trasmessi nella chiamata dell’evento. Il nuovo elemento è un nome leggibile. Una volta elaborato, il nome in questo file verrà visualizzato come opzione nel menu Creative di un rapporto [!UICONTROL Audience Optimization].

![contenuto di un file di metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

Consulta [Formato del contenuto per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Consegna file

Dopo aver assegnato un nome e aggiunto i dati a un file, lo si invia a una directory di archiviazione Amazon S3 fornita da [!DNL Audience Manager]. Consulta [Metodi di consegna per file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [File di dati per report di Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Acquisizione dei dati di clic delle campagne attraverso chiamate pixel](../../../integration/media-data-integration/click-data-pixels.md)
>* [Acquisizione dei dati di impression delle campagne attraverso chiamate pixel](../../../integration/media-data-integration/impression-data-pixels.md)

