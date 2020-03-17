---
description: Per creare una nuova origine dati, accedi a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ciascuna sezione descritta qui. Per creare un'origine dati è necessario disporre delle autorizzazioni di amministratore.
keywords: data sources;manage data source;audience manager data source
seo-description: Per creare una nuova origine dati, accedi a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ciascuna sezione descritta qui. Per creare un'origine dati è necessario disporre delle autorizzazioni di amministratore.
seo-title: Creazione di un'origine dati
solution: Audience Manager
title: Gestisci origini dati
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

Per creare una nuova origine dati, passare a **[!UICONTROL Audience Data > Data Sources > Add New]** e completare i passaggi descritti di seguito. Per creare un&#39;origine dati è necessario disporre delle autorizzazioni di amministratore.

<!-- create-datasource.xml -->

>[!TIP]
>
>Per una descrizione di questi diversi controlli, vedere Impostazioni origine [dati e Opzioni](../features/datasources-list-and-settings.md#settings-menu-options) menu.

## Dettagli origine dati {#details}

Per completare la [!UICONTROL Data Source Details] sezione:

1. Denominare l&#39;origine dati.
1. *(Facoltativo)* Descrivere l&#39;origine dati. Una breve descrizione consente di definire il ruolo o lo scopo dell&#39;origine dati.
1. Fornite un codice di integrazione. In genere, i codici di integrazione sono facoltativi. Sono necessari per:

   * [Crea un&#39;origine](../features/profile-merge-rules/merge-rules-start.md#create-data-source)dati multi-dispositivo.
   * Utilizzate [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Utilizzare le regole [di unione dei](../features/profile-merge-rules/merge-rules-start.md)profili.

1. Scegliete un **[!UICONTROL ID Type]**. Le opzioni per il tipo di ID includono:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obbligatorio per creare un [!UICONTROL Profile Merge Rule]). Nota: per alcuni clienti questa selezione espone le **[!UICONTROL ID Definition]** opzioni.

1. Scegliete un’ **[!UICONTROL ID Definition]** opzione. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controlli sull&#39;esportazione dei dati {#export-controls}

[I Controlli](../features/data-export-controls.md) sull&#39;esportazione dei dati sono regole di classificazione facoltative applicabili a un&#39;origine dati e a una destinazione. Impediscono l&#39;invio di dati a una destinazione in caso di violazione della privacy dei dati o dell&#39;accordo di utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Queste impostazioni determinano il modo in cui un&#39;origine dati viene identificata, utilizzata e condivisa. È inoltre possibile abilitare la segnalazione degli errori per i file di dati in entrata. Per completare la [!UICONTROL Data Source Settings] sezione:

1. Selezionare una [!UICONTROL Data Source Setting] casella di controllo per applicare un&#39;opzione all&#39;origine dati.
2. Clic **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Impostazioni origine dati e opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options)


## Eliminazione di un&#39;origine dati {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminare un&#39;origine dati non più necessaria.

>[!NOTE]
>
>Prendete nota delle seguenti limitazioni:
>
>* Non puoi eliminare un [Pubblico attivo o una caratteristica](../features/traits/client-activity-synced-audience-traits.md)sincronizzata origine dati.
>* Per i clienti che utilizzano Adobe Analytics: Audience Manager non consente di eliminare le origini dati create automaticamente dalle suite di [!DNL Analytics] rapporti. Utilizzate il servizio [](https://marketing.adobe.com/resources/help/en_US/mcloud/) core per annullare la mappatura di queste origini dati.


1. Clic **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Selezionare la casella di controllo accanto a una o più origini dati.
È possibile utilizzare la [!UICONTROL Search] casella per individuare le origini dati desiderate se si dispone di un elenco lungo.
1. Fare clic ![](assets/icon_trash.png), quindi confermare l&#39;eliminazione.