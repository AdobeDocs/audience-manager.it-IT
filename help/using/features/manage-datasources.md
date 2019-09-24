---
description: Per creare una nuova origine dati, accedi a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ciascuna sezione descritta qui. Per creare un'origine dati è necessario disporre delle autorizzazioni di amministratore.
keywords: origini dati;gestire l'origine dati;origine dati di Gestione dell'audience
seo-description: Per creare una nuova origine dati, accedi a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ciascuna sezione descritta qui. Per creare un'origine dati è necessario disporre delle autorizzazioni di amministratore.
seo-title: Creazione di un'origine dati
solution: Audience Manager
title: Gestisci origini dati
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

Per creare una nuova origine dati, passare a **[!UICONTROL Audience Data > Data Sources > Add New]** e completare i passaggi descritti di seguito. Per creare un'origine dati è necessario disporre delle autorizzazioni di amministratore.

<!-- create-datasource.xml -->

>[!TIP]
>
>Per una descrizione di questi diversi controlli, vedere Impostazioni origine [dati e Opzioni](../features/datasources-list-and-settings.md#settings-menu-options) menu.

## Dettagli origine dati {#details}

Per completare la [!UICONTROL Data Source Details] sezione:

1. Denominare l'origine dati.
1. *(Facoltativo)* Descrivere l'origine dati. Una breve descrizione consente di definire il ruolo o lo scopo dell'origine dati.
1. Fornite un codice di integrazione. In genere, i codici di integrazione sono facoltativi. Sono necessari per:

   * [Create a cross-device data source](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Usa il servizio [](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID.
   * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an . **[!UICONTROL ID Type]** ID Type options include:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Required to create a [!UICONTROL Profile Merge Rule]). Nota: per alcuni clienti questa selezione espone le **[!UICONTROL ID Definition]** opzioni.

1. Scegliete un’ **[!UICONTROL ID Definition]** opzione. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controlli sull'esportazione dei dati {#export-controls}

[I Controlli](../features/data-export-controls.md) sull'esportazione dei dati sono regole di classificazione facoltative applicabili a un'origine dati e a una destinazione. Impediscono l'invio di dati a una destinazione in caso di violazione della privacy dei dati o dell'accordo di utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Queste impostazioni determinano il modo in cui un'origine dati viene identificata, utilizzata e condivisa. È inoltre possibile abilitare la segnalazione degli errori per i file di dati in entrata. Per completare la [!UICONTROL Data Source Settings] sezione:

1. Selezionare una [!UICONTROL Data Source Setting] casella di controllo per applicare un'opzione all'origine dati.
2. Fai clic su **[!UICONTROL Save]**.

>[!MORE_LIKE_this]
>
>* [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Delete a data source that you no longer need.

>[!NOTE]
>
>Please note the following restrictions:
>
>* You cannot delete an Active Audience or Data Source Synced Trait.[](../features/traits/client-activity-synced-audience-traits.md)
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your  report suites. [!DNL Analytics] Use the Core Service to unmap these data sources.[](https://marketing.adobe.com/resources/help/en_US/mcloud/)


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Selezionare la casella di controllo accanto a una o più origini dati.
You can use the  box to locate the desired data sources if you have a long list.[!UICONTROL Search]
1. Click  , then confirm the deletion.![](assets/icon_trash.png)