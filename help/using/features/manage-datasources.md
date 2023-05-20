---
description: Per creare una nuova origine dati, passa a Dati pubblico > Origini dati > Aggiungi nuova e completa i passaggi per ciascuna sezione descritta qui. Per creare un'origine dati sono necessarie le autorizzazioni di amministratore.
keywords: origini dati;gestire origine dati;audience manager origine dati;data sources;manage data source;audience manager data source
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Gestire le origini dati
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 1%

---

# Gestire i  [!UICONTROL Data Sources] {#manage-data-sources}

## Creare un [!UICONTROL Data Source] {#create-data-source}

Per creare un nuovo [!UICONTROL data source], vai a **[!UICONTROL Audience Data > Data Sources > Add New]** e completa i passaggi per ciascuna sezione qui descritta. Le autorizzazioni di amministratore sono necessarie per creare un [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Consulta [Impostazioni origine dati e opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options) descrizioni di questi diversi controlli.

## [!UICONTROL Data Source] Dettagli {#details}

Per completare la [!UICONTROL Data Source Details] sezione:

1. Denomina il [!UICONTROL data source].
1. *(Facoltativo)* Descrivi la [!UICONTROL data source]. Una descrizione concisa consente di definire il ruolo o lo scopo del [!UICONTROL data source].
1. Fornisci un [!UICONTROL integration code]. Generalmente, [!UICONTROL integration codes] sono facoltativi. Sono necessarie quando si desidera:

   * [Creare un’origine dati per più dispositivi](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilizza il [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Utilizzare [Regole di unione profili](../features/profile-merge-rules/merge-rules-start.md).

1. Scegli un **[!UICONTROL ID Type]**. [!UICONTROL ID Type] le opzioni includono:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Necessario per creare un [!UICONTROL Profile Merge Rule]). Nota: per alcuni clienti, questa selezione espone **[!UICONTROL ID Definition]** opzioni.

   >[!NOTE]
   >
   >Per ogni organizzazione per la quale è stato eseguito il provisioning, ad Audience Manager e Experience Platform, anche se non è stata impostata la condivisione dei segmenti tra le due app, quando si crea un’origine dati cross-device viene visualizzata una [spazio dei nomi delle identità](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) viene creato in Experience Platform.

1. Scegli un **[!UICONTROL ID Definition]** opzione. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Controlli sull’esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a una [!UICONTROL data source] e [!UICONTROL destination]. Ti impediscono di inviare dati a un [!UICONTROL destination] quando tale azione viola un accordo sulla privacy dei dati o sull’uso. Salti questa sezione se non utilizza [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Impostazioni {#settings}

Queste impostazioni determinano come [!UICONTROL data source] viene identificato, utilizzato e condiviso. Puoi anche abilitare la segnalazione di errori per i file di dati in entrata. Per completare la [!UICONTROL Data Source Settings] sezione:

1. Seleziona un [!UICONTROL Data Source Setting] casella di controllo per applicare un&#39;opzione al [!UICONTROL data source].
2. Clic **[!UICONTROL Save]**.

## Eliminare un’origine dati {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminare un [!UICONTROL data source] che non ti serve più.

>[!NOTE]
>
>Si prega di notare le seguenti restrizioni:
>
>* Non è possibile eliminare un [Caratteristiche sincronizzate del pubblico attivo o della sorgente dei dati](../features/traits/client-activity-synced-audience-traits.md).
>* Per i clienti che utilizzano Adobe Analytics: Audience Manager non consente di eliminare le origini dati create automaticamente dal [!DNL Analytics] suite di rapporti. Utilizza il [Servizio core](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) per annullare la mappatura di queste origini dati.


1. Clic **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Selezionare la casella di controllo accanto a una o più origini dati.
È possibile utilizzare [!UICONTROL Search] per individuare le origini dati desiderate se l&#39;elenco è lungo.
1. Clic  ![](assets/icon_trash.png), quindi conferma l’eliminazione.


>[!MORELIKETHIS]
>
>* [Impostazioni origine dati e opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options)

