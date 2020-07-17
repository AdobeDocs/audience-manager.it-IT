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
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 9%

---


# Gestisci caratteristiche cartella {#manage-folder-traits}

Creare, modificare ed eliminare le caratteristiche delle cartelle.

## Creare una caratteristica cartella {#create-folder-trait}

Una cartella [!UICONTROL folder trait] viene creata automaticamente quando create una nuova cartella nella tassonomia.

<!-- create-folder-trait.xml -->

1. Vai **[!UICONTROL Audience Data > Traits]** a per passare al dashboard **Caratteristiche** .
1. Nella [!UICONTROL Trait Storage] finestra, passate il mouse sopra:

   * Testo &quot;Tutte le caratteristiche&quot; per aggiungere una nuova cartella di livello principale.
   * Una cartella principale esistente per aggiungere una nuova cartella subordinata.

   ![](assets/folder_traits_create.PNG)

1. Fai clic sull&#39;icona + per creare la cartella. Puoi creare fino a un massimo di 2.000 cartelle nella tassonomia. Per ulteriori informazioni, consulta la documentazione sui [limiti di utilizzo](../../features/administration/usage-limits.md).
1. Assegnate un nome alla cartella e fate clic su **Salva**. Ad esempio, una cartella denominata Electronics avrà una caratteristica cartella denominata &#39;Caratteristiche cartella elettronica&#39;. Potete visualizzare e selezionare la nuova caratteristica della cartella nel dashboard delle caratteristiche.
1. La nuova caratteristica della cartella viene assegnata automaticamente all&#39;origine dati [!DNL Audience Manager] generata. Gli utenti con autorizzazioni [!UICONTROL Role-Based Access Control ([!DNL RBAC])] appropriate possono modificare l&#39;origine dati nel flusso di lavoro di modifica delle caratteristiche della cartella. Consultate [Modificare una caratteristica](../../features/traits/manage-folder-traits.md#edit-folder-trait)della cartella.

## Modifica di una caratteristica cartella {#edit-folder-trait}

Descrive come modificare un [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. Nel [!UICONTROL Traits] dashboard, passate il mouse sulla **[!UICONTROL Actions]** colonna relativa alla caratteristica della cartella da modificare.
1. Fate clic sulla matita per modificare la caratteristica.

   ![](assets/folder_traits_edit_border.png)

1. Il **[!UICONTROL Edit]** flusso di lavoro consente di modificare l’origine dati per le caratteristiche della cartella. Seleziona l&#39;origine dati desiderata e fai clic su **[!UICONTROL Save]**. Le origini dati sono ordinate numericamente, per [!DNL DPID], nella casella a discesa.

   Se la tua azienda utilizza [!UICONTROL Role-Based Access Rights (RBAC)], tu o i tuoi utenti devi avere [le autorizzazioni](../../features/traits/about-folder-traits.md#role-based-access-controls) di accesso alle origini dati delle caratteristiche.

>[!NOTE]
>
>Non è possibile rinominare direttamente una caratteristica della cartella. [Rinominare la cartella](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) di archiviazione associata per modificare il nome della caratteristica della cartella.

## Eliminare una caratteristica cartella {#delete-folder-trait}

Eliminate una caratteristica della cartella eliminando la cartella di memorizzazione a cui appartiene la caratteristica.

<!-- delete-folder-trait.xml -->

1. **Dati audience > Caratteristiche** per passare al dashboard **Caratteristiche** .
1. Nella [!UICONTROL Trait Storage] finestra, eliminate una cartella posizionando il puntatore del mouse sopra di essa e facendo clic sull’icona X.

   ![Risultato del passaggio](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Non è possibile eliminare una caratteristica cartella, se utilizzata in un&#39;espressione di segmento. Andate alla sezione della vista [delle](../../features/traits/trait-details-page.md) caratteristiche per vedere quali segmenti utilizzano le caratteristiche della cartella. Quindi, fate clic sul nome del segmento per aprire la visualizzazione [di riepilogo del](../../features/segments/segment-summary-view.md)segmento, che consente di rimuovere le caratteristiche dalle espressioni del segmento.