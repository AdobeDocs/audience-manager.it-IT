---
description: Creare, modificare ed eliminare le caratteristiche delle cartelle.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Creare, modificare ed eliminare le caratteristiche delle cartelle.
seo-title: Gestisci caratteristiche cartella
solution: Audience Manager
title: Gestisci caratteristiche cartella
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: 4ea5ba4ebd8cd4c13c99c8272f4b5733ab5fa125
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 9%

---


# Gestisci caratteristiche cartella {#manage-folder-traits}

Creare, modificare ed eliminare le caratteristiche delle cartelle.

## Crea una caratteristica cartella {#create-folder-trait}

Un [!UICONTROL folder trait] viene creato automaticamente quando create una nuova cartella nella tassonomia.

<!-- create-folder-trait.xml -->

1. Andate a **[!UICONTROL Audience Data > Traits]** per passare al dashboard **Caratteristiche**.
1. Nella finestra [!UICONTROL Trait Storage], passate il puntatore del mouse sopra:

   * Testo &quot;Tutte le caratteristiche&quot; per aggiungere una nuova cartella di livello principale.
   * Una cartella principale esistente per aggiungere una nuova cartella subordinata.

   ![](assets/folder_traits_create.PNG)

1. Fai clic sull&#39;icona + per creare la cartella. Puoi creare fino a un massimo di 2.000 cartelle nella tassonomia. Per ulteriori informazioni, consulta la documentazione sui [limiti di utilizzo](../../features/administration/usage-limits.md).
1. Assegnate un nome alla cartella e fate clic su **Salva**. Ad esempio, una cartella denominata Electronics avrà una caratteristica cartella denominata &#39;Caratteristiche cartella elettronica&#39;. Potete visualizzare e selezionare la nuova caratteristica della cartella nel dashboard delle caratteristiche.
1. La nuova caratteristica della cartella viene assegnata automaticamente all&#39;origine dati generata [!DNL Audience Manager]. Gli utenti con autorizzazioni [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) appropriate possono modificare l&#39;origine dati nel flusso di lavoro di modifica delle caratteristiche della cartella. Vedere [Modifica di una caratteristica cartella](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Modifica di una caratteristica cartella {#edit-folder-trait}

Descrive come modificare un [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. Nel dashboard di [!UICONTROL Traits], passate il puntatore del mouse sulla colonna **[!UICONTROL Actions]** relativa alla caratteristica della cartella da modificare.
1. Fate clic sulla matita per modificare la caratteristica.

   ![](assets/folder_traits_edit_border.png)

1. Il flusso di lavoro **[!UICONTROL Edit]** consente di modificare l&#39;origine dati per le caratteristiche delle cartelle. Selezionare l&#39;origine dati desiderata e fare clic su **[!UICONTROL Save]**. Le origini dati sono ordinate numericamente, per [!DNL DPID], nella casella a discesa.

   Se l&#39;azienda utilizza [!UICONTROL Role-Based Access Rights (RBAC)], l&#39;utente o gli utenti devono disporre di [autorizzazioni di accesso](../../features/traits/about-folder-traits.md#role-based-access-controls) per le origini dati delle caratteristiche.

>[!NOTE]
>
>Non è possibile rinominare direttamente una caratteristica della cartella. [Rinominare la ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) cartella di memorizzazione associata per modificare il nome della caratteristica della cartella.

## Eliminare una caratteristica cartella {#delete-folder-trait}

Eliminate una caratteristica della cartella eliminando la cartella di memorizzazione a cui appartiene la caratteristica.

<!-- delete-folder-trait.xml -->

1. **Audience Data >** Caratteristiche per passare alla dashboard  **** Caratteristiche.
1. Nella finestra [!UICONTROL Trait Storage], eliminate una cartella posizionando il puntatore del mouse sopra di essa e facendo clic sull&#39;icona X.

   ![Risultato del passaggio](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Non è possibile eliminare una caratteristica cartella, se utilizzata in un&#39;espressione di segmento. Andate alla sezione [Trait view](../../features/traits/trait-details-page.md) per vedere quali segmenti utilizzano la caratteristica della cartella. Quindi, fate clic sul nome del segmento per aprire la [visualizzazione di riepilogo del segmento](../../features/segments/segment-summary-view.md), che consente di rimuovere caratteristiche dalle espressioni del segmento.
