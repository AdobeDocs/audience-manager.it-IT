---
description: Creare, modificare ed eliminare le caratteristiche della cartella.
keywords: Caratteristica cartella;Caratteristiche cartella;caratteristiche cartella;Folder Trait;folder traits;folder trait
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: Gestisci caratteristiche cartella
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 5%

---

# Gestisci caratteristiche cartella {#manage-folder-traits}

Creare, modificare ed eliminare le caratteristiche della cartella.

## Creare una caratteristica cartella {#create-folder-trait}

A [!UICONTROL folder trait] viene creato automaticamente quando si crea una nuova cartella nella tassonomia.

<!-- create-folder-trait.xml -->

1. Vai a **[!UICONTROL Audience Data > Traits]** per passare al **Caratteristiche** dashboard.
1. In [!UICONTROL Trait Storage] finestra, passaggio del mouse:

   * Testo &quot;All Traits&quot; (Tutte le caratteristiche) per aggiungere una nuova cartella principale.
   * Cartella padre esistente per aggiungere una nuova cartella subordinata.

   ![](assets/folder_traits_create.PNG)

1. Fai clic sull&#39;icona + per creare la cartella. Puoi creare un massimo di 2.000 cartelle nella tassonomia. Per ulteriori informazioni, consulta la documentazione sui [limiti di utilizzo](../../features/administration/usage-limits.md).
1. Denomina la cartella e fai clic su **Salva**. Ad esempio, una cartella denominata Elettronica avrà una caratteristica cartella denominata &quot;Caratteristica cartella elettronica&quot;. Puoi visualizzare e selezionare la nuova caratteristica della cartella nel dashboard delle caratteristiche.
1. La nuova caratteristica della cartella viene assegnata automaticamente al [!DNL Audience Manager] origine dati generata. I tuoi utenti con i [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) le autorizzazioni di possono modificare l’origine dati nel flusso di lavoro modifica caratteristica cartella. Consulta [Modificare una caratteristica cartella](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Modificare una caratteristica cartella {#edit-folder-trait}

Descrive come modificare un [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. In [!UICONTROL Traits] dashboard, passa il puntatore del mouse sulla **[!UICONTROL Actions]** per la caratteristica della cartella da modificare.
1. Fai clic sulla matita per modificare la caratteristica.

   ![](assets/folder_traits_edit_border.png)

1. Il **[!UICONTROL Edit]** workflow consente di modificare l&#39;origine dati per le caratteristiche della cartella. Seleziona l’origine dati desiderata e fai clic su **[!UICONTROL Save]**. Le origini dati vengono ordinate numericamente in base a [!DNL DPID], nella casella a discesa.

   Se l’azienda utilizza [!UICONTROL Role-Based Access Rights (RBAC)], tu o i tuoi utenti avete bisogno di [autorizzazioni di accesso](../../features/traits/about-folder-traits.md#role-based-access-controls) alle caratteristiche delle origini dati.

>[!NOTE]
>
>Non è possibile rinominare direttamente una caratteristica della cartella. [Rinomina la cartella di archiviazione associata](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) per modificare il nome della caratteristica della cartella.

## Eliminare una caratteristica cartella {#delete-folder-trait}

Elimina una caratteristica della cartella eliminando la cartella di archiviazione a cui appartiene la caratteristica.

<!-- delete-folder-trait.xml -->

1. **Dati pubblico > Caratteristiche** per passare al **Caratteristiche** dashboard.
1. In [!UICONTROL Trait Storage] eliminare una cartella passando con il mouse sopra di essa e facendo clic sull&#39;icona X.

   ![Risultato passaggio](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Non puoi eliminare una caratteristica di cartella se viene utilizzata in un’espressione di segmento. Accedi a [vista caratteristica](../../features/traits/trait-details-page.md) per vedere quali segmenti utilizzano la caratteristica cartella. Fai clic sul nome del segmento per aprire [visualizzazione riepilogo segmenti](../../features/segments/segment-summary-view.md), che consente di rimuovere le caratteristiche dalle espressioni di segmento.
