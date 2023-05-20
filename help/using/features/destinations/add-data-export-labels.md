---
description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un'origine dati. Le etichette di esportazione dei dati impediscono l’aggiunta di caratteristiche soggette a restrizioni a un segmento e l’invio di dati del segmento a una destinazione. Puoi impostare più etichette di esportazione su un cookie o una destinazione URL nuova o esistente.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Aggiungere controlli sull’esportazione dei dati a una destinazione
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 6%

---

# Aggiungere etichette di esportazione dei dati a una destinazione {#add-data-export-labels}

[!DNL Data Export Labels] utilizzare [!DNL Export Controls] è stata impostata su un&#39;origine dati. [!DNL Data Export Labels] impedisci di aggiungere caratteristiche soggette a restrizioni a un segmento e di inviare dati del segmento a una destinazione. È possibile impostare più etichette di esportazione su una nuova o esistente [!DNL cookie] o [!DNL URL] destinazione.

>[!NOTE]
>
>Per aggiungere un’etichetta di esportazione sono necessarie le autorizzazioni di amministratore *o* privilegi sufficienti per creare o modificare una destinazione.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Clic **[!UICONTROL Audience Data]**:
   * Per le nuove destinazioni: fai clic su **[!UICONTROL Create New Destination]**. Completa il [!UICONTROL Basic Information] prima di selezionare un&#39;etichetta di esportazione dati. Consulta [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md) o [Creare una destinazione URL](../../features/destinations/create-url-destination.md) per informazione.
   * Per le destinazioni esistenti: utilizza [!DNL Search] per trovare la destinazione o scorrere l&#39;elenco e fare clic sul nome della destinazione per aprirlo.
1. Seleziona una [!DNL Data Export Label]. Lasciare vuote le caselle di controllo se non si desidera impostare alcuna restrizione all&#39;esportazione. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Le restrizioni all&#39;esportazione non funzioneranno a meno che non si imposti un [controllo di esportazione corrispondente](../../features/data-export-controls.md) su un&#39;origine dati.
1. Clic **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Creare una sorgente di dati](../../features/manage-datasources.md#create-data-source)

