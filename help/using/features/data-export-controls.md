---
description: Controlli sull'esportazione dei dati non consentono l'invio di dati alle destinazioni in caso di violazione della privacy dei dati o degli accordi sull'uso dei dati.
seo-description: Controlli sull'esportazione dei dati non consentono l'invio di dati alle destinazioni in caso di violazione della privacy dei dati o degli accordi sull'uso dei dati.
seo-title: Controlli sull’esportazione dei dati
solution: Audience Manager
title: Controlli sull’esportazione dei dati
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 1%

---


# Controlli sull’esportazione dei dati {#data-export-controls}

[!UICONTROL Data Export Controls] impedire l&#39;invio di dati alle destinazioni in caso di violazione della privacy dei dati o degli accordi sull&#39;utilizzo dei dati.

## Panoramica {#overview}

[!UICONTROL Data Export Controls] consente di classificare origini [e](../features/datasources-list-and-settings.md#data-sources-list-and-settings) destinazioni [](../features/destinations/destinations.md)di dati. Le classificazioni applicate determinano quando è possibile o meno esportare i dati in una destinazione. Questa funzione è costituita da:

* **[!UICONTROL Data Export Controls]**: È possibile impostare Controlli sull&#39;esportazione dei dati sulle origini ** dati. Se impostati su un&#39;origine dati, questi controlli limitano il modo in cui l&#39;origine dati e le relative caratteristiche possono essere utilizzate.
* **[!UICONTROL Data Export Labels]**: Puoi impostare le etichette di esportazione dei dati sulle *destinazioni*. Se impostate su una destinazione, queste etichette identificano il modo in cui la destinazione utilizza i dati. Per informazioni su come aggiungere etichette di esportazione a una destinazione, consulta [Aggiungere etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) .

In base alle classificazioni applicate a un&#39;origine dati e a una destinazione, i controlli per l&#39;esportazione non consentono di:

* Aggiunta di una caratteristica a un segmento quando la caratteristica appartiene a un&#39;origine dati con un controllo di esportazione dei dati incompatibile con un&#39;etichetta di esportazione dei dati su una o più destinazioni a cui è mappato il segmento.
Ad esempio, supponiamo che un segmento sia mappato su una destinazione con l&#39;etichetta di esportazione **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. I controlli di esportazione impediscono di aggiungere una caratteristica a tale segmento se l’origine dati a cui appartiene la caratteristica dispone di un controllo di esportazione dei dati che ne riporta la dicitura **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* L&#39;invio di dati a una destinazione presenta un&#39;etichetta di esportazione di dati bloccata da un controllo di esportazione di dati in uno dei seguenti modi:
   * L&#39;origine dati di una caratteristica inclusa;
   * L&#39;origine dati di una caratteristica utilizzata in un segmento incluso;
   * Regola di unione del profilo utilizzata da un segmento incluso;
   * Qualsiasi origine dati utilizzata dalla regola di unione dei profili di un segmento inclusa.

[!UICONTROL Data Export Controls] sono disponibili automaticamente per tutti  clienti Audience Manager. Tuttavia, è necessario disporre di autorizzazioni di amministratore per aggiungere controlli di esportazione a un&#39;origine dati. L&#39;aggiunta di etichette di esportazione a una destinazione richiede autorizzazioni di amministratore *o* privilegi sufficienti per creare o modificare una destinazione.

## Controlli ed etichette definiti {#controls-labels}

[!UICONTROL Data Export Controls] forniscono i seguenti controlli per semplificare la classificazione delle origini dati e delle destinazioni.

Per bloccare la consegna dei dati, è necessario classificare un&#39;origine dati con un controllo di esportazione e aggiungere un&#39;etichetta di esportazione a una destinazione. Se si applicano controlli di esportazione solo a un&#39;origine dati o a una destinazione, questa funzione non limita la consegna dei dati. Se impostati sia sull’origine dati che sulla ** destinazione, i controlli di esportazione limiteranno le caratteristiche che è possibile aggiungere a un segmento e impediranno l’invio dei membri del segmento a una destinazione.

Inoltre, almeno un&#39;etichetta di esportazione deve corrispondere a un controllo di esportazione prima dell&#39;entrata in vigore delle restrizioni di consegna dei dati. Ad esempio, aggiungere il controllo [!UICONTROL PII] di esportazione a un&#39;origine dati. Quindi, aggiungete l&#39;etichetta di targeting on-site a una destinazione. In questo caso, i controlli di esportazione non limiteranno la consegna dei dati perché le impostazioni non corrispondono. Tuttavia, se aggiungete l’etichetta di [!UICONTROL PII] esportazione alla destinazione, i controlli di esportazione bloccheranno l’esportazione.

>[!IMPORTANT]
>
>Non è possibile bloccare l&#39;esportazione di un segmento inserendo un controllo di esportazione dei dati nell&#39;origine dati del segmento, è necessario impostare il controllo su uno dei seguenti elementi:
> * Le origini dati delle caratteristiche utilizzate nel segmento;
> * Regola di unione del profilo utilizzata dal segmento;
> * Qualsiasi origine dati utilizzata dalla regola di unione dei profili del segmento.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Controlli sull'esportazione dei dati per un'origine dati </th> 
   <th colname="col2" class="entry"> Etichette esportazione dati per una destinazione </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nessuna limitazione</span></b> </td> 
   <td colname="col2"> n/d </td> 
   <td colname="col3"> Per impostazione predefinita, le restrizioni all'esportazione non sono impostate su nuove origini dati e destinazioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere legato a informazioni</span></b> personali (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può consentire una combinazione con informazioni personali (PII)</span></b> </td> 
   <td colname="col3">Se questa opzione è selezionata, non è possibile: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Aggiungi caratteristiche ai segmenti mappati a destinazioni che utilizzano PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Mappa i segmenti generati con una caratteristica dall’origine dati alle destinazioni che utilizzano PII. </li> 
    </ul> <p>Questo è spesso richiesto da fornitori di dati di terze parti e quando si utilizzano origini dati che contengono informazioni sul tracciamento di annunci o supporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per il targeting di annunci on-site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per il targeting on-site degli annunci</span></b> </td> 
   <td colname="col3">Se questa opzione è selezionata, non è possibile: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Aggiungi caratteristiche ai segmenti mappati a destinazioni che personalizzano la distribuzione degli annunci in base alla cronologia di navigazione Web di un visitatore. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Mappa i segmenti generati con una caratteristica dall'origine dati alle destinazioni che personalizzano la distribuzione degli annunci in base alla cronologia di navigazione Web di un visitatore. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per il targeting di annunci fuori sito</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per targeting di annunci fuori sito</span></b> </td> 
   <td colname="col3">Queste restrizioni vengono utilizzate generalmente con l'opzione Se selezionata, non è possibile: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Aggiungi caratteristiche ai segmenti mappati a destinazioni che eseguono nuovamente il targeting degli utenti su altri siti. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mappa i segmenti generati con una caratteristica dall’origine dati a destinazioni che rieseguono il targeting degli utenti su altri siti. </li> 
    </ul> <p>Spesso richiesto quando si lavora con dati provenienti da piattaforme social media. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per la personalizzazione sul sito</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per la personalizzazione degli annunci sul sito</span></b> </td> 
   <td colname="col3">Se questa opzione è selezionata, non è possibile: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Aggiungi caratteristiche ai segmenti mappati a destinazioni che personalizzano il contenuto in base agli interessi degli utenti o alla cronologia di navigazione sul Web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Mappa i segmenti creati con una caratteristica dall’origine dati alle destinazioni che personalizzano i contenuti in base agli interessi degli utenti o alla cronologia di navigazione sul Web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Flusso di lavoro {#workflow}

Per iniziare, consulta la documentazione sull’origine dati e sulla destinazione. Questi articoli forniscono istruzioni su come aggiungere controlli ed etichette di esportazione alle origini dati e alle destinazioni.

* [Creare una sorgente di dati](../features/manage-datasources.md#create-data-source)
* [Aggiungi etichette di esportazione dati a una destinazione](../features/destinations/add-data-export-labels.md)