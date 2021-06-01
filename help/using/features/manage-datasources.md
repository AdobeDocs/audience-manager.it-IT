---
description: Per creare una nuova origine dati, vai a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ogni sezione descritta qui. Per creare un’origine dati sono necessarie le autorizzazioni di amministratore.
keywords: origini dati;gestire origine dati;origine dati di audience manager
seo-description: Per creare una nuova origine dati, vai a Audience Data > Origini dati > Aggiungi nuovo e completa i passaggi per ogni sezione descritta qui. Per creare un’origine dati sono necessarie le autorizzazioni di amministratore.
seo-title: Creare una sorgente di dati
solution: Audience Manager
title: Gestisci origini dati
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Sorgenti di dati
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 4%

---

# Gestire i  [!UICONTROL Data Sources]{#manage-data-sources}

## Crea un [!UICONTROL Data Source] {#create-data-source}

Per creare un nuovo [!UICONTROL data source], vai a **[!UICONTROL Audience Data > Data Sources > Add New]** e completa i passaggi per ogni sezione descritta qui. Per creare un [!UICONTROL data source] sono necessarie le autorizzazioni di amministratore.

<!-- create-datasource.xml -->

>[!TIP]
>
>Per la descrizione di questi diversi controlli, consulta [Impostazioni origine dati e Opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options) .

## [!UICONTROL Data Source] Dettagli {#details}

Per completare la sezione [!UICONTROL Data Source Details]:

1. Denomina il simbolo [!UICONTROL data source].
1. *(Facoltativo)* Descrivi il  [!UICONTROL data source]. Una descrizione concisa ti aiuta a definire il ruolo o lo scopo di [!UICONTROL data source].
1. Specifica un [!UICONTROL integration code]. In genere, [!UICONTROL integration codes] è facoltativo. Sono necessari per:

   * [Crea un’origine dati multi-dispositivo](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilizza il [servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html).
   * Lavora con [Regole di unione profili](../features/profile-merge-rules/merge-rules-start.md).

1. Scegli un elemento **[!UICONTROL ID Type]**. [!UICONTROL ID Type] le opzioni includono:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obbligatorio per creare un  [!UICONTROL Profile Merge Rule]). Nota: per alcuni clienti, questa selezione espone le opzioni **[!UICONTROL ID Definition]** .

1. Scegli un&#39;opzione **[!UICONTROL ID Definition]**. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[I ](../features/data-export-controls.md) controlli di esportazione dei dati sono regole di classificazione facoltative applicabili a  [!UICONTROL data source] e  [!UICONTROL destination]. Ti impediscono di inviare dati a un [!UICONTROL destination] quando tale azione viola la privacy dei dati o l’accordo sull’utilizzo. Ignora questa sezione se non utilizzi [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Impostazioni {#settings}

Queste impostazioni determinano il modo in cui un [!UICONTROL data source] viene identificato, utilizzato e condiviso. È inoltre possibile abilitare la generazione di rapporti sugli errori per i file di dati in entrata. Per completare la sezione [!UICONTROL Data Source Settings]:

1. Seleziona una casella di controllo [!UICONTROL Data Source Setting] per applicare un&#39;opzione al tuo [!UICONTROL data source].
2. Clic **[!UICONTROL Save]**.

## Eliminare un&#39;origine dati {#delete-data-source}

<!-- t_datasource_delete.xml -->

Elimina un elemento [!UICONTROL data source] non più necessario.

>[!NOTE]
>
>Si prega di notare le seguenti restrizioni:
>
>* Non è possibile eliminare un [Pubblico attivo o una caratteristica sincronizzata dell&#39;origine dati](../features/traits/client-activity-synced-audience-traits.md).
>* Per i clienti che utilizzano Adobe Analytics: Audience Manager non consente di eliminare le origini dati create automaticamente dalle suite di rapporti [!DNL Analytics]. Utilizza il [Servizio di base](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) per annullare la mappatura di queste origini dati.


1. Clic **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Seleziona la casella di controllo accanto a una o più origini dati.
È possibile utilizzare la casella [!UICONTROL Search] per individuare le origini dati desiderate se si dispone di un elenco lungo.
1. Fai clic su ![](assets/icon_trash.png), quindi conferma l’eliminazione.


>[!MORELIKETHIS]
>
>* [Impostazioni origine dati e opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options)

