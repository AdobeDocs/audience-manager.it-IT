---
description: Crea nuove caratteristiche da tutti i segnali, inclusi quelli già utilizzati nelle caratteristiche, e acquisisci i tipi di pubblico futuri idonei dopo la creazione delle caratteristiche.
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: Creare caratteristiche dai segnali
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Creare caratteristiche dai segnali

Crea nuove caratteristiche da tutti i segnali, inclusi quelli già utilizzati nelle caratteristiche, e acquisisci i tipi di pubblico futuri idonei dopo la creazione delle caratteristiche. Guarda il video per una breve dimostrazione o leggi ulteriori informazioni:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Creare caratteristiche dal dashboard Segnale {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard] consente di creare nuove caratteristiche da [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] e dalle ricerche salvate.

Quando crei una nuova caratteristica, il tipo di caratteristica è preimpostato in base al tipo di segnale:

* **[!UICONTROL Rule-based]** caratteristiche per segnali in tempo reale, file di registro utilizzabili e [!DNL Adobe Analytics] segnali;

* **[!UICONTROL Onboarded]** caratteristiche per i segnali onboarded.

Per creare nuove caratteristiche da **[!UICONTROL Signal Dashboard]**, identifica il segnale da utilizzare nella caratteristica, quindi fai clic sul collegamento **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]** corrispondente.

![](assets/signals-create-trait.png)

Verrai reindirizzato al **[Generatore di caratteristiche](../../features/traits/about-trait-builder.md)** per creare le nuove caratteristiche.

## Creare caratteristiche dalla ricerca del segnale {#create-traits-from-signal-search}

Creare caratteristiche basate su segnali utilizzati o non utilizzati che non sono visualizzati in [!UICONTROL Signal Dashboard].

Cerca segnali specifici e crea caratteristiche basate su regole o onboarded in base ai risultati. Ecco come eseguire questa operazione:

1. Vai a **[!UICONTROL Audience Data > Signals > Search]** ed esegui una ricerca in base alle coppie chiave-valore che stai cercando, oppure fai clic su **[!UICONTROL Search]** senza immettere alcuna coppia chiave-valore per visualizzare tutti i risultati.
2. Identifica i segnali che desideri utilizzare nella caratteristica, nell’elenco dei risultati.
   * Per creare una caratteristica da un segnale, fare clic sul collegamento **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]** corrispondente.
   * Per creare una caratteristica da più segnali, fare clic sulla casella di controllo corrispondente di ciascun segnale, quindi fare clic su **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Puoi creare caratteristiche solo da segnali dello stesso tipo. Non è possibile creare una caratteristica basata su una combinazione di un segnale in tempo reale e uno integrato.
   >
   > ![](assets/signals-create-trait-search.png)
   >Puoi anche creare caratteristiche dai segnali usati. I segnali già utilizzati nelle caratteristiche hanno il numero di caratteristiche visualizzate nella colonna **[!UICONTROL Included in Traits]**. Fare clic sulla freccia per visualizzare le caratteristiche che includono il segnale.
   >
   >![](assets/signals-used-traits.png)

3. Utilizza **[Generatore caratteristiche](../../features/traits/about-trait-builder.md)** per creare le nuove caratteristiche.
