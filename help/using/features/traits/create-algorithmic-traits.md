---
description: Descrive i passaggi e le funzionalità di configurazione univoci del processo di creazione delle caratteristiche algoritmiche.
seo-description: Descrive i passaggi e le funzionalità di configurazione univoci del processo di creazione delle caratteristiche algoritmiche.
seo-title: Creare caratteristiche algoritmiche
solution: Audience Manager
title: Creare caratteristiche algoritmiche
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: 'Caratteristiche '
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 5%

---

# Creare caratteristiche algoritmiche {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Per creare una caratteristica algoritmica, vai a [!UICONTROL Traits] e segui i passaggi seguenti:

1. Fai clic su **[!UICONTROL Create New Trait]** e seleziona **[!UICONTROL Algorithmic]** dal menu a discesa.
1. Nella sezione [Informazioni di base](../../features/traits/create-onboarded-rule-based-traits.md)
   * Denomina la caratteristica.
   * Selezionare un’origine dati.
   * Scegliere una cartella di archiviazione.
1. Espandi il riquadro [!UICONTROL Configuration] e fai clic su **[!UICONTROL Browse All Models]**.
Viene visualizzata una nuova finestra che consente di selezionare il modello da utilizzare con la caratteristica.
1. Seleziona un modello e fai clic su **[!UICONTROL Add Selected Model to Trait]**.
L&#39;aggiunta del modello espone le impostazioni di portata e precisione.
1. Seleziona la portata o la precisione come obiettivo e scegli un valore dai rispettivi menu a discesa. Al termine, fai clic su **[!UICONTROL Save]** .

## Impostazioni di configurazione per le caratteristiche algoritmiche {#configure-settings}

In [!UICONTROL Trait Builder], la sezione [!UICONTROL Configuration] ti consente di associare un modello algoritmico a una caratteristica. Per completare il processo di creazione delle caratteristiche algoritmiche, seleziona un modello e scegli un obiettivo di portata o precisione.

### Prerequisiti

<!-- r_algo_trait_config_section.xml -->

* [Creare un modello lookalike](../../features/algorithmic-models/create-model.md).
* Attendi l’e-mail di notifica che ti consente di sapere che l’esecuzione dei dati del modello è stata completata.
* Compila i campi richiesti nella sezione [Informazioni di base](../../features/traits/create-onboarded-rule-based-traits.md) .

### Campi e impostazioni di configurazione

| Elemento interfaccia | Spiegazione |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Fai clic sul pulsante **[!UICONTROL Update]** per aprire la finestra dei modelli. Dalla finestra , seleziona il modello algoritmico da utilizzare per creare la caratteristica. |
| **[!UICONTROL Select Goal Accuracy]** | Seleziona questa opzione per creare una caratteristica in base alla precisione. Precisione è un valore con punteggio che indica la vicinanza degli utenti potenziali alla linea di base. La scala di precisione va da 0 (precisione minore) a 1 (precisione maggiore). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Situata a destra, questa sezione visualizza fino a 21 righe di dati numerici che mostrano i valori di precisione e portata del modello. |
| **[!UICONTROL Reach and Accuracy Slider]** | Situato nella parte inferiore del grafico, il cursore consente di impostare un valore numerico per gli obiettivi di portata o precisione. Puoi impostare il cursore e quindi scegliere il pulsante dell’obiettivo di portata o precisione per creare una caratteristica. |

>[!MORELIKETHIS]
>
>* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)

