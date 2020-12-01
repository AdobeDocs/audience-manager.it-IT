---
description: Questa procedura illustra i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-description: Questa procedura illustra i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-title: Gestire gruppi di test
solution: Audience Manager
title: Gestire gruppi di test
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 1%

---


# Gestire gruppi di test {#manage-test-groups}

Questa procedura illustra i passaggi necessari per creare, modificare o eliminare un gruppo di test in [!UICONTROL Audience Lab].

## Crea gruppi di test dei segmenti {#create-test-groups}

### Prerequisiti

<!-- create-test-group.xml -->

* È necessario disporre di almeno una **caratteristica di conversione** impostata. È possibile impostare le caratteristiche di conversione in [Generatore di caratteristiche](../../features/traits/create-onboarded-rule-based-traits.md), selezionando **conversion** come tipo di evento. Per ulteriori informazioni sulle caratteristiche di conversione e su come configurarle, abbiamo preparato un [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) per voi.

   >[!IMPORTANT]
   >
   >[Le ](../../features/traits/about-folder-traits.md) caratteristiche delle cartelle  **non sono** supportate da  [!UICONTROL Audience Lab]. Se si imposta la caratteristica [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) di una cartella su **conversion**, non verranno generati dati in [!UICONTROL Audience Lab] per la caratteristica specifica della cartella.

* Per le aziende che utilizzano [Controllo dell&#39;accesso basato su ruolo](../../features/administration/administration-overview.md): Assegnate l&#39;autorizzazione [!UICONTROL Audience Lab] [carattere jolly](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** per fornire l&#39;accesso. Questa autorizzazione consente all&#39;utente di creare e visualizzare i risultati di un test. Un utente può utilizzare solo i segmenti da un&#39;origine dati per i quali dispone dei privilegi di **lettura** e di **mappatura a destinazione**. L&#39;utente potrà utilizzare solo caratteristiche di conversione da un&#39;origine dati per la quale dispone di autorizzazioni **&quot;read&quot;**. Un utente potrà visualizzare solo le destinazioni a cui ha accesso. Quindi, prima di aggiungere l&#39;autorizzazione per il carattere jolly [!DNL Audience Lab] a un gruppo, accertatevi che il gruppo abbia:
   * accesso alle caratteristiche di conversione rilevanti per la lettura;
   * accesso alla lettura e mappatura dei segmenti pertinenti per i test;
   * accesso alle destinazioni pertinenti.

Per creare una nuova [!UICONTROL Segment Test Group]:

1. Selezionare **[!UICONTROL Create New Test Group]** nel dashboard [!UICONTROL Audience Lab] per avviare la procedura guidata.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Compilare un **[!UICONTROL Test Group Name]** e un **[!UICONTROL Description]**.
   * Scegliere la **[!UICONTROL Base Segment]** navigando nel browser file o digitando nella barra di ricerca, confermare premendo **[!UICONTROL Choose Segment.]**
   * Potete salvare il gruppo di test come bozza e riprendere a lavorarci in un secondo momento.
   * Viene visualizzato un avviso nel caso in cui il segmento di base selezionato sia già utilizzato in altri gruppi di test. L’utilizzo doppio del segmento di base potrebbe distorcere i risultati di conversione per entrambi i test.

1. **[!UICONTROL Allocate Test Segments]**

   * Puoi creare **fino a 15 segmenti di test** e dividere la percentuale di dispositivi come desideri.
   * Potete modificare il nome dei segmenti di test facendo clic su di essi.
   * Le percentuali si suddividono automaticamente in modo uniforme al 100% quando vengono allocati nuovi segmenti di test. Potete quindi modificare manualmente le percentuali. Dopo aver modificato le percentuali, fate clic sulla casella di controllo e accertatevi che arrivino al 100%. In caso contrario, non sarà possibile passare al passaggio successivo.

1. **[!UICONTROL Set a Control Segment]**

   * Selezionare un segmento di controllo se si desidera mettere da parte una parte specifica del segmento da utilizzare come gruppo di controllo. I gruppi di controllo consentono di vedere l&#39;impatto dei segmenti di test creati rispetto a un benchmark.
   * È possibile selezionare un segmento di test come segmento di controllo nell&#39;elenco a discesa, oppure scegliere **[!UICONTROL None]** senza alcun controllo.
   * Fare clic su **[!UICONTROL Next]** al termine.

1. **[!UICONTROL Select Conversion Traits]**

   * Aggiungi caratteristiche di conversione digitando nella finestra delle caratteristiche di conversione. Si tratta di un passaggio **obbligatorio** e non è possibile passare al passaggio successivo a meno che non si aggiunga almeno una caratteristica di conversione.
   * Se lo desiderate, potete aggiungere fino a 5 caratteristiche di conversione.
   * Se selezionate una caratteristica di conversione già utilizzata per altri gruppi di test, viene visualizzato un avviso.
   *  Audience Manager non supporta l&#39;utilizzo di [caratteristiche delle cartelle](/help/using/features/traits/about-folder-traits.md) come caratteristiche di conversione. Selezionando una caratteristica della cartella come caratteristica di conversione, vengono visualizzati 0 rapporti aggregati e tendenze all’interno del test.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digita le destinazioni desiderate nel campo di ricerca o utilizza la freccia a discesa. [!UICONTROL Audience Lab] i segmenti di test possono essere inviati a destinazioni URL, cookie o server-to-server.
   * Trascina i segmenti nelle destinazioni.
   * Dopo aver rilasciato un segmento in una destinazione, compila il **[!UICONTROL Destination Mapping Value]** nel cieco.
   * Potete inviare lo stesso segmento di test a più destinazioni e aggiungere più segmenti di test a una singola destinazione.
   * Le destinazioni sono disabilitate se non sono disponibili per un determinato segmento di test in base a [Controlli sull&#39;esportazione dei dati](../../features/data-export-controls.md).
   * Gli utenti vedranno solo le destinazioni a cui hanno accesso in base al [Gruppo di utenti RBAC](../../features/administration/administration-overview.md) a cui appartengono.
   * Infine, è necessario selezionare una data di inizio per il gruppo di test. Questa data indica l&#39;inizio del periodo in cui il gruppo di test verrà pubblicato nelle destinazioni. Selezionare **Nessuna data di fine** per un confronto indefinito dei segmenti di test.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un profilo autenticato sono supportati solo in destinazioni in tempo reale. Se un segmento di test con una regola di unione dei profili di tale configurazione viene inviato a una destinazione server-to-server basata su file, l&#39;audience potrebbe non essere popolata.

   Fate clic su **[!UICONTROL Next]** per rivedere e finalizzare il gruppo di test.

1. **[!UICONTROL Summary & Finalize]**

   * Rivedete le informazioni aggiunte nei passaggi precedenti e selezionate **[!UICONTROL Finalize Group]**.
   * Una volta finalizzato un gruppo di test, questo può essere duplicato o eliminato, ma non modificato.

   >[!NOTE]
   >* È possibile salvare i gruppi di test in qualsiasi momento del processo di creazione e tornare alla procedura guidata in un secondo momento. Lo stato del gruppo di test sarà **[!UICONTROL Draft]** e il gruppo di test non invierà dati alle destinazioni finché non finalizzerete il gruppo di test del segmento.
   >* Per le bozze di test, potete tornare indietro e modificare i gruppi di test facendo clic su **[!UICONTROL Edit]** nella scheda del gruppo di test nella vista principale [!UICONTROL Audience Lab].


## Modifica gruppi di test dei segmenti {#edit-test-groups}

In [!UICONTROL Audience Lab], potete modificare solo i gruppi di test delle bozze. Nella procedura guidata [!UICONTROL Create Segment Test Group], potete salvare il gruppo di test come bozza e riprendere a lavorarci in un secondo momento.

1. Passate alla vista principale [!UICONTROL Audience Lab].
1. Cercate i gruppi di test bozza e selezionate il controllo **[!UICONTROL Edit]** nella scheda del gruppo di test.
1. Riprendere la procedura guidata [Crea gruppo di test segmenti](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) e selezionare **[!UICONTROL Finalize Group]** al termine.

## Elimina gruppi di test segmento {#delete-test-groups}

1. Passate alla vista principale [!UICONTROL Audience Lab].
1. Individuate il gruppo di test da eliminare. Potete:

   * premere il controllo **[!UICONTROL Delete]** nella scheda del gruppo di test, oppure
   * premere il titolo del gruppo di test nella scheda del gruppo di test per passare alla visualizzazione [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) e premere il controllo **[!UICONTROL Delete]** nella barra del titolo.

1. Per [segmenti di test completati](../../features/audience-lab/audience-lab.md#status), viene visualizzato un avviso che richiede di scaricare il file CSV per salvare il rapporto, se lo si desidera.
