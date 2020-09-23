---
description: Descrive i passaggi obbligatori e facoltativi che consentono di creare un modello algoritmico in Model Builder.
keywords: algo how works
seo-description: Descrive i passaggi obbligatori e facoltativi che consentono di creare un modello algoritmico in Model Builder.
seo-title: Creare un modello algoritmico
solution: Audience Manager
title: Creare un modello algoritmico
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: bff108115e7ebd4375d81c1c32ec9bb7d1a207c1
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%

---


# Creare un modello lookalike {#create-an-algorithmic-model}

Descrive i passaggi obbligatori e facoltativi che consentono di creare un [!UICONTROL Look-Alike Model].

## Sezione Generatore modelli

[!UICONTROL Model Builder] è costituito dalle sezioni [!UICONTROL Basic Information] e [!UICONTROL Configuration] . Per creare un modello, completare i campi richiesti in queste due sezioni. Salvate il modello per avviare l&#39;algoritmo. [!DNL Audience Manager] invia una notifica automatica al termine della prima esecuzione dei dati. Dopo aver ricevuto l&#39;e-mail, puoi andare a [Trait Builder](../../features/traits/about-trait-builder.md) e creare caratteristiche algoritmiche.

>[!NOTE]
>
>* Il processo di modellazione viene eseguito solo una volta se create un modello e non ne create alcuna caratteristica.
>* Creare modelli da origini dati contenenti una quantità significativa di informazioni. I modelli con dati insufficienti verranno eseguiti, ma non restituiranno risultati.
>* *Non* creare modelli con altre caratteristiche o segmenti algoritmici.
>* La notifica e-mail automatica viene inviata una sola volta (dopo la prima esecuzione dei dati).


## Creare il modello

Per creare un [!UICONTROL Look-Alike Model]:

1. Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e fai clic **[!UICONTROL Add New]** nella [!UICONTROL Look-Alike Modeling] sezione.
   ![sosia-add](assets/look-alike-add.png)
1. Nella sezione [Informazioni](../../features/algorithmic-models/create-model.md#basic-information) di base
   * Denominate il modello.
   * *(Facoltativo)* Fornire una breve descrizione del modello.
   * Impostare lo stato del modello su **[!UICONTROL Active]** o **[!UICONTROL Inactive]**. I modelli inattivi non verranno eseguiti e non produrranno alcun dato.
      ![sosia-base](assets/look-alike-basic.png)
1. Nella sezione [Configurazione](../../features/algorithmic-models/create-model.md#configuration) :
   * Fare clic **[!UICONTROL Browse All Traits]** o **[!UICONTROL Browse All Segments]** per selezionare una caratteristica o un segmento rispetto al quale si desidera creare il modello. Cerca caratteristiche per nome, ID, descrizione o origine dati. Fate clic su una cartella durante la ricerca per limitare i risultati a tale cartella e alle relative sottocartelle. Puoi anche filtrare le caratteristiche per tipo di caratteristica ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]e [!UICONTROL Algorithmic]) o per tipo di popolazione (ID[](../../reference/ids-in-aam.md) dispositivo e ID [](../../reference/ids-in-aam.md)multi-dispositivo).
      ![browse-Traits](assets/browse-traits.png)
   * Scegliete un periodo di look-back di 30, 60 o 90 giorni. Questo imposta un intervallo di tempo per il modello.
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Selezionare un&#39;origine dati dall&#39; [!UICONTROL Available Data] elenco.
   * Al **[!UICONTROL Save]** termine, fate clic.
      ![configurazione simile](assets/look-alike-configuration.png)

Guardate il video seguente per vedere in dettaglio come funzionano le metriche tra dispositivi.

>[!VIDEO](https://video.tv.adobe.com/v/33445/)

## Informazioni di base per i modelli algoritmici {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], le [!UICONTROL Basic Information] impostazioni consentono di creare nuovi modelli o di modificarne quelli esistenti. Per creare un nuovo modello, immettete un nome e passate alle [!UICONTROL Configuration] impostazioni. Il campo di descrizione è facoltativo.

| Campo | Descrizione |
|---|---|
| **[!UICONTROL Name]** | Assegnare al modello un nome logico breve che ne descriva funzione o finalità. Evitare abbreviazioni, caratteri speciali e segni di accento. |
| **[!UICONTROL Description]** | Campo per ulteriori informazioni descrittive sul modello. |
| **[!UICONTROL Status]** | Attiva o disattiva il modello (attivo per impostazione predefinita). |

## Configurazione {#configuration}

In [!UICONTROL Model Builder], la [!UICONTROL Configuration] sezione consente di aggiungere caratteristiche o segmenti al modello. In questa sezione, seleziona una caratteristica o un segmento della linea di base, un periodo di look-back e i dati dalle origini dati di prime e terze parti.

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
   <td colname="col1"> <p><b>Selezionare una caratteristica o un segmento della linea di base (1)</b> </p> </td> 
   <td colname="col2"> <p>Fai clic sul pulsante tratto o segmento per visualizzare un elenco di tutte le caratteristiche o i segmenti. Il segmento o la caratteristica selezionata diventa la linea di base utilizzata dagli algoritmi di sistema per la modellazione. </p> <p> <p><b>Nota</b>:  Seleziona come linea di base una caratteristica costruita, una caratteristica basata su regole o un segmento. In caso contrario, i modelli non verranno eseguiti. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleziona periodo di look back (2)</b> </p> </td> 
   <td colname="col2"> <p>Imposta un intervallo di tempo per il modello. In base alla selezione effettuata, l'algoritmo include e valuta i dati dei precedenti 30, 60 o 90 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleziona algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>Al momento, Model Builder funziona solo con il nostro algoritmo proprietario <span class="keyword"> Trait Weight</span> . <span class="keyword">  Audience Manager</span> può aggiungere altre funzioni algoritmiche nelle versioni successive. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Seleziona dati modello da origine dati (4)</b> </p> </td> 
   <td colname="col2"> <p>Consente di selezionare le origini dati di prima e terza parte da utilizzare nel modello. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esclusioni (5)</b> </p> </td> 
   <td colname="col2"> <p>È possibile escludere caratteristiche dalle origini dati selezionate per la modellazione. Utilizzare l'elenco <span class="wintitle"> Esclusioni</span> e leggere Modelli <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> algoritmici: Trait Exclusion</a> per saperne di più. </p> </td>
  </tr> 
 </tbody>
</table>

Guardate il video qui sotto per scoprire come creare un modello simile di prima parte, in modo da poter trovare più visitatori che somigliano ai vostri convertitori.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Comprensione di TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

