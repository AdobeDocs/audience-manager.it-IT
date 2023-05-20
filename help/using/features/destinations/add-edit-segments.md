---
description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un'origine dati. Le etichette di esportazione dei dati impediscono l’aggiunta di caratteristiche soggette a restrizioni a un segmento e l’invio di dati del segmento a una destinazione. Puoi impostare più etichette di esportazione su un cookie o una destinazione URL nuova o esistente.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: Aggiungere o modificare segmenti per le destinazioni server-to-server
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---

# Aggiungere o modificare segmenti per le destinazioni server-to-server {#add-edit-segments}

È possibile aggiungere o modificare segmenti solo per un server-to-server ([!DNL S2S]) destinazione. Impossibile creare [!DNL S2S] destinazioni con [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Contatta il tuo consulente per configurare [!DNL S2S] destinazioni. Segui queste istruzioni per aggiungere o modificare segmenti per un [!DNL S2S] destinazione.

<!-- destination-s2s-edit.xml -->

Per aggiungere o modificare mappature di segmenti per un [!DNL S2S] destinazione:

1. Vai a **[!UICONTROL Audience Data > Destinations]**. Seleziona **Piattaforme integrate > Basate su dispositivi** e trovare [!DNL S2S] destinazione con cui lavorare.
2. In [!UICONTROL Action] , fai clic sull’icona della matita per modificare la destinazione.
   * In **[!UICONTROL Search and Add Segments]** , inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** sfoglia un elenco di segmenti disponibili.
   * Clic **[!UICONTROL Add Selected Segments]** quando trovi il segmento che desideri utilizzare. L’aggiunta di un segmento apre il [!UICONTROL Edit Mapping] finestra.
   * In [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: imposta un valore per [coppia chiave-valore](../../features/destinations/key-value-pairs.md) utilizzato da questa destinazione.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: scegli una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade mai.
3. Clic **[!UICONTROL Save]** e quindi fare clic su **[!UICONTROL Done]**.
