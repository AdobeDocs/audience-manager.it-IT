---
description: Descrive i passaggi e le funzionalità di configurazione univoci per il processo di creazione delle caratteristiche algoritmiche.
seo-description: Descrive i passaggi e le funzionalità di configurazione univoci per il processo di creazione delle caratteristiche algoritmiche.
seo-title: Creare caratteristiche algoritmiche
solution: Audience Manager
title: Creare caratteristiche algoritmiche
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 5%

---


# Creare caratteristiche algoritmiche {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Per creare una caratteristica algoritmica, andate a [!UICONTROL Traits] e seguite la procedura seguente:

1. Fare clic **[!UICONTROL Create New Trait]** e selezionare **[!UICONTROL Algorithmic]** dal menu a discesa.
1. Nella sezione [Informazioni](../../features/traits/create-onboarded-rule-based-traits.md) di base
   * Denominate la caratteristica.
   * Selezionare un&#39;origine dati.
   * Scegliete una cartella di archiviazione.
1. Espandete il [!UICONTROL Configuration] riquadro e fate clic su **[!UICONTROL Browse All Models]**.
Si apre una nuova finestra che consente di selezionare il modello da utilizzare con la caratteristica.
1. Selezionate un modello e fate clic su **[!UICONTROL Add Selected Model to Trait]**.
L&#39;aggiunta del modello espone le impostazioni di portata e precisione.
1. Selezionate l’obiettivo o la precisione e scegliete un valore dai rispettivi menu a discesa. Al **[!UICONTROL Save]** termine, fate clic.

## Impostazioni di configurazione per caratteristiche algoritmiche {#configure-settings}

In [!UICONTROL Trait Builder], la [!UICONTROL Configuration] sezione consente di associare un modello algoritmico a una caratteristica. Per completare il processo di creazione delle caratteristiche algoritmiche, selezionate un modello e scegliete un obiettivo di raggiungimento o precisione.

### Prerequisiti

<!-- r_algo_trait_config_section.xml -->

* [Creare un modello lookalike](../../features/algorithmic-models/create-model.md).
* Attendi il messaggio e-mail di notifica che ti consente di sapere che l&#39;esecuzione dei dati del modello è stata completata.
* Compila i campi richiesti nella sezione Informazioni [di](../../features/traits/create-onboarded-rule-based-traits.md) base.

### Campi e impostazioni di configurazione

| Elemento di interfaccia | Spiegazione |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Fare clic sul **[!UICONTROL Update]** pulsante per aprire la finestra dei modelli. Dalla finestra, selezionate il modello algoritmico da usare per creare la caratteristica. |
| **[!UICONTROL Select Goal Accuracy]** | Selezionate questa opzione per creare una caratteristica basata sulla precisione. Precisione è un valore con un punteggio che indica il grado di prossimità degli utenti potenziali alla linea di base. La scala di precisione va da 0 (minimo accurato) a 1 (più preciso). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Situata a destra, questa sezione visualizza fino a 21 righe di dati numerici che mostrano la precisione e i valori di portata del modello. |
| **[!UICONTROL Reach and Accuracy Slider]** | Posizionato nella parte inferiore del grafico, il cursore consente di impostare un valore numerico per raggiungere o raggiungere gli obiettivi di precisione. Potete impostare il cursore e quindi scegliere il pulsante di raggiungimento o di precisione dell’obiettivo per creare una caratteristica. |

>[!MORELIKETHIS]
>
>* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)

