---
description: Questa procedura descrive i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-description: Questa procedura descrive i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-title: Gestire i gruppi di test
solution: Audience Manager
title: Gestire i gruppi di test
uuid: 2 fadddeb -7574-4853-8 c 52-c 58456582 c 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Test Groups {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Create Segment Test Groups {#create-test-groups}

### Prerequisiti

<!-- create-test-group.xml -->

* You need to have at least one **conversion trait** set up. You can set up conversion traits in the [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md), by selecting **conversion** as the event type. For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[Le caratteristiche](../../features/traits/about-folder-traits.md) della cartella **non sono supportate** da [!UICONTROL Audience Lab]. Setting the [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait.

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. Questa autorizzazione consente all'utente di creare e visualizzare i risultati di un test. A user will only be able to use segments from a data source they have **read** and **map to destination** privileges for. The user will only be able to use conversion traits from a data source for which they have **"read"** permissions. Un utente può solo visualizzare le destinazioni a cui hanno accesso. So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has:
   * accesso per leggere le caratteristiche di conversione rilevanti;
   * accesso per leggere e mappare segmenti rilevanti per i test;
   * accesso alle destinazioni pertinenti.

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**.
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * Potete salvare il gruppo di test come bozza e riprendere il lavoro su di esso in un secondo momento.
   * Un avviso viene visualizzato nel caso in cui il segmento di base selezionato sia già utilizzato in altri gruppi di test. L'utilizzo di due volte il segmento di base può distorcere i risultati di conversione per entrambi i test.

1. **[!UICONTROL Allocate Test Segments]**

   * You can create **up to 15 test segments** and divide the percentage of devices as you wish.
   * Potete modificare il nome dei segmenti di prova facendo clic su di essi.
   * Le percentuali si dividono automaticamente a 100% quando vengono allocati nuovi segmenti di test. Potete quindi modificare manualmente le percentuali. Fate clic sulla casella di controllo dopo aver modificato le percentuali e assicuratevi che aggiungano fino a 100%; in caso contrario non potrete passare al passaggio successivo.

1. **[!UICONTROL Set a Control Segment]**

   * Seleziona un segmento di controllo se vuoi impostare una parte del segmento da usare come gruppo di controllo. I gruppi di controllo consentono di visualizzare l'impatto dei segmenti di prova creati rispetto a un benchmark.
   * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control.
   * Click **[!UICONTROL Next]** when you're done.

1. **[!UICONTROL Select Conversion Traits]**

   * Aggiungete le caratteristiche di conversione digitando nella finestra delle caratteristiche di conversione. This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait.
   * Se desiderato, potete aggiungere fino a 5 caratteristiche di conversione.
   * Se selezionate un trait di conversione già utilizzato per altri gruppi di test, verrà visualizzato un avviso.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digitate le destinazioni desiderate nel campo di ricerca o utilizzate la freccia a discesa. [!UICONTROL Audience Lab] i segmenti di prova possono essere inviati a destinazioni di URL, cookie o server-to-server.
   * Trascina i segmenti in destinazioni.
   * After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind.
   * Puoi inviare lo stesso segmento di test a più destinazioni e puoi aggiungere più segmenti di test a una singola destinazione.
   * Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../features/data-export-controls.md).
   * Users will only see the destinations they have access to based on the [RBAC User Group](../../features/administration/administration-overview.md) they belong to.
   * Infine, devi selezionare una data di inizio per il gruppo di test. Questa data indica l'inizio del periodo in cui verrà pubblicato il gruppo di test sulle destinazioni. Select **No End Date** for an indefinite comparison of the test segments.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un profilo autenticato sono supportati solo nelle destinazioni in tempo reale. Se un segmento di test con una regola di unione profilo di tale configurazione viene inviato a una destinazione server-to-server basata su file, l'audience potrebbe non essere compilata.

   Click **[!UICONTROL Next]** to review and finalize your test group.

1. **[!UICONTROL Summary & Finalize]**

   * Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.
   * Una volta finalizzato un gruppo di prova, è possibile duplicarlo o eliminarlo, ma non modificarlo.
   >[!NOTE]
   >* Potete salvare i gruppi di test in qualsiasi momento nel processo di creazione e tornare alla procedura guidata in un secondo momento. The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.


## Edit Segment Test Groups {#edit-test-groups}

In [!UICONTROL Audience Lab], you are only able to edit draft test groups. In the [!UICONTROL Create Segment Test Group] wizard, you can save your test group as a draft and resume working on it later.

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard and select **[!UICONTROL Finalize Group]** when you're done.

## Delete Segment Test Groups {#delete-test-groups}

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Individuate il gruppo di test da eliminare. Potete:

   * press the **[!UICONTROL Delete]** control in the test group card, or
   * press the test group title in the test group card to go to the [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) view and press the **[!UICONTROL Delete]** control in the title bar.

1. For [completed test segments](../../features/audience-lab/audience-lab.md#status), an alert will prompt you to download the CSV file to save the reporting if you wish.
