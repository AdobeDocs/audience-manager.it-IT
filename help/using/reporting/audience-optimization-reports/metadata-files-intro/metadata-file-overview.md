---
description: Un file di metadati collega gli ID numerici con nomi comprensibili e leggibili. I rapporti sugli Audienci Optimization di  visualizzano nomi leggibili nei menu delle varie opzioni per i rapporti.
seo-description: Un file di metadati collega gli ID numerici con nomi comprensibili e leggibili. I rapporti sugli Audienci Optimization di  visualizzano nomi leggibili nei menu delle varie opzioni per i rapporti.
seo-title: Panoramica e mappature dei file di metadati
solution: Audience Manager
title: Panoramica e mappature dei file di metadati
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: log files
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 4%

---


# Panoramica e mappature dei file di metadati{#overview-and-mappings-for-metadata-files}

Un file di metadati collega gli ID numerici con nomi comprensibili e leggibili. I rapporti sugli Audienci Optimization di  visualizzano nomi leggibili nei menu delle varie opzioni per i rapporti.

## Panoramica {#overview}

Una revisione dei metadati e di come vengono utilizzati. Un file di metadati deve essere accompagnato da un file di dati. I contenuti dei file di metadati corrispondono alle informazioni sui file di dati e alle relative etichette leggibili dai menu dei report. Per ulteriori informazioni, vedere [File di dati per  Audienci Optimization e file](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)di registro fruibili.

### I File Di Metadati Contengono Dati Su Altri Dati

Un file di metadati contiene informazioni su altri tipi di dati. Per aiutarti a capire come funziona, vediamo in che modo [!DNL Audience Manager] ricevono i dati.

Durante un evento impression o clic, [!DNL Audience Manager] riceve i dati in una stringa URL nota come chiamata *di* evento.

La chiamata dell’evento organizza le informazioni in set di coppie chiave-valore definite. I valori di una coppia chiave-valore contengono dati numerici. Il file di metadati contiene nomi e altre informazioni leggibili corrispondenti all&#39;ID in ciascuna coppia chiave-valore.

### ID dei collegamenti ai metadati per nomi leggibili

Il file di metadati è necessario per associare un ID numerico a un nome leggibile. Ad esempio, supponiamo che una chiamata evento contenga un ID creativo in una coppia chiave-valore come questa: `d_creative:1234`. Senza un file di metadati, questo creativo apparirebbe a 1234 in un menu delle opzioni.

Tuttavia, un file di metadati formattato correttamente può collegare questo creativo a un nome reale come &quot;Advertiser Creative A&quot;, un nome che potete leggere e riconoscere in un rapporto.

### Quando hai bisogno di un file di metadati

Innanzitutto, un file di metadati e tutti i parametri elencati di seguito sono richiesti in una chiamata dell&#39;evento quando si desidera utilizzare i Rapporti [sugli Audienci Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

In secondo luogo, è necessario un file di metadati se si inviano dati personali [!DNL Audience Manager] o se si desidera visualizzare i dati nei rapporti di altri fornitori con cui non siamo integrati. Ad esempio, [!DNL Audience Manager] dispone di un&#39;integrazione con Google’s [Double-click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). Grazie a questa relazione, [!DNL Audience Manager] è possibile associare gli ID ai nomi e alle descrizioni utilizzati dalle opzioni del rapporto. Senza un&#39;integrazione, è comunque possibile acquisire i dati, ma le opzioni del rapporto mostreranno ID numerici invece del nome descrittivo.

![](assets/metadata_menu.png)

## Mappature file {#file-mappings}

Nella tabella seguente sono elencate le coppie chiave-valore che contengono i dati utilizzati dai [!UICONTROL Audience Optimization] report. Se è necessario utilizzare un file di metadati, questo contiene informazioni leggibili dall&#39;utente che corrispondono ai valori di queste coppie chiave-valore. I valori di queste chiavi accettano solo numeri interi (tipo di dati INT). Note, *italics* indicates a variable placeholder. Gli altri elementi sono costanti o chiavi e non vengono modificati.

>[!IMPORTANT]
>
>Se utilizzate i [!UICONTROL Audience Optimization] rapporti, *tutti* questi valori sono richiesti nella chiamata dell&#39;evento.

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
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Si tratta dell'ID origine dati dell'inserzionista o del codice di integrazione fornito durante la creazione di un'origine dati. See <a href="../../../features/manage-datasources.md#create-data-source"> Create a Data Source</a>. </p> </td> 
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
   <td colname="col1"> <p>Creative </p> </td> 
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
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Si tratta dell'ID origine <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"></a> dati per la piattaforma che fornisce informazioni sui metadati (ad esempio, DFA, Atlas, GBM, MediaMath, ecc.). </p> </td> 
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

## Come gli ID delle chiamate evento definiscono i nomi dei file, il contenuto e i percorsi di consegna {#how-ids-shape-file-names}

Gli ID trasmessi da queste coppie chiave-valore aiutano a creare il nome del file di metadati e il relativo contenuto. Le sezioni e le illustrazioni seguenti illustrano come funziona. Questi esempi creano un file che contiene il nome di un creativo in una campagna, ma altre combinazioni sono possibili.

### Chiamata evento

In questo esempio creeremo un file di metadati che inserirà nomi creativi in un [!UICONTROL Audience Optimization] rapporto. A tal fine, è necessario estrarre gli ID creativi, delle campagne e delle origini dati da una chiamata all&#39;evento.

![](assets/metadata_file_event.png)

### Nome file

Il nome del file è basato sugli ID creativi, della campagna e dell’origine dati. In questo caso, confrontate le differenze tra i dati chiave-valore presenti in una chiamata dell&#39;evento e il modo in cui vengono utilizzati in un nome file.

In un nome file:

* La chiave dell&#39;origine dati diventa `dpid` da `d_src`.

* Gli ID creativi e della campagna rappresentano una categoria anziché un identificatore effettivo.

![](assets/metadata_file_name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Sommario file

In questo esempio, il contenuto del file riflette gli ID creativi e della campagna trasmessi durante la chiamata dell’evento. Il nuovo elemento è un nome leggibile. Una volta elaborato, il nome in questo file verrà visualizzato come opzione nel menu Creative di un [!UICONTROL Audience Optimization] rapporto.

![](assets/metadata_file_contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Consegna file

Dopo aver assegnato un nome e aggiunto dati a un file, lo si invia a una directory di memorizzazione Amazon S3  fornita da [!DNL Audience Manager]. See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [File di dati per i rapporti  Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Acquisizione dei dati di clic delle campagne attraverso chiamate pixel](../../../integration/media-data-integration/click-data-pixels.md)
>* [Acquisizione dei dati di impression delle campagne attraverso chiamate pixel](../../../integration/media-data-integration/impression-data-pixels.md)

