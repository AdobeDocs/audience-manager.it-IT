---
description: I file di registro fruibili consentono di acquisire segnali multimediali dai file di registro di ad server per creare caratteristiche in Audience Manager. Acquisisci impression, clic e conversioni dai server di annunci come caratteristiche senza dover aggiungere pixel.
keywords: registri actionable, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: File di registro fruibili
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 1%

---

# File di registro fruibili {#actionable-log-files}

[!UICONTROL Actionable Log Files] consente di acquisire dati multimediali dai file di registro di ad server e di utilizzarli per creare caratteristiche in Audience Manager. Acquisisci impression, clic e conversioni dai server di annunci come caratteristiche senza dover aggiungere [pixel](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi quadre `[ ]` `( )` e così via) in questo documento indicano elementi e opzioni di codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../reference/code-style-elements.md).

## Finalità {#purpose}

[!UICONTROL Actionable Log Files] semplifica la modalità di acquisizione di impression, clic e conversioni dai server di annunci. Utilizzare queste informazioni per la segmentazione degli utenti senza dover eseguire manualmente il pixel dei file multimediali per inviare gli attributi della campagna a [!DNL Audience Manager].

## Introduzione {#getting-started}

Per iniziare a utilizzare [!UICONTROL Actionable Log Files], è necessario importare i dati di registro in [!DNL Audience Manager]. I seguenti collegamenti ti aiuteranno a iniziare:

* Per [!UICONTROL Google Campaign Manager] registri, consulta [Importare file di dati di Google Campaign Manager in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *e* contatta il tuo consulente [!DNL Audience Manager].
* Per i registri di [!UICONTROL Google Ad Manager] (precedentemente Google DFP), vedi [Importare file di dati di Google Ad Manager in Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *e* contatta il tuo consulente [!DNL Audience Manager].
* Per altri registri di ad server, vedere [File di dati e metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *e* contattare il proprio consulente [!DNL Audience Manager].

Se stai già importando i dati di registro in [!DNL Audience Manager], chiedi al tuo consulente [!DNL Audience Manager] o all&#39;[Assistenza clienti](https://helpx.adobe.com/it/contact/enterprise-support.ec.html) di abilitare [!UICONTROL Actionable Log Files].

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/it/contact/enterprise-support.ec.html) to get started.

-->

## Utilizzo dei file di registro fruibili {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], le informazioni dei registri del server di annunci vengono acquisite in [!DNL Audience Manager] nello stesso modo in cui si acquisiscono i dati dalle interazioni in tempo reale del sito Web. [!DNL Audience Manager] si connette all&#39;archivio dei registri dell&#39;ad server, analizza le informazioni contenute nei registri e invia i dati di registro come segnali utilizzabili ai nostri [server di raccolta dati](../../reference/system-components/components-data-collection.md#dcs-pcs).

È comunque necessario impostare caratteristiche basate su regole per acquisire i segnali utilizzabili. Scopri come impostare caratteristiche basate su regole nell&#39;interfaccia utente di [Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) o utilizzando i nostri [strumenti per la gestione in blocco](../../reference/bulk-management-tools/bulk-create.md). Scorri verso il basso fino alla sezione [Segnali utilizzabili](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) per un elenco di tutte le chiavi che puoi utilizzare nelle caratteristiche basate su regole.

>[!IMPORTANT]
>
>È consigliabile implementare [!UICONTROL Actionable Log Files] *anziché* [Chiamate pixel](../../integration/media-data-integration/impression-data-pixels.md). Sconsigliamo l’uso di entrambe le opzioni, in quanto ciò comporta un aumento del numero di frequenze per le caratteristiche.

## Segnali utilizzabili {#actionable-signals}

I segnali sono le [unità di dati più piccole](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] consente di acquisire i valori di inserzionista, business unit, creativo e campagna in eventi di impression, eventi di clic e eventi di conversione come segnali dai registri di ad server.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] sono supportati per i seguenti server di annunci:
>&#x200B;> <br>
>
> * [Gestione campagne Google](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalk e Sizmek](#generic-logs-signals)

Ricorda, per utilizzare queste informazioni per la creazione di tipi di pubblico e la segmentazione, devi impostare autonomamente le caratteristiche basate su regole.

### Segnali utilizzabili dai registri di Google Campaign Manager {#dcm-logs-signals}

Nella tabella sono elencati i segnali utilizzabili dai file di registro [!DNL Google Campaign Manager]:

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
   <td colname="col3"> <p>Disponibile solo per eventi di conversione. </p> <p>Rappresenta l’ID numerico per l’attività di conversione in Google Campaign Manager. Questo campo viene mappato sull’ID attività di Google Campaign Manager. </p> <p> <p>Suggerimento: puoi acquisire più o specifiche attività di conversione da Google Campaign Manager. Crea caratteristiche utilizzando <code> d_conversion = activity ID</code> per ogni attività di conversione da Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Disponibile solo per eventi di conversione. </p> <p>Questo campo viene mappato sull’ID conversione in Google Campaign Manager. Indica l’attività che precede la conversione utente da Google Campaign Manager. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> per conversioni post-clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> per conversioni post-impression. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> per conversioni non corrispondenti. La conversione non può corrispondere a un'attività precedente. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Data e ora UTC per l’evento di impression, clic o conversione. Rappresentato in microsecondi dal 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Un codice di integrazione per l’origine dati dell’inserzionista. Tieni presente che non è correlato alle origini dati di Audience Manager.</p> <p>Questo campo viene mappato sull’ID gruppo inserzionista di Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID Business Unit. Questo campo viene mappato sull’ID inserzionista di Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>ID campagna fornito da Google Campaign Manager.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>ID Creative fornito da Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> L'importo delle vendite in USD, alla potenza di -6. Moltiplica per 1.000.000 per vedere come importo in dollari.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica il tipo di evento. Audience Manager legge il tipo di evento dal nome del file di registro di Google Campaign Manager e lo trasforma in un segnale actionable. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> per le impression. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> per i clic. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> per le conversioni. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ID dell’origine dati utilizzata per acquisire i dati di Google Campaign Manager. Vedere <a href="../../features/manage-datasources.md#create-data-source"> Come creare un Data Source</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

I segnali descritti nella tabella vengono acquisiti in [!DNL Audience Manager] come una chiamata `HTTP` in tempo reale. La chiamata di esempio seguente contiene informazioni su un evento di conversione da [!DNL Google Campaign Manager]. Le chiamate non devono necessariamente includere *tutti* i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Per un file di registro [!DNL Google Campaign Manager] di dimensioni medie pari a 2 milioni di righe, qualsiasi caratteristica creata da segnali utilizzabili viene realizzata entro circa un&#39;ora dall&#39;elaborazione dei registri.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>La marca temporale dell&#39;evento fornita nei registri [!DNL Google Campaign Manager] verrà rispettata e passata a [!UICONTROL Data Collection Servers].
>
>* Se non è disponibile un timestamp per una riga di dati nel file di registro [!DNL Google Campaign Manager], come timestamp dell&#39;evento viene utilizzato l&#39;ora della chiamata `HTTP`.
>* Se la riga di dati nel file di registro [!DNL Google Campaign Manager] contiene una marca temporale non valida, l&#39;intera riga verrà ignorata.

<br> 

### Segnali utilizzabili da [!DNL Google Ad Manager] registri {#ad-manager-logs-signals}

Nella tabella sono elencati i segnali utilizzabili dai file di registro [!DNL Google Ad Manager]:


| Nome intestazione nel file di registro | Segnale | Descrizione |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | ID numerico per la riga dell’Ad Manager consegnata |
| `OrderId` | `d_orderid` | ID numerico dell’ordine di Ad Manager contenente la riga consegnata e la creatività. |
| `CreativeId` | `d_creative` | L’ID numerico della creatività di Ad Manager consegnata. |
| `-` | `d_event` | Indica il tipo di evento. Audience Manager legge il tipo di evento dal nome del file di registro di Ad Manager e lo trasforma in un segnale actionable. I valori accettati sono: <br> <ul><li>d_event = imp per le impression.</li><li>d_event = clic per i clic.</li><li>d_event = conv per conversioni e attività.</li></ul> |
| `-` | `d_src` | ID dell’origine dati utilizzata per acquisire i dati di Ad Manager. Consulta [Come creare un Source dati](/help/using/features/manage-datasources.md). |

I segnali descritti nella tabella vengono acquisiti in Audience Manager come una chiamata HTTP in tempo reale. La chiamata di esempio seguente contiene informazioni su un evento di conversione da Google Ad Manager. Le chiamate non devono necessariamente includere tutti i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>La marca temporale dell&#39;evento fornita nei registri [!DNL Google Ad Manager] verrà rispettata e passata a [!UICONTROL Data Collection Servers].
>
>
>* Se non è disponibile un timestamp per una riga di dati nel file di registro [!DNL Google Ad Manager], come timestamp dell&#39;evento viene utilizzato l&#39;ora della chiamata `HTTP`.
>* Se la riga di dati nel file di registro [!DNL Google Ad Manager] contiene una marca temporale non valida, l&#39;intera riga verrà ignorata.

<br> 

### Segnali utilizzabili dai registri di Adobe Advertising Cloud, Flashtalk e Sizmek ad server {#generic-logs-signals}

Innanzitutto, devi depositare i registri del server di annunci nei nostri bucket Amazon S3. Per ottenere questo risultato, leggere [File di dati per report di Audience Optimization e file di registro fruibili](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *e* contattare il tuo consulente [!DNL Audience Manager]. Nella tabella sono elencati i segnali utilizzabili dai file di registro di ad server:

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
      <li id="li_29D3FF8919B7404297E80BACA913117A"> Impression <code> 0</code> </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> clic </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> non attribuito o sconosciuto </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Data e ora UTC per l’evento di impression, clic o conversione. Utilizza il formato <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Un codice di integrazione per l’origine dati dell’inserzionista. Questo campo non è correlato a <a href="../../features/datasources-list-and-settings.md">origini dati Audience Manager.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>ID Business Unit.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>L’ID della campagna dal file di registro.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>L’ID Creative dal file di registro. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Importo di acquisto o altra conversione. Tipo di dati: mobile. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Indica il tipo di evento. Audience Manager legge il tipo di evento dal nome del file di registro e lo trasforma in un segnale actionable. Consulta <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">convenzioni di denominazione dei file di registro</a>. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> per le impression. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> per i clic. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> per le conversioni. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ID dell’origine dati utilizzata per acquisire i dati di registro. Vedere <a href="../../features/manage-datasources.md#create-data-source"> Come creare un Data Source</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

I segnali descritti nella tabella vengono acquisiti in [!DNL Audience Manager] come una chiamata `HTTP` in tempo reale. Le chiamate non devono necessariamente includere *tutti* i segnali nella chiamata di esempio.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Utilizzo dei segnali utilizzabili nell’interfaccia utente di Audience Manager {#actionable-signals-in-ui}

Puoi visualizzare i segnali utilizzabili in arrivo nell&#39;interfaccia di [Ricerca segnali](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md).

Vai a **Dati pubblico** (1) > **Segnali** (2) > **Cerca** (3) e seleziona il filtro **File di registro fruibili** (4).

![Segnali utilizzabili nell&#39;interfaccia utente](/help/using/integration/assets/alf-in-signals.png)

Per creare caratteristiche basate su regole utilizzando i segnali actionable, selezionare **File di registro actionable** (1), selezionare i segnali actionable che si desidera utilizzare come regole di caratteristiche (2) e premere **Crea caratteristica da segnali selezionati** (3).

![Crea caratteristiche da segnali](/help/using/integration/assets/alf-create-trait.png)


## Casi d&#39;uso {#use-cases}

Uno dei vantaggi dell&#39;implementazione di [!UICONTROL Actionable Log Files] è l&#39;opzione di applicare i controlli [recency e frequenza](../../features/segments/recency-and-frequency.md) a [caratteristiche basate su regole](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) che contengono segnali actionable. Questo consente, ad esempio, di limitare il numero di volte in cui un utente riceve un particolare contenuto creativo all’interno di una campagna multimediale. Leggi [Instant Cross-Device Suppression](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) per scoprire come eseguire questa operazione. Altri casi d’uso includono:

### Utenti di retargeting

Puoi eseguire il retargeting degli utenti che hanno visto creative 123 ma non hanno fatto clic o convertito e mostrare creative 456. Effettua questa operazione:

1. Crea una caratteristica per acquisire gli utenti che hanno visto la creatività. Supponiamo che tu chiami la caratteristica [!DNL Creative Trait 123]. Utilizza la regola delle caratteristiche:

   `d_creative == 123 AND d_event == imp`

2. Crea una caratteristica per acquisire gli utenti che fanno clic o si convertono. Supponiamo che tu chiami questo [!DNL Click and Converter]. Utilizza la regola delle caratteristiche:

   `d_event == click OR d_event=conv`

3. Crea un segmento da compilare con gli utenti che hanno visto Creative 123 ma non hanno fatto clic o convertito. Denominarlo [!DNL Retarget Users] e utilizzare la regola del segmento:

   `Creative Trait 123 AND NOT Click and Converter`

4. Mappare il segmento [!DNL Retarget Users] su una destinazione ed eseguire il targeting degli utenti nella destinazione con Creative 456.

### Utilizzare l’attività di Google Campaign Manager Floodlight nei rapporti di Audience Optimization o in Audience Lab

[I tag Floodlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) consentono agli inserzionisti di tenere traccia delle conversioni utente. Con [!UICONTROL Actionable Log Files], puoi tenere traccia delle [!DNL Google Campaign Manager] conversioni nei [report Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md) o in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Crea una caratteristica e utilizza la seguente regola di caratteristica per acquisire una conversione dai registri dell’ad server:

   `d_event == conv AND d_conversion == 123`

   Durante la creazione della caratteristica in Audience Manager [!UICONTROL UI], selezionare [!UICONTROL Conversion] come [!UICONTROL Event Type].

2. Dopo aver creato la caratteristica, la conversione inizierà a essere segnalata in [!UICONTROL Audience Optimization Reports] e in [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importare File Di Dati Di Google Campaign Manager In Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Rapporti di Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
