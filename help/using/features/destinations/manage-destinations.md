---
description: Nella pagina Destinazione di destinazione sono elencati tutti i tuoi URL, cookie e destinazioni server-to-server. Offre funzioni per creare, modificare, cercare e generare rapporti sulle destinazioni. La pagina di destinazione si trova in Data Data > Destinations (Destinazioni).
seo-description: Nella pagina Destinazione di destinazione sono elencati tutti i tuoi URL, cookie e destinazioni server-to-server. Offre funzioni per creare, modificare, cercare e generare rapporti sulle destinazioni. La pagina di destinazione si trova in Data Data > Destinations (Destinazioni).
seo-title: Gestisci destinazioni
solution: Audience Manager
title: Gestisci destinazioni
uuid: 6 b 66 ff 42-0075-49 a 7-a 58 f -7 f 8 ea 2295 fdc
translation-type: tm+mt
source-git-commit: 1d516c49a16c38adcc22827dc254da1ebada0734

---


# Manage Destinations {#manage-destinations}

The [!UICONTROL Destination] landing page lists all of your [!DNL URL], cookie, and server-to-server destinations. Offre funzioni per creare, modificare, cercare e generare rapporti sulle destinazioni. The landing page is located in **[!UICONTROL Audience Data > Destinations]**.

## Default Landing Page {#default-landing-page}

<!-- destinations-home.xml -->

La pagina di destinazione predefinita elenca le destinazioni in base al tipo. Potete filtrare le destinazioni utilizzando le quattro schede disponibili:

* **Tutti**: mostra tutti i tipi di destinazioni.
* **Adobe Experience Cloud**: mostra le destinazioni che inviano dati ad altre soluzioni Adobe Experience Cloud. Attualmente, l'unica opzione supportata è Adobe Analytics. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **Piattaforme integrate**: mostra le destinazioni basate su dispositivo e basate su dispositivo (denominate anche destinazioni server-to-server). Le destinazioni basate su persone sono al momento disponibili solo per i clienti selezionati.
* **Personalizzato**: mostra le destinazioni di cookie e URL.


![](assets/destinations-landing.png)

## Addressable Audiences Landing Page {#audiences-landing-page}

To see audience data and match rates for your server-to-server destination, select **[!UICONTROL Integrated Platforms > Device-Based]**.

For more information about the displayed information, see [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] consente di creare una o più [!DNL URL] destinazioni basate su cookie. You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. Contact your consultant to set up a [!DNL S2S] destination. [!UICONTROL Destination Builder] si trova in **[!UICONTROL Audience Data > Destinations]**.

### Destination Builder Settings {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] sono costituite dalle seguenti sezioni e impostazioni:

| [!UICONTROL Destination Builder] Sezione | Finalità |
|--- |--- |
| Informazioni di base | Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]). |
| Configurazione | Includes controls for: <br/><ul><li>Passing in key-value data to [!DNL URL] destinations. È possibile inviare dati come coppie chiave-valore singole o serializzate. For details see, [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) and [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md). </li><li>Elementi di una destinazione cookie come nome del cookie, dominio, dimensione, intervallo di scadenza, formato dati, ecc.</li></ul> |
| Mappature segmento | Consente di: <br/><ul><li>Cercare, aggiungere e gestire segmenti associati a tutti i tipi di destinazione. </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul> |

### Data Delivery Methods {#data-delivery-methods}

Send information to a destination by passing it in through a [!DNL URL] string, by writing to a browser [!DNL cookie], or through offline server-to-server data transfers.

* [!DNL URL] e le destinazioni basate su cookie trasmettono i dati in modo sincrono, man mano che un utente utilizza una pagina.
* La trasmissione dei dati server-to-server è asincrona e può verificarsi molto dopo che un utente è uscito dalla pagina. Il tipo di consegna selezionato dipende dai requisiti aziendali e dal modo in cui un particolare partner di dati desidera o può ricevere dati.

See [How to Choose a Destination Type](../../features/destinations/destinations.md) for more information.

>[!MORE_ LIKE_ THIS]
>
>* [Creare una destinazione cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [Creare una destinazione URL](../../features/destinations/manage-destinations.md#configure-url-destination)


## Configure a Cookie Destination {#create-cookie-destination}

Una destinazione di cookie restituisce e scrive dati in un cookie nel browser dell'utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

To create a new cookie destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### Informazioni di base {#basic-information}

Questa sezione contiene campi e opzioni che avviano il processo di creazione di destinazione del cookie. Per completare questa sezione:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivete la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select **[!UICONTROL Browser]**. Non è possibile configurare le destinazioni dei cookie per ambienti mobili nativi, ad esempio app Android o iOS.
6. In the **[!UICONTROL Type]** list, click **[!UICONTROL Cookie]**.
7. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l'ID segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitata a 255 caratteri, massimo.
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-cookies}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a cookie destination. Ignorate questo passaggio se non utilizzate i controlli di esportazione dei dati. Per completare questa sezione:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Fai clic su **[!UICONTROL Save]**.

### Configurazione {#configuration}

Questa sezione contiene campi e opzioni che consentono di impostare il cookie per la destinazione.

>[!NOTE]
>
>[!DNL Audience Manager] codifica i dati scritti nel cookie di destinazione. For example, spaces are encoded as `%20` and semicolons are encoded as `%3B`.

Per completare questa sezione:

1. Click **[!UICONTROL Configuration]** to expose the controls
1. Denominate il cookie. Evitare abbreviazioni e caratteri speciali.
1. Scegliere un'opzione di formato dati. Queste opzioni consentono di scegliere i delimitatori e i separatori per le coppie chiave-valore che inviano dati di segmento a una destinazione. Le opzioni di formattazione includono:
   * **Chiave singola:** Consente di impostare la chiave in una coppia chiave-valore. You'll set the value after you select a segment in the [!UICONTROL Segment Mappings] section below.
   * **Chiave multipla:** Consente di impostare la chiave e il valore per una coppia chiave-valore. La coppia chiave-valore viene creata dopo aver selezionato un segmento nella sezione Mappature segmenti di seguito.
See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. Fai clic su **[!UICONTROL Save]**.

Tutte le altre impostazioni sono facoltative. For more information about the **[!UICONTROL Cookie Domain]** and **[!UICONTROL Publish data to]** settings, see [Optional Settings for Cookie Destinations](../../features/destinations/manage-destinations.md#optional-settings-cookies).

### Segment Mappings {#segments-mapping}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** to browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In the [!UICONTROL Edit Mapping] dialog:
   * **[!UICONTROL Mapping]** consente di impostare un valore per la chiave specificata nella sezione Configurazione di cui sopra.
   * **[!UICONTROL Publish from]** consente di impostare la data di inizio e di fine della destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Fai clic su **[!UICONTROL Save]**.
1. Fai clic su **[!UICONTROL Done]**.

## Configure a URL Destination {#configure-url-destination}

A [!DNL URL] destination makes pixel calls from a page to your destination. Follow these instructions to create a [!DNL URL] destination with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano il processo di creazione di destinazione URL. Per completare questa sezione:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
1. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
1. *(Facoltativo)* Descrivete la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
1. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
1. In the **[!UICONTROL Environment]** list, select the environment in which to trigger the URL destination.
1. In the **[!UICONTROL Type]** list, click **[!UICONTROL URL]**.
1. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l'ID segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitata a 255 caratteri, massimo.
1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-dest}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. Ignorate questo passaggio se non utilizzate i controlli di esportazione dei dati. Per completare questa sezione:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Fai clic su **[!UICONTROL Save]**.

### Configurazione {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. Questa sezione è facoltativa. Per completare questa sezione:

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(Facoltativo)* Selezionate la casella **[!UICONTROL Serialize]** di controllo.
Questo consente di inviare segmenti a una destinazione in sequenza anziché effettuare chiamate separate per ogni segmento. La serializzazione contribuisce a rendere efficiente i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatore. For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| Campo | Descrizione |
|--- |--- |
| URL di base | The base part of a standard `HTTP` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`  [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Esempio: `https://www.myCompany.com/%alias%...` |
| URL protetto | The base part of a secure `HTTPS` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`   [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Esempio: `https://www.myCompany.com/%alias%...` |
| Delimitatore | The symbol that separates the segment variables in the [!DNL URL] string. Solitamente si tratta di una virgola o di un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

### Segment Mappings {#segment-mappings}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fornite le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Fai clic su **[!UICONTROL Done]**.

### Optional Settings for Cookie Destinations {#optional-settings-cookies}

In [!UICONTROL Destination Builder], the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields. Queste consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] lavorare in modo indipendente e facoltativo. Potete creare una destinazione di cookie senza utilizzarne nessuno.

## Cookie Domain: Syntax and Examples {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dominio cookie </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sintassi</b> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Cookie Domain</span> field accepts a simple text string that lets you set cookies on a specified domain or all domains. Quando si utilizza questa funzione: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Imposta un solo dominio per ogni destinazione del cookie. Do not type multiple domains in the <span class="wintitle"> Cookie Domain</span> field. Create another <span class="wintitle"> Destination</span> instead. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Non utilizzate caratteri jolly. </li> 
     </ul> </p> <p> Leave the <span class="wintitle"> Cookie Domain</span> field blank to set a cookie on all domains. Questa è l'impostazione predefinita. </p> <p>Per impostare i cookie su un dominio e sottodomini specifici: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Type the name of the domain in the <span class="wintitle"> Cookie Domain</span> field. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inizia il nome di dominio con un punto. For example, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esempio</b> </p> </td> 
   <td colname="col2"> <p>Come esempio semplice, supponiamo di avere un sito fittizio denominato sport. com. Sports.com contiene domini per golf, baseball e football. To set a cookie in all the sports domains, you would type that in the <span class="wintitle"> Cookie Domain</span> box as shown below: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>This tells <span class="keyword"> Audience Manager</span> to set a cookie in any domain that contains the pattern <code><i>something</i></code>.sports.com. Consultate di seguito un set più complesso di esempi. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi di dominio cookie complessi

These examples show you if [!DNL Audience Manager] will set a cookie based on how the [!UICONTROL Cookie Domain] option is configured.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sito Web </th> 
   <th colname="col2" class="entry">Dominio cookie: .sports.com <p>Set cookie </p> </th> 
   <th colname="col3" class="entry">Dominio cookie: .golf.sports.com <p>Set cookie </p> </th> 
   <th colname="col4" class="entry">Dominio cookie: Vuoto <p>Set cookie </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> Sì </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> No </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> Sì </td> 
  </tr> 
 </tbody> 
</table>

## Publish Data To {#publish-data-to}

[!UICONTROL Publish Data To] Le impostazioni restituiscono un cookie se il dominio soddisfa i criteri impostati dalle opzioni selezionate. Le opzioni includono:

* **[!UICONTROL All of our domains]**: (Impostazione predefinita) Restituisce un [!DNL cookie] qualsiasi dominio.
* **[!UICONTROL Only the selected domains]**: Restituisce un cookie solo per i domini selezionati nell'elenco dei domini.
* **[!UICONTROL All of our domains except the selected domains]**: Impedisce ai domini selezionati di ricevere un [!DNL cookie]. All other domains can receive a [!DNL cookie].

>[!MORE_ LIKE_ THIS]
>
>* [Creare una destinazione cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)


## Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL Destination Builder]. Contact your consultant to set up [!DNL S2S] destinations. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

To add or edit segment mappings for an [!DNL S2S] destination:

1. **[!UICONTROL Audience Data > Destinations]** Vai a. Select **Integrated Platforms &gt; Device-Based** and find the [!DNL S2S] destination you want to work with.
1. In the [!UICONTROL Action] column, click the pencil icon to edit the destination.
   * In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   * In [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Impostare un valore per la coppia [chiave-valore](../../features/destinations/key-value-pairs.md) utilizzata da questa destinazione.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.

## Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] lavorare con il [!DNL Export Controls] set impostato su un'origine dati. [!DNL Data Export Labels] impedire l'aggiunta di caratteristiche limitate a un segmento e l'invio di dati di segmento a una destinazione. You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Fai clic su **[!UICONTROL Audience Data]**:
   * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
   * For existing destinations: Use the [!DNL Search] box to find your destination or scroll through the list and click on the destination name to open it.
1. Seleziona una [!DNL Data Export Label]. Lasciate vuote le caselle di controllo se non desiderate impostare restrizioni di esportazione. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Export restrictions will not work unless you set a [matching export control](../../features/data-export-controls.md) on a data source.
1. Fai clic su **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Creare un'origine dati](../../features/manage-datasources.md#create-data-source)

