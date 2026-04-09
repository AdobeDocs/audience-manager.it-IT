---
description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un'origine dati. Le etichette di esportazione dei dati impediscono l’aggiunta di caratteristiche soggette a restrizioni a un segmento e l’invio di dati del segmento a una destinazione. Puoi impostare più etichette di esportazione su un cookie o una destinazione URL nuova o esistente.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: Aggiungere o modificare segmenti per le destinazioni server-to-server
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
TQID: https://experienceleague.adobe.com/3bcMGBGMb4HtnPA8yFvO4UzfGXmpvM2Drs427ztfWDc
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c138d302-73f0-4186-93ea-10c4ba52f943
  - id: e7029888-c8b0-46a7-849a-cf132a1559bf
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 202
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
