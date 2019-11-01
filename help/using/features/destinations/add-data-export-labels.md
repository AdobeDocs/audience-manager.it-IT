---
description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un'origine dati. Le etichette di esportazione dei dati non consentono di aggiungere caratteristiche limitate a un segmento e di inviare dati del segmento a una destinazione. Potete impostare più etichette di esportazione su una destinazione di cookie o URL nuova o esistente.
seo-description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un'origine dati. Le etichette di esportazione dei dati non consentono di aggiungere caratteristiche limitate a un segmento e di inviare dati del segmento a una destinazione. Potete impostare più etichette di esportazione su una destinazione di cookie o URL nuova o esistente.
seo-title: Aggiungi controlli di esportazione dati a una destinazione
solution: Audience Manager
title: Aggiungi controlli di esportazione dati a una destinazione
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---



# Aggiungi etichette di esportazione dati a una destinazione {#add-data-export-labels}

[!DNL Data Export Labels] lavorare con l' [!DNL Export Controls] impostazione su un'origine dati. [!DNL Data Export Labels] impedisci di aggiungere caratteristiche limitate a un segmento e di inviare dati di segmento a una destinazione. Potete impostare più etichette di esportazione su una nuova o esistente [!DNL cookie] o su una [!DNL URL] destinazione.

>[!NOTE]
>
>Per aggiungere un'etichetta di esportazione, è necessario disporre di autorizzazioni di amministratore *o di privilegi sufficienti per* creare o modificare una destinazione.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Fai clic su **[!UICONTROL Audience Data]**:
   * Per le nuove destinazioni:Fate clic **[!UICONTROL Create New Destination]**. Completare la [!UICONTROL Basic Information] sezione prima di selezionare un'etichetta di esportazione dei dati. Per informazioni, consultate [Creare una destinazione](../../features/destinations/create-cookie-destination.md) cookie o [Creare una destinazione](../../features/destinations/create-url-destination.md) URL.
   * Per le destinazioni esistenti: Utilizzare la [!DNL Search] casella per trovare la destinazione o scorrere l'elenco e fare clic sul nome della destinazione per aprirlo.
1. Seleziona una [!DNL Data Export Label]. Se non si desidera impostare alcuna limitazione all’esportazione, lasciare le caselle di controllo vuote. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Le restrizioni all'esportazione non funzioneranno se non imposti un controllo [](../../features/data-export-controls.md) di esportazione corrispondente su un'origine dati.
1. Fai clic su **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Creazione di un'origine dati](../../features/manage-datasources.md#create-data-source)