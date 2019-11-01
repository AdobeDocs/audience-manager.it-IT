---
description: Descrive i passaggi e le funzionalità di configurazione univoci per il processo di creazione delle caratteristiche algoritmiche.
seo-description: Descrive i passaggi e le funzionalità di configurazione univoci per il processo di creazione delle caratteristiche algoritmiche.
seo-title: Creare caratteristiche algoritmiche
solution: Audience Manager
title: Creare caratteristiche algoritmiche
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Creare caratteristiche algoritmiche {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Per creare una caratteristica algoritmica, andate a [!UICONTROL Traits] e seguite la procedura seguente:

1. Fare clic **[!UICONTROL Create New Trait]** e selezionare **[!UICONTROL Algorithmic]** dal menu a discesa.
1. Nella sezione [Informazioni](../../features/traits/create-onboarded-rule-based-traits.md) di base
   * Denominate la caratteristica.
   * Selezionare un'origine dati.
   * Scegliete una cartella di archiviazione.
1. Espandete il [!UICONTROL Configuration] riquadro e fate clic su **[!UICONTROL Browse All Models]**.
Si apre una nuova finestra che consente di selezionare il modello da utilizzare con la caratteristica.
1. Selezionate un modello e fate clic su **[!UICONTROL Add Selected Model to Trait]**.
L'aggiunta del modello espone le impostazioni di portata e precisione.
1. Selezionate l’obiettivo o la precisione e scegliete un valore dai rispettivi menu a discesa. Click **[!UICONTROL Save]** when done.

## Impostazioni di configurazione per caratteristiche algoritmiche {#configure-settings}

In [!UICONTROL Trait Builder], la [!UICONTROL Configuration] sezione consente di associare un modello algoritmico a una caratteristica. Per completare il processo di creazione delle caratteristiche algoritmiche, selezionate un modello e scegliete un obiettivo di raggiungimento o precisione.

### Prerequisiti

<!-- r_algo_trait_config_section.xml -->

* [Creare un modello](../../features/algorithmic-models/create-model.md#build-model)algoritmico.
* Attendi il messaggio e-mail di notifica che ti consente di sapere che l'esecuzione dei dati del modello è terminata.
*  Compila i campi richiesti nella sezione Informazioni [di](../../features/traits/create-onboarded-rule-based-traits.md) base.

### Campi e impostazioni di configurazione

| Elemento interfaccia | Spiegazione |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Fare clic sul **[!UICONTROL Update]** pulsante per aprire la finestra dei modelli. Dalla finestra, selezionate il modello algoritmico da usare per creare la caratteristica. |
| **[!UICONTROL Select Goal Accuracy]** | Selezionate questa opzione per creare una caratteristica basata sulla precisione. Precisione è un valore con un punteggio che indica il grado di prossimità degli utenti potenziali alla linea di base. La scala di precisione va da 0 (minimo accurato) a 1 (più preciso). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Situata a destra, questa sezione visualizza fino a 21 righe di dati numerici che mostrano la precisione e i valori di portata del modello. |
| **[!UICONTROL Reach and Accuracy Slider]** | Posizionato nella parte inferiore del grafico, il cursore consente di impostare un valore numerico per raggiungere o raggiungere gli obiettivi di precisione. Potete impostare il cursore e quindi scegliere il pulsante di raggiungimento o precisione dell’obiettivo per creare una caratteristica. |

>[!MORELIKETHIS]
>
>* [Precisione e raggiungimento](../../features/traits/trait-accuracy-reach.md)

