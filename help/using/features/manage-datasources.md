---
description: Per creare una nuova origine dati, vai a Dati audience > Origini dati > Aggiungi nuovo e completa i passaggi per ogni sezione descritta qui. Per creare un'origine dati sono necessarie autorizzazioni di amministratore.
keywords: cdf; feed dati personalizzato
seo-description: Per creare una nuova origine dati, vai a Dati audience > Origini dati > Aggiungi nuovo e completa i passaggi per ogni sezione descritta qui. Per creare un'origine dati sono necessarie autorizzazioni di amministratore.
seo-title: Creare un'origine dati
solution: Audience Manager
title: Creare un'origine dati
uuid: 4 df 65 bcb -9 ad 9-4 b 72-a 71 e -8918 b 43 d 4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Per creare un'origine dati sono necessarie autorizzazioni di amministratore.

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Denominate l'origine dati.
1. *(Facoltativo)* Descrivete l'origine dati. Una descrizione concisa consente di definire il ruolo o lo scopo dell'origine dati.
1. Fornite un codice di integrazione. In genere, i codici di integrazione sono facoltativi. Sono necessari quando si desidera:

   * [Crea un'origine dati cross-device](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Use the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an **[!UICONTROL ID Type]**. Le opzioni Tipo ID includono:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obbligatorio per creare un [!UICONTROL Profile Merge Rule]). Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controlli sull'esportazione dei dati {#export-controls}

[I controlli sull'esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a un'origine dati e a una destinazione. Essi non potranno inviare dati a una destinazione quando questa azione viola una privacy dei dati o utilizzano l'accordo. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Queste impostazioni determinano in che modo un'origine dati viene identificata, utilizzata e condivisa. Potete inoltre attivare la generazione di rapporti degli errori per i file di dati in entrata. To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. Fai clic su **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Impostazioni origine dati e Opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminare un'origine dati non più necessaria.

>[!NOTE]
>
>Tenete presente le seguenti limitazioni:
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Seleziona la casella di controllo accanto a una o più origini dati.
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.