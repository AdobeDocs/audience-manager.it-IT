---
description: Questa procedura illustra i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-description: Questa procedura illustra i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-title: Gestisci gruppi di test
solution: Audience Manager
title: Gestisci gruppi di test
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Gestisci gruppi di test {#manage-test-groups}

Questa procedura illustra i passaggi necessari per creare, modificare o eliminare un gruppo di test in [!UICONTROL Audience Lab].

## Crea gruppi di test di segmento {#create-test-groups}

### Prerequisiti

<!-- create-test-group.xml -->

* È necessario disporre di almeno una caratteristica **di** conversione impostata. Potete impostare le caratteristiche di conversione nel Generatore di [caratteristiche](../../features/traits/create-onboarded-rule-based-traits.md)selezionando **Conversione** come tipo di evento. Per ulteriori informazioni sulle caratteristiche di conversione e su come configurarle, abbiamo preparato un [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) .

   >[!IMPORTANT]
   >
   >[Le caratteristiche](../../features/traits/about-folder-traits.md) delle cartelle **non sono supportate** da [!UICONTROL Audience Lab]. L'impostazione del tipo [di](../../features/traits/create-onboarded-rule-based-traits.md) evento di una caratteristica della cartella per la **conversione** non genera alcun dato in [!UICONTROL Audience Lab] per la caratteristica specifica della cartella.

* Per le aziende che utilizzano il controllo [dell'accesso basato sul](../../features/administration/administration-overview.md)ruolo: Assegnate l'autorizzazione [!UICONTROL Audience Lab] del [carattere jolly a](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** per fornire l'accesso. Questa autorizzazione consente all'utente di creare e visualizzare i risultati di un test. Un utente può utilizzare solo i segmenti da un'origine dati per la quale dispone di **lettura** e **mappatura ai privilegi di destinazione** . L'utente potrà utilizzare solo caratteristiche di conversione da un'origine dati per la quale dispone di autorizzazioni di **"lettura"** . Un utente potrà visualizzare solo le destinazioni a cui ha accesso. Quindi, prima di aggiungere l'autorizzazione per il [!DNL Audience Lab] carattere jolly a un gruppo, accertatevi che il gruppo abbia:
   * accesso alle caratteristiche di conversione pertinenti alla lettura;
   * accesso alla lettura e mappatura dei segmenti pertinenti per i test;
   * accesso alle destinazioni pertinenti.

Per creare una nuova [!UICONTROL Segment Test Group]:

1. Selezionate **[!UICONTROL Create New Test Group]** nel [!UICONTROL Audience Lab] dashboard per avviare la procedura guidata.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Compilate un **[!UICONTROL Test Group Name]** e un **[!UICONTROL Description]**.
   * Scegliere il file **[!UICONTROL Base Segment]** navigando nel browser del file o digitando nella barra di ricerca, confermare premendo **[!UICONTROL Choose Segment.]**
   * Potete salvare il gruppo di test come bozza e riprendere a lavorarci in seguito.
   * Viene visualizzato un avviso nel caso in cui il segmento di base selezionato sia già utilizzato in altri gruppi di test. L’utilizzo doppio del segmento di base potrebbe distorcere i risultati di conversione per entrambi i test.

1. **[!UICONTROL Allocate Test Segments]**

   * Potete creare **fino a 15 segmenti** di test e dividere la percentuale di dispositivi come desiderate.
   * Potete modificare il nome dei segmenti di test facendo clic su di essi.
   * Le percentuali si suddividono automaticamente in modo uniforme al 100% quando vengono allocati nuovi segmenti di test. Potete quindi modificare manualmente le percentuali. Dopo aver modificato le percentuali, fate clic sulla casella di controllo e accertatevi che arrivino al 100%. In caso contrario non sarà possibile passare al passaggio successivo.

1. **[!UICONTROL Set a Control Segment]**

   * Selezionate un segmento di controllo se desiderate mettere da parte una parte specifica del segmento da utilizzare come gruppo di controllo. I gruppi di controllo consentono di vedere l'impatto dei segmenti di test creati rispetto a un benchmark.
   * È possibile selezionare un segmento di test come segmento di controllo nell'elenco a discesa, oppure **[!UICONTROL None]** per nessun controllo.
   * Fate clic **[!UICONTROL Next]** al termine.

1. **[!UICONTROL Select Conversion Traits]**

   * Aggiungi caratteristiche di conversione digitando nella finestra delle caratteristiche di conversione. Si tratta di un passaggio **obbligatorio** e non puoi passare al passaggio successivo a meno che non aggiungi almeno una caratteristica di conversione.
   * Se lo desiderate, potete aggiungere fino a 5 caratteristiche di conversione.
   * Se selezionate una caratteristica di conversione già utilizzata per altri gruppi di test, compare un avviso.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digita le destinazioni desiderate nel campo di ricerca o utilizza la freccia a discesa. [!UICONTROL Audience Lab] i segmenti di test possono essere inviati a destinazioni URL, cookie o server-to-server.
   * Trascina i segmenti nelle destinazioni.
   * Dopo aver rilasciato un segmento in una destinazione, compila il **[!UICONTROL Destination Mapping Value]** punto cieco.
   * Potete inviare lo stesso segmento di test a più destinazioni e aggiungere più segmenti di test a una singola destinazione.
   * Le destinazioni sono disabilitate se non sono disponibili per un determinato segmento di test in base ai controlli [di esportazione](../../features/data-export-controls.md)dati.
   * Gli utenti vedranno solo le destinazioni a cui hanno accesso in base al gruppo [di utenti](../../features/administration/administration-overview.md) RBAC a cui appartengono.
   * Infine, è necessario selezionare una data di inizio per il gruppo di test. Questa data indica l'inizio del periodo in cui il gruppo di test verrà pubblicato nelle destinazioni. Selezionare **Nessuna data** di fine per un confronto indefinito dei segmenti di test.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un profilo autenticato sono supportati solo in destinazioni in tempo reale. Se un segmento di test con una regola di unione dei profili di tale configurazione viene inviato a una destinazione server-to-server basata su file, l'audience potrebbe non essere popolata.

   Fate clic **[!UICONTROL Next]** per rivedere e finalizzare il gruppo di test.

1. **[!UICONTROL Summary & Finalize]**

   * Rivedete le informazioni aggiunte nei passaggi precedenti e selezionate **[!UICONTROL Finalize Group]**.
   * Una volta finalizzato un gruppo di test, questo può essere duplicato o eliminato, ma non modificato.
   >[!NOTE]
   >* È possibile salvare i gruppi di test in qualsiasi momento del processo di creazione e tornare alla procedura guidata in un secondo momento. Lo stato del gruppo di test sarà **[!UICONTROL Draft]** e il gruppo di test non invierà dati alle destinazioni fino a quando non finalizzerete il gruppo di test del segmento.
   >* Per le bozze di test, potete tornare indietro e modificare i gruppi di test facendo clic **[!UICONTROL Edit]** nella scheda del gruppo di test nella [!UICONTROL Audience Lab] vista principale.


## Modifica gruppi di test dei segmenti {#edit-test-groups}

In [!UICONTROL Audience Lab], potete modificare solo i gruppi di test delle bozze. Nella [!UICONTROL Create Segment Test Group] procedura guidata, potete salvare il gruppo di test come bozza e riprendere a lavorarci in seguito.

1. Passate alla vista [!UICONTROL Audience Lab] principale.
1. Cercate i gruppi di test bozza e selezionate il **[!UICONTROL Edit]** controllo nella scheda del gruppo di test.
1. Riprende la procedura guidata [Crea gruppo](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) di test segmenti e seleziona **[!UICONTROL Finalize Group]** al termine.

## Elimina gruppi di test segmenti {#delete-test-groups}

1. Passate alla vista [!UICONTROL Audience Lab] principale.
1. Individuate il gruppo di test da eliminare. Potete:

   * premere il **[!UICONTROL Delete]** controllo nella scheda del gruppo di test, oppure
   * premete il titolo del gruppo di test nella scheda del gruppo di test per passare alla visualizzazione Informazioni [gruppo di](../../features/audience-lab/audience-lab-information-view.md) test e premete il **[!UICONTROL Delete]** controllo nella barra del titolo.

1. Per i segmenti [di prova](../../features/audience-lab/audience-lab.md#status)completati, viene visualizzato un avviso che richiede di scaricare il file CSV per salvare il rapporto, se lo desiderate.
