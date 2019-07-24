---
description: L'esclusione caratteristica fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, che consentono di aggiungere al modello le barre di controllo necessarie, in base alle conoscenze e ai requisiti normativi del sistema. Utilizzare l'opzione Esclusioni per selezionare le caratteristiche da ignorare quando si creano modelli da una o più origini dati.
seo-description: L'esclusione caratteristica fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, che consentono di aggiungere al modello le barre di controllo necessarie, in base alle conoscenze e ai requisiti normativi del sistema. Utilizzare l'opzione Esclusioni per selezionare le caratteristiche da ignorare quando si creano modelli da una o più origini dati.
seo-title: Esclusione trait modelli algoritmici
title: Esclusione trait modelli algoritmici
uuid: 1359800 b -6 e 6 c -41 e 1-88 b 4-23 d 31952 abb 3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, che consentono di aggiungere al modello le barre di controllo necessarie, in base alle conoscenze e ai requisiti normativi del sistema. Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## Casi d'uso {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] consente di escludere alcune caratteristiche catch-all, ad esempio le caratteristiche dei visitatori del sito, in modo da non influenzare il modello, generando risultati semplici.
* Potete rimuovere caratteristiche che non conoscete o considerare affidabili da un'origine dati, per comprendere meglio le caratteristiche influenti.
* Potete escludere alcune caratteristiche, ad esempio caratteristiche demografiche, per fornire assistenza con eventuali obblighi di conformità.

>[!IMPORTANT]
>
>Nota importante sul terzo caso d'uso. If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. Dopo la creazione del modello non potete escludere caratteristiche dalla modellazione. See [Important Aspects &amp; Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Attenetevi alla cautela quando utilizzate questa funzione e lavorate con il provider di dati per essere informati di eventuali modifiche alla struttura dei feed.

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. [!UICONTROL Exclusions] La selezione viene visualizzata in grigio finché non selezioni una o più origini dati per la modellazione.
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. In the **[!UICONTROL Select Traits to Exclude]** window, you can see all traits associated with the data sources you selected previously. Selezionate le caratteristiche da escludere.
4. Potete filtrare le caratteristiche per tipo di caratteristica oppure sfogliare le cartelle delle caratteristiche. Tieni presente che le cartelle delle caratteristiche visualizzano solo le caratteristiche associate alle origini dati selezionate.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>Potete escludere intere cartelle escludendo la caratteristica della cartella, anziché escluderle. Ad esempio, in una cartella con 20 caratteristiche, dovrete escludere solo la caratteristica della cartella, anziché escluderle una per volta.

Se preferite esercitazioni video, guardate la nostra dimostrazione video per l'esclusione delle caratteristiche:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=ita)

## Important Aspects &amp; Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche escluse nella visualizzazione Riepilogo modelli </p> </td>
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controlli di accesso basati su ruolo (RBAC) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifica le caratteristiche escluse dopo il salvataggio del modello </p> </td>
   <td colname="col2"> <p>Non è possibile modificare le caratteristiche escluse dopo aver creato e salvato un modello. Se desiderate regolare i risultati, potete clonare il modello e modificare le caratteristiche escluse. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Numero massimo di caratteristiche che è possibile escludere </p> </td>
   <td colname="col2"> <p>Il numero massimo di caratteristiche che è possibile escludere da un modello è 500. Utilizzate le caratteristiche delle cartelle per massimizzare le esclusioni. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escludi caratteristica linea di base </p> </td>
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## Collegamenti correlati

* [Informazioni sulle caratteristiche algoritmiche](/help/using/features/algorithmic-models/understanding-models.md)
* [Esclusione caratteristica - Esercitazione](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)