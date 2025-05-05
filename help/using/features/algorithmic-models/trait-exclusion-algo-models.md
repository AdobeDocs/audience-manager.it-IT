---
description: L’esclusione delle caratteristiche fornisce ulteriori controlli nel flusso di lavoro di modellazione, consentendoti di aggiungere le barre di protezione necessarie al modello, in base all’esperienza nel dominio e ai requisiti normativi. Utilizza l’opzione Esclusioni per selezionare le caratteristiche da ignorare durante la creazione di modelli da una o più origini dati.
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: Esclusione di caratteristiche per modelli algoritmici
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Modellazione lookalike: esclusione di caratteristiche {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fornisce ulteriori controlli nel flusso di lavoro di modellazione, consentendoti di aggiungere le protezioni necessarie al modello, in base alla tua esperienza nel dominio e ai requisiti normativi. Utilizza l&#39;opzione [!UICONTROL Exclusions] per selezionare le caratteristiche da ignorare durante la creazione di modelli da una o più origini dati.

## Casi d&#39;uso {#use-cases}

Di seguito sono riportati alcuni casi d&#39;uso che è possibile risolvere con [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] consente di escludere alcune caratteristiche onnicomprensive, ad esempio le caratteristiche dei visitatori del sito, in modo da non distorcere il modello e ottenere risultati piatti.
* Puoi rimuovere caratteristiche di cui non sei a conoscenza o di cui non ti fidi da un’origine dati, per comprendere meglio le caratteristiche influenti.
* Puoi escludere alcune caratteristiche, ad esempio quelle demografiche, per aiutarti con gli obblighi di conformità che ti incombono.

>[!IMPORTANT]
>
>Una nota importante sul terzo caso d’uso. Se il provider di dati di terze parti aggiunge una nuova caratteristica demografica al feed di dati *dopo la creazione del modello*, la caratteristica verrà automaticamente rilevata dal modello. Non potete escludere le caratteristiche dalla modellazione dopo aver creato il modello. Consulta [Aspetti importanti e limitazioni](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Presta attenzione quando utilizzi questa funzione e collabora con il provider di dati per assicurarti di essere informato di eventuali modifiche alla struttura dei feed.

![](assets/lam_exclude_traits.png)

## Come utilizzare le esclusioni di caratteristiche {#how-to-use}

Utilizza il flusso di lavoro [Genera un modello](../../features/algorithmic-models/create-model.md#build-model) per generare nuovi modelli algoritmici.

1. La selezione di [!UICONTROL Exclusions] è disattivata finché non si selezionano una o più origini dati per la modellazione.
2. Dopo aver selezionato una o più origini dati per la modellazione, premere **[!UICONTROL Browse All Traits]**.
3. Nella finestra **[!UICONTROL Select Traits to Exclude]** è possibile visualizzare tutte le caratteristiche associate alle origini dati selezionate in precedenza. Seleziona le caratteristiche da escludere.
4. Puoi filtrare le caratteristiche per tipo di caratteristica, tipo di popolazione della caratteristica ([ID dispositivo](../../reference/ids-in-aam.md) e [ID multi-dispositivo](../../reference/ids-in-aam.md)), oppure sfogliare le cartelle delle caratteristiche. Nelle cartelle delle caratteristiche vengono visualizzate solo le caratteristiche associate alle origini dati selezionate.
5. Premere **[!UICONTROL Exclude Selected Traits]**.

![esclusioni di caratteristiche](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>È possibile escludere intere cartelle escludendo la caratteristica della cartella invece di escludere, singolarmente, le caratteristiche presenti nella cartella. Ad esempio, in una cartella con 20 caratteristiche, dovresti escludere solo la caratteristica della cartella invece di tutte le caratteristiche una alla volta.

Se preferisci i tutorial video, guarda la nostra dimostrazione video per Esclusione di caratteristiche:

>[!VIDEO](https://video.tv.adobe.com/v/326998/?quality=12&captions=ita)

Inoltre, guarda il video seguente per una panoramica dettagliata del funzionamento delle metriche tra dispositivi diversi.

>[!VIDEO](https://video.tv.adobe.com/v/36892/?quality=12&captions=ita)

## Aspetti importanti e limitazioni {#important-aspects-and-limitations}

Tieni presente i seguenti aspetti e limitazioni relativi a [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche escluse nella vista di riepilogo dei modelli </p> </td>
   <td colname="col2"> <p>Le caratteristiche escluse <i>non vengono visualizzate</i> nella visualizzazione Riepilogo modelli. È possibile visualizzare le caratteristiche escluse solo nel flusso di lavoro <b><span class="uicontrol"> Modifica modello</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>RBAC (Role-Based Access Controls) </p> </td>
   <td colname="col2"> <p>Notare le seguenti limitazioni per le aziende che utilizzano <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Se non hai accesso alla visualizzazione di una caratteristica, <i>non puoi</i> selezionare la caratteristica da escludere dal modello. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Se non hai accesso alla visualizzazione di una caratteristica, <i>non puoi</i> visualizzarla nell'elenco delle caratteristiche escluse. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifica le caratteristiche escluse dopo il salvataggio del modello </p> </td>
   <td colname="col2"> <p>Non potete modificare le caratteristiche escluse dopo aver creato e salvato un modello. Se desiderate modificare i risultati, potete clonare il modello e modificare le caratteristiche escluse. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Numero massimo di caratteristiche da escludere </p> </td>
   <td colname="col2"> <p>Il numero massimo di caratteristiche che è possibile escludere da un modello è 500. Utilizza le caratteristiche della cartella per massimizzare le esclusioni. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escludi caratteristica linea di base </p> </td>
   <td colname="col2"> <p>La caratteristica della linea di base è esclusa per impostazione predefinita, pertanto non viene visualizzata nell'elenco <b><span class="uicontrol"> Esclusioni</span></b> durante la creazione del modello. </p> </td>
  </tr>
 </tbody>
</table>

Guarda il video seguente per scoprire come e perché escludere caratteristiche specifiche da un [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/326998?captions=ita)

## Collegamenti correlati

* [Informazioni sulle caratteristiche algoritmiche](/help/using/features/algorithmic-models/understanding-models.md)
* [Esclusione caratteristiche - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
