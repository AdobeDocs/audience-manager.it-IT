---
description: Create, modificate ed eliminate le caratteristiche delle cartelle.
keywords: Caratteristica cartella; Caratteristiche cartella; caratteristiche della cartella; caratteristica cartella
seo-description: Create, modificate ed eliminate le caratteristiche delle cartelle.
seo-title: Gestisci caratteristiche cartella
solution: Audience Manager
title: Gestisci caratteristiche cartella
uuid: 287 ac 280-bd 58-4985-85 bd-b 6501 eb 64 b 7 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Folder Traits {#manage-folder-traits}

Create, modificate ed eliminate le caratteristiche delle cartelle.

## Create a Folder Trait {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. In the [!UICONTROL Trait Storage] window, hover over:

   * Testo «Tutte le caratteristiche» per aggiungere una nuova cartella livello principale.
   * Una cartella principale esistente per aggiungere una nuova cartella subordinata.
   ![](assets/folder_traits_create.PNG)

1. Fai clic sull'icona + per creare la cartella. Puoi creare fino a un massimo di 2.000 cartelle nella tassonomia. Per ulteriori informazioni, consulta la documentazione sui [limiti di utilizzo](../../features/administration/usage-limits.md).
1. Name the folder and click **Save**. Ad esempio, una cartella denominata Electronics dispone di una caratteristica di cartella denominatà Electronics Folder Trait '(Caratteristiche cartella elettronica). Potete visualizzare e selezionare la nuova caratteristica di cartella nella dashboard delle caratteristiche.
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control ([!DNL RBAC])] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Edit a Folder Trait {#edit-folder-trait}

Describes how you can edit a [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the folder trait you want to edit.
1. Fate clic sulla matita per modificare la caratteristica.

   ![](assets/folder_traits_edit_border.png)

1. The **[!UICONTROL Edit]** workflow allows you to change the data source for folder traits. Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by [!DNL DPID], in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>Non è possibile rinominare direttamente una caratteristica di cartella. [Rinominate la cartella di memorizzazione associata](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) per cambiare il nome della caratteristica della cartella.

## Delete a Folder Trait {#delete-folder-trait}

Eliminate una caratteristica di una cartella eliminando la cartella di archiviazione a cui appartiene.

<!-- delete-folder-trait.xml -->

1. **Audience Data &gt; Traits** (Caratteristiche) per passare al **dashboard Caratteristiche** .
1. In the [!UICONTROL Trait Storage] window, delete a folder by hovering over it and clicking the X icon.

   ![Risultato passaggio](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Non potete eliminare una caratteristica di una cartella, se utilizzata in un'espressione di segmento. Navigate to the [trait view](../../features/traits/trait-details-page.md) section to see which segments use the folder trait. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md), which allows you to remove traits from segment expressions.