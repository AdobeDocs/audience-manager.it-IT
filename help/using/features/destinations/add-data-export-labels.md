---
description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un'origine dati. Le etichette di esportazione dei dati non consentono di aggiungere caratteristiche limitate a un segmento e di inviare dati del segmento a una destinazione. Potete impostare più etichette di esportazione su una destinazione di cookie o URL nuova o esistente.
seo-description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un'origine dati. Le etichette di esportazione dei dati non consentono di aggiungere caratteristiche limitate a un segmento e di inviare dati del segmento a una destinazione. Potete impostare più etichette di esportazione su una destinazione di cookie o URL nuova o esistente.
seo-title: Aggiungere controlli sull’esportazione dei dati a una destinazione
solution: Audience Manager
title: Aggiungere controlli sull’esportazione dei dati a una destinazione
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---



# Aggiungi etichette di esportazione dati a una destinazione {#add-data-export-labels}

[!DNL Data Export Labels] lavorare con l&#39; [!DNL Export Controls] impostazione su un&#39;origine dati. [!DNL Data Export Labels] impedisci di aggiungere caratteristiche limitate a un segmento e di inviare dati di segmento a una destinazione. È possibile impostare più etichette di esportazione su una destinazione [!DNL cookie] o [!DNL URL] nuova o esistente.

>[!NOTE]
>
>Per aggiungere un&#39;etichetta di esportazione, è necessario disporre di autorizzazioni di amministratore *o* sufficienti privilegi per creare o modificare una destinazione.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Clic **[!UICONTROL Audience Data]**:
   * Per le nuove destinazioni: Fare clic su **[!UICONTROL Create New Destination]**. Completare la sezione [!UICONTROL Basic Information] prima di selezionare un&#39;etichetta di esportazione dei dati. Per ulteriori informazioni, vedere [Creare una destinazione di cookie](../../features/destinations/create-cookie-destination.md) o [Creare una destinazione URL](../../features/destinations/create-url-destination.md).
   * Per le destinazioni esistenti: Utilizzare la casella [!DNL Search] per trovare la destinazione oppure scorrere l&#39;elenco e fare clic sul nome della destinazione per aprirlo.
1. Seleziona una [!DNL Data Export Label]. Se non si desidera impostare alcuna limitazione all’esportazione, lasciare le caselle di controllo vuote. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Le restrizioni all&#39;esportazione non funzioneranno se non si imposta un [corrispondente controllo di esportazione](../../features/data-export-controls.md) su un&#39;origine dati.
1. Clic **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Creare una sorgente di dati](../../features/manage-datasources.md#create-data-source)