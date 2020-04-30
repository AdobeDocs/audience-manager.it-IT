---
description: Trait Exclusion offre controlli aggiuntivi nel flusso di lavoro di modellazione, consentendo di aggiungere al modello le guide di protezione necessarie, in base alle competenze di dominio e ai requisiti normativi. Utilizzate l'opzione Esclusioni per selezionare le caratteristiche da ignorare durante la creazione di modelli da una o più origini dati.
seo-description: Trait Exclusion offre controlli aggiuntivi nel flusso di lavoro di modellazione, consentendo di aggiungere al modello le guide di protezione necessarie, in base alle competenze di dominio e ai requisiti normativi. Utilizzate l'opzione Esclusioni per selezionare le caratteristiche da ignorare durante la creazione di modelli da una o più origini dati.
seo-title: Esclusione dei modelli algoritmici
title: Esclusione dei modelli algoritmici
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
translation-type: tm+mt
source-git-commit: e6e22c0c4a8f1374d3d8d18cb7b242e18a29571f

---


# Modellazione Simile: Esclusione caratteristica {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, consentendo di aggiungere al modello le guide necessarie, in base alle competenze del dominio e ai requisiti normativi. Utilizzare l&#39; [!UICONTROL Exclusions] opzione per selezionare le caratteristiche da ignorare durante la creazione di modelli da una o più origini dati.

## Casi d&#39;uso {#use-cases}

Di seguito sono riportati alcuni esempi di casi d’uso con [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] consente di escludere alcune caratteristiche catch-all, come le caratteristiche del visitatore del sito, in modo da non alterare il modello, generando risultati semplici.
* È possibile rimuovere le caratteristiche che non si conoscono o che non si fida di un&#39;origine dati per comprendere meglio le caratteristiche influenti.
* È possibile escludere alcune caratteristiche, come caratteristiche demografiche, per facilitare l&#39;adempimento di eventuali obblighi di conformità.

>[!IMPORTANT]
>
>Una nota importante sul terzo caso di utilizzo. Se il provider di dati di terze parti aggiunge una nuova caratteristica demografica al feed di dati *dopo la creazione del modello*, la caratteristica viene automaticamente rilevata dal modello. Non è possibile escludere le caratteristiche dalla modellazione dopo la creazione del modello. Consulta [Aspetti e limitazioni](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)importanti. Prestate attenzione quando utilizzate questa funzione e collaborate con il provider di dati per essere certi di essere informati di eventuali modifiche alla struttura del feed.

![](assets/lam_exclude_traits.png)

## Come utilizzare le esclusioni di caratteristiche {#how-to-use}

Utilizzate il flusso di lavoro [Crea un modello](../../features/algorithmic-models/create-model.md#build-model) per creare nuovi modelli algoritmici.

1. La [!UICONTROL Exclusions] selezione è disattivata fino a quando non si selezionano una o più origini dati per la modellazione.
2. Dopo aver selezionato una o più origini dati per la modellazione, premere **[!UICONTROL Browse All Traits]**.
3. Nella **[!UICONTROL Select Traits to Exclude]** finestra sono visualizzate tutte le caratteristiche associate alle origini dati selezionate in precedenza. Selezionate le caratteristiche da escludere.
4. Potete filtrare le caratteristiche per tipo di caratteristica, tipo di popolazione delle caratteristiche (ID[](../../reference/ids-in-aam.md) dispositivo e ID [](../../reference/ids-in-aam.md)multi-dispositivo) oppure potete sfogliare le cartelle delle caratteristiche. Nelle cartelle delle caratteristiche vengono visualizzate solo le caratteristiche associate alle origini dati selezionate.
5. Premere **[!UICONTROL Exclude Selected Traits]**.

![esclusioni di caratteristiche](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>Potete escludere intere cartelle escludendo la caratteristica della cartella invece di escludere le caratteristiche della cartella, una per una. Ad esempio, in una cartella con 20 caratteristiche, è sufficiente escludere la caratteristica della cartella anziché tutte le caratteristiche una per una.

Se preferite le esercitazioni video, guardate la nostra dimostrazione video per l&#39;esclusione delle caratteristiche:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

## Aspetti e limitazioni importanti {#important-aspects-and-limitations}

Prendete nota dei seguenti aspetti e limitazioni relativi a [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche escluse nella vista di riepilogo modelli </p> </td>
   <td colname="col2"> <p>Le caratteristiche escluse <i>non vengono visualizzate</i> nella visualizzazione Riepilogo modelli. Potete visualizzare le caratteristiche escluse solo nel flusso di lavoro <b><span class="uicontrol"> Modifica modello</span></b> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controlli di accesso basati sul ruolo (RBAC) </p> </td>
   <td colname="col2"> <p>Prendete nota delle seguenti limitazioni per le aziende che utilizzano <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Se non si dispone dell'accesso per visualizzare una caratteristica, <i>non è possibile</i> selezionarla per escluderla dal modello. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Se non disponete dell'accesso per visualizzare una caratteristica, <i>non potete</i> visualizzarla nell'elenco delle caratteristiche escluse. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificare le caratteristiche escluse dopo il salvataggio del modello </p> </td>
   <td colname="col2"> <p>Non è possibile modificare le caratteristiche escluse dopo aver creato e salvato un modello. Se si desidera modificare i risultati, è possibile duplicare il modello e modificare le caratteristiche escluse. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Numero massimo di caratteristiche che è possibile escludere </p> </td>
   <td colname="col2"> <p>Il numero massimo di caratteristiche che è possibile escludere da un modello è 500. Utilizzate le caratteristiche delle cartelle per massimizzare le esclusioni. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escludi tratto della linea di base </p> </td>
   <td colname="col2"> <p>La caratteristica di base è esclusa per impostazione predefinita, pertanto non viene visualizzata nell'elenco <b><span class="uicontrol"> Esclusioni</span></b> al momento della creazione del modello. </p> </td>
  </tr>
 </tbody>
</table>

Guardate il video seguente per scoprire come e perché escludere tratti specifici da un [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## Collegamenti correlati

* [Informazioni sulle caratteristiche algoritmiche](/help/using/features/algorithmic-models/understanding-models.md)
* [Esclusione delle caratteristiche - Esercitazione](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)