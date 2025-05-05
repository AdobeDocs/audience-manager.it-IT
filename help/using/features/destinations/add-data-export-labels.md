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
ht-degree: 1%

---

# Aggiungere etichette di esportazione dei dati a una destinazione {#add-data-export-labels}

[!DNL Data Export Labels] funziona con [!DNL Export Controls] impostato su un&#39;origine dati. [!DNL Data Export Labels] impedisce l&#39;aggiunta di caratteristiche con restrizioni a un segmento e l&#39;invio di dati del segmento a una destinazione. È possibile impostare più etichette di esportazione su una destinazione [!DNL cookie] o [!DNL URL] nuova o esistente.

>[!NOTE]
>
>Per aggiungere un&#39;etichetta di esportazione, sono necessarie autorizzazioni di amministratore *o* sufficienti per creare o modificare una destinazione.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Fare clic su **[!UICONTROL Audience Data]**:
   * Per le nuove destinazioni: fare clic su **[!UICONTROL Create New Destination]**. Completare la sezione [!UICONTROL Basic Information] prima di selezionare un&#39;etichetta di esportazione dati. Per informazioni, vedere [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md) o [Creare una destinazione URL](../../features/destinations/create-url-destination.md).
   * Per le destinazioni esistenti: utilizzare la casella [!DNL Search] per trovare la destinazione o scorrere l&#39;elenco e fare clic sul nome della destinazione per aprirla.
1. Seleziona [!DNL Data Export Label]. Lasciare vuote le caselle di controllo se non si desidera impostare alcuna restrizione all&#39;esportazione. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Le restrizioni all&#39;esportazione non funzioneranno se non si imposta un controllo di esportazione [corrispondente](../../features/data-export-controls.md) in un&#39;origine dati.
1. Fare clic su **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Creare una sorgente di dati](../../features/manage-datasources.md#create-data-source)
