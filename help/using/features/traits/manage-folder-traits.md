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


# Gestisci caratteristiche cartella {#manage-folder-traits}

Create, modificate ed eliminate le caratteristiche delle cartelle.

## Creare una caratteristica cartella {#create-folder-trait}

Viene [!UICONTROL folder trait] creata automaticamente quando si crea una nuova cartella nella tassonomia.

<!-- create-folder-trait.xml -->

1. Passate alla **[!UICONTROL Audience Data > Traits]** dashboard **Caratteristiche** .
1. Nella [!UICONTROL Trait Storage] finestra, passate il mouse su:

   * Testo «Tutte le caratteristiche» per aggiungere una nuova cartella livello principale.
   * Una cartella principale esistente per aggiungere una nuova cartella subordinata.
   ![](assets/folder_traits_create.PNG)

1. Fai clic sull&#39;icona + per creare la cartella. Puoi creare fino a un massimo di 2.000 cartelle nella tassonomia. Per ulteriori informazioni, consulta la documentazione sui [limiti di utilizzo](../../features/administration/usage-limits.md).
1. Denominate la cartella e fate clic **su Salva**. Ad esempio, una cartella denominata Electronics dispone di una caratteristica di cartella denominatà Electronics Folder Trait &#39;(Caratteristiche cartella elettronica). Potete visualizzare e selezionare la nuova caratteristica di cartella nella dashboard delle caratteristiche.
1. La nuova caratteristica di cartella viene assegnata automaticamente all&#39;origine dati [!DNL Audience Manager] generata. I vostri utenti [! Le autorizzazioni di controllo del ruolo ([!DNL RBAC]) di UICONTROL possono cambiare l&#39;origine dati nel flusso di lavoro delle caratteristiche della cartella modifica. Consultate [Modificare una caratteristica cartella](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Modificare una caratteristica di una cartella {#edit-folder-trait}

Descrive la modalità di modifica di un [!UICONTROL folder trait]file.

<!-- edit-folder-trait.xml -->

1. Nel [!UICONTROL Traits] dashboard, passate il mouse sulla **[!UICONTROL Actions]** colonna per la caratteristica di cartella che desiderate modificare.
1. Fate clic sulla matita per modificare la caratteristica.

   ![](assets/folder_traits_edit_border.png)

1. Il **[!UICONTROL Edit]** flusso di lavoro consente di modificare l&#39;origine dati per le caratteristiche delle cartelle. Selezionate l&#39;origine dati desiderata e fate clic **[!UICONTROL Save]** su. Le origini dati sono ordinate numericamente, nel [!DNL DPID]riquadro a discesa.

   Se la tua azienda utilizza [!UICONTROL Role-Based Access Rights (RBAC)], tu o i tuoi utenti avrete bisogno di autorizzazioni [di accesso](../../features/traits/about-folder-traits.md#role-based-access-controls) per le caratteristiche delle caratteristiche.

>[!NOTE]
>
>Non è possibile rinominare direttamente una caratteristica di cartella. [Rinominate la cartella di memorizzazione associata](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) per cambiare il nome della caratteristica della cartella.

## Eliminare una caratteristica cartella {#delete-folder-trait}

Eliminate una caratteristica di una cartella eliminando la cartella di archiviazione a cui appartiene.

<!-- delete-folder-trait.xml -->

1. **Audience Data &gt; Traits** (Caratteristiche) per passare al **dashboard Caratteristiche** .
1. Nella [!UICONTROL Trait Storage] finestra, eliminate una cartella posizionandola sopra di essa e facendo clic sull&#39;icona X.

   ![Risultato passaggio](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Non potete eliminare una caratteristica di una cartella, se utilizzata in un&#39;espressione di segmento. Passa alla [sezione di visualizzazione](../../features/traits/trait-details-page.md) delle caratteristiche per vedere quali segmenti usano la caratteristica della cartella. Quindi, fai clic sul nome del segmento per aprire la [visualizzazione di riepilogo dei segmenti](../../features/segments/segment-summary-view.md), che consente di rimuovere le caratteristiche dalle espressioni dei segmenti.