---
description: Descrive i passaggi richiesti e facoltativi che consentono di creare un modello algoritmico in Model Builder.
keywords: algo come funziona
seo-description: Descrive i passaggi richiesti e facoltativi che consentono di creare un modello algoritmico in Model Builder.
seo-title: Creare un modello algoritmico
solution: Audience Manager
title: Creare un modello algoritmico
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Modelli algoritmici
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# Creare un modello lookalike {#create-an-algorithmic-model}

Descrive i passaggi obbligatori e facoltativi che consentono di creare un [!UICONTROL Look-Alike Model].

## Sezione di Generatore di modelli

[!UICONTROL Model Builder] è costituito dalle sezioni  [!UICONTROL Basic Information] e  [!UICONTROL Configuration] . Per creare un modello, completare i campi obbligatori in queste due sezioni. Salva il modello per avviare l&#39;algoritmo. [!DNL Audience Manager] invia una notifica automatica al termine della prima esecuzione dei dati. Dopo aver ricevuto l&#39;e-mail, puoi passare a [Generatore di caratteristiche](../../features/traits/about-trait-builder.md) e creare caratteristiche algoritmiche.

>[!NOTE]
>
>* Il processo di modellazione viene eseguito una sola volta se si crea un modello e non si creano caratteristiche con esso.
>* Crea modelli da origini dati che contengono una quantità significativa di informazioni. I modelli con dati insufficienti verranno eseguiti, ma non restituiranno risultati.
>* *Non* creare modelli con altre caratteristiche o segmenti algoritmici.
>* La notifica e-mail automatica viene inviata una sola volta (dopo la prima esecuzione dei dati).


## Creare il modello

Segui i passaggi seguenti per creare un [!UICONTROL Look-Alike Model]:

1. Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** e fai clic su **[!UICONTROL Add New]** nella sezione [!UICONTROL Look-Alike Modeling] .
   ![look-alike-add](assets/look-alike-add.png)
1. Nella sezione [Informazioni di base](../../features/algorithmic-models/create-model.md#basic-information)
   * Denomina il modello.
   * *(Facoltativo)* Fornisci una breve descrizione del modello.
   * Imposta lo stato del modello su **[!UICONTROL Active]** o **[!UICONTROL Inactive]**. I modelli inattivi non verranno eseguiti e non produrranno alcun dato.
      ![lookalike-basic](assets/look-alike-basic.png)
1. Nella sezione [Configurazione](../../features/algorithmic-models/create-model.md#configuration) :
   * Fai clic su **[!UICONTROL Browse All Traits]** o **[!UICONTROL Browse All Segments]** per selezionare una caratteristica o un segmento rispetto al quale desideri eseguire il modello. Cerca le caratteristiche per nome, ID, descrizione o origine dati. Fai clic su una cartella durante la ricerca per limitare i risultati a tale cartella e alle relative sottocartelle. Puoi anche filtrare le caratteristiche per tipo di caratteristica ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] e [!UICONTROL Algorithmic]) o per tipo di popolazione ([ID dispositivo](../../reference/ids-in-aam.md) e [ID multidispositivo](../../reference/ids-in-aam.md)).
      ![caratteristiche del browser](assets/browse-traits.png)
   * Scegli un periodo di look-back di 30, 60 o 90 giorni. Questo imposta un intervallo di tempo per il modello.
   * L’algoritmo [!UICONTROL TraitWeight] è selezionato per impostazione predefinita.
   * Selezionare un&#39;origine dati dall&#39;elenco [!UICONTROL Available Data].
   * Al termine, fai clic su **[!UICONTROL Save]** .
      ![configurazione lookalike](assets/look-alike-configuration.png)

Guarda il video seguente per vedere in dettaglio come funzionano le metriche per dispositivi diversi.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Informazioni di base per i modelli algoritmici {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], le impostazioni [!UICONTROL Basic Information] consentono di creare o modificare modelli esistenti. Per creare un nuovo modello, fornisci un nome e passa alle impostazioni [!UICONTROL Configuration] . Il campo di descrizione è facoltativo.

| Campo | Descrizione |
|---|---|
| **[!UICONTROL Name]** | Assegna al modello un nome logico breve che ne descrive funzione o scopo. Evitare abbreviazioni, caratteri speciali e segni di accento. |
| **[!UICONTROL Description]** | Campo per ulteriori informazioni descrittive sul modello. |
| **[!UICONTROL Status]** | Attiva o disattiva il modello (attivo per impostazione predefinita). |

## Configurazione {#configuration}

In [!UICONTROL Model Builder], la sezione [!UICONTROL Configuration] consente di aggiungere caratteristiche o segmenti al modello. In questa sezione, seleziona una caratteristica o un segmento della linea di base, un periodo di look-back e i dati dalle origini dati di prime e terze parti.

<!-- r_model_configuration.xml -->

### Prerequisiti

Compila prima i campi richiesti nella sezione [!UICONTROL Basic Information] .

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
   <td colname="col2"> <p>Fai clic sul pulsante caratteristiche o segmenti per visualizzare un elenco di tutte le caratteristiche o i segmenti. Il segmento o la caratteristica selezionata diventa la linea di base utilizzata dagli algoritmi di sistema per la modellazione. </p> <p> <p><b>Nota</b>: Seleziona come linea di base una caratteristica onboarded, una caratteristica basata su regole o un segmento. In caso contrario, i modelli non verranno eseguiti. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleziona periodo di look back (2)</b> </p> </td> 
   <td colname="col2"> <p>Imposta un intervallo di tempo per il modello. In base alla selezione, l’algoritmo include e valuta i dati dei precedenti 30, 60 o 90 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Seleziona algoritmo (3)</b> </p> </td> 
   <td colname="col2"> <p>Al momento, Model Builder funziona solo con il nostro algoritmo proprietario <span class="keyword"> Trait Weight</span>. <span class="keyword"> Audience </span> Manager può aggiungere altre funzioni algoritmiche nelle versioni successive. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Seleziona dati modello da origine dati (4)</b> </p> </td> 
   <td colname="col2"> <p>Consente di selezionare le origini dati di prima e terze parti che si desidera utilizzare nel modello. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Esclusioni (5)</b> </p> </td> 
   <td colname="col2"> <p>È possibile escludere le caratteristiche dalle origini dati selezionate per la modellazione. Utilizza l'elenco <span class="wintitle"> Esclusioni</span> e leggi <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Modelli algoritmici: Esclusione delle caratteristiche</a> per ulteriori informazioni. </p> </td>
  </tr> 
 </tbody>
</table>

Guarda il video seguente per scoprire come creare un modello lookalike di prima parte, in modo da poter trovare più visitatori che assomigliano ai tuoi convertitori.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Comprensione di TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

