---
description: Crea nuove caratteristiche da tutti i segnali, compresi quelli già utilizzati nelle caratteristiche, e acquisisci i tipi di pubblico futuri che si qualificano dopo la creazione delle caratteristiche.
seo-description: Crea nuove caratteristiche da tutti i segnali, compresi quelli già utilizzati nelle caratteristiche, e acquisisci i tipi di pubblico futuri che si qualificano dopo la creazione delle caratteristiche.
seo-title: Creare caratteristiche dai segnali
title: Creare caratteristiche dai segnali
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: 'Data Explorer '
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# Creare caratteristiche dai segnali

Crea nuove caratteristiche da tutti i segnali, compresi quelli già utilizzati nelle caratteristiche, e acquisisci i tipi di pubblico futuri che si qualificano dopo la creazione delle caratteristiche. Guarda il video per una rapida dimostrazione o leggi su per informazioni dettagliate:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Creare caratteristiche dal dashboard del segnale {#create-traits-from-signal-dashboard}

Il [!UICONTROL Signal Dashboard] ti consente di creare nuove caratteristiche dalle [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] e dalle ricerche salvate.

Quando crei una nuova caratteristica, il tipo di caratteristica è preimpostato in base al tipo di segnale:

* **[!UICONTROL Rule-based]** caratteristiche per segnali in tempo reale, file di log actionable e  [!DNL Adobe Analytics] segnali;

* **[!UICONTROL Onboarded]** caratteristiche per segnali onboarded.

Per creare nuove caratteristiche dal **[!UICONTROL Signal Dashboard]**, identifica il segnale che desideri utilizzare nella caratteristica, quindi fai clic sul collegamento corrispondente **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]**.

![](assets/signals-create-trait.png)

Verrai reindirizzato al **[Generatore di caratteristiche](../../features/traits/about-trait-builder.md)** per creare le nuove caratteristiche.

## Creare caratteristiche dalla ricerca del segnale {#create-traits-from-signal-search}

Crea caratteristiche basate su segnali utilizzati o non utilizzati che non vengono visualizzati in [!UICONTROL Signal Dashboard].

Cerca segnali specifici e crea caratteristiche basate su regole o onboarded in base ai risultati. Ecco come eseguire questa operazione:

1. Vai a **[!UICONTROL Audience Data > Signals > Search]** ed esegui una ricerca in base alle coppie chiave-valore che stai cercando, oppure fai clic su **[!UICONTROL Search]** senza inserire alcuna coppia chiave-valore per visualizzare tutti i risultati.
2. Identifica i segnali che desideri utilizzare nella caratteristica, nell’elenco dei risultati.
   * Per creare una caratteristica da un segnale, fai clic sul collegamento corrispondente **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]**.
   * Per creare una caratteristica da più segnali, fai clic sulla casella di controllo corrispondente di ciascun segnale, quindi fai clic su **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Puoi creare caratteristiche solo da segnali dello stesso tipo. Non puoi creare una caratteristica basata su una combinazione di un segnale in tempo reale e di un segnale onboarded.
   >
   > ![](assets/signals-create-trait-search.png)
   >Puoi anche creare caratteristiche dai segnali usati. I segnali già utilizzati nelle caratteristiche presentano il numero di caratteristiche visualizzate nella colonna **[!UICONTROL Included in Traits]** . Fai clic sulla freccia per visualizzare le caratteristiche che includono il segnale.
   >
   >![](assets/signals-used-traits.png)

3. Utilizza il **[Generatore di caratteristiche](../../features/traits/about-trait-builder.md)** per creare le nuove caratteristiche.
