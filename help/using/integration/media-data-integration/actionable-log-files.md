---
description: I file di registro fruibili consentono di acquisire dati multimediali dai file di registro di Google DCM e di utilizzare i dati per creare caratteristiche in Audience Manager. Puoi acquisire come caratteristiche impression, clic e conversioni da server di annunci, senza dover ricorrere a chiamate pixel.
keywords: registri fruibili
seo-description: I file di registro fruibili consentono di acquisire dati multimediali dai file di registro di Google DCM e di utilizzare i dati per creare caratteristiche in Audience Manager. Puoi acquisire come caratteristiche impression, clic e conversioni da server di annunci, senza dover ricorrere a chiamate pixel.
seo-title: File di registro fruibili
solution: Audience Manager
title: File di registro fruibili
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# File di registro fruibili {#actionable-log-files}

[!UICONTROL Actionable Log Files] consente di acquisire dati multimediali dai file di [!DNL Google DCM] registro e di utilizzare i dati per creare caratteristiche in Audience Manager. Puoi acquisire come caratteristiche impression, clic e conversioni da server di annunci, senza dover ricorrere a chiamate pixel.

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) in questo documento indicano gli elementi e le opzioni del codice. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../reference/code-style-elements.md).

## Finalità {#purpose}

[!UICONTROL Actionable Log Files] ottimizza il modo in cui acquisisci impression, clic e conversioni dai server di annunci. Utilizzate queste informazioni per la segmentazione degli utenti senza dover inviare manualmente i file multimediali in pixel per inviare gli attributi della campagna a [!DNL Audience Manager].

## Introduzione {#getting-started}

Per iniziare [!UICONTROL Actionable Log Files]e per utilizzare i nostri report [di ottimizzazione dell'](../../reporting/audience-optimization-reports/audience-optimization-reports.md)audience, devi importare i dati di registro di DCM in [!DNL Audience Manager]. Consultate [Importare file di dati DCM in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *e contattate* il [!DNL Audience Manager] consulente.

Se state già importando i dati di [!UICONTROL DCM] registro in [!DNL Audience Manager], chiedete al vostro [!DNL Audience Manager] consulente o all'Assistenza [](https://helpx.adobe.com/contact/enterprise-support.ec.html) clienti di effettuare [!UICONTROL Actionable Log Files] l'operazione.

>[!NOTE] {important="high"}
>
>[!UICONTROL Actionable Log Files] funziona solo con i file di [!DNL Google DCM] registro.

## Utilizzo dei file di registro fruibili {#working-with-actionable-log-files}

Con [!UICONTROL Actionable Log Files], le informazioni dai [!DNL DCM] registri vengono acquisite [!DNL Audience Manager] nello stesso modo in cui si acquisiscono i dati dalle interazioni in tempo reale sui siti Web. [!DNL Audience Manager] si collega al [!DNL Google Cloud] sistema di storage, analizza le informazioni dai [!DNL DCM] registri e invia i dati del registro come segnali fruibili ai nostri server [di raccolta](../../reference/system-components/components-data-collection.md#dcs-pcs)dati.

È comunque necessario impostare caratteristiche basate su regola per acquisire i segnali fruibili. Scopri come impostare caratteristiche basate su regola nell’interfaccia utente [di](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) Audience Manager o tramite i nostri strumenti [di gestione](../../reference/bulk-management-tools/bulk-create.md)in blocco. Scorri verso il basso fino alla sezione [Segnali](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) fruibili per visualizzare un elenco di tutte le chiavi utilizzabili nelle caratteristiche basate su regola.

Per un file di [!DNL DCM] registro di dimensioni medie di 2 milioni di righe, tutte le caratteristiche create dai segnali attivabili vengono realizzate entro circa un'ora dopo l'elaborazione dei registri.

>[!IMPORTANT] {important="high"}
>
>È consigliabile implementare [!UICONTROL Actionable Log Files] invece *delle chiamate* pixel [](../../integration/media-data-integration/impression-data-pixels.md). Non scoraggiamo l'uso di entrambe le opzioni, in quanto ciò comporta un aumento del numero di frequenze per le caratteristiche.

## Segnali fruibili {#actionable-signals}

I segnali sono le unità [dati](../../reference/signal-trait-segment.md) più piccole in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] consente di acquisire i valori di advertiser, business unit, creative e campaign in eventi impression, clic ed eventi di conversione come segnali dai [!DNL DCM] registri.

Ricordate che, per utilizzare queste informazioni per la creazione e la segmentazione dell'audience, dovete impostare voi stessi le caratteristiche basate su regola. Nella tabella sono elencati i segnali utilizzabili dai file di [!DNL DCM] registro:

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
   <td colname="col1"> <p> <code> d_event</code> </p> </td> 
   <td colname="col2"> <p>Indica il tipo di evento da DCM. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> per le impression. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> for click. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> per le conversioni. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col2"> <p>Disponibile solo per gli eventi di conversione. </p> <p>Rappresenta l'ID numerico per l'attività di conversione in DCM. Questo campo viene mappato sull'ID attività da DCM. </p> <p> <p>Suggerimento: È possibile acquisire attività di conversione multiple o specifiche da DCM. Create caratteristiche utilizzando <code> d_conversion = ID</code> attività per ogni attività di conversione da DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversionType</code> </p> </td> 
   <td colname="col2"> <p>Disponibile solo per gli eventi di conversione. </p> <p>Questo campo viene mappato sull’ID conversione in DCM. Indica l'attività che precede la conversione utente da DCM. </p> <p>I valori accettati sono: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> per le conversioni post-clic. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> per le conversioni post-impressione. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> per conversioni non corrispondenti. Impossibile associare la conversione a un'attività precedente. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col2"> <p>ID inserzionista.</p> <p>Un codice di integrazione per l'origine dati dell'inserzionista. Questo non è correlato alle origini dati di Audience Manager.</p> <p>Questo campo viene mappato sull’ID del gruppo di inserzionisti da DCM. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col2"> <p>ID unità aziendale. Questo campo viene mappato sull’ID inserzionista da DCM. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col2"> <p>L'ID campagna fornito da DCM. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col2"> <p>ID creativo fornito da DCM. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col2"> <p>L'ID dell'origine dati utilizzata per acquisire i dati DCM. Vedere <a href="../../features/manage-datasources.md#create-data-source"> Come creare un'origine</a>dati. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

I segnali descritti nella tabella vengono acquisiti in [!DNL Audience Manager] modo simile a una `HTTP` chiamata in tempo reale. La seguente chiamata di esempio contiene informazioni su un evento di conversione da [!DNL DCM]. Le chiamate non devono necessariamente includere *tutti* i segnali nella chiamata di esempio.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {important="high"}
>
>La marca temporale dell'evento fornita nei [!DNL DCM] registri verrà rispettata e trasmessa al [!UICONTROL Data Collection Servers].
>
>* Se una marca temporale non è disponibile per una riga di dati nel file di [!DNL DCM] registro, utilizzeremo l'ora della `HTTP` chiamata come marca temporale dell'evento.
>* Se la riga di dati nel file di [!DNL DCM] registro contiene una marca temporale non valida, ignoreremo l'intera riga.


## Casi d'uso {#use-cases}

Un vantaggio dell'implementazione [!UICONTROL Actionable Log Files] è la possibilità di applicare controlli di [aggiornamento e frequenza](../../features/segments/recency-and-frequency.md) a qualsiasi caratteristica [basata su](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) regole che contenga segnali fruibili. Questo consente, ad esempio, di limitare la frequenza al massimo del numero di volte in cui un utente riceve una particolare creatività all’interno di una campagna multimediale. Altri casi di utilizzo:

### Utenti di Retarget

Riavviate gli utenti che hanno visto creative 123 ma non hanno fatto clic o convertito per mostrare loro creative 456. Effettuate le seguenti operazioni:

1. Create una caratteristica per catturare gli utenti che hanno visto il creativo. Diciamo che chiami la caratteristica [!DNL Creative Trait 123]. Utilizzate la regola delle caratteristiche:

   `d_creative == 123 AND d_event == imp`

1. Create una caratteristica per catturare gli utenti che fanno clic o convertono. Diciamo che chiami questo [!DNL Click and Converter]. Utilizzate la regola delle caratteristiche:

   `d_event == click OR d_event=conv`

1. Crea un segmento da compilare con gli utenti che hanno visto creative 123 ma non hanno fatto clic o convertito. Assegnate un nome [!DNL Retarget Users] e utilizzate la regola del segmento:

   `Creative Trait 123 AND NOT Click and Converter`

1. Mappatura il segmento [!DNL Retarget Users] a una destinazione e targeting degli utenti nella destinazione con creative 456.

### Utilizzare l'attività di DCM Floodlight nei report di ottimizzazione dell'audience o in Audience Lab

[I tag](https://support.google.com/dcm/partner/answer/4293719?hl=en) Floodlight consentono agli inserzionisti di tenere traccia delle conversioni degli utenti. Con [!UICONTROL Actionable Log Files], puoi tenere traccia delle [!DNL DCM] conversioni nei report [di ottimizzazione](../../reporting/audience-optimization-reports/audience-optimization-reports.md) dell'audience o in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Create una caratteristica e utilizzate la seguente regola di caratteristiche per acquisire una conversione dai registri del server di annunci:

   `d_event == conv AND d_conversion == 123`

   Quando create la caratteristica in Audience Manager [!UICONTROL UI], selezionate [!UICONTROL Conversion] come [!UICONTROL Event Type].

2. Una volta creata la caratteristica, la conversione inizierà a essere segnalata nel [!UICONTROL Audience Optimization Reports] e in [!UICONTROL Audience Lab].

>[!MORE_LIKE_this]
>
>* [Importa file di dati DCM in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Report di ottimizzazione dell'audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

