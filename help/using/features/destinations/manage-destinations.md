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


# Gestisci destinazioni {#manage-destinations}

La [!UICONTROL Destination] pagina di destinazione elenca tutti i cookie [!DNL URL], i cookie e le destinazioni server-to-server. Offre funzioni per creare, modificare, cercare e generare rapporti sulle destinazioni. La pagina di destinazione si trova in **[!UICONTROL Audience Data > Destinations]**.

## Pagina di destinazione predefinita {#default-landing-page}

<!-- destinations-home.xml -->

La pagina di destinazione predefinita elenca le destinazioni in base al tipo. Potete filtrare le destinazioni utilizzando le quattro schede disponibili:

* **Tutti**: mostra tutti i tipi di destinazioni.
* **Adobe Experience Cloud**: mostra le destinazioni che inviano dati ad altre soluzioni Adobe Experience Cloud. Attualmente, l&#39;unica opzione supportata è Adobe Analytics. Consultate [Configurare una destinazione di Analytics](/help/using/features/destinations/create-analytics-destination.md).
* **Piattaforme integrate**: mostra le destinazioni basate su dispositivo e basate su dispositivo (denominate anche destinazioni server-to-server). Le destinazioni basate su persone sono al momento disponibili solo per i clienti selezionati.
* **Personalizzato**: mostra le destinazioni di cookie e URL.


![](assets/destinations-landing.png)

## Pagina di destinazione pubblico indirizzabile {#audiences-landing-page}

Per visualizzare i dati del pubblico e le percentuali di corrispondenza per la destinazione server-to-server, seleziona **[!UICONTROL Integrated Platforms > Device-Based]**.

Per ulteriori informazioni sulle informazioni visualizzate, consulta [Interfaccia di pubblico di riferimento](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Generatore di destinazione {#destination-builder}

[!UICONTROL Destination Builder] consente di creare una o più [!DNL URL] destinazioni basate su cookie. Non è possibile creare destinazioni server-to-server con[!DNL S2S][!UICONTROL Destination Builder], ma è possibile gestirne le mappature dei segmenti. Contatta il tuo consulente per configurare [!DNL S2S] una destinazione. [!UICONTROL Destination Builder] si trova in **[!UICONTROL Audience Data > Destinations]**.

### Impostazioni di Generatore di destinazione {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] sono costituite dalle seguenti sezioni e impostazioni:

| [!UICONTROL Destination Builder] Sezione | Finalità |
|--- |--- |
| Informazioni di base | Utilizzato per denominare la destinazione, descriverla e selezionare tipo di destinazione ([!DNL URL] o [!DNL cookie]) e piattaforma (tutto [!DNL Android], browser o [!DNL iOS]). |
| Configurazione | Include controlli per: <br/><ul><li>Trasmissione di dati chiave-valore alle [!DNL URL] destinazioni. È possibile inviare dati come coppie chiave-valore singole o serializzate. Per informazioni dettagliate, consultate Serializzazione [destinazione](../../features/destinations/key-value-pairs.md#destination-serialized) e [Standard e Chiave chiave-valore](../../features/destinations/key-value-pairs.md). </li><li>Elementi di una destinazione cookie come nome del cookie, dominio, dimensione, intervallo di scadenza, formato dati, ecc.</li></ul> |
| Mappature segmento | Consente di: <br/><ul><li>Cercare, aggiungere e gestire segmenti associati a tutti i tipi di destinazione. </li><li>Imposta le priorità di consegna su singoli segmenti (solo per segmenti basati su [!DNL cookie]segmenti).</li></ul> |

### Metodi di consegna dati {#data-delivery-methods}

Inviare informazioni a una destinazione passandola attraverso [!DNL URL] una stringa, scrivendo in un browser [!DNL cookie]o tramite trasferimento dati da server a server offline.

* [!DNL URL] e le destinazioni basate su cookie trasmettono i dati in modo sincrono, man mano che un utente utilizza una pagina.
* La trasmissione dei dati server-to-server è asincrona e può verificarsi molto dopo che un utente è uscito dalla pagina. Il tipo di consegna selezionato dipende dai requisiti aziendali e dal modo in cui un particolare partner di dati desidera o può ricevere dati.

Per [ulteriori informazioni, consultate Scegliere un tipo](../../features/destinations/destinations.md) di destinazione.

>[!MORE_ LIKE_ THIS]
>
>* [Creare una destinazione cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [Creare una destinazione URL](../../features/destinations/manage-destinations.md#configure-url-destination)


## Configurare una destinazione cookie {#create-cookie-destination}

Una destinazione di cookie restituisce e scrive dati in un cookie nel browser dell&#39;utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Per creare una destinazione di cookie con [!UICONTROL Destination Builder], effettuate le seguenti operazioni.

<!-- create-cookie-destination.xml -->

Per creare una nuova destinazione del cookie, accedete **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completate le sezioni come descritto di seguito.

### Informazioni di base {#basic-information}

Questa sezione contiene campi e opzioni che avviano il processo di creazione di destinazione del cookie. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Basic Information]** esporre i controlli.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivete la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. Nell **[!UICONTROL Category]** &#39;elenco, scegliete **[!UICONTROL Custom]**.
5. Nell **[!UICONTROL Environment]** &#39;elenco, selezionate **[!UICONTROL Browser]**. Non è possibile configurare le destinazioni dei cookie per ambienti mobili nativi, ad esempio app Android o iOS.
6. Nell **[!UICONTROL Type]** &#39;elenco, fate clic **[!UICONTROL Cookie]** su.
7. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l&#39;ID segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitata a 255 caratteri, massimo.
8. Fate clic per **[!UICONTROL Next]** passare alle [!UICONTROL Configuration] impostazioni o fare clic per **[!UICONTROL Data Export Labels]** applicare i controlli di esportazione alla destinazione.

### Etichette esportazione dati {#data-export-labels-cookies}

Questa sezione contiene le opzioni che applicano [i controlli di esportazione dei dati](../../features/data-export-controls.md) a una destinazione del cookie. Ignorate questo passaggio se non utilizzate i controlli di esportazione dei dati. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Data Export Labels]** esporre i controlli.
2. Selezionate un&#39;etichetta che corrisponda al controllo sull&#39;esportazione dei dati applicato alla destinazione (per ulteriori informazioni, consultate [Aggiungi etichette esportazione a una destinazione)](../../features/destinations/manage-destinations.md#add-data-export-labels) .
3. Fai clic su **[!UICONTROL Save]**.

### Configurazione {#configuration}

Questa sezione contiene campi e opzioni che consentono di impostare il cookie per la destinazione.

>[!NOTE]
>
>[!DNL Audience Manager] codifica i dati scritti nel cookie di destinazione. Ad esempio, gli spazi sono codificati e `%20` il punto e virgola è codificato come `%3B`.

Per completare questa sezione:

1. Fare clic per **[!UICONTROL Configuration]** esporre i controlli
1. Denominate il cookie. Evitare abbreviazioni e caratteri speciali.
1. Scegliere un&#39;opzione di formato dati. Queste opzioni consentono di scegliere i delimitatori e i separatori per le coppie chiave-valore che inviano dati di segmento a una destinazione. Le opzioni di formattazione includono:
   * **Chiave singola:** Consente di impostare la chiave in una coppia chiave-valore. Il valore viene impostato dopo aver selezionato un segmento nella [!UICONTROL Segment Mappings] sezione di seguito.
   * **Chiave multipla:** Consente di impostare la chiave e il valore per una coppia chiave-valore. La coppia chiave-valore viene creata dopo aver selezionato un segmento nella sezione Mappature segmenti di seguito.
See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. Fai clic su **[!UICONTROL Save]**.

Tutte le altre impostazioni sono facoltative. Per ulteriori informazioni sulle impostazioni **[!UICONTROL Cookie Domain]** e **[!UICONTROL Publish data to]** sulle impostazioni, consultate [Impostazioni facoltative per destinazioni cookie](../../features/destinations/manage-destinations.md#optional-settings-cookies).

### Mappature segmento {#segments-mapping}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Segment Mappings]** esporre i controlli.
1. Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic su per **[!UICONTROL Browse All Segments]** sfogliare un elenco dei segmenti disponibili.
1. Fai clic **[!UICONTROL Add Selected Segments]** su quando trovi il segmento da utilizzare. L&#39;aggiunta di un segmento apre la [!UICONTROL Edit Mapping] finestra.
1. Nella [!UICONTROL Edit Mapping] finestra di dialogo:
   * **[!UICONTROL Mapping]** consente di impostare un valore per la chiave specificata nella sezione Configurazione di cui sopra.
   * **[!UICONTROL Publish from]** consente di impostare la data di inizio e di fine della destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Fai clic su **[!UICONTROL Save]**.
1. Fai clic su **[!UICONTROL Done]**.

## Configurare una destinazione URL {#configure-url-destination}

Una [!DNL URL] destinazione effettua chiamate pixel da una pagina alla destinazione. Per creare [!DNL URL] una destinazione con [!UICONTROL Destination Builder], effettuate le seguenti operazioni.

<!-- create-url-destination.xml -->

Per creare una nuova [!DNL URL] destinazione, accedi **[!UICONTROL Audience Data > Destinations > Create New Destination]** a e completa le sezioni come descritto di seguito.

### Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano il processo di creazione di destinazione URL. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Basic Information]** esporre i controlli.
1. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
1. *(Facoltativo)* Descrivete la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
1. Nell **[!UICONTROL Category]** &#39;elenco, scegliete **[!UICONTROL Custom]**.
1. Nell **[!UICONTROL Environment]** &#39;elenco, selezionate l&#39;ambiente in cui attivare la destinazione URL.
1. Nell **[!UICONTROL Type]** &#39;elenco, fate clic **[!UICONTROL URL]** su.
1. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l&#39;ID segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitata a 255 caratteri, massimo.
1. Fate clic per **[!UICONTROL Next]** passare alle [!UICONTROL Configuration] impostazioni o fare clic per **[!UICONTROL Data Export Labels]** applicare i controlli di esportazione alla destinazione.

### Etichette esportazione dati {#data-export-labels-dest}

Questa sezione contiene le opzioni che applicano [i controlli di esportazione dei dati](../../features/data-export-controls.md) a una [!DNL URL] destinazione. Ignorate questo passaggio se non utilizzate i controlli di esportazione dei dati. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Data Export Labels]** esporre i controlli.
2. Selezionate un&#39;etichetta che corrisponda al controllo sull&#39;esportazione dei dati applicato alla destinazione (per informazioni, consultate [Aggiungi etichette esportazione a una destinazione)](../../features/destinations/manage-destinations.md#add-data-export-labels) .
3. Fai clic su **[!UICONTROL Save]**.

### Configurazione {#configure-base-data}

Questa sezione contiene opzioni che consentono di impostare i delimitatori di base [!DNL URL] e di dati trasmessi dalla [!DNL URL] stringa. Questa sezione è facoltativa. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Configuration]** esporre i controlli.
1. *(Facoltativo)* Selezionate la casella **[!UICONTROL Serialize]** di controllo.
Questo consente di inviare segmenti a una destinazione in sequenza anziché effettuare chiamate separate per ogni segmento. La serializzazione contribuisce a rendere efficiente i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatore. Per ulteriori informazioni, consultate [Coppie di valori standard e chiave di serie](../../features/destinations/key-value-pairs.md).
1. Se selezionate **[!UICONTROL Serialize]**, dovete anche configurare i campi URL e delimitatore descritti di seguito.

| Campo | Descrizione |
|--- |--- |
| URL di base | Parte di base di uno standard `HTTP`[!DNL URL] che non cambia. Inoltre, è necessario inserire la macro `%ALIAS%`[segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| URL protetto | Parte di base di una versione protetta `HTTPS`[!DNL URL] che non viene modificata. Inoltre, è necessario inserire la macro `%ALIAS%`[segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| Delimitatore | Simbolo che separa le variabili del segmento nella [!DNL URL] stringa. Solitamente si tratta di una virgola o di un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

### Mappature segmento {#segment-mappings}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Segment Mappings]** esporre i controlli.
1. Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic **[!UICONTROL Browse All Segments]** su Sfoglia un elenco dei segmenti disponibili.
1. Fai clic **[!UICONTROL Add Selected Segments]** su quando trovi il segmento da utilizzare. L&#39;aggiunta di un segmento apre la [!UICONTROL Edit Mapping] finestra.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fornite le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Fai clic su **[!UICONTROL Done]**.

### Impostazioni facoltative per destinazioni cookie {#optional-settings-cookies}

In [!UICONTROL Destination Builder], i [!UICONTROL Configuration section] campi e [!UICONTROL Cookie Domain][!UICONTROL Publish Data To] i campi. Queste consentono di creare regole per determinare se una destinazione imposta un cookie o restituisce un cookie. [!UICONTROL Cookie Domain] e [!UICONTROL Publish Data To] lavorare in modo indipendente e facoltativo. Potete creare una destinazione di cookie senza utilizzarne nessuno.

## Dominio cookie: Sintassi ed esempi {#cookie-domain-syntax}

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
   <td colname="col2"> <p>Il campo <span class="wintitle"> Dominio</span> cookie accetta una semplice stringa di testo che consente di impostare i cookie su un dominio specificato o su tutti i domini. Quando si utilizza questa funzione: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Imposta un solo dominio per ogni destinazione del cookie. Non digitare più domini nel campo <span class="wintitle"> Dominio</span> cookie. Create invece un'altra <span class="wintitle"> destinazione</span> . </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Non utilizzate caratteri jolly. </li> 
     </ul> </p> <p> Lasciate vuoto <span class="wintitle"> il campo Dominio</span> cookie per impostare un cookie su tutti i domini. Questa è l'impostazione predefinita. </p> <p>Per impostare i cookie su un dominio e sottodomini specifici: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Digita il nome del dominio nel <span class="wintitle"> campo Dominio</span> cookie. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Inizia il nome di dominio con un punto. Ad esempio <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">Il <code> prefisso https://www</code> non è richiesto. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esempio</b> </p> </td> 
   <td colname="col2"> <p>Come esempio semplice, supponiamo di avere un sito fittizio denominato sport. com. Sports.com contiene domini per golf, baseball e football. Per impostare un cookie in tutti i domini sportivi, digitali nella casella Dominio <span class="wintitle"> cookie come</span> mostrato di seguito: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Questo indica <span class="keyword"> a Audience Manager</span> di impostare un cookie in qualsiasi dominio che contenga il pattern <code><i>something</i></code>. sports. com. Consultate di seguito un set più complesso di esempi. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Esempi di dominio cookie complessi

Questi esempi mostrano se [!DNL Audience Manager] impostare un cookie in base alla configurazione dell&#39; [!UICONTROL Cookie Domain] opzione.

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

## Pubblica dati in {#publish-data-to}

[!UICONTROL Publish Data To] Le impostazioni restituiscono un cookie se il dominio soddisfa i criteri impostati dalle opzioni selezionate. Le opzioni includono:

* **[!UICONTROL All of our domains]**: (Impostazione predefinita) Restituisce un [!DNL cookie] qualsiasi dominio.
* **[!UICONTROL Only the selected domains]**: Restituisce un cookie solo per i domini selezionati nell&#39;elenco dei domini.
* **[!UICONTROL All of our domains except the selected domains]**: Impedisce ai domini selezionati di ricevere un [!DNL cookie]. Tutti gli altri domini possono ricevere un [!DNL cookie].

>[!MORE_ LIKE_ THIS]
>
>* [Creare una destinazione cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)


## Aggiungere o modificare segmenti per destinazioni server-to-server {#add-edit-segments}

Puoi aggiungere o modificare solo i segmenti per una destinazione server-to-server ([!DNL S2S]). Non è possibile creare [!DNL S2S] destinazioni con [!UICONTROL Destination Builder]. Contatta il tuo consulente per impostare [!DNL S2S] le destinazioni. Per aggiungere o modificare segmenti per [!DNL S2S] una destinazione, effettuate le seguenti operazioni.

<!-- destination-s2s-edit.xml -->

Per aggiungere o modificare mappature segmenti per [!DNL S2S] una destinazione:

1. **[!UICONTROL Audience Data > Destinations]** Vai a. Selezionate **Piattaforme integrate &gt; Basate su dispositivo** e individuate la [!DNL S2S] destinazione con cui desiderate lavorare.
1. Nella [!UICONTROL Action] colonna, fate clic sull&#39;icona a forma di matita per modificare la destinazione.
   * Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic **[!UICONTROL Browse All Segments]** su Sfoglia un elenco dei segmenti disponibili.
   * Fai clic **[!UICONTROL Add Selected Segments]** su quando trovi il segmento da utilizzare. L&#39;aggiunta di un segmento apre la [!UICONTROL Edit Mapping] finestra.
   * In [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Impostare un valore per la coppia [chiave-valore](../../features/destinations/key-value-pairs.md) utilizzata da questa destinazione.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Fate clic **[!UICONTROL Save]****[!UICONTROL Done]** su e quindi su.

## Aggiungere etichette di esportazione dati a una destinazione {#add-data-export-labels}

[!DNL Data Export Labels] lavorare con il [!DNL Export Controls] set impostato su un&#39;origine dati. [!DNL Data Export Labels] impedire l&#39;aggiunta di caratteristiche limitate a un segmento e l&#39;invio di dati di segmento a una destinazione. Potete impostare più etichette di esportazione su una nuova o esistente [!DNL cookie][!DNL URL] destinazione.

>[!NOTE]
>
>Per aggiungere un&#39;etichetta di esportazione, dovete disporre delle autorizzazioni *di amministratore o* di privilegi sufficienti per creare o modificare una destinazione.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Fai clic su **[!UICONTROL Audience Data]**:
   * Per nuove destinazioni: Fate clic **[!UICONTROL Create New Destination]** su. Completate [!UICONTROL Basic Information] la sezione prima di selezionare un&#39;etichetta di esportazione dati. Per informazioni, consultate [Creare una destinazione](../../features/destinations/manage-destinations.md#create-cookie-destination) cookie o [Creare una destinazione](../../features/destinations/manage-destinations.md#configure-url-destination) URL.
   * Per le destinazioni esistenti: Usate la [!DNL Search] casella per trovare la destinazione o scorrere l&#39;elenco e fate clic sul nome della destinazione per aprirla.
1. Seleziona una [!DNL Data Export Label]. Lasciate vuote le caselle di controllo se non desiderate impostare restrizioni di esportazione. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Le limitazioni di esportazione non funzionano a meno che non imposti un [controllo di esportazione corrispondente](../../features/data-export-controls.md) su un&#39;origine dati.
1. Fai clic su **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Creare un&#39;origine dati](../../features/manage-datasources.md#create-data-source)

