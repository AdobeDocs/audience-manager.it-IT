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
source-git-commit: bda66cb9aaee3a40ae64dda100f42b88696a027e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# Gestisci [!UICONTROL Data Sources] {#manage-data-sources}

## Crea un [!UICONTROL Data Source] {#create-data-source}

Per creare un nuovo [!UICONTROL data source], vai a **[!UICONTROL Audience Data > Data Sources > Add New]** e completa i passaggi per ogni sezione qui descritta. Per creare [!UICONTROL data source] sono necessarie le autorizzazioni di amministratore.

<!-- create-datasource.xml -->

>[!TIP]
>
>Per le descrizioni dei diversi controlli, vedere [Impostazioni e opzioni di menu di Data Source](../features/datasources-list-and-settings.md#settings-menu-options).

## Dettagli di [!UICONTROL Data Source] {#details}

Per completare la sezione [!UICONTROL Data Source Details], compilare i campi seguenti:

1. **[!UICONTROL Name]**: specificare un nome per l&#39;origine dati.
1. **[!UICONTROL Description]** (facoltativo): immettere una descrizione per l&#39;origine dati per definire il ruolo o lo scopo dell&#39;origine dati.
1. **[!UICONTROL Integration Code]** (facoltativo): immettere un codice di integrazione. Questi codici sono necessari quando si desidera:
   * [Crea un&#39;origine dati multi-dispositivo](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilizza il [servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).
   * Utilizzare [Regole di unione profili](../features/profile-merge-rules/merge-rules-start.md).
1. **[!UICONTROL Namespace]** (sola lettura): questo campo è di sola lettura e viene generato automaticamente quando si salva l&#39;origine dati. Se si desidera esportare segmenti da Audience Manager a Experience Platform, è necessario creare uno spazio dei nomi [identità](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=it#manage-namespaces) corrispondente in Experience Platform, utilizzando il valore generato automaticamente come spazio dei nomi [simbolo di identità](https://experienceleague.adobe.com/it/docs/experience-platform/identity/features/namespaces#components-of-a-namespace) in Experience Platform.
1. **[!UICONTROL ID Type]**: selezionare il tipo di ID che l&#39;origine dati conterrà:
   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (necessario per creare [!UICONTROL Profile Merge Rule]). Per alcuni clienti, questa selezione espone le opzioni **[!UICONTROL ID Definition]**.
1. Scegliere un&#39;opzione **[!UICONTROL ID Definition]**. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[I controlli sull&#39;esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative che è possibile applicare a [!UICONTROL data source] e [!UICONTROL destination]. Impediscono l&#39;invio di dati a [!UICONTROL destination] quando tale azione viola un accordo sulla privacy dei dati o sull&#39;utilizzo. Ignorare questa sezione se non si utilizza [!UICONTROL Data Export Controls].

## Impostazioni [!UICONTROL Data Source] {#settings}

Queste impostazioni determinano come un [!UICONTROL data source] viene identificato, utilizzato e condiviso. Puoi anche abilitare la segnalazione di errori per i file di dati in entrata. Per completare la sezione [!UICONTROL Data Source Settings]:

1. Selezionare una casella di controllo [!UICONTROL Data Source Setting] per applicare un&#39;opzione a [!UICONTROL data source].
2. Fare clic su **[!UICONTROL Save]**.

## Eliminare un Source dati {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminare un [!UICONTROL data source] non più necessario.

>[!NOTE]
>
>Si prega di notare le seguenti restrizioni:
>
>* Non puoi eliminare un [pubblico attivo o una caratteristica sincronizzata di Data Source](../features/traits/client-activity-synced-audience-traits.md).
>* Per i clienti che utilizzano Adobe Analytics: Audience Manager non consente di eliminare le origini dati create automaticamente dalle suite di rapporti [!DNL Analytics]. Utilizza il [servizio core](https://experienceleague.adobe.com/it/docs/core-services/interface/services/customer-attributes/attributes) per annullare la mappatura di queste origini dati.

1. Fare clic su **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Selezionare la casella di controllo accanto a una o più origini dati.
Se l&#39;elenco è lungo, è possibile utilizzare la casella [!UICONTROL Search] per individuare le origini dati desiderate.
1. Fai clic su ![](assets/icon_trash.png), quindi conferma l&#39;eliminazione.


>[!MORELIKETHIS]
>
>* [Impostazioni e opzioni di menu di Data Source](../features/datasources-list-and-settings.md#settings-menu-options)
