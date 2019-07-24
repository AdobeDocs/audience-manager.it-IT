---
description: Descrive i passaggi obbligatori e facoltativi che consentono di creare un modello algoritmico in Model Builder.
keywords: algo how works
seo-description: Descrive i passaggi obbligatori e facoltativi che consentono di creare un modello algoritmico in Model Builder.
seo-title: Creare un modello algoritmico
solution: Audience Manager
title: Creare un modello algoritmico
topic: API DIL
uuid: ccf 4 fc 4 e-cf 92-445 f-b 2 d 9-71 c 3 ca 624 e 26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in [!UICONTROL Model Builder].

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### Sezione Builder modello

[!UICONTROL Model Builder] consiste in [!UICONTROL Basic Information] sezioni e [!UICONTROL Configuration] sezioni. Per creare un modello, completare i campi richiesti in queste due sezioni. Salvate il modello per avviare l'algoritmo. [!DNL Audience Manager] invia una notifica automatizzata al completamento della prima esecuzione dei dati. After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* Il processo di modellazione viene eseguito una sola volta se si crea un modello e non si crea alcuna caratteristica.
>* Creare modelli da origini dati contenenti una quantità significativa di informazioni. I modelli con dati insufficienti vengono eseguiti, ma non restituiranno risultati.
>* *Non* create modelli con altre caratteristiche algoritmiche o segmenti.
>* La notifica e-mail automatica viene inviata una sola volta (dopo la prima esecuzione dei dati).


### Creare il modello

To build a model, go to the [!UICONTROL Models] section and click **[!UICONTROL Add New]** and follow the steps below:

1. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
   * Denominate il modello.
   * *(Facoltativo)* Fornite una breve descrizione del modello.
   * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. I modelli inattivi non vengono eseguiti e non generano dati.
1. In the [Configuration](../../features/algorithmic-models/create-model.md#configuration) section:
   * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. Seleziona una caratteristica caricata, una caratteristica basata su regole o un segmento come linea di base. In caso contrario, i modelli non saranno eseguiti.
   * Scegliete un periodo di aspetto del 30, 60 o 90 giorni. Questo imposta un intervallo di tempo per il modello.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. Il campo descrizione è facoltativo.

| Campo | Descrizione |
|---|---|
| **[!UICONTROL Name]** | Assegnare al modello un nome breve e logico che descrive la funzione o lo scopo. Evitare abbreviazioni, caratteri speciali e indicatori di accento. |
| **[!UICONTROL Description]** | Campo per ulteriori informazioni descrittive sul modello. |
| **[!UICONTROL Status]** | Attiva o disattiva il modello (attivo per impostazione predefinita). |

## Configurazione {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. In questa sezione, seleziona una caratteristica o segmento di base, un periodo di look-back e dati dalla prima e da origini dati di terze parti.

<!-- r_model_configuration.xml -->

### Prerequisiti

Complete the required fields in the [!UICONTROL Basic Information] section first.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Seleziona un segmento o segmento di base (1)</b> </p> </td> 
   <td colname="col2"> <p>Fai clic sul pulsante o sul segmento per visualizzare un elenco di tutte le caratteristiche o i segmenti. Il segmento o la caratteristica selezionato diventa la linea di base utilizzata dagli algoritmi di sistema per la modellazione. </p> <p> <p><b>Nota</b>: Seleziona una caratteristica caricata, una caratteristica basata su regole o un segmento come linea di base. In caso contrario, i modelli non saranno eseguiti. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleziona punto indietro (2)</b> </p> </td> 
   <td colname="col2"> <p>Imposta un intervallo di tempo per il modello. In base alla selezione, l'algoritmo include e valuta i dati dei precedenti 30, 60 o 90 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleziona algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> Audience Manager</span> può aggiungere altre funzioni algoritmiche nelle release successive. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Seleziona dati modello dall'origine dati (4)</b> </p> </td> 
   <td colname="col2"> <p>Consente di selezionare la prima e l'origine dati di terze parti che desideri utilizzare nel modello. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esclusioni (5)</b> </p> </td> 
   <td colname="col2"> <p>Puoi escludere caratteristiche dalle origini dati selezionate per la modellazione. Use the <span class="wintitle"> Exclusions</span> list and read <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion</a> to learn more. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Informazioni sulle caratteristiche](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

