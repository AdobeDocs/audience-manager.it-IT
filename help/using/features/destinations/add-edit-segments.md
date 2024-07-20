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
ht-degree: 0%

---

# Aggiungere o modificare segmenti per le destinazioni server-to-server {#add-edit-segments}

È possibile aggiungere o modificare segmenti solo per una destinazione da server a server ([!DNL S2S]). Impossibile creare [!DNL S2S] destinazioni con [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Contatta il tuo consulente per configurare [!DNL S2S] destinazioni. Seguire queste istruzioni per aggiungere o modificare segmenti per una destinazione [!DNL S2S].

<!-- destination-s2s-edit.xml -->

Per aggiungere o modificare i mapping di segmenti per una destinazione [!DNL S2S]:

1. Vai a **[!UICONTROL Audience Data > Destinations]**. Seleziona **Piattaforme integrate > Basate su dispositivo** e individua la destinazione [!DNL S2S] con cui vuoi lavorare.
2. Nella colonna [!UICONTROL Action] fare clic sull&#39;icona della matita per modificare la destinazione.
   * Nella casella **[!UICONTROL Search and Add Segments]**, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** Sfoglia un elenco di segmenti disponibili.
   * Fare clic su **[!UICONTROL Add Selected Segments]** quando si trova il segmento che si desidera utilizzare. L&#39;aggiunta di un segmento apre la finestra [!UICONTROL Edit Mapping].
   * In [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: impostare un valore per la [coppia chiave-valore](../../features/destinations/key-value-pairs.md) utilizzata da questa destinazione.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: scegliere una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade mai.
3. Fare clic su **[!UICONTROL Save]** e quindi su **[!UICONTROL Done]**.
