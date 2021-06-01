---
description: Creare, modificare ed eliminare le caratteristiche della cartella.
keywords: Caratteristiche cartella;Caratteristiche cartella;caratteristiche cartella;caratteristiche cartella;caratteristica cartella
seo-description: Creare, modificare ed eliminare le caratteristiche della cartella.
seo-title: Gestisci caratteristiche cartella
solution: Audience Manager
title: Gestisci caratteristiche cartella
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: 'Caratteristiche '
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 9%

---

# Gestisci caratteristiche cartella {#manage-folder-traits}

Creare, modificare ed eliminare le caratteristiche della cartella.

## Creare una caratteristica cartella {#create-folder-trait}

Una [!UICONTROL folder trait] viene creata automaticamente quando crei una nuova cartella nella tassonomia.

<!-- create-folder-trait.xml -->

1. Vai a **[!UICONTROL Audience Data > Traits]** per passare al dashboard **Caratteristiche**.
1. Nella finestra [!UICONTROL Trait Storage], passa il puntatore del mouse su:

   * Testo &quot;Tutte le caratteristiche&quot; per aggiungere una nuova cartella a livello principale.
   * Una cartella padre esistente per aggiungere una nuova cartella subordinata.

   ![](assets/folder_traits_create.PNG)

1. Fai clic sull&#39;icona + per creare la cartella. Puoi creare fino a un massimo di 2.000 cartelle nella tassonomia. Per ulteriori informazioni, consulta la documentazione sui [limiti di utilizzo](../../features/administration/usage-limits.md).
1. Denomina la cartella e fai clic su **Salva**. Ad esempio, una cartella denominata Elettronica avrà una caratteristica cartella denominata &quot;Caratteristiche cartella elettronica&quot;. Puoi visualizzare e selezionare la nuova caratteristica della cartella nel dashboard delle caratteristiche.
1. La nuova caratteristica della cartella viene assegnata automaticamente all&#39;origine dati generata [!DNL Audience Manager]. Gli utenti con le autorizzazioni [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) appropriate possono modificare l&#39;origine dati nel flusso di lavoro modifica caratteristiche cartella. Consulta [Modificare una caratteristica di una cartella](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Modificare una caratteristica cartella {#edit-folder-trait}

Descrive come modificare un [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. Nel dashboard [!UICONTROL Traits], passa il cursore del mouse sulla colonna **[!UICONTROL Actions]** relativa alla caratteristica della cartella da modificare.
1. Fai clic sulla matita per modificare la caratteristica.

   ![](assets/folder_traits_edit_border.png)

1. Il flusso di lavoro **[!UICONTROL Edit]** ti consente di modificare l’origine dati per le caratteristiche della cartella. Seleziona l’origine dati desiderata e fai clic su **[!UICONTROL Save]**. Le origini dati sono ordinate numericamente, in base a [!DNL DPID], nella casella a discesa.

   Se la tua azienda utilizza [!UICONTROL Role-Based Access Rights (RBAC)], o i tuoi utenti devono [accedere alle autorizzazioni](../../features/traits/about-folder-traits.md#role-based-access-controls) per le caratteristiche delle origini dati.

>[!NOTE]
>
>Non è possibile rinominare direttamente una caratteristica della cartella. [Rinomina la ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) cartella di archiviazione associata per modificare il nome della caratteristica della cartella.

## Eliminare una caratteristica cartella {#delete-folder-trait}

Eliminare una caratteristica cartella eliminando la cartella di archiviazione a cui appartiene la caratteristica.

<!-- delete-folder-trait.xml -->

1. **Dati del pubblico >** Caratteristiche per passare alla dashboard  **** Caratteristiche.
1. Nella finestra [!UICONTROL Trait Storage], elimina una cartella passando con il mouse sopra di essa e facendo clic sull&#39;icona X.

   ![Risultato del passaggio](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Non è possibile eliminare una caratteristica della cartella se viene utilizzata in un’espressione di segmento. Passa alla sezione [visualizzazione caratteristiche](../../features/traits/trait-details-page.md) per vedere quali segmenti utilizzano le caratteristiche della cartella. Quindi, fai clic sul nome del segmento per aprire la [visualizzazione di riepilogo dei segmenti](../../features/segments/segment-summary-view.md), che ti consente di rimuovere caratteristiche dalle espressioni dei segmenti.
