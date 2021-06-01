---
description: L’esclusione delle caratteristiche fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, consentendoti di aggiungere al modello le barre di protezione necessarie, in base alle competenze del dominio e ai requisiti normativi. Utilizza l’opzione Esclusioni per selezionare le caratteristiche da ignorare durante la creazione di modelli da una o più origini dati.
seo-description: L’esclusione delle caratteristiche fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, consentendoti di aggiungere al modello le barre di protezione necessarie, in base alle competenze del dominio e ai requisiti normativi. Utilizza l’opzione Esclusioni per selezionare le caratteristiche da ignorare durante la creazione di modelli da una o più origini dati.
seo-title: Esclusione delle caratteristiche dei modelli algoritmici
title: Esclusione delle caratteristiche dei modelli algoritmici
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Modelli algoritmici
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Modellazione lookalike: esclusione di caratteristiche {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] fornisce controlli aggiuntivi nel flusso di lavoro di modellazione, che consentono di aggiungere al modello le guide di protezione necessarie, in base alle competenze del dominio e ai requisiti normativi. Utilizza l’opzione [!UICONTROL Exclusions] per selezionare le caratteristiche da ignorare durante la creazione di modelli da una o più origini dati.

## Casi d&#39;uso {#use-cases}

Di seguito sono riportati alcuni casi d’uso che è possibile risolvere con [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] consente di escludere alcune caratteristiche catch-all, come le caratteristiche dei visitatori del sito, in modo da non influenzare il modello, generando risultati piatti.
* È possibile rimuovere le caratteristiche di cui non si è a conoscenza o di cui non si è certi da un’origine dati, per comprendere meglio le caratteristiche influenti.
* Puoi escludere alcune caratteristiche, ad esempio le caratteristiche demografiche, per aiutarti con eventuali obblighi di conformità.

>[!IMPORTANT]
>
>Una nota importante sul terzo caso d’uso. Se il provider di dati di terze parti aggiunge una nuova caratteristica demografica al feed di dati *dopo la creazione del modello*, la caratteristica viene automaticamente rilevata dal modello. Non è possibile escludere le caratteristiche dalla modellazione dopo la creazione del modello. Consulta [Aspetti e limitazioni importanti](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Presta attenzione quando utilizzi questa funzione e collabora con il provider di dati per assicurarti di essere informato di eventuali modifiche alla struttura del feed.

![](assets/lam_exclude_traits.png)

## Come utilizzare le esclusioni di caratteristiche {#how-to-use}

Utilizza il flusso di lavoro [Crea un modello](../../features/algorithmic-models/create-model.md#build-model) per creare nuovi modelli algoritmici.

1. La selezione [!UICONTROL Exclusions] è disattivata fino a quando non selezioni una o più origini dati per la modellazione.
2. Dopo aver selezionato una o più origini dati per la modellazione, premere **[!UICONTROL Browse All Traits]**.
3. Nella finestra **[!UICONTROL Select Traits to Exclude]** è possibile visualizzare tutte le caratteristiche associate alle origini dati selezionate in precedenza. Seleziona le caratteristiche da escludere.
4. Puoi filtrare le caratteristiche per tipo di caratteristica, tipo di popolazione delle caratteristiche ([ID dispositivo](../../reference/ids-in-aam.md) e [ID multi-dispositivo](../../reference/ids-in-aam.md)) oppure puoi sfogliare le cartelle delle caratteristiche. Le cartelle di caratteristiche visualizzano solo le caratteristiche associate alle origini dati selezionate.
5. Premere **[!UICONTROL Exclude Selected Traits]**.

![esclusioni di caratteristiche](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>È possibile escludere intere cartelle escludendo una per una la caratteristica della cartella anziché escluderne le caratteristiche. Ad esempio, in una cartella con 20 caratteristiche, è sufficiente escludere la caratteristica della cartella anziché tutte le caratteristiche una per una.

Se preferisci i tutorial video, guarda la nostra dimostrazione video per l’esclusione delle caratteristiche:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

Inoltre, guarda il video seguente per un’analisi dettagliata del funzionamento delle metriche tra dispositivi.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## Aspetti e limitazioni importanti {#important-aspects-and-limitations}

Prendi nota dei seguenti aspetti e limitazioni relativi a [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caratteristiche escluse nella visualizzazione di riepilogo dei modelli </p> </td>
   <td colname="col2"> <p>Le caratteristiche escluse <i>non vengono visualizzate</i> nella vista Riepilogo modelli. Puoi visualizzare le caratteristiche escluse solo nel flusso di lavoro <b><span class="uicontrol"> Modifica modello</span></b> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Controlli di accesso basati sul ruolo (RBAC) </p> </td>
   <td colname="col2"> <p>Tieni presente le seguenti limitazioni per le aziende che utilizzano <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Se non disponi dell'accesso per visualizzare una caratteristica, <i>non è possibile</i> selezionare la caratteristica da escludere dal modello. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Se non hai accesso per visualizzare una caratteristica, <i>non puoi</i> visualizzarla nell’elenco delle caratteristiche escluse. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificare le caratteristiche escluse dopo il salvataggio del modello </p> </td>
   <td colname="col2"> <p>Non è possibile modificare le caratteristiche escluse dopo aver creato e salvato un modello. Se desiderate modificare i risultati, potete clonare il modello e modificare le caratteristiche escluse. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Numero massimo di caratteristiche da escludere </p> </td>
   <td colname="col2"> <p>Il numero massimo di caratteristiche che è possibile escludere da un modello è 500. Utilizza le caratteristiche della cartella per massimizzare le esclusioni. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escludere le caratteristiche della linea di base </p> </td>
   <td colname="col2"> <p>La caratteristica della linea di base è esclusa per impostazione predefinita, pertanto non viene visualizzata nell'elenco <b><span class="uicontrol"> Esclusioni</span></b> durante la creazione del modello. </p> </td>
  </tr>
 </tbody>
</table>

Guarda il video seguente per scoprire come e perché escludere caratteristiche specifiche da un [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## Collegamenti correlati

* [Informazioni sulle caratteristiche algoritmiche](/help/using/features/algorithmic-models/understanding-models.md)
* [Esclusione di caratteristiche - Tutorial](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
