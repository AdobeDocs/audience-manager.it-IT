---
description: I file di registro fruibili consentono di acquisire dati multimediali dai file di registro di Google DCM e di utilizzare i dati per creare caratteristiche in Audience Manager. Puoi acquisire come caratteristiche impression, clic e conversioni da server di annunci, senza dover ricorrere a chiamate pixel.
keywords: registri fruibili
seo-description: I file di registro fruibili consentono di acquisire dati multimediali dai file di registro di Google DCM e di utilizzare i dati per creare caratteristiche in Audience Manager. Puoi acquisire come caratteristiche impression, clic e conversioni da server di annunci, senza dover ricorrere a chiamate pixel.
seo-title: File di registro fruibili
solution: Audience Manager
title: File di registro fruibili
uuid: 4 c 47615 f-ed 47-41 ba -8694-1 d 7 de 4 f 55 d 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File di registro fruibili {#actionable-log-files}

[!UICONTROL Actionable Log Files] consente di acquisire dati multimediali dai file [!DNL Google DCM] di registro e di utilizzare i dati per creare caratteristiche in Audience Manager. Puoi acquisire come caratteristiche impression, clic e conversioni da server di annunci, senza dover ricorrere a chiamate pixel.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indica gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../reference/code-style-elements.md).

## Finalità {#purpose}

[!UICONTROL Actionable Log Files] semplificare il modo in cui acquisisci impression, clic e conversioni dai server di annunci. Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## Introduzione {#getting-started}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {importance = "high"}
>
>[!UICONTROL Actionable Log Files] funzionano solo con [!DNL Google DCM] i file di registro.

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] si connette all [!DNL Google Cloud] 'archiviazione, analizza le informazioni dai [!DNL DCM] registri e invia i dati del registro come segnali utilizzabili ai nostri [server di raccolta dati](../../reference/system-components/components-data-collection.md#dcs-pcs).

È comunque necessario impostare caratteristiche basate su regole per acquisire i segnali utilizzabili. See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) section for a list of all the keys you can use in rule-based traits.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {importance = "high"}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). Non si consiglia di utilizzare entrambe le opzioni, in quanto si ottiene un aumento dei conteggi delle frequenze per le caratteristiche.

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] consente di acquisire i valori creatore, business unit, creative e campaign in eventi impression, clic su eventi e eventi di conversione come segnali dai [!DNL DCM] registri.

Ricorda che per utilizzare queste informazioni per la creazione e la segmentazione dell'audience, devi configurare autonomamente le caratteristiche basate su regole. The table lists the actionable signals from [!DNL DCM] log files:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segnale </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Esempio di valore </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ event</code> </p> </td> 
   <td colname="col2"> <p>Indica il tipo di evento da DCM. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_ event = imp</code> per le impression. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_ event = click</code> per i clic. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_ event = conv</code> per le conversioni. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversion</code> </p> </td> 
   <td colname="col2"> <p>Disponibile solo per gli eventi di conversione. </p> <p>Rappresenta l'ID numerico per l'attività di conversione in DCM. Questo campo viene mappato sull'ID attività da DCM. </p> <p> <p>Suggerimento: Puoi acquisire attività di conversione multiple o specifiche da DCM. Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversiontype</code> </p> </td> 
   <td colname="col2"> <p>Disponibile solo per gli eventi di conversione. </p> <p>Questo campo viene mappato sull'ID conversione in DCM. Indica l'attività prima della conversione dell'utente da DCM. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> per le conversioni post-clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> per le conversioni di post-impression. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> per le conversioni senza corrispondenza. La conversione non può corrispondere a un'attività precedente. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col2"> <p>ID inserzionista. Questo campo viene mappato sull'ID del gruppo Inserzionista da DCM. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col2"> <p>ID unità aziendale. Questo campo viene mappato sull'ID inserzionista da DCM. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col2"> <p>L'ID campagna fornito da DCM. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col2"> <p>L'ID creativo fornito da DCM. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col2"> <p>L'ID dell'origine dati che utilizzi per acquisire dati DCM. See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance = "high"}
>
>The event timestamp provided in the [!DNL DCM] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn't available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL DCM] log file contains a malformed timestamp, we ignore the entire row.


## Casi d'uso {#use-cases}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. Questo consente, ad esempio, di calcolare il numero di volte in cui un utente mostra un particolare elemento creativo, all'interno di una campagna multimediale. Altri casi d'uso includono:

### Utenti di destinazione

Gli utenti di retargeting che hanno visto creative 123 ma non hanno fatto clic o sono stati convertiti e mostrano creative 456. Effettua questa operazione:

1. Create una caratteristica per acquisire gli utenti che hanno visto i creativi. Let's say you name the trait [!DNL Creative Trait 123]. Utilizzate la regola caratteristica:

   `d_creative == 123 AND d_event == imp`

1. Create una caratteristica per acquisire gli utenti che fanno clic o convertite. Let's say you name this one [!DNL Click and Converter]. Utilizzate la regola caratteristica:

   `d_event == click OR d_event=conv`

1. Crea un segmento da compilare con utenti che hanno visto creative 123, ma non hanno fatto clic o convertito. Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### Utilizzare l'attività DCM Buttdlight nei report di ottimizzazione dell'audience o in Audience Lab

[I tag Feadlight](https://support.google.com/dcm/partner/answer/4293719?hl=en) consentono agli inserzionisti di tenere traccia delle conversioni degli utenti. With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Create una caratteristica e utilizzate la seguente regola caratteristica per acquisire una conversione dai registri di annunci pubblicitari:

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_ LIKE_ THIS]
>
>* [Importare file di dati DCM in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Report di ottimizzazione dell'audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

