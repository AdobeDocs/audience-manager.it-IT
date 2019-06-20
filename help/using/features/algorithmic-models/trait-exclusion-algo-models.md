---
description: L'esclusione caratteristica fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, che consentono di aggiungere al modello le barre di controllo necessarie, in base alle conoscenze e ai requisiti normativi del sistema. Utilizzare l'opzione Esclusioni per selezionare le caratteristiche da ignorare quando si creano modelli da una o più origini dati.
seo-description: L'esclusione caratteristica fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, che consentono di aggiungere al modello le barre di controllo necessarie, in base alle conoscenze e ai requisiti normativi del sistema. Utilizzare l'opzione Esclusioni per selezionare le caratteristiche da ignorare quando si creano modelli da una o più origini dati.
seo-title: Esclusione trait modelli algoritmici
title: Esclusione trait modelli algoritmici
uuid: 1359800 b -6 e 6 c -41 e 1-88 b 4-23 d 31952 abb 3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Modelli algoritmici: Esclusione caratteristica {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, che consentono di aggiungere al modello le barre di controllo necessarie, in base alle conoscenze e ai requisiti normativi del sistema. Utilizzate l [!UICONTROL Exclusions] &#39;opzione per selezionare le caratteristiche da ignorare quando si creano modelli da una o più origini dati.

## Casi d&#39;uso {#use-cases}

Di seguito sono riportati alcuni casi d&#39;uso che [!UICONTROL Trait Exclusion]potete usare:

* [!UICONTROL Trait Exclusion] consente di escludere alcune caratteristiche catch-all, ad esempio le caratteristiche dei visitatori del sito, in modo da non influenzare il modello, generando risultati semplici.
* Potete rimuovere caratteristiche che non conoscete o considerare affidabili da un&#39;origine dati, per comprendere meglio le caratteristiche influenti.
* Potete escludere alcune caratteristiche, ad esempio caratteristiche demografiche, per fornire assistenza con eventuali obblighi di conformità.

>[!IMPORTANT]
>
>Nota importante sul terzo caso d&#39;uso. Se il fornitore di dati di terze parti aggiunge una nuova caratteristica demografica al feed *di dati dopo aver creato il modello*, il modello viene prelevato automaticamente dal modello. Dopo la creazione del modello non potete escludere caratteristiche dalla modellazione. Consultate [Aspetti e limitazioni importanti](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Attenetevi alla cautela quando utilizzate questa funzione e lavorate con il provider di dati per essere informati di eventuali modifiche alla struttura dei feed.

![](assets/lam_exclude_traits.png)

## Come utilizzare le esclusioni Caratteristiche {#how-to-use}

Utilizzate il [flusso di lavoro Crea un modello](../../features/algorithmic-models/create-model.md#build-model) per creare nuovi modelli algoritmici.

1. [!UICONTROL Exclusions] La selezione viene visualizzata in grigio finché non selezioni una o più origini dati per la modellazione.
2. Dopo aver selezionato una o più origini dati per la modellazione, **[!UICONTROL Browse All Traits]** premete.
3. Nella **[!UICONTROL Select Traits to Exclude]** finestra, puoi vedere tutte le caratteristiche associate alle origini dati selezionate in precedenza. Selezionate le caratteristiche da escludere.
4. Potete filtrare le caratteristiche per tipo di caratteristica oppure sfogliare le cartelle delle caratteristiche. Tieni presente che le cartelle delle caratteristiche visualizzano solo le caratteristiche associate alle origini dati selezionate.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>Potete escludere intere cartelle escludendo la caratteristica della cartella, anziché escluderle. Ad esempio, in una cartella con 20 caratteristiche, dovrete escludere solo la caratteristica della cartella, anziché escluderle una per volta.

Se preferite esercitazioni video, guardate la nostra dimostrazione video per l&#39;esclusione delle caratteristiche:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=ita)

## Aspetti e limitazioni importanti {#important-aspects-and-limitations}

Prendete nota dei seguenti aspetti e limitazioni relativi [!UICONTROL Trait Exclusion]a:

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
   <td colname="col2"> <p>Le caratteristiche <i>escluse non vengono visualizzate</i> nella visualizzazione Riepilogo modelli. Puoi visualizzare le caratteristiche escluse solo nel flusso di lavoro <b><span class="uicontrol"> Modifica modello</span></b> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controlli di accesso basati su ruolo (RBAC) </p> </td>
   <td colname="col2"> <p>Tenete presente le seguenti limitazioni per le aziende che usano <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Se non disponete dell'accesso per visualizzare una caratteristica, <i>non potete</i> selezionare tale caratteristica per essere esclusa dal modello. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Se non avete accesso per visualizzare una caratteristica, <i>non potete</i> visualizzarla nell'elenco delle caratteristiche escluse. </li>
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
   <td colname="col2"> <p>La caratteristica di base è esclusa per impostazione predefinita, pertanto non viene visualizzata nell'elenco <b><span class="uicontrol"> Exclusions</span></b> (Esclusioni) durante la creazione del modello. </p> </td>
  </tr>
 </tbody>
</table>

## Collegamenti correlati

* [Informazioni sulle caratteristiche algoritmiche](/help/using/features/algorithmic-models/understanding-models.md)
* [Esclusione caratteristica - Esercitazione](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)