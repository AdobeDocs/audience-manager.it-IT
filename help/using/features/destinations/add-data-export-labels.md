---
description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un’origine dati. Le etichette di esportazione dei dati impediscono l’aggiunta di caratteristiche limitate a un segmento e l’invio di dati di segmento a una destinazione. Puoi impostare più etichette di esportazione su un cookie o una destinazione URL nuova o esistente.
seo-description: Le etichette di esportazione dei dati funzionano con i controlli di esportazione impostati su un’origine dati. Le etichette di esportazione dei dati impediscono l’aggiunta di caratteristiche limitate a un segmento e l’invio di dati di segmento a una destinazione. Puoi impostare più etichette di esportazione su un cookie o una destinazione URL nuova o esistente.
seo-title: Aggiungere controlli sull’esportazione dei dati a una destinazione
solution: Audience Manager
title: Aggiungere controlli sull’esportazione dei dati a una destinazione
feature: Controlli sull’esportazione dei dati
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 8%

---

# Aggiungere etichette di esportazione dei dati a una destinazione {#add-data-export-labels}

[!DNL Data Export Labels] utilizzare le impostazioni  [!DNL Export Controls] impostate in un’origine dati. [!DNL Data Export Labels] impedisce l’aggiunta di caratteristiche limitate a un segmento e l’invio di dati di segmento a una destinazione. Puoi impostare più etichette di esportazione su una destinazione nuova o esistente [!DNL cookie] o [!DNL URL].

>[!NOTE]
>
>Per aggiungere un’etichetta di esportazione, è necessario disporre delle autorizzazioni di amministratore *o* di privilegi sufficienti per creare o modificare una destinazione.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Clic **[!UICONTROL Audience Data]**:
   * Per le nuove destinazioni: Fare clic su **[!UICONTROL Create New Destination]**. Completa la sezione [!UICONTROL Basic Information] prima di selezionare un’etichetta di esportazione dei dati. Per informazioni, consulta [Creare una destinazione cookie](../../features/destinations/create-cookie-destination.md) o [Creare una destinazione URL](../../features/destinations/create-url-destination.md) .
   * Per le destinazioni esistenti: Usa la casella [!DNL Search] per trovare la destinazione oppure scorri l’elenco e fai clic sul nome della destinazione per aprirla.
1. Seleziona una [!DNL Data Export Label]. Se non si desidera impostare alcuna restrizione all’esportazione, lasciare le caselle di controllo vuote. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Le restrizioni all&#39;esportazione non funzioneranno se non si imposta un [controllo di esportazione corrispondente](../../features/data-export-controls.md) su un&#39;origine dati.
1. Clic **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Creare una sorgente di dati](../../features/manage-datasources.md#create-data-source)

