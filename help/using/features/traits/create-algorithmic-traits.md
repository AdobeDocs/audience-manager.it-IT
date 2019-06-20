---
description: Descrive la configurazione di passaggi e funzioni univoche per il processo di creazione algoritmica.
seo-description: Descrive la configurazione di passaggi e funzioni univoche per il processo di creazione algoritmica.
seo-title: Creare caratteristiche algoritmiche
solution: Audience Manager
title: Creare caratteristiche algoritmiche
uuid: 50 c 2 d 2 d 1-f 412-479 b-bb 70-4 f 139429 c 388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Creare caratteristiche algoritmiche {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Per creare una caratteristica algoritmica, accedete a ed [!UICONTROL Traits] effettuate le seguenti operazioni:

1. Fate clic **[!UICONTROL Create New Trait]** e selezionate **[!UICONTROL Algorithmic]** dal menu a discesa.
1. Nella [sezione Informazioni](../../features/traits/create-onboarded-rule-based-traits.md) di base
   * Denominate la caratteristica.
   * Selezionare un&#39;origine dati.
   * Scegliete una cartella di archiviazione.
1. Espandete [!UICONTROL Configuration] il riquadro e fate clic **[!UICONTROL Browse All Models]**su.
Viene aperta una nuova finestra che consente di selezionare il modello da utilizzare con la caratteristica.
1. Selezionate un modello e fate clic **[!UICONTROL Add Selected Model to Trait]**su.
L&#39;aggiunta del modello espone le impostazioni di portata e accuratezza.
1. Selezionate l&#39;approssimazione o la precisione come obiettivo e scegliete un valore dai rispettivi menu a discesa. Fate clic **[!UICONTROL Save]** su di essa.

>[!MORE_ LIKE_ THIS]
>
>* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)


## Impostazioni di configurazione per caratteristiche algoritmiche {#configure-settings}

In [!UICONTROL Trait Builder], la [!UICONTROL Configuration] sezione consente di associare un modello algoritmico a una caratteristica. Per completare il processo di creazione algoritmica delle caratteristiche, selezionate un modello e scegliete un obiettivo o un obiettivo di precisione.

### Prerequisiti

<!-- r_algo_trait_config_section.xml -->

* [Create un modello algoritmico](../../features/algorithmic-models/create-model.md#build-model).
* Attendete l&#39;e-mail di notifica che vi consente di sapere che i dati del modello sono finiti.
* Compila i campi richiesti nella [sezione Informazioni](../../features/traits/create-onboarded-rule-based-traits.md) di base.

### Campi di configurazione e impostazioni

| Elemento interfaccia | Spiegazione |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Fate clic sul **[!UICONTROL Update]** pulsante per aprire la finestra dei modelli. Dalla finestra, selezionate il modello algoritmico che desiderate utilizzare per creare la caratteristica. |
| **[!UICONTROL Select Goal Accuracy]** | Selezionate questa opzione per creare una caratteristica basata sull&#39;accuratezza. Precisione è un valore punteggio che indica il livello di prossimità degli utenti potenziali alla linea di base. La scala di precisione va da 0 (meno precisa) a 1 (più accurata). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | A destra, questa sezione visualizza fino a 21 righe di dati numerici che mostrano i valori di precisione e di portata per il modello. |
| **[!UICONTROL Reach and Accuracy Slider]** | Nella parte inferiore del grafico, il cursore consente di impostare un valore numerico per la portata o per gli obiettivi di precisione. Potete impostare il cursore, quindi scegliere il pulsante di portata o di precisione per creare una caratteristica. |

>[!MORE_ LIKE_ THIS]
>
>* [Precisione e portata](../../features/traits/trait-accuracy-reach.md)