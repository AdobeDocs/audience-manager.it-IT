---
description: Questa procedura illustra i passaggi necessari per creare, modificare o eliminare un gruppo di test in Audience Lab
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Gestisci gruppi di test
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Gestisci gruppi di test {#manage-test-groups}

Questa procedura illustra i passaggi necessari per creare, modificare o eliminare un gruppo di test in [!UICONTROL Audience Lab].

## Creare gruppi di test dei segmenti {#create-test-groups}

### Prerequisiti

<!-- create-test-group.xml -->

* Devi avere almeno una **caratteristica di conversione** configurata. È possibile impostare le caratteristiche di conversione nel [Generatore caratteristiche](../../features/traits/create-onboarded-rule-based-traits.md) selezionando **conversione** come tipo di evento. Per ulteriori informazioni sulle caratteristiche di conversione e su come configurarle, abbiamo preparato un [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html).

  >[!IMPORTANT]
  >
  >[Caratteristiche cartella](../../features/traits/about-folder-traits.md) **non supportate** da [!UICONTROL Audience Lab]. Se si imposta il [Tipo evento](../../features/traits/create-onboarded-rule-based-traits.md) di una caratteristica cartella su **conversione**, non verranno generati dati in [!UICONTROL Audience Lab] per tale caratteristica cartella specifica.

* Per le aziende che utilizzano [il controllo degli accessi basato sul ruolo](../../features/administration/administration-overview.md): assegnare l&#39;autorizzazione [!UICONTROL Audience Lab] [jolly](../../features/administration/administration-overview.md#wild-card-permissions) a **[!UICONTROL User Groups]** per fornire l&#39;accesso. Questa autorizzazione consente all’utente di creare e visualizzare i risultati di un test. Un utente potrà utilizzare solo i segmenti di un&#39;origine dati per la quale dispone di privilegi di **lettura** e di **mappatura sulla destinazione**. L&#39;utente potrà utilizzare solo le caratteristiche di conversione da un&#39;origine dati per la quale dispone di autorizzazioni di **&quot;lettura&quot;**. Un utente può visualizzare solo le destinazioni a cui ha accesso. Pertanto, prima di aggiungere l&#39;autorizzazione con caratteri jolly [!DNL Audience Lab] a un gruppo, verificare che il gruppo disponga di:
   * accesso alle caratteristiche di conversione pertinenti alla lettura;
   * accesso alla lettura e alla mappatura dei segmenti pertinenti per le prove;
   * l&#39;accesso alle destinazioni pertinenti.

Per creare un nuovo [!UICONTROL Segment Test Group]:

1. Selezionare **[!UICONTROL Create New Test Group]** nel dashboard [!UICONTROL Audience Lab] per avviare la procedura guidata.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Compila un **[!UICONTROL Test Group Name]** e un **[!UICONTROL Description]**.
   * Scegliere **[!UICONTROL Base Segment]** spostandosi nel browser dei file o digitando nella barra di ricerca, confermare premendo **[!UICONTROL Choose Segment.]**
   * È possibile salvare il gruppo di test come bozza e riprendere a lavorarci in un secondo momento.
   * Se il segmento di base selezionato è già utilizzato in altri gruppi di test, viene visualizzato un avviso. Se si utilizza due volte il segmento di base, i risultati della conversione per entrambi i test potrebbero risultare distorti.

1. **[!UICONTROL Allocate Test Segments]**

   * Puoi creare fino a **15 segmenti di test** e dividere la percentuale di dispositivi come desideri.
   * Puoi modificare il nome dei segmenti di test facendo clic su di essi.
   * Quando vengono allocati nuovi segmenti di test, le percentuali si dividono automaticamente in modo uniforme al 100%. È quindi possibile modificare manualmente le percentuali. Dopo aver modificato le percentuali, fai clic sulla casella di controllo e accertati che la somma raggiunga il 100%, altrimenti non potrai procedere al passaggio successivo.

1. **[!UICONTROL Set a Control Segment]**

   * Selezionare un segmento di controllo se si desidera mettere da parte una determinata parte del segmento da utilizzare come gruppo di controllo. I gruppi di controllo ti consentono di visualizzare l’impatto dei segmenti di test creati rispetto a un benchmark.
   * È possibile selezionare un segmento di test come segmento di controllo nell&#39;elenco a discesa oppure scegliere **[!UICONTROL None]** per nessun controllo.
   * Al termine, fai clic su **[!UICONTROL Next]**.

1. **[!UICONTROL Select Conversion Traits]**

   * Aggiungi le caratteristiche di conversione digitando nella finestra delle caratteristiche di conversione. Questo è un passaggio **obbligatorio** e non puoi procedere al passaggio successivo a meno che non aggiungi almeno una caratteristica di conversione.
   * Puoi aggiungere fino a 5 caratteristiche di conversione, se lo desideri.
   * Se selezioni una caratteristica di conversione già utilizzata per altri gruppi di test, viene visualizzato un avviso.
   * Audience Manager non supporta l&#39;utilizzo di [caratteristiche cartella](/help/using/features/traits/about-folder-traits.md) come caratteristiche di conversione. Se si seleziona una caratteristica di cartella come caratteristica di conversione, nel test vengono visualizzati i rapporti aggregati e di tendenza 0.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Digita le destinazioni desiderate nel campo di ricerca o utilizza la freccia a discesa. [!UICONTROL Audience Lab] segmenti di test possono essere inviati a destinazioni URL, cookie o server-to-server.
   * Trascina i segmenti nelle destinazioni.
   * Dopo aver rilasciato un segmento in una destinazione, compila **[!UICONTROL Destination Mapping Value]** in cieco.
   * Puoi inviare lo stesso segmento di test a più destinazioni e aggiungere più segmenti di test a una singola destinazione.
   * Le destinazioni sono disattivate se non sono disponibili per un determinato segmento di test basato su [Controlli sull&#39;esportazione dei dati](../../features/data-export-controls.md).
   * Gli utenti visualizzeranno solo le destinazioni a cui hanno accesso in base al [gruppo di utenti RBAC](../../features/administration/administration-overview.md) a cui appartengono.
   * Infine, devi selezionare una data di inizio per il gruppo di test. Questa data segna l’inizio del periodo in cui il gruppo di test verrà pubblicato sulle destinazioni. Selezionare **Nessuna data di fine** per un confronto indefinito dei segmenti di test.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] con un profilo autenticato sono supportati solo nelle destinazioni in tempo reale. Se un segmento di test con una regola di unione profili di tale configurazione viene inviato a una destinazione da server a server basata su file, i tipi di pubblico potrebbero non essere popolati.

   Fare clic su **[!UICONTROL Next]** per rivedere e finalizzare il gruppo di test.

1. **[!UICONTROL Summary & Finalize]**

   * Rivedi le informazioni aggiunte nei passaggi precedenti e seleziona **[!UICONTROL Finalize Group]**.
   * Una volta finalizzato, un gruppo di test può essere duplicato o eliminato, ma non modificato.

   >[!NOTE]
   >* Puoi salvare i gruppi di test in qualsiasi momento del processo di creazione e tornare alla procedura guidata in un secondo momento. Lo stato del gruppo di test sarà **[!UICONTROL Draft]** e il gruppo di test non invierà alcun dato alle destinazioni fino a quando non avrai finalizzato il gruppo di test dei segmenti.
   >* Per le bozze dei test, è possibile tornare indietro e modificare i gruppi di test facendo clic su **[!UICONTROL Edit]** nella scheda gruppo di test nella visualizzazione principale di [!UICONTROL Audience Lab].

## Modifica gruppi di test dei segmenti {#edit-test-groups}

In [!UICONTROL Audience Lab] è possibile modificare solo gruppi di test bozza. Nella procedura guidata [!UICONTROL Create Segment Test Group] è possibile salvare il gruppo di test come bozza e riprendere a lavorarci in un secondo momento.

1. Passare alla visualizzazione principale [!UICONTROL Audience Lab].
1. Cercare i gruppi di test bozza e selezionare il controllo **[!UICONTROL Edit]** nella scheda gruppo di test.
1. Al termine, riprendi la procedura guidata [Crea gruppo di test dei segmenti](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) e seleziona **[!UICONTROL Finalize Group]**.

## Eliminare i gruppi di test dei segmenti {#delete-test-groups}

1. Passare alla visualizzazione principale [!UICONTROL Audience Lab].
1. Individuare il gruppo di test da eliminare. Puoi effettuare le seguenti operazioni:

   * premere il controllo **[!UICONTROL Delete]** nella scheda del gruppo di test oppure
   * premere il titolo del gruppo di test nella scheda gruppo di test per passare alla visualizzazione [Informazioni gruppo di test](../../features/audience-lab/audience-lab-information-view.md) e premere il controllo **[!UICONTROL Delete]** nella barra del titolo.

1. Per [segmenti di test completati](../../features/audience-lab/audience-lab.md#status), un avviso ti chiederà di scaricare il file CSV per salvare il reporting, se lo desideri.
