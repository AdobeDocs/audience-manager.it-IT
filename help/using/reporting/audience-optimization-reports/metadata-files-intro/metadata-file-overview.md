---
description: Un file di metadati collega gli ID numerici con nomi che puoi leggere e comprendere. Nei rapporti di Audience Optimization vengono visualizzati nomi leggibili nei vari menu delle opzioni dei rapporti.
seo-description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-title: Overview and Mappings for Metadata Files
solution: Audience Manager
title: Panoramica e mappature dei file di metadati
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 3%

---

# Panoramica e mappature dei file di metadati{#overview-and-mappings-for-metadata-files}

Un file di metadati collega gli ID numerici con nomi che puoi leggere e comprendere. Nei rapporti di Audience Optimization vengono visualizzati nomi leggibili nei vari menu delle opzioni dei rapporti.

## Panoramica {#overview}

Revisione dei metadati e del loro utilizzo. Un file di metadati deve essere accompagnato da un file di dati. Il contenuto del file di metadati corrisponde alle informazioni del file di dati con le relative etichette leggibili dall&#39;utente nei menu del report. Per ulteriori informazioni, consulta [File di dati per report di Audience Optimization e file di registro fruibili](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### I File Di Metadati Contengono Dati Su Altri Dati

Un file di metadati contiene informazioni su altri tipi di dati. Per aiutarti a capire come funziona, rivediamo come [!DNL Audience Manager] riceve dati.

Durante un evento di impression o clic, [!DNL Audience Manager] riceve dati in una stringa URL nota come *chiamata evento*.

La chiamata dell&#39;evento organizza le informazioni in set di coppie chiave-valore definite. I valori in una coppia chiave-valore contengono dati numerici. Il file di metadati contiene nomi e altre informazioni leggibili corrispondenti all’ID in ogni coppia chiave-valore.

### Metadati Collega gli ID ai nomi leggibili

Il file di metadati è necessario per collegare un ID numerico a un nome leggibile. Ad esempio, supponiamo che una chiamata evento contenga un ID creativo in una coppia chiave-valore come questa: `d_creative:1234`. Senza un file di metadati, questo contenuto creativo verrebbe visualizzato come 1234 in un menu di opzioni.

Tuttavia, un file di metadati formattato correttamente può ricollegare questo contenuto creativo a un nome reale come &quot;Inserzionista Creativo A&quot;, che è un nome che puoi leggere e riconoscere in un rapporto.

### Quando è necessario un file di metadati

In primo luogo, un file di metadati e tutti i parametri elencati di seguito sono necessari in una chiamata evento quando desideri utilizzare [Rapporti di Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

In secondo luogo, se invii dati personali a, devi disporre di un file di metadati [!DNL Audience Manager] oppure se desideri visualizzare i dati nei rapporti di altri provider con cui non siamo integrati. Ad esempio: [!DNL Audience Manager] ha un’integrazione con Google [Fai doppio clic su Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM) A causa di questa relazione, [!DNL Audience Manager] può associare gli ID ai nomi e alle descrizioni utilizzati dalle opzioni del rapporto. Senza un’integrazione, possiamo comunque acquisire i dati, ma le opzioni del rapporto mostreranno gli ID numerici invece del nome descrittivo.

![immagine del menu metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## Mappature file {#file-mappings}

Nella tabella seguente sono elencate le coppie chiave-valore che contengono i dati utilizzati da [!UICONTROL Audience Optimization] rapporti. Se devi utilizzare un file di metadati, questo conterrà informazioni leggibili dagli utenti che corrispondono ai valori in queste coppie chiave-valore. I valori di queste chiavi accettano solo numeri interi (tipo di dati INT). Nota: *corsivo* indica un segnaposto variabile. Gli altri elementi sono costanti o chiavi e non cambiano.

>[!IMPORTANT]
>
>Se utilizzi il [!UICONTROL Audience Optimization] rapporti, *tutto* di questi valori sono necessari nella chiamata dell’evento.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione report </th> 
   <th colname="col2" class="entry"> Coppie chiave-valore metadati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Inserzionista </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Questo è l’ID sorgente dati o il codice di integrazione fornito dall’inserzionista al momento della creazione di un’origine dati. Consulta <a href="../../../features/manage-datasources.md#create-data-source"> Creare un’origine dati</a>. </p> </td> 
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
   <td colname="col2"> <p>Accetta 2 coppie chiave-valore diverse: </p> 
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
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Questo è il <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> origine dati</a> ID della piattaforma che fornisce informazioni sui metadati (ad esempio, DFA, Atlas, GBM, MediaMath, ecc.). </p> </td> 
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

## Forma degli ID chiamata evento per nomi, contenuti e percorsi di consegna dei file {#how-ids-shape-file-names}

Gli ID trasmessi da queste coppie chiave-valore aiutano a creare il nome e il contenuto del file di metadati. Le sezioni e le illustrazioni seguenti illustrano il funzionamento di questa funzione. Questi esempi creano un file che contiene il nome di un contenuto creativo in una campagna, ma sono possibili altre combinazioni.

### Chiamata evento

In questo esempio creeremo un file di metadati che porta nomi creativi in un [!UICONTROL Audience Optimization] rapporto. A tal fine, è necessario estrarre gli ID creativi, delle campagne e delle origini dati da una chiamata dell’evento.

![immagine chiamata evento](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### Nome file

Il nome del file si basa sugli ID creativi, della campagna e dell’origine dati. In questo caso, confronta le differenze tra i dati chiave-valore in una chiamata evento e il modo in cui vengono utilizzati in un nome file.

In un nome di file:

* La chiave dell’origine dati viene modificata in `dpid` da `d_src`.

* Gli ID creativi e della campagna rappresentano una categoria anziché un identificatore effettivo.

![come viene creato un nome di file](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

Consulta [Convenzioni di denominazione per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Contenuto file

In questo esempio, il contenuto del file riflette gli ID creativi e della campagna trasmessi durante la chiamata dell’evento. Il nuovo elemento qui è un nome leggibile. Una volta elaborato, il nome in questo file apparirà come opzione nel menu Creativo di un [!UICONTROL Audience Optimization] rapporto.

![contenuto di un file di metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

Consulta [Formato contenuto per file metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Consegna dei file

Dopo aver denominato e aggiunto i dati a un file, inviali a una directory di archiviazione Amazon S3 fornita da [!DNL Audience Manager]. Consulta [Metodi di distribuzione dei file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [File di dati per report di Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Acquisizione dei dati di clic delle campagne attraverso chiamate pixel](../../../integration/media-data-integration/click-data-pixels.md)
>* [Acquisizione dei dati di impression delle campagne attraverso chiamate pixel](../../../integration/media-data-integration/impression-data-pixels.md)

