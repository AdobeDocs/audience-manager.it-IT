---
description: Questa procedura descrive i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-description: Questa procedura descrive i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-title: Gestire gruppi di test
solution: Audience Manager
title: Gestire gruppi di test
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: 'Audience Lab '
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---

# Gestire gruppi di test {#manage-test-groups}

Questa procedura descrive i passaggi necessari per creare, modificare o eliminare un gruppo di test in [!UICONTROL Audience Lab].

## Creare gruppi di test dei segmenti {#create-test-groups}

### Prerequisiti

<!-- create-test-group.xml -->

* Devi avere almeno una **caratteristica di conversione** impostata. Puoi impostare le caratteristiche di conversione in [Generatore di caratteristiche](../../features/traits/create-onboarded-rule-based-traits.md), selezionando **conversion** come tipo di evento. Per ulteriori informazioni sulle caratteristiche di conversione e su come configurarle, abbiamo preparato un [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) per te.

   >[!IMPORTANT]
   >
   >[Le ](../../features/traits/about-folder-traits.md) caratteristiche delle cartelle  **non sono** supportate da  [!UICONTROL Audience Lab]. L&#39;impostazione del [Tipo evento](../../features/traits/create-onboarded-rule-based-traits.md) di una caratteristica cartella su **conversion** non genererà alcun dato in [!UICONTROL Audience Lab] per la caratteristica specifica della cartella.

* Per le aziende che utilizzano [Controllo degli accessi basato su ruoli](../../features/administration/administration-overview.md): Assegna il [!UICONTROL Audience Lab] [permesso jolly](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** per fornire l&#39;accesso. Questa autorizzazione consente all’utente di creare e visualizzare i risultati di un test. Un utente può utilizzare solo i segmenti da un’origine dati per i quali dispone dei privilegi **read** e **map to destination** per . L&#39;utente sarà in grado di utilizzare solo le caratteristiche di conversione da un&#39;origine dati per cui dispone di autorizzazioni **&quot;read&quot;**. Un utente potrà vedere solo le destinazioni a cui ha accesso. Quindi, prima di aggiungere l&#39;autorizzazione del carattere jolly [!DNL Audience Lab] a un gruppo, assicurati che il gruppo abbia:
   * accesso alle caratteristiche di conversione pertinenti in lettura;
   * accesso alla lettura e alla mappatura dei segmenti pertinenti per i test;
   * accesso alle destinazioni pertinenti.

Per creare un nuovo [!UICONTROL Segment Test Group]:

1. Seleziona **[!UICONTROL Create New Test Group]** nel dashboard [!UICONTROL Audience Lab] per avviare la procedura guidata.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Compila un **[!UICONTROL Test Group Name]** e un **[!UICONTROL Description]**.
   * Scegli il **[!UICONTROL Base Segment]** navigando nel browser dei file o digitando nella barra di ricerca, confermando premendo **[!UICONTROL Choose Segment.]**
   * Puoi salvare il gruppo di test come bozza e riprendere a lavorarci in un secondo momento.
   * Viene visualizzato un avviso nel caso in cui il segmento di base selezionato sia già utilizzato in altri gruppi di test. L’utilizzo due volte del segmento di base può distorcere i risultati della conversione per entrambi i test.

1. **[!UICONTROL Allocate Test Segments]**

   * Puoi creare **fino a 15 segmenti di test** e dividere la percentuale di dispositivi come desideri.
   * Puoi modificare il nome dei segmenti di test facendo clic su di essi.
   * Le percentuali si suddividono automaticamente in modo uniforme al 100% quando vengono allocati nuovi segmenti di test. Puoi quindi modificare manualmente le percentuali. Fai clic sulla casella di controllo dopo aver modificato le percentuali e accertati che aggiungano fino al 100%, altrimenti non potrai procedere al passaggio successivo.

1. **[!UICONTROL Set a Control Segment]**

   * Selezionare un segmento di controllo se si desidera mettere da parte una determinata parte del segmento da utilizzare come gruppo di controllo. I gruppi di controllo ti consentono di vedere l’impatto dei segmenti di test creati rispetto a un benchmark.
   * È possibile selezionare un segmento di test come segmento di controllo nell’elenco a discesa, oppure è possibile scegliere **[!UICONTROL None]** senza alcun controllo.
   * Al termine, fai clic su **[!UICONTROL Next]** .

1. **[!UICONTROL Select Conversion Traits]**

   * Aggiungi le caratteristiche di conversione digitando nella finestra delle caratteristiche di conversione. Si tratta di un passaggio **obbligatorio** e non puoi procedere al passaggio successivo a meno che non aggiungi almeno una caratteristica di conversione.
   * Se lo desideri, puoi aggiungere fino a 5 caratteristiche di conversione.
   * Se selezioni una caratteristica di conversione già utilizzata per altri gruppi di test, viene visualizzato un avviso.
   * Nota che Audience Manager non supporta l’utilizzo di [caratteristiche della cartella](/help/using/features/traits/about-folder-traits.md) come caratteristiche di conversione. Quando si seleziona una caratteristica della cartella come caratteristica di conversione, nel test vengono visualizzati 0 rapporti aggregati e tendenze.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digita le destinazioni desiderate nel campo di ricerca o utilizza la freccia a discesa. [!UICONTROL Audience Lab] i segmenti di test possono essere inviati a destinazioni URL, cookie o server-to-server.
   * Trascina i segmenti nelle destinazioni.
   * Dopo aver rilasciato un segmento in una destinazione, compila il segno **[!UICONTROL Destination Mapping Value]** nel cieco.
   * Puoi inviare lo stesso segmento di test a più destinazioni e aggiungere più segmenti di test a una singola destinazione.
   * Le destinazioni sono disattivate se non sono disponibili per un determinato segmento di test in base a [Controlli sull&#39;esportazione dei dati](../../features/data-export-controls.md).
   * Gli utenti vedranno solo le destinazioni a cui hanno accesso in base al [Gruppo di utenti RBAC](../../features/administration/administration-overview.md) a cui appartengono.
   * Infine, devi selezionare una data di inizio per il gruppo di test. Questa data segna l’inizio del periodo in cui il gruppo di test verrà pubblicato nelle destinazioni. Seleziona **Nessuna data di fine** per un confronto indefinito dei segmenti di test.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un profilo autenticato sono supportati solo nelle destinazioni in tempo reale. Se un segmento di test con una regola di unione profili di tale configurazione viene inviato a una destinazione server-to-server basata su file, il pubblico potrebbe non essere compilato.

   Fai clic su **[!UICONTROL Next]** per rivedere e finalizzare il gruppo di test.

1. **[!UICONTROL Summary & Finalize]**

   * Rivedi le informazioni aggiunte nei passaggi precedenti e seleziona **[!UICONTROL Finalize Group]**.
   * Ricorda che una volta finalizzato un gruppo di test, può essere duplicato o eliminato, ma non modificato.

   >[!NOTE]
   >* Puoi salvare i gruppi di test in qualsiasi momento del processo di creazione e tornare alla procedura guidata in un secondo momento. Lo stato del gruppo di test sarà **[!UICONTROL Draft]** e il gruppo di test non invierà dati alle destinazioni finché non finalizzerai il gruppo di test dei segmenti.
   >* Per le bozze di test, puoi tornare indietro e modificare i gruppi di test facendo clic su **[!UICONTROL Edit]** nella scheda del gruppo di test nella vista principale [!UICONTROL Audience Lab].


## Modificare i gruppi di test dei segmenti {#edit-test-groups}

In [!UICONTROL Audience Lab] puoi modificare solo gruppi di test bozza. Nella procedura guidata [!UICONTROL Create Segment Test Group] puoi salvare il gruppo di test come bozza e riprendere a lavorarci in un secondo momento.

1. Passa alla vista principale [!UICONTROL Audience Lab].
1. Cerca i gruppi di test bozza e seleziona il controllo **[!UICONTROL Edit]** nella scheda del gruppo di test.
1. Riprende la procedura guidata [Crea gruppo di test dei segmenti](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) e seleziona **[!UICONTROL Finalize Group]** al termine.

## Eliminare i gruppi di test dei segmenti {#delete-test-groups}

1. Passa alla vista principale [!UICONTROL Audience Lab].
1. Individuare il gruppo di test da eliminare. Potete:

   * premere il controllo **[!UICONTROL Delete]** nella scheda del gruppo di test, oppure
   * premere il titolo del gruppo di test nella scheda del gruppo di test per passare alla visualizzazione [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) e premere il controllo **[!UICONTROL Delete]** nella barra del titolo.

1. Per [segmenti di test completati](../../features/audience-lab/audience-lab.md#status), viene richiesto di scaricare il file CSV per salvare il rapporto, se lo desideri.
