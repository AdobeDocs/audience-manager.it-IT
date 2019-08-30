---
description: I Controlli sull'esportazione dei dati impediscono l'invio di dati alle destinazioni quando questa azione viola la privacy dei dati o i dati utilizzati.
seo-description: I Controlli sull'esportazione dei dati impediscono l'invio di dati alle destinazioni quando questa azione viola la privacy dei dati o i dati utilizzati.
seo-title: Controlli sull'esportazione dei dati
solution: Audience Manager
title: Controlli sull'esportazione dei dati
uuid: de 7 f 3608-c 0 cb -4049-973 a -8 be 54525 c 600
translation-type: tm+mt
source-git-commit: 22657113512e136296be5c4bcb8e092e65f45c06

---


# Controlli sull'esportazione dei dati {#data-export-controls}

[!UICONTROL Data Export Controls] impedire l'invio di dati alle destinazioni quando questa azione viola la privacy dei dati o i dati.

## Panoramica {#overview}

[!UICONTROL Data Export Controls] consente di classificare [le origini](../features/datasources-list-and-settings.md#data-sources-list-and-settings) dati e [le destinazioni](../features/destinations/destinations.md). Le classificazioni applicate determinano quando i dati possono o meno essere esportati in una destinazione. Questa funzione consiste in:

* **[!UICONTROL Data Export Controls]**: Potete impostare Controlli esportazione dati sulle *origini dati*. Se si imposta un'origine dati, questi controlli limitano l'utilizzo delle caratteristiche e delle caratteristiche dell'origine dati.
* **[!UICONTROL Data Export Labels]**: Potete impostare Etichette esportazione dati sulle *destinazioni*. Quando viene impostata su una destinazione, queste etichette identificano in che modo la destinazione utilizza i dati. Per informazioni su come aggiungere etichette di esportazione a una destinazione, consultate [Aggiungere etichette di esportazione dati a una destinazione](/help/using/features/destinations/add-data-export-labels.md) .

In base alle classificazioni applicate a un'origine dati e a una destinazione, i controlli di esportazione ti interrompono da:

* Aggiungere una caratteristica a un segmento quando questo appartiene a un'origine dati con un controllo di esportazione dati incompatibile con un'etichetta di esportazione dati su una o più destinazioni a cui il segmento viene mappato.
Ad esempio, supponiamo che un segmento sia mappato a una destinazione con l'etichetta **[!DNL This destination may enable a combination with personally identifiable information (PII)]** di esportazione. I controlli per l'esportazione non consentono **[!DNL Cannot be tied to personally identifiable information (PII)]** di aggiungere una caratteristica a tale segmento se l'origine dati a cui appartiene ha un controllo sull'esportazione di dati.
* L'invio di dati a una destinazione di destinazione presenta un'etichetta di esportazione dati bloccata da un controllo di esportazione dei dati su:
   * L'origine dati di una caratteristica inclusa;
   * L'origine dati di una caratteristica utilizzata in un segmento incluso;
   * La regola di unione profilo sfrutta un segmento incluso;
   * Una qualsiasi delle sorgenti dati utilizzate da una regola di unione profilo del segmento incluso.

[!UICONTROL Data Export Controls] sono disponibili automaticamente per tutti i clienti di Audience Manager. Tuttavia, è necessario disporre delle autorizzazioni di amministratore per aggiungere controlli di esportazione a un'origine dati. Per aggiungere etichette di esportazione a una destinazione è necessario disporre di autorizzazioni *amministratore o* di privilegi sufficienti per creare o modificare una destinazione.

## Controlli ed etichette definite {#controls-labels}

[!UICONTROL Data Export Controls] fornisce i seguenti controlli per la classificazione delle origini dati e delle destinazioni.

Per bloccare la consegna dei dati, è necessario classificare un'origine dati con un controllo di esportazione e aggiungere un'etichetta di esportazione a una destinazione. Se si applicano controlli di esportazione a un'origine dati o a una destinazione, questa funzione non limita la distribuzione dei dati. Se si imposta sia l'origine *dati* che la destinazione, i controlli di esportazione limiteranno le caratteristiche che è possibile aggiungere a un segmento e impedirne l'invio a una destinazione.

Inoltre, almeno un'etichetta di esportazione deve corrispondere a un controllo dell'esportazione prima di applicare le limitazioni di consegna dei dati. Ad esempio, supponete di aggiungere il [!UICONTROL PII] controllo esportazione a un'origine dati. Successivamente, aggiungete l'etichetta di targeting on-site a una destinazione. In questo caso, i controlli di esportazione non limitano la distribuzione dei dati, poiché le impostazioni non corrispondono. Tuttavia, se aggiungete l'etichetta [!UICONTROL PII] di esportazione alla destinazione, i controlli di esportazione bloccano l'esportazione.

>[!IMPORTANT]
>
>Non puoi bloccare l'esportazione di un segmento inserendo un controllo di esportazione dati sull'origine dati del segmento, devi impostare il controllo su:
> * Le origini dati delle caratteristiche utilizzate nel segmento;
> * La regola di unione profilo sfrutta il segmento;
> * Qualsiasi sorgente dati utilizzata dalla regola unione profilo del segmento.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Controlli esportazione dati per un'origine dati </th> 
   <th colname="col2" class="entry"> Etichette esportazione dati per una destinazione </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nessuna limitazione</span></b> </td> 
   <td colname="col2"> n/d </td> 
   <td colname="col3"> Per impostazione predefinita, le limitazioni di esportazione non vengono impostate su nuove origini dati e destinazioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere associato a informazioni</span></b> personali identificabili (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può consentire una combinazione con informazioni personali (PII)</span></b> </td> 
   <td colname="col3">Se selezionato, non è possibile: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Aggiungi caratteristiche a segmenti mappati a destinazioni che utilizzano PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Mappa i segmenti creati con una caratteristica dall'origine dati alle destinazioni che utilizzano PII. </li> 
    </ul> <p>Questa funzione è spesso necessaria per fornitori di dati di terze parti e quando si utilizzano origini dati contenenti informazioni di tracciamento pubblicitari/supporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per targeting on-site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per targeting on-site</span></b> </td> 
   <td colname="col3">Se selezionato, non è possibile: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Aggiungi caratteristiche a segmenti mappati alle destinazioni che personalizzano la distribuzione degli annunci in base alla cronologia di esplorazione Web di un visitatore. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Mappatura di segmenti creati con una caratteristica dall'origine dati alle destinazioni che personalizzano la distribuzione degli annunci in base alla cronologia di esplorazione Web di un visitatore. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per targeting di annunci offline</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per targeting di annunci offsite</span></b> </td> 
   <td colname="col3">Queste limitazioni vengono utilizzate in genere con l'opzione Se selezionata, non è possibile: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Aggiungi caratteristiche a segmenti mappati a destinazioni che eseguono il targeting degli utenti su altri siti. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mappatura di segmenti creati con una caratteristica dall'origine dati alle destinazioni che eseguono il targeting degli utenti su altri siti. </li> 
    </ul> <p>Spesso richiesto quando si lavora con dati provenienti da piattaforme social media. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Non può essere utilizzato per la personalizzazione sul sito</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Questa destinazione può essere utilizzata per la personalizzazione degli annunci sul sito</span></b> </td> 
   <td colname="col3">Se selezionato, non è possibile: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Aggiungi caratteristiche a segmenti mappati a destinazioni che personalizzano il contenuto in base agli interessi degli utenti o alla cronologia di navigazione Web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Mappatura di segmenti creati con una caratteristica dall'origine dati alle destinazioni che personalizzano il contenuto in base agli interessi degli utenti o alla cronologia di navigazione Web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Flusso di lavoro {#workflow}

Per iniziare, consulta la documentazione di origine dati e di destinazione. Questi articoli forniscono istruzioni su come aggiungere controlli ed etichette di esportazione alle origini dati e alle destinazioni.

* [Creare un'origine dati](../features/manage-datasources.md#create-data-source)
* [Aggiungere etichette di esportazione dati a una destinazione](../features/destinations/add-data-export-labels.md)