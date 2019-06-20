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


# Gestire i gruppi di test {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Crea gruppi di test segmenti {#create-test-groups}

### Prerequisiti

<!-- create-test-group.xml -->

* Devi avere almeno una **serie di caratteristiche** di conversione. Potete configurare le caratteristiche di conversione nel Generatore [](../../features/traits/create-onboarded-rule-based-traits.md)di caratteristiche, selezionando **la conversione** come tipo di evento. Per ulteriori informazioni sulle caratteristiche di conversione e su come impostarle, abbiamo preparato [un video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) per voi.

   >[!IMPORTANT]
   >
   >[Le caratteristiche](../../features/traits/about-folder-traits.md) della cartella **non sono supportate** da [!UICONTROL Audience Lab]. Se si imposta il tipo [Evento](../../features/traits/create-onboarded-rule-based-traits.md) di una caratteristica di cartella su **conversione** , non vengono generati dati per [!UICONTROL Audience Lab] quella caratteristica specifica della cartella.

* Per le aziende che usano [il controllo accesso basato su ruolo](../../features/administration/administration-overview.md): Assegnate l&#39;autorizzazione [!UICONTROL Audience Lab][jolly](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** cui fornire l&#39;accesso. Questa autorizzazione consente all&#39;utente di creare e visualizzare i risultati di un test. Un utente può essere in grado di utilizzare solo i segmenti di un&#39;origine dati **che hanno letto** e **mappare sui** privilegi di destinazione. L&#39;utente può essere in grado di utilizzare solo caratteristiche di conversione da un&#39;origine dati per cui dispone **di autorizzazioni &quot;leggere&quot;** . Un utente può solo visualizzare le destinazioni a cui hanno accesso. Quindi, prima di aggiungere l&#39;autorizzazione [!DNL Audience Lab] jolly a un gruppo, assicuratevi che il gruppo sia:
   * accesso per leggere le caratteristiche di conversione rilevanti;
   * accesso per leggere e mappare segmenti rilevanti per i test;
   * accesso alle destinazioni pertinenti.

Per creare una nuova [!UICONTROL Segment Test Group]:

1. Selezionate **[!UICONTROL Create New Test Group]** nel [!UICONTROL Audience Lab] dashboard per avviare la procedura guidata.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Compila a e **[!UICONTROL Test Group Name]****[!UICONTROL Description]** a.
   * Scegliete se **[!UICONTROL Base Segment]** navigare nel browser file o digitando nella barra di ricerca, premendo premendo **[!UICONTROL Choose Segment.]**
   * Potete salvare il gruppo di test come bozza e riprendere il lavoro su di esso in un secondo momento.
   * Un avviso viene visualizzato nel caso in cui il segmento di base selezionato sia già utilizzato in altri gruppi di test. L&#39;utilizzo di due volte il segmento di base può distorcere i risultati di conversione per entrambi i test.

1. **[!UICONTROL Allocate Test Segments]**

   * Puoi creare **fino a 15 segmenti di test** e dividere la percentuale di dispositivi come desideri.
   * Potete modificare il nome dei segmenti di prova facendo clic su di essi.
   * Le percentuali si dividono automaticamente a 100% quando vengono allocati nuovi segmenti di test. Potete quindi modificare manualmente le percentuali. Fate clic sulla casella di controllo dopo aver modificato le percentuali e assicuratevi che aggiungano fino a 100%; in caso contrario non potrete passare al passaggio successivo.

1. **[!UICONTROL Set a Control Segment]**

   * Seleziona un segmento di controllo se vuoi impostare una parte del segmento da usare come gruppo di controllo. I gruppi di controllo consentono di visualizzare l&#39;impatto dei segmenti di prova creati rispetto a un benchmark.
   * Puoi selezionare un segmento di test come segmento di controllo nell&#39;elenco a discesa oppure scegliere **[!UICONTROL None]** per nessun controllo.
   * Fate clic **[!UICONTROL Next]** al termine.

1. **[!UICONTROL Select Conversion Traits]**

   * Aggiungete le caratteristiche di conversione digitando nella finestra delle caratteristiche di conversione. Questo passaggio **è obbligatorio** e non potete passare al passaggio successivo, a meno che non aggiungiate almeno un trait di conversione.
   * Se desiderato, potete aggiungere fino a 5 caratteristiche di conversione.
   * Se selezionate un trait di conversione già utilizzato per altri gruppi di test, verrà visualizzato un avviso.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digitate le destinazioni desiderate nel campo di ricerca o utilizzate la freccia a discesa. [!UICONTROL Audience Lab] i segmenti di prova possono essere inviati a destinazioni di URL, cookie o server-to-server.
   * Trascina i segmenti in destinazioni.
   * Dopo aver rilasciato un segmento in una destinazione, compila i **[!UICONTROL Destination Mapping Value]** non vedenti.
   * Puoi inviare lo stesso segmento di test a più destinazioni e puoi aggiungere più segmenti di test a una singola destinazione.
   * Le destinazioni sono disabilitate se non sono disponibili per un determinato segmento di test basato su [Controlli esportazione dati](../../features/data-export-controls.md).
   * Gli utenti visualizzeranno solo le destinazioni a cui hanno accesso in base al gruppo [di utenti RBAC a cui](../../features/administration/administration-overview.md) appartengono.
   * Infine, devi selezionare una data di inizio per il gruppo di test. Questa data indica l&#39;inizio del periodo in cui verrà pubblicato il gruppo di test sulle destinazioni. Selezionate **Nessuna data** fine per un confronto indefinito dei segmenti di test.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un profilo autenticato sono supportati solo nelle destinazioni in tempo reale. Se un segmento di test con una regola di unione profilo di tale configurazione viene inviato a una destinazione server-to-server basata su file, l&#39;audience potrebbe non essere compilata.

   Fate clic per **[!UICONTROL Next]** esaminare e finalizzare il gruppo di test.

1. **[!UICONTROL Summary & Finalize]**

   * Esaminate le informazioni aggiunte nei passaggi precedenti e selezionate **[!UICONTROL Finalize Group]**.
   * Una volta finalizzato un gruppo di prova, è possibile duplicarlo o eliminarlo, ma non modificarlo.
   >[!NOTE]
   >* Potete salvare i gruppi di test in qualsiasi momento nel processo di creazione e tornare alla procedura guidata in un secondo momento. Lo stato del gruppo di prova sarà **[!UICONTROL Draft]** e il gruppo di test non invierà alcun dato alle destinazioni fino alla finalizzazione del gruppo di test dei segmenti.
   >* Per i test bozza, potete tornare indietro e modificare i gruppi di test facendo clic sulla **[!UICONTROL Edit]** scheda del gruppo di prova nella [!UICONTROL Audience Lab] vista principale.


## Modifica gruppi di test segmenti {#edit-test-groups}

In [!UICONTROL Audience Lab], potete modificare solo i gruppi di bozza di bozza. Nella [!UICONTROL Create Segment Test Group] procedura guidata, potete salvare il gruppo di test come bozza e riprendere il lavoro su di esso in un secondo momento.

1. Passate alla vista [!UICONTROL Audience Lab] principale.
1. Cercate i gruppi di test bozza e selezionate il **[!UICONTROL Edit]** controllo nella scheda del gruppo di prova.
1. Riprendi la procedura guidata [Crea gruppo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) di test segmenti e seleziona **[!UICONTROL Finalize Group]** al termine.

## Elimina gruppi di test segmenti {#delete-test-groups}

1. Passate alla vista [!UICONTROL Audience Lab] principale.
1. Individuate il gruppo di test da eliminare. Potete:

   * premete il **[!UICONTROL Delete]** controllo nella scheda del gruppo di prova, oppure
   * premete il titolo del gruppo di prova nella scheda del gruppo di prova per passare alla visualizzazione [di Test Group Information](../../features/audience-lab/audience-lab-information-view.md) (Informazioni gruppo di test) e premete il **[!UICONTROL Delete]** controllo nella barra del titolo.

1. Per [i segmenti di test completati](../../features/audience-lab/audience-lab.md#status), un avviso vi chiederà di scaricare il file CSV per salvare il reporting, se desiderato.
