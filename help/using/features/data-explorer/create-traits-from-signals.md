---
description: Create nuove caratteristiche da tutti i segnali, inclusi quelli già utilizzati nelle caratteristiche, e acquisite audience future idonee dopo la creazione delle caratteristiche.
seo-description: Create nuove caratteristiche da tutti i segnali, inclusi quelli già utilizzati nelle caratteristiche, e acquisite audience future idonee dopo la creazione delle caratteristiche.
seo-title: Creare caratteristiche dai segnali
title: Creare caratteristiche dai segnali
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---


# Creare caratteristiche dai segnali

Create nuove caratteristiche da tutti i segnali, inclusi quelli già utilizzati nelle caratteristiche, e acquisite audience future idonee dopo la creazione delle caratteristiche. Guardate il video per una rapida dimostrazione o leggete su per informazioni dettagliate:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Creare caratteristiche dal dashboard del segnale {#create-traits-from-signal-dashboard}

Consente [!UICONTROL Signal Dashboard] di creare nuove caratteristiche dalle ricerche salvate [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals]e

Quando create una nuova caratteristica, il tipo di caratteristica è preimpostato in base al tipo di segnale:

* **[!UICONTROL Rule-based]** caratteristiche per segnali in tempo reale, file di registro e [!DNL Adobe Analytics] segnali fruibili;

* **[!UICONTROL Onboarded]** caratteristiche dei segnali caricati.

Per creare nuove caratteristiche dal **[!UICONTROL Signal Dashboard]**, identificate il segnale che desiderate usare nella caratteristica, quindi fate clic sul **[!UICONTROL Create Rule-Based Trait]** collegamento o **[!UICONTROL Create Onboarded Trait]** collegamento corrispondente.

![](assets/signals-create-trait.png)

Verrai reindirizzato al **[Generatore](../../features/traits/about-trait-builder.md)**di caratteristiche per creare le nuove caratteristiche.

## Creare caratteristiche dalla ricerca del segnale {#create-traits-from-signal-search}

Create caratteristiche basate su segnali usati o non utilizzati che non vengono visualizzati nel [!UICONTROL Signal Dashboard].

Cercare segnali specifici e creare tratti basati su regole o caricati in base ai risultati. Come procedere:

1. Andate a **[!UICONTROL Audience Data > Signals > Search]** ed eseguite una ricerca in base alle coppie chiave-valore che state cercando, oppure fate clic su **[!UICONTROL Search]** senza immettere alcuna coppia chiave-valore per visualizzare tutti i risultati.
2. Identificare i segnali che si desidera utilizzare nella caratteristica, nell&#39;elenco dei risultati.
   * Per creare una caratteristica da un segnale, fare clic sul **[!UICONTROL Create Rule-Based Trait]** collegamento o **[!UICONTROL Create Onboarded Trait]** collegamento corrispondente.
   * Per creare una caratteristica da più segnali, fare clic sulla casella di controllo corrispondente di ciascun segnale, quindi fare clic **[!UICONTROL Create Trait from Multiple Signals]**.
   >[!NOTE]
   >È possibile creare caratteristiche solo da segnali dello stesso tipo. Non è possibile creare una caratteristica basata su una combinazione di un segnale in tempo reale e uno integrato.
   >
   > ![](assets/signals-create-trait-search.png)
   >Potete anche creare caratteristiche dai segnali usati. I segnali già utilizzati nelle caratteristiche presentano il numero di caratteristiche visualizzate nella **[!UICONTROL Included in Traits]** colonna. Fare clic sulla freccia per visualizzare le caratteristiche che includono il segnale.
   >
   >![](assets/signals-used-traits.png)

3. Utilizzate **[Trait Builder](../../features/traits/about-trait-builder.md)**per creare nuove caratteristiche.
