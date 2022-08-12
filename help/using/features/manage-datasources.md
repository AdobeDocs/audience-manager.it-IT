---
description: Per creare una nuova origine dati, vai a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ogni sezione descritta qui. Per creare un’origine dati sono necessarie le autorizzazioni di amministratore.
keywords: origini dati;gestire origine dati;origine dati di audience manager
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Gestisci origini dati
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 1%

---

# Gestire i  [!UICONTROL Data Sources] {#manage-data-sources}

## Crea un [!UICONTROL Data Source] {#create-data-source}

Per creare una nuova [!UICONTROL data source], vai a **[!UICONTROL Audience Data > Data Sources > Add New]** e completa i passaggi descritti qui. Per creare un [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Vedi [Impostazioni origine dati e opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options) per la descrizione di questi diversi controlli.

## [!UICONTROL Data Source] Dettagli {#details}

Per completare la [!UICONTROL Data Source Details] sezione:

1. Assegna un nome al [!UICONTROL data source].
1. *(Facoltativo)* Descrivi le [!UICONTROL data source]. Una descrizione concisa ti aiuta a definire il ruolo o lo scopo del [!UICONTROL data source].
1. Fornisci un [!UICONTROL integration code]. In generale, [!UICONTROL integration codes] sono facoltativi. Sono necessari per:

   * [Creare un’origine dati multi-dispositivo](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilizza la [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Utilizzare [Regole di unione profili](../features/profile-merge-rules/merge-rules-start.md).

1. Scegli un **[!UICONTROL ID Type]**. [!UICONTROL ID Type] le opzioni includono:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Necessario per creare un [!UICONTROL Profile Merge Rule]). Nota: per alcuni clienti, questa selezione espone il **[!UICONTROL ID Definition]** opzioni.

   >[!NOTE]
   >
   >Per ogni organizzazione per la quale è stato eseguito il provisioning, ad Audience Manager e Experience Platform, anche se non è stata impostata la condivisione dei segmenti tra le due app, quando crei un’origine dati multi-dispositivo, una [spazio dei nomi identità](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) viene creato in Experience Platform.

1. Scegli un **[!UICONTROL ID Definition]** opzione . Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Controlli sull&#39;esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative applicabili a un [!UICONTROL data source] e [!UICONTROL destination]. Ti impediscono di inviare dati a un [!UICONTROL destination] quando tale azione viola la privacy dei dati o l&#39;accordo sull&#39;utilizzo. Ignora questa sezione se non utilizzi [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Impostazioni {#settings}

Queste impostazioni determinano come [!UICONTROL data source] è identificato, utilizzato e condiviso. È inoltre possibile abilitare la generazione di rapporti sugli errori per i file di dati in entrata. Per completare la [!UICONTROL Data Source Settings] sezione:

1. Seleziona una [!UICONTROL Data Source Setting] casella di controllo per applicare un&#39;opzione al [!UICONTROL data source].
2. Clic **[!UICONTROL Save]**.

## Eliminare un’origine dati {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminare un [!UICONTROL data source] di cui non hai più bisogno.

>[!NOTE]
>
>Si prega di notare le seguenti restrizioni:
>
>* Non è possibile eliminare un [Pubblico attivo o caratteristica sincronizzata con origine dati](../features/traits/client-activity-synced-audience-traits.md).
>* Per i clienti che utilizzano Adobe Analytics: Audience Manager non consente di eliminare le origini dati create automaticamente dal [!DNL Analytics] suite di rapporti. Utilizza la [Servizio core](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) per annullare la mappatura di queste origini dati.


1. Clic **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Seleziona la casella di controllo accanto a una o più origini dati.
È possibile utilizzare [!UICONTROL Search] per individuare le origini dati desiderate se si dispone di un elenco lungo.
1. Fai clic su  ![](assets/icon_trash.png), quindi conferma l’eliminazione.


>[!MORELIKETHIS]
>
>* [Impostazioni origine dati e opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options)

