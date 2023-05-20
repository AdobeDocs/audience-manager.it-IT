---
description: La funzione Controlli sull’esportazione dei dati impedisce l’invio di dati alle destinazioni quando questa azione viola la privacy dei dati o gli accordi sull’utilizzo dei dati.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Controlli sull’esportazione dei dati
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 26aa0a210a045b40b2329844324315a092947188
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Controlli sull’esportazione dei dati {#data-export-controls}

[!UICONTROL Data Export Controls] impedisce l’invio di dati alle destinazioni quando questa azione viola la privacy dei dati o gli accordi sull’utilizzo dei dati.

## Panoramica {#overview}

[!UICONTROL Data Export Controls] ti consente di classificare [origini dati](../features/datasources-list-and-settings.md#data-sources-list-and-settings) e [destinazioni](../features/destinations/destinations.md). Le classificazioni applicate determinano quando i dati possono o non possono essere esportati in una destinazione. Questa funzione è costituita da:

* **[!UICONTROL Data Export Controls]**: è possibile impostare i controlli di esportazione dei dati su *origini dati*. Se impostati su un&#39;origine dati, questi controlli limitano le modalità di utilizzo dell&#39;origine dati e delle caratteristiche.
* **[!UICONTROL Data Export Labels]**: è possibile impostare le etichette di esportazione dei dati su *destinazioni*. Se impostate su una destinazione, queste etichette identificano il modo in cui la destinazione utilizza i dati. Consulta [Aggiungere etichette di esportazione dei dati a una destinazione](/help/using/features/destinations/add-data-export-labels.md) per scoprire come aggiungere etichette di esportazione a una destinazione.

In base alle classificazioni applicate a un’origine dati e a una destinazione, i controlli di esportazione impediscono di:

* Aggiunta di una caratteristica a un segmento quando la caratteristica appartiene a un’origine dati con un controllo di esportazione dati incompatibile con un’etichetta di esportazione dati su una o più destinazioni a cui è mappato il segmento.
Ad esempio, supponiamo che un segmento sia mappato a una destinazione con l’etichetta di esportazione **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. I controlli di esportazione impediscono l’aggiunta di una caratteristica a quel segmento se l’origine dati a cui appartiene la caratteristica dispone di un controllo di esportazione dei dati che indica **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* Invio di dati a una destinazione con un&#39;etichetta di esportazione dei dati bloccata da un controllo di esportazione dei dati su uno dei seguenti elementi:
   * La fonte di dati di una caratteristica inclusa;
   * La fonte di dati di una caratteristica utilizzata in un segmento incluso;
   * La regola di unione dei profili utilizzata da un segmento incluso;
   * Una qualsiasi delle origini dati utilizzate dalla regola di unione profili di un segmento incluso.

[!UICONTROL Data Export Controls] sono disponibili automaticamente per tutti i clienti Audience Manager. Tuttavia, per aggiungere controlli di esportazione a un&#39;origine dati è necessario disporre delle autorizzazioni di amministratore. L’aggiunta di etichette di esportazione a una destinazione richiede le autorizzazioni di amministratore *o* privilegi sufficienti per creare o modificare una destinazione.

## Definizione di controlli ed etichette {#controls-labels}

[!UICONTROL Data Export Controls] fornisci i seguenti controlli per classificare le origini dati e le destinazioni.

Per bloccare la consegna dei dati, è necessario classificare un&#39;origine dati con un controllo di esportazione e aggiungere un&#39;etichetta di esportazione a una destinazione. Se si applicano i controlli di esportazione solo a un&#39;origine dati o a una destinazione, questa funzione non limiterà la distribuzione dei dati. Se impostata su entrambe le origini dati *e* destinazione, i controlli di esportazione limitano le caratteristiche che puoi aggiungere a un segmento e impediscono l’invio dei membri del segmento a una destinazione.

Inoltre, almeno un’etichetta di esportazione deve corrispondere a un controllo di esportazione prima che le restrizioni di consegna dei dati diventino effettive. Ad esempio, supponiamo che tu aggiunga il [!UICONTROL PII] esportare il controllo in un&#39;origine dati. Successivamente, aggiungi l’etichetta di targeting nel sito a una destinazione. In questo caso, i controlli di esportazione non limitano la consegna dei dati perché le impostazioni non corrispondono. Tuttavia, se si aggiunge [!UICONTROL PII] export label to the destination, i controlli di esportazione bloccheranno l’esportazione.

>[!IMPORTANT]
>
>Non è possibile bloccare l’esportazione di un segmento inserendo un controllo di esportazione dati nell’origine dati del segmento, è necessario impostare il controllo su:
> * Le fonti di dati delle caratteristiche utilizzate nel segmento;
> * La regola di unione dei profili utilizzata dal segmento;
> * Una qualsiasi delle origini dati utilizzate dalla regola di unione profili del segmento.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Controlli sull’esportazione dei dati per un’origine dati </th> 
   <th colname="col2" class="entry"> Etichette di esportazione dei dati per una destinazione </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nessuna restrizione</span></b> </td> 
   <td colname="col2"> n/d </td> 
   <td colname="col3"> Per impostazione predefinita, le restrizioni all’esportazione non sono impostate sulle nuove origini dati e destinazioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere legato a informazioni personali identificabili</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può consentire la combinazione con informazioni personali (PII)</span></b> </td> 
   <td colname="col3">Se selezionata, non è possibile: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Aggiungi caratteristiche ai segmenti mappati su destinazioni che utilizzano dati PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Mappa i segmenti generati con una caratteristica dall’origine dati alle destinazioni che utilizzano dati PII. </li> 
    </ul> <p>Questo è spesso richiesto da fornitori di dati di terze parti e quando si utilizzano origini dati che contengono informazioni di tracciamento di annunci/media. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per il targeting di annunci nel sito</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per il targeting di annunci nel sito</span></b> </td> 
   <td colname="col3">Se selezionata, non è possibile: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Aggiungi caratteristiche ai segmenti mappati su destinazioni che personalizzano la distribuzione degli annunci in base alla cronologia di navigazione web di un visitatore. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Mappa i segmenti generati con una caratteristica dell’origine dati su destinazioni che personalizzano la distribuzione degli annunci in base alla cronologia di navigazione web di un visitatore. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per il targeting di annunci esterni al sito</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per il targeting di annunci fuori sito</span></b> </td> 
   <td colname="col3">Se selezionata, non è possibile: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Aggiungi caratteristiche ai segmenti mappati su destinazioni per il ritargeting di utenti su altri siti. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mappa i segmenti generati con una caratteristica dell’origine dati su destinazioni che eseguono il retargeting degli utenti su altri siti. </li> 
    </ul> <p>Spesso necessario quando si lavora con dati provenienti da piattaforme di social media. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per la personalizzazione nel sito</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per la personalizzazione degli annunci nel sito</span></b> </td> 
   <td colname="col3">Se selezionata, non è possibile: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Aggiungi caratteristiche ai segmenti mappati su destinazioni che personalizzano il contenuto in base agli interessi degli utenti o alla cronologia delle esplorazioni web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Mappa i segmenti generati con una caratteristica dell’origine dati su destinazioni che personalizzano il contenuto in base agli interessi degli utenti o alla cronologia delle esplorazioni web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Flusso di lavoro {#workflow}

Per iniziare, consulta la documentazione su origine dati e destinazione. In questi articoli vengono fornite istruzioni su come aggiungere controlli ed etichette di esportazione alle origini dati e alle destinazioni.

* [Creare una sorgente di dati](../features/manage-datasources.md#create-data-source)
* [Aggiungere etichette di esportazione dei dati a una destinazione](../features/destinations/add-data-export-labels.md)
