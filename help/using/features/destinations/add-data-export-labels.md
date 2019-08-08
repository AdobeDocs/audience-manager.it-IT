---
description: Etichette esportazione dati funzionano con i controlli esportazione impostati su un'origine dati. Etichette esportazione dati impedisce l'aggiunta di caratteristiche limitate a un segmento e l'invio di dati di segmento a una destinazione. Potete impostare più etichette di esportazione su un cookie nuovo o esistente o su una destinazione URL.
seo-description: Etichette esportazione dati funzionano con i controlli esportazione impostati su un'origine dati. Etichette esportazione dati impedisce l'aggiunta di caratteristiche limitate a un segmento e l'invio di dati di segmento a una destinazione. Potete impostare più etichette di esportazione su un cookie nuovo o esistente o su una destinazione URL.
seo-title: Aggiungere controlli per l'esportazione di dati a una destinazione
solution: Audience Manager
title: Aggiungere controlli per l'esportazione di dati a una destinazione
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---



# Aggiungere etichette di esportazione dati a una destinazione {#add-data-export-labels}

[!DNL Data Export Labels] lavorare con il [!DNL Export Controls] set impostato su un'origine dati. [!DNL Data Export Labels] impedire l'aggiunta di caratteristiche limitate a un segmento e l'invio di dati di segmento a una destinazione. Potete impostare più etichette di esportazione su una nuova o esistente [!DNL cookie][!DNL URL] destinazione.

>[!NOTE]
>
>Per aggiungere un'etichetta di esportazione, dovete disporre delle autorizzazioni *di amministratore o* di privilegi sufficienti per creare o modificare una destinazione.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Fai clic su **[!UICONTROL Audience Data]**:
   * Per nuove destinazioni: Fate clic **[!UICONTROL Create New Destination]** su. Completate [!UICONTROL Basic Information] la sezione prima di selezionare un'etichetta di esportazione dati. Per informazioni, consultate [Creare una destinazione](../../features/destinations/manage-destinations.md#create-cookie-destination) cookie o [Creare una destinazione](../../features/destinations/manage-destinations.md#configure-url-destination) URL.
   * Per le destinazioni esistenti: Usate la [!DNL Search] casella per trovare la destinazione o scorrere l'elenco e fate clic sul nome della destinazione per aprirla.
1. Seleziona una [!DNL Data Export Label]. Lasciate vuote le caselle di controllo se non desiderate impostare restrizioni di esportazione. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Le limitazioni di esportazione non funzionano a meno che non imposti un [controllo di esportazione corrispondente](../../features/data-export-controls.md) su un'origine dati.
1. Fai clic su **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Creare un'origine dati](../../features/manage-datasources.md#create-data-source)