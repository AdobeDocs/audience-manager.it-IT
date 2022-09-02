---
description: I file di registro fruibili consentono di acquisire segnali multimediali da file di registro ad server per creare caratteristiche in Audience Manager. Cattura come caratteristiche impression, clic e conversioni da server di annunci senza dover aggiungere pixel.
keywords: tronchi actionable, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: File di registro fruibili
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 2%

---

# File di registro fruibili {#actionable-log-files}

[!UICONTROL Actionable Log Files] ti consente di acquisire dati multimediali dai file di registro di ad server e di utilizzare i dati per creare caratteristiche in Audience Manager. Acquisisci impression, clic e conversioni da server di annunci come caratteristiche senza dover aggiungere [pixel](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicare gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../reference/code-style-elements.md).

## Finalità {#purpose}

[!UICONTROL Actionable Log Files] ottimizza il modo in cui acquisisci impression, clic e conversioni dai server di annunci. Utilizza queste informazioni per la segmentazione degli utenti senza dover pixel multimediali manuali per inviare attributi della campagna a [!DNL Audience Manager].

## Introduzione {#getting-started}

Per iniziare a utilizzare [!UICONTROL Actionable Log Files], è necessario importare i dati di registro in [!DNL Audience Manager]. I seguenti collegamenti sono utili per iniziare:

* Per [!UICONTROL Google Campaign Manager] registri, vedi [Importare file di dati Google Campaign Manager in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *e* contatta [!DNL Audience Manager] consulente.
* Per [!UICONTROL Google Ad Manager] (precedentemente Google DFP), vedi [Importare file di dati Google Ad Manager in Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *e* contatta [!DNL Audience Manager] consulente.
* Per altri registri del server di annunci, vedi [File di dati e metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *e* contatta [!DNL Audience Manager] consulente.

Se si importano già dati di registro in [!DNL Audience Manager], chiedi [!DNL Audience Manager] consulente o [Assistenza clienti](https://helpx.adobe.com/it/contact/enterprise-support.ec.html) per abilitare [!UICONTROL Actionable Log Files] per te.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Utilizzo dei file di registro fruibili {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], le informazioni dai log degli ad server vengono acquisite in [!DNL Audience Manager] allo stesso modo in cui acquisiresti dati da interazioni in tempo reale con siti web. [!DNL Audience Manager] si connette all&#39;archivio dei log del server di annunci, analizza le informazioni dai log e invia i dati di log come segnali actionable al nostro [Server di raccolta dati](../../reference/system-components/components-data-collection.md#dcs-pcs).

È comunque necessario impostare caratteristiche basate su regole per acquisire i segnali utilizzabili. Scopri come impostare caratteristiche basate su regole nel [Interfaccia utente di Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o utilizzando [Strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-create.md). Scorri verso il basso fino a [Segnali fruibili](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) per un elenco di tutte le chiavi utilizzabili nelle caratteristiche basate su regole.

>[!IMPORTANT]
>
>Si consiglia di implementare [!UICONTROL Actionable Log Files] *anziché*  [Chiamate pixel](../../integration/media-data-integration/impression-data-pixels.md). Scoraggiamo l&#39;uso di entrambe le opzioni, in quanto ciò porta ad un aumento del numero di frequenze per le caratteristiche.

## Segnali fruibili {#actionable-signals}

I segnali sono [unità di dati più piccole](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] consente di acquisire i valori di inserzionista, business unit, creativo e campagna in eventi di impression, eventi di clic ed eventi di conversione come segnali dai registri ad server.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] sono supportati per i seguenti server di annunci:
> <br>
>
> * [Google Campaign Manager](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalk e Sizmek](#generic-logs-signals)


Tieni presente che, per utilizzare queste informazioni per la creazione e la segmentazione del pubblico, devi impostare autonomamente le caratteristiche basate su regole.

### Segnali fruibili dai registri di Google Campaign Manager {#dcm-logs-signals}

Nella tabella sono elencati i segnali actionable da [!DNL Google Campaign Manager] file di registro:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome intestazione nel file di registro </th> 
   <th colname="col2" class="entry"> Segnale </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
   <th colname="col4" class="entry"> Esempio di valore </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Disponibile solo per gli eventi di conversione. </p> <p>Rappresenta l’ID numerico dell’attività di conversione in Google Campaign Manager. Questo campo viene mappato sull’ID attività da Google Campaign Manager. </p> <p> <p>Suggerimento: Puoi acquisire più attività di conversione o specifiche da Google Campaign Manager. Creare caratteristiche utilizzando <code> d_conversion = activity ID</code> per ogni attività di conversione da Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponibile solo per gli eventi di conversione. </p> <p>Questo campo viene mappato sull’ID conversione in Google Campaign Manager. Indica l’attività che precede la conversione dell’utente da Google Campaign Manager. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> per conversioni post-clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> per conversioni post-impression. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> per conversioni senza corrispondenza. Non è possibile abbinare la conversione a un’attività precedente. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Una data e un’ora UTC per l’evento impression, click o conversione. Rappresentato in microsecondi dal 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Un codice di integrazione per l’origine dati dell’inserzionista. Tieni presente che questo non è correlato alle origini dati di Audience Manager.</p> <p>Questo campo viene mappato sull’ID del gruppo inserzionista da Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID unità aziendale. Questo campo viene mappato sull’ID inserzionista da Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>L’ID della campagna fornito da Google Campaign Manager.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ID creativo fornito da Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> L'importo delle vendite in USD, alla potenza di -6. Moltiplica per 1.000.000 per vedere come un importo in dollari.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica il tipo di evento. L’Audience Manager legge il tipo di evento dal nome del file di registro di Google Campaign Manager e lo trasforma in un segnale fruibile. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> per impression. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> per clic. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> per le conversioni. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ID dell’origine dati utilizzata per acquisire i dati di Google Campaign Manager. Vedi <a href="../../features/manage-datasources.md#create-data-source"> Come creare un’origine dati</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

I segnali descritti nella tabella vengono acquisiti in [!DNL Audience Manager] come un tempo reale `HTTP` chiama. La chiamata di esempio seguente contiene informazioni su un evento di conversione da [!DNL Google Campaign Manager]. Le chiamate non devono necessariamente includere *tutto* i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Per dimensioni medie [!DNL Google Campaign Manager] file di log di 2 milioni di righe, tutte le caratteristiche create da segnali actionable vengono realizzate entro circa un&#39;ora dopo l&#39;elaborazione dei log.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>La marca temporale dell’evento fornita nel [!DNL Google Campaign Manager] i log saranno onorati e trasmessi al [!UICONTROL Data Collection Servers].
>
>* Se una marca temporale non è disponibile per una riga di dati nel [!DNL Google Campaign Manager] file di log, utilizziamo l&#39;ora del `HTTP` chiama come timestamp dell’evento.
>* Se la riga di dati nel [!DNL Google Campaign Manager] il file di registro contiene una marca temporale non valida. Viene ignorata l’intera riga.


<br> 

### Segnali fruibili da [!DNL Google Ad Manager] logs {#ad-manager-logs-signals}

Nella tabella sono elencati i segnali actionable da [!DNL Google Ad Manager] file di registro:


| Nome intestazione nel file di registro | Segnale | Descrizione |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | ID numerico della riga Ad Manager consegnata |
| `OrderId` | `d_orderid` | ID numerico dell’ordine di Ad Manager che conteneva l’elemento riga consegnato e l’elemento creativo. |
| `CreativeId` | `d_creative` | ID numerico del creativo di Ad Manager consegnato. |
| `-` | `d_event` | Indica il tipo di evento. L’Audience Manager legge il tipo di evento dal nome del file di registro di Ad Manager e lo trasforma in un segnale fruibile. I valori accettati sono: <br> <ul><li>d_event = imp per le impression.</li><li>d_event = fare clic per i clic.</li><li>d_event = conv per conversioni e attività.</li></ul> |
| `-` | `d_src` | ID dell’origine dati utilizzata per acquisire i dati di Ad Manager. Vedi [Come creare un’origine dati](/help/using/features/manage-datasources.md). |

I segnali descritti nella tabella vengono acquisiti in Audience Manager come una chiamata HTTP in tempo reale. La chiamata di esempio riportata di seguito contiene informazioni su un evento di conversione da Google Ad Manager. Le chiamate non devono necessariamente includere tutti i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>La marca temporale dell’evento fornita nel [!DNL Google Ad Manager] i log saranno onorati e trasmessi al [!UICONTROL Data Collection Servers].
>
>
>* Se una marca temporale non è disponibile per una riga di dati nel [!DNL Google Ad Manager] file di log, utilizziamo l&#39;ora del `HTTP` chiama come timestamp dell’evento.
>* Se la riga di dati nel [!DNL Google Ad Manager] il file di registro contiene una marca temporale non valida. Viene ignorata l’intera riga.


<br> 

### Segnali fruibili dai registri del server di annunci Adobe Advertising Cloud, Flashtalk e Sizmek {#generic-logs-signals}

Innanzitutto, devi depositare i log del server annunci nei nostri bucket Amazon S3. Per eseguire questa operazione, leggi [File di dati per Audienci Optimization di rapporti e file di registro fruibili](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *e* contatta [!DNL Audience Manager] consulente. Nella tabella sono elencati i segnali actionable provenienti dai file di registro ad server:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome intestazione nel file di registro </th> 
   <th colname="col2" class="entry"> Segnale </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
   <th colname="col4" class="entry"> Esempio di valore </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Indica se una conversione corrisponde o meno. Le opzioni includono: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impressioni </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Clic </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Non attribuiti o sconosciuti </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Una data e un’ora UTC per l’evento impression, click o conversione. Utilizza la <code>yyyy-MM-dd HH:mm:ss</code> formato. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Un codice di integrazione per l’origine dati dell’inserzionista. Tieni presente che questo campo non è correlato a <a href="../../features/datasources-list-and-settings.md">Audience Manager di origini dati.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID unità aziendale.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>ID campagna dal file di registro.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ID creativo dal file di registro. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Acquisto o altro importo di conversione. Tipo di dati: Mobile. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica il tipo di evento. L’Audience Manager legge il tipo di evento dal nome del file di registro e lo trasforma in un segnale fruibile. Vedi <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">convenzioni di denominazione dei file di registro</a>. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> per impression. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> per clic. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> per le conversioni. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ID dell’origine dati utilizzata per acquisire i dati di registro. Vedi <a href="../../features/manage-datasources.md#create-data-source"> Come creare un’origine dati</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

I segnali descritti nella tabella vengono acquisiti in [!DNL Audience Manager] come un tempo reale `HTTP` chiama. Le chiamate non devono necessariamente includere *tutto* i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Utilizzo dei segnali utilizzabili nell’interfaccia utente di Audience Manager {#actionable-signals-in-ui}

Puoi visualizzare i segnali actionable in entrata nella sezione [Ricerca di segnali](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) interfaccia.

Vai a **Dati sul pubblico** (1) > **Segnali** (2) > **Ricerca** (3) e seleziona il **File di registro fruibili** (4) filtro.

![Segnali fruibili nell’interfaccia utente](/help/using/integration/assets/alf-in-signals.png)

Per creare caratteristiche basate su regole utilizzando i segnali utilizzabili, seleziona **File di registro fruibili** (1), selezionare i segnali actionable che si desidera utilizzare come regole di caratteristiche (2) e premere **Creare caratteristiche dai segnali selezionati** (3)

![Creare caratteristiche dai segnali](/help/using/integration/assets/alf-create-trait.png)


## Casi d&#39;uso {#use-cases}

Un unico vantaggio nell&#39;attuazione [!UICONTROL Actionable Log Files] è l’opzione da applicare [recency e frequenza](../../features/segments/recency-and-frequency.md) controlli [caratteristiche basate su regole](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) che contengono segnali actionable. Questo consente, ad esempio, di limitare la frequenza al numero di volte in cui un utente viene mostrato un particolare creativo all’interno di una campagna multimediale. Leggi [Soppressione immediata su diversi dispositivi](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) per imparare come fare questo. Altri casi di utilizzo includono:

### Utenti di Retargeting

Esegui il retargeting degli utenti che hanno visto creative 123 ma non hanno fatto clic o convertito e hanno mostrato loro creative 456. Esegui questa operazione:

1. Crea una caratteristica per catturare gli utenti che hanno visto il creativo. Diciamo che denomini la caratteristica [!DNL Creative Trait 123]. Utilizza la regola delle caratteristiche:

   `d_creative == 123 AND d_event == imp`

2. Crea una caratteristica per acquisire gli utenti che fanno clic o convertono. Diciamo che chiami questo [!DNL Click and Converter]. Utilizza la regola delle caratteristiche:

   `d_event == click OR d_event=conv`

3. Crea un segmento da compilare con gli utenti che hanno visto creative 123 ma non hanno fatto clic o convertito. Denomina [!DNL Retarget Users] e utilizza la regola del segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Mappare il segmento [!DNL Retarget Users] a una destinazione e rivolgiti agli utenti della destinazione con creative 456.

### Utilizzare l’attività Google Campaign Manager Floodlight nei rapporti di Audience Optimization o in Audience Lab

[Tag di luce mobile](https://support.google.com/dcm/partner/answer/4293719?hl=en) abilitare gli inserzionisti a tenere traccia delle conversioni degli utenti. Con [!UICONTROL Actionable Log Files], puoi tenere traccia delle [!DNL Google Campaign Manager] conversioni nel [Rapporti di Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) o [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Crea una caratteristica e utilizza la seguente regola di caratteristiche per acquisire una conversione dai registri del server di annunci:

   `d_event == conv AND d_conversion == 123`

   Durante la creazione della caratteristica nell’Audience Manager [!UICONTROL UI], seleziona [!UICONTROL Conversion] come [!UICONTROL Event Type].

2. Una volta creata la caratteristica, la conversione inizierà a essere segnalata con nel [!UICONTROL Audience Optimization Reports] e [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importare file di dati Google Campaign Manager in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Rapporti di Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

