---
description: I file di registro fruibili consentono di acquisire i segnali multimediali dai file di registro dei server di annunci per creare caratteristiche in  Audience Manager. Cattura come caratteristiche impression, clic e conversioni dai server di annunci senza dover aggiungere pixel.
keywords: actionable logs, alf, ALF
seo-description: I file di registro fruibili consentono di acquisire i segnali multimediali dai file di registro dei server di annunci per creare caratteristiche in  Audience Manager. Cattura come caratteristiche impression, clic e conversioni dai server di annunci senza dover aggiungere pixel.
seo-title: File di registro fruibili
solution: Audience Manager
title: File di registro fruibili
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
translation-type: tm+mt
source-git-commit: a4d86fb0324a03002123f8713eb9786b5b74c38e
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 3%

---


# File di registro fruibili {#actionable-log-files}

[!UICONTROL Actionable Log Files] consente di acquisire i dati multimediali dai file di registro del server di annunci e di utilizzare i dati per creare caratteristiche in  Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicano gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../reference/code-style-elements.md).

## Finalità {#purpose}

[!UICONTROL Actionable Log Files] ottimizza il modo in cui acquisisci impression, clic e conversioni dai server di annunci. Utilizzate queste informazioni per la segmentazione degli utenti senza dover inviare manualmente i file multimediali in pixel per inviare gli attributi della campagna a [!DNL Audience Manager].

## Introduzione {#getting-started}

Per iniziare, [!UICONTROL Actionable Log Files]devi importare i dati di registro in [!DNL Audience Manager]. I seguenti collegamenti sono utili per iniziare:

* Per [!UICONTROL Google Campaign Manager] i registri, consulta [Importare i file di dati di Google Campaign Manager in  Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *e* contatta il tuo [!DNL Audience Manager] consulente.
* Per i registri [!UICONTROL Google Ad Manager] (già Google DFP), consulta [Importare file di dati Google Ad Manager in  Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *e* contatta il tuo [!DNL Audience Manager] consulente.
* Per altri registri del server di annunci, consulta [Dati e file](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) di metadati *e contatta* il tuo [!DNL Audience Manager] consulente.

Se state già importando i dati di registro in [!DNL Audience Manager], chiedete al vostro [!DNL Audience Manager] consulente o all&#39;Assistenza [](https://helpx.adobe.com/it/contact/enterprise-support.ec.html) clienti di effettuare [!UICONTROL Actionable Log Files] l&#39;operazione.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Utilizzo dei file di registro fruibili {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], le informazioni provenienti dai registri dei server di annunci vengono acquisite nello [!DNL Audience Manager] stesso modo in cui si acquisiscono i dati dalle interazioni in tempo reale dei siti Web. [!DNL Audience Manager] si connette alla memorizzazione del registro del server di annunci, analizza le informazioni dai registri e invia i dati del registro come segnali fruibili ai nostri server [di raccolta](../../reference/system-components/components-data-collection.md#dcs-pcs)dati.

È comunque necessario impostare caratteristiche basate su regola per acquisire i segnali fruibili. Scoprite come impostare caratteristiche basate su regola nell&#39;interfaccia [utente](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) Audience Manager o utilizzando i nostri strumenti [di gestione](../../reference/bulk-management-tools/bulk-create.md)di massa. Scorri verso il basso fino alla sezione [Segnali](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) fruibili per visualizzare un elenco di tutte le chiavi utilizzabili nelle caratteristiche basate su regola.

>[!IMPORTANT]
>
>È consigliabile implementare [!UICONTROL Actionable Log Files] invece *delle chiamate* pixel [](../../integration/media-data-integration/impression-data-pixels.md). Non scoraggiamo l&#39;uso di entrambe le opzioni, in quanto ciò comporta un aumento del numero di frequenze per le caratteristiche.

## Segnali fruibili {#actionable-signals}

I segnali sono le unità [dati](../../reference/signal-trait-segment.md) più piccole in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] consente di acquisire i valori di advertiser, business unit, creative e campaign in eventi impression, clic ed eventi di conversione come segnali dai registri dei server di annunci.

Ricordate che, per utilizzare queste informazioni per la creazione e la segmentazione dell&#39;audience, dovete impostare voi stessi le caratteristiche basate su regola.

### Segnali fruibili dai registri di Google Campaign Manager {#dcm-logs-signals}

Nella tabella sono elencati i segnali attivabili dai file di [!DNL Google Campaign Manager] registro:

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
   <td colname="col3"> <p>Disponibile solo per gli eventi di conversione. </p> <p>Rappresenta l'ID numerico per l'attività di conversione in Google Campaign Manager. Questo campo viene mappato sull'ID attività da Google Campaign Manager. </p> <p> <p>Suggerimento: Puoi acquisire più attività di conversione o attività specifiche da Google Campaign Manager. Crea caratteristiche utilizzando <code> d_conversion = activity ID</code> per ogni attività di conversione da Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponibile solo per gli eventi di conversione. </p> <p>Questo campo viene mappato sull’ID conversione in Google Campaign Manager. Indica l'attività che precede la conversione utente da Google Campaign Manager. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> per conversioni post-clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> per conversioni post-impressione. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> per conversioni non associate. Impossibile associare la conversione a un'attività precedente. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Una data e un'ora UTC per l'evento di impression, clic o conversione. Rappresentato in microsecondi dal 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Un codice di integrazione per l'origine dati dell'inserzionista. Questo non è correlato alle origini dati  Audience Manager.</p> <p>Questo campo viene mappato sull'ID del gruppo di inserzionisti da Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID unità aziendale. Questo campo viene mappato sull'ID inserzionista da Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>L'ID campagna fornito da Google Campaign Manager.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>L'ID creativo fornito da Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> L'importo delle vendite in USD, al potere di -6. Moltiplicate per 1.000.000 per visualizzare come importo in dollari.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica il tipo di evento.  Audience Manager legge il tipo di evento dal nome del file di registro di Google Campaign Manager e lo trasforma in un segnale fruibile. </p> <p>I valori accettati sono: </p> <p> 
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
   <td colname="col3"> <p>L'ID dell'origine dati utilizzata per acquisire i dati di Google Campaign Manager. Vedere <a href="../../features/manage-datasources.md#create-data-source"> Come creare un'origine</a>dati. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

I segnali descritti nella tabella vengono catturati in [!DNL Audience Manager] modo simile a una `HTTP` chiamata in tempo reale. La seguente chiamata di esempio contiene informazioni su un evento di conversione da [!DNL Google Campaign Manager]. Le chiamate non devono necessariamente includere *tutti* i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Per un file di [!DNL Google Campaign Manager] registro di dimensioni medie di 2 milioni di righe, tutte le caratteristiche create dai segnali attivabili vengono realizzate entro circa un&#39;ora dopo l&#39;elaborazione dei registri.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>La marca temporale dell&#39;evento fornita nei [!DNL Google Campaign Manager] registri verrà rispettata e trasmessa al [!UICONTROL Data Collection Servers].
>
>* Se una marca temporale non è disponibile per una riga di dati nel file di [!DNL Google Campaign Manager] registro, utilizzeremo l&#39;ora della `HTTP` chiamata come marca temporale dell&#39;evento.
>* Se la riga di dati nel file di [!DNL Google Campaign Manager] registro contiene una marca temporale non valida, ignoreremo l&#39;intera riga.


<br> 

### Segnali fruibili dai [!DNL Google Ad Manager] registri {#ad-manager-logs-signals}

Nella tabella sono elencati i segnali attivabili dai file di [!DNL Google Ad Manager] registro:


| Nome intestazione nel file di registro | Segnale | Descrizione |
---------|----------|---------
| `LineItemId` | `d_lineitem` | ID numerico per l&#39;elemento riga Ad Manager consegnato |
| `OrderId` | `d_orderid` | L&#39;ID numerico per l&#39;ordine di Ad Manager che conteneva l&#39;elemento di riga consegnato e l&#39;elemento creativo. |
| `CreativeId` | `d_creative` | ID numerico per il creativo di Ad Manager consegnato. |
| `-` | `d_event` | Indica il tipo di evento.  Audience Manager legge il tipo di evento dal nome del file di registro di Ad Manager e lo trasforma in un segnale fruibile. I valori accettati sono: <br> <ul><li>d_event = imp per le impression.</li><li>d_event = click for click.</li><li>d_event = conv per conversioni e attività.</li></ul> |
| `-` | `d_src` | L&#39;ID dell&#39;origine dati utilizzata per acquisire i dati di Ad Manager. Vedere [Come creare un&#39;origine](/help/using/features/manage-datasources.md)dati. |

I segnali descritti nella tabella vengono acquisiti in  Audience Manager come una chiamata HTTP in tempo reale. La chiamata di esempio seguente contiene informazioni su un evento di conversione da Google Ad Manager. Le chiamate non devono necessariamente includere tutti i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>La marca temporale dell&#39;evento fornita nei [!DNL Google Ad Manager] registri verrà rispettata e trasmessa al [!UICONTROL Data Collection Servers].
>
>* Se una marca temporale non è disponibile per una riga di dati nel file di [!DNL Google Ad Manager] registro, utilizzeremo l&#39;ora della `HTTP` chiamata come marca temporale dell&#39;evento.
>* Se la riga di dati nel file di [!DNL Google Ad Manager] registro contiene una marca temporale non valida, ignoreremo l&#39;intera riga.


<br> 

### Segnali fruibili dai registri Ad Server Generici {#generic-logs-signals}

Innanzitutto, devi depositare i registri del server di annunci nei nostri bucket Amazon S3. A tal fine, leggete File [di dati per Report di ottimizzazione dell&#39;audience e File](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) di registro fruibili *e contattate* il vostro [!DNL Audience Manager] consulente. Nella tabella sono elencati i segnali utilizzabili provenienti da file di registro generici:

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
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Non attribuito o sconosciuto </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Una data e un'ora UTC per l'evento di impression, clic o conversione. Utilizzate il <code>yyyy-MM-dd HH:mm:ss</code> formato. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Un codice di integrazione per l'origine dati dell'inserzionista. Questo campo non è correlato alle origini dati <a href="../../features/datasources-list-and-settings.md">Audience Manager.</a></p></td> 
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
   <td colname="col3"> <p>Indica il tipo di evento.  Audience Manager legge il tipo di evento dal nome del file di registro e lo trasforma in un segnale fruibile. Consultate convenzioni <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">di denominazione dei file di</a>registro. </p> <p>I valori accettati sono: </p> <p> 
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
   <td colname="col3"> <p>L'ID dell'origine dati utilizzata per acquisire i dati del registro. Vedere <a href="../../features/manage-datasources.md#create-data-source"> Come creare un'origine</a>dati. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

I segnali descritti nella tabella vengono catturati in [!DNL Audience Manager] modo simile a una `HTTP` chiamata in tempo reale. Le chiamate non devono necessariamente includere *tutti* i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Utilizzo dei segnali fruibili nell&#39;interfaccia utente  Audience Manager {#actionable-signals-in-ui}

Puoi visualizzare i segnali attivabili in ingresso nell&#39;interfaccia di ricerca [](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) segnali.

Andate a Dati **** Pubblico (1) > **Segnali** (2) > **Ricerca** (3) e selezionate il filtro File **di registro** fruibili (4).

![Segnali fruibili nell’interfaccia utente](/help/using/integration/assets/alf-in-signals.png)

Per creare caratteristiche basate su regole utilizzando i segnali fruibili, selezionare File **di registro** fruibili (1), selezionare i segnali attivabili che si desidera utilizzare come regole sulle caratteristiche (2), quindi premere **Crea caratteristica dai segnali** selezionati (3).

![Creazione di caratteristiche dai segnali](/help/using/integration/assets/alf-create-trait.png)


## Casi d&#39;uso {#use-cases}

Un vantaggio dell&#39;implementazione [!UICONTROL Actionable Log Files] è la possibilità di applicare controlli di [aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) a qualsiasi caratteristica [basata su](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) regole che contenga segnali fruibili. Questo consente, ad esempio, di limitare la frequenza al massimo del numero di volte in cui un utente riceve una particolare creatività all’interno di una campagna multimediale. Leggi [Instant Cross-Device Suppression](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) (Soppressione tra dispositivi istantanea) per apprendere come eseguire questa operazione. Altri casi di utilizzo:

### Utenti di Retarget

Riavviate gli utenti che hanno visto creative 123 ma non hanno fatto clic o convertito per mostrare loro creative 456. Effettuate le seguenti operazioni:

1. Create una caratteristica per catturare gli utenti che hanno visto il creativo. Diciamo che chiami la caratteristica [!DNL Creative Trait 123]. Utilizzate la regola delle caratteristiche:

   `d_creative == 123 AND d_event == imp`

2. Create una caratteristica per catturare gli utenti che fanno clic o convertono. Diciamo che chiami questo [!DNL Click and Converter]. Utilizzate la regola delle caratteristiche:

   `d_event == click OR d_event=conv`

3. Crea un segmento da compilare con gli utenti che hanno visto creative 123 ma non hanno fatto clic o convertito. Assegnate un nome [!DNL Retarget Users] e utilizzate la regola del segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Mappatura il segmento [!DNL Retarget Users] a una destinazione e targeting degli utenti nella destinazione con creative 456.

### Utilizzare l&#39;attività di Google Campaign Manager Floodlight nei report di ottimizzazione dell&#39;audience o in Audience Lab

[I tag](https://support.google.com/dcm/partner/answer/4293719?hl=en) Floodlight consentono agli inserzionisti di tenere traccia delle conversioni degli utenti. Con [!UICONTROL Actionable Log Files], puoi tenere traccia delle [!DNL Google Campaign Manager] conversioni nei report [di ottimizzazione](../../reporting/audience-optimization-reports/audience-optimization-reports.md) dell&#39;audience o in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Create una caratteristica e utilizzate la seguente regola di caratteristiche per acquisire una conversione dai registri del server di annunci:

   `d_event == conv AND d_conversion == 123`

   Quando create la caratteristica nell&#39;Audience Manager  [!UICONTROL UI], selezionate [!UICONTROL Conversion] come [!UICONTROL Event Type].

2. Una volta creata la caratteristica, la conversione inizierà a essere segnalata nel [!UICONTROL Audience Optimization Reports] e in [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importa i file di dati di Google Campaign Manager in  Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Rapporti di Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

