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


# Creare un modello algoritmico {#create-an-algorithmic-model}

Descrive i passaggi obbligatori e facoltativi che consentono di creare un modello algoritmico in [!UICONTROL Model Builder].

## Creare un modello {#build-model}

<!-- t_model_build.xml -->

### Sezione Builder modello

[!UICONTROL Model Builder] consiste in [!UICONTROL Basic Information] sezioni e [!UICONTROL Configuration] sezioni. Per creare un modello, completare i campi richiesti in queste due sezioni. Salvate il modello per avviare l&#39;algoritmo. [!DNL Audience Manager] invia una notifica automatizzata al completamento della prima esecuzione dei dati. Dopo aver ricevuto l&#39;e-mail, potete passare al Generatore [di caratteristiche](../../features/traits/about-trait-builder.md) e creare caratteristiche algoritmiche.

>[!NOTE]
>
>* Il processo di modellazione viene eseguito una sola volta se si crea un modello e non si crea alcuna caratteristica.
>* Creare modelli da origini dati contenenti una quantità significativa di informazioni. I modelli con dati insufficienti vengono eseguiti, ma non restituiranno risultati.
>* *Non* create modelli con altre caratteristiche algoritmiche o segmenti.
>* La notifica e-mail automatica viene inviata una sola volta (dopo la prima esecuzione dei dati).


### Creare il modello

Per creare un modello, andate alla [!UICONTROL Models] sezione e fate clic **[!UICONTROL Add New]** ed effettuate le seguenti operazioni:

1. Nella [sezione Informazioni](../../features/algorithmic-models/create-model.md#basic-information) di base
   * Denominate il modello.
   * *(Facoltativo)* Fornite una breve descrizione del modello.
   * Impostate lo stato per il modello su **[!UICONTROL Active]** o **[!UICONTROL Inactive]**. I modelli inattivi non vengono eseguiti e non generano dati.
1. Nella sezione [Configurazione](../../features/algorithmic-models/create-model.md#configuration) :
   * Fai clic **[!UICONTROL Browse All Traits]** su o **[!UICONTROL Browse All Segments]** per selezionare una caratteristica o un segmento rispetto al quale vuoi modellare il modello. Seleziona una caratteristica caricata, una caratteristica basata su regole o un segmento come linea di base. In caso contrario, i modelli non saranno eseguiti.
   * Scegliete un periodo di aspetto del 30, 60 o 90 giorni. Questo imposta un intervallo di tempo per il modello.
   * L&#39; [!UICONTROL TraitWeight] algoritmo è selezionato per impostazione predefinita.
   * Selezionare un&#39;origine dati dall&#39; [!UICONTROL Available Data] elenco.
   * Fate clic **[!UICONTROL Save]** su di essa.

## Informazioni di base per i modelli algoritmici {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], le [!UICONTROL Basic Information] impostazioni consentono di creare nuovi o modificare modelli esistenti. Per creare un nuovo modello, fornire un nome e passare alle [!UICONTROL Configuration] impostazioni. Il campo descrizione è facoltativo.

| Campo | Descrizione |
|---|---|
| **[!UICONTROL Name]** | Assegnare al modello un nome breve e logico che descrive la funzione o lo scopo. Evitare abbreviazioni, caratteri speciali e indicatori di accento. |
| **[!UICONTROL Description]** | Campo per ulteriori informazioni descrittive sul modello. |
| **[!UICONTROL Status]** | Attiva o disattiva il modello (attivo per impostazione predefinita). |

## Configurazione {#configuration}

In [!UICONTROL Model Builder], la [!UICONTROL Configuration] sezione consente di aggiungere caratteristiche o segmenti al modello. In questa sezione, seleziona una caratteristica o segmento di base, un periodo di look-back e dati dalla prima e da origini dati di terze parti.

<!-- r_model_configuration.xml -->

### Prerequisiti

Compila prima i campi richiesti nella [!UICONTROL Basic Information] sezione.

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
   <td colname="col2"> <p>Al momento, Model Builder funziona solo con il nostro algoritmo proprietario <span class="keyword"> per Spessore</span> caratteristica. <span class="keyword"> Audience Manager</span> può aggiungere altre funzioni algoritmiche nelle release successive. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Seleziona dati modello dall'origine dati (4)</b> </p> </td> 
   <td colname="col2"> <p>Consente di selezionare la prima e l'origine dati di terze parti che desideri utilizzare nel modello. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esclusioni (5)</b> </p> </td> 
   <td colname="col2"> <p>Puoi escludere caratteristiche dalle origini dati selezionate per la modellazione. Utilizzare l'elenco <span class="wintitle"> Esclusioni</span> e leggere <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> i modelli algoritmici: Esclusione caratteristica</a> per ulteriori informazioni. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Informazioni sulle caratteristiche](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

