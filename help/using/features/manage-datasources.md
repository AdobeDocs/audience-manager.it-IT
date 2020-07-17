---
description: Per creare una nuova origine dati, accedi a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ciascuna sezione descritta qui. Per creare un'origine dati è necessario disporre delle autorizzazioni di amministratore.
keywords: data sources;manage data source;audience manager data source
seo-description: Per creare una nuova origine dati, accedi a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ciascuna sezione descritta qui. Per creare un'origine dati è necessario disporre delle autorizzazioni di amministratore.
seo-title: Creare una sorgente di dati
solution: Audience Manager
title: Gestisci origini dati
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 4%

---


# Gestire i  [!UICONTROL Data Sources]{#manage-data-sources}

## Crea un [!UICONTROL Data Source] {#create-data-source}

Per creare una nuova sezione, [!UICONTROL data source]andate a **[!UICONTROL Audience Data > Data Sources > Add New]** completare i passaggi descritti di seguito. Per creare un account è necessario disporre delle autorizzazioni di amministratore [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Per una descrizione di questi diversi controlli, vedere Impostazioni origine [dati e Opzioni](../features/datasources-list-and-settings.md#settings-menu-options) menu.

## [!UICONTROL Data Source] Dettagli {#details}

Per completare la [!UICONTROL Data Source Details] sezione:

1. Denominate il [!UICONTROL data source].
1. *(Facoltativo)* Descrivete il [!UICONTROL data source]. Una breve descrizione consente di definire il ruolo o lo scopo dell’ [!UICONTROL data source].
1. Fornisci un [!UICONTROL integration code]. In genere [!UICONTROL integration codes] sono facoltative. Sono necessari per:

   * [Crea un&#39;origine](../features/profile-merge-rules/merge-rules-start.md#create-data-source)dati multi-dispositivo.
   * Use the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html).
   * Utilizzare le regole [di unione dei](../features/profile-merge-rules/merge-rules-start.md)profili.

1. Scegliete un **[!UICONTROL ID Type]**. [!UICONTROL ID Type] le opzioni includono:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obbligatorio per creare un [!UICONTROL Profile Merge Rule]). Nota: per alcuni clienti questa selezione espone le **[!UICONTROL ID Definition]** opzioni.

1. Scegliete un’ **[!UICONTROL ID Definition]** opzione. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[I controlli](../features/data-export-controls.md) di esportazione dei dati sono regole di classificazione facoltative applicabili a un [!UICONTROL data source] e [!UICONTROL destination]. Impediscono l&#39;invio di dati a un [!UICONTROL destination] utente in caso di violazione della privacy dei dati o dell&#39;accordo di utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Impostazioni {#settings}

Queste impostazioni determinano il modo in cui un utente [!UICONTROL data source] viene identificato, utilizzato e condiviso. È inoltre possibile abilitare la segnalazione degli errori per i file di dati in entrata. Per completare la [!UICONTROL Data Source Settings] sezione:

1. Selezionate una [!UICONTROL Data Source Setting] casella di controllo per applicare un’opzione al vostro [!UICONTROL data source].
2. Clic **[!UICONTROL Save]**.

## Eliminazione di un&#39;origine dati {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminare un elemento [!UICONTROL data source] che non è più necessario.

>[!NOTE]
>
>Prendete nota delle seguenti limitazioni:
>
>* Non puoi eliminare un [Pubblico attivo o una caratteristica](../features/traits/client-activity-synced-audience-traits.md)sincronizzata origine dati.
>* Per i clienti che utilizzano Adobe  Analytics:  Audience Manager non consente di eliminare le origini dati create automaticamente dalle suite di [!DNL Analytics] rapporti. Utilizzate il servizio [](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) core per annullare la mappatura di queste origini dati.


1. Clic **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Selezionare la casella di controllo accanto a una o più origini dati.
È possibile utilizzare la [!UICONTROL Search] casella per individuare le origini dati desiderate se si dispone di un elenco lungo.
1. Fare clic ![](assets/icon_trash.png), quindi confermare l&#39;eliminazione.


>[!MORELIKETHIS]
>
>* [Impostazioni origine dati e opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options)