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

## Creare un [!UICONTROL Data Source] {#create-data-source}

Per creare una nuova [!UICONTROL data source], andate a **[!UICONTROL Audience Data > Data Sources > Add New]** e completate i passaggi per ciascuna sezione descritta qui. Per creare un [!UICONTROL data source] sono necessarie autorizzazioni di amministratore.

<!-- create-datasource.xml -->

>[!TIP]
>
>Per le descrizioni di questi diversi controlli, vedere [Impostazioni origine dati e Opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options).

## [!UICONTROL Data Source] Dettagli {#details}

Per completare la sezione [!UICONTROL Data Source Details]:

1. Denominate il simbolo [!UICONTROL data source].
1. *(Facoltativo)* Descrivete il  [!UICONTROL data source]pulsante. Una breve descrizione consente di definire il ruolo o lo scopo della [!UICONTROL data source].
1. Specificare un [!UICONTROL integration code]. In genere, [!UICONTROL integration codes] è facoltativo. Sono necessari per:

   * [Crea un&#39;origine](../features/profile-merge-rules/merge-rules-start.md#create-data-source) dati multi-dispositivo.
   * Utilizzare il [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html).
   * Utilizzare le [regole di unione dei profili](../features/profile-merge-rules/merge-rules-start.md).

1. Scegliete un elemento **[!UICONTROL ID Type]**. [!UICONTROL ID Type] le opzioni includono:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obbligatorio per creare un  [!UICONTROL Profile Merge Rule]). Nota: per alcuni clienti, questa selezione espone le opzioni **[!UICONTROL ID Definition]**.

1. Scegliete un&#39;opzione **[!UICONTROL ID Definition]**. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[I ](../features/data-export-controls.md) controlli di esportazione dei dati sono regole di classificazione facoltative applicabili a  [!UICONTROL data source] e  [!UICONTROL destination]. Ciò impedisce l&#39;invio di dati a un [!UICONTROL destination] in caso di violazione della privacy dei dati o dell&#39;accordo sull&#39;utilizzo. Saltate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Impostazioni {#settings}

Queste impostazioni determinano in che modo [!UICONTROL data source] viene identificato, utilizzato e condiviso. È inoltre possibile abilitare la segnalazione degli errori per i file di dati in entrata. Per completare la sezione [!UICONTROL Data Source Settings]:

1. Selezionare una casella di controllo [!UICONTROL Data Source Setting] per applicare un&#39;opzione a [!UICONTROL data source].
2. Clic **[!UICONTROL Save]**.

## Eliminare un&#39;origine dati {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminare un [!UICONTROL data source] non più necessario.

>[!NOTE]
>
>Prendete nota delle seguenti limitazioni:
>
>* Non è possibile eliminare un [Pubblico attivo o una caratteristica sincronizzata origine dati](../features/traits/client-activity-synced-audience-traits.md).
>* Per i clienti che utilizzano  Adobe Analytics:  Audience Manager non consente di eliminare le origini dati create automaticamente dalle suite di rapporti [!DNL Analytics]. Utilizzare il [servizio di base](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) per annullare la mappatura di queste origini dati.


1. Clic **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Selezionare la casella di controllo accanto a una o più origini dati.
È possibile utilizzare la casella [!UICONTROL Search] per individuare le origini dati desiderate se si dispone di un elenco lungo.
1. Fare clic su ![](assets/icon_trash.png), quindi confermare l&#39;eliminazione.


>[!MORELIKETHIS]
>
>* [Impostazioni origine dati e opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options)