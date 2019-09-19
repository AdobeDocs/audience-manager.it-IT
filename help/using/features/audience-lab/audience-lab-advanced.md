---
description: Questo articolo descrive due funzioni che forniscono funzionalità avanzate per i modelli di allocazione duplicati e il blocco dei segmenti di Audience Lab.
seo-description: Questo articolo descrive due funzioni che forniscono funzionalità avanzate per i modelli di allocazione duplicati e il blocco dei segmenti di Audience Lab.
seo-title: Funzionalità avanzata di Audience Lab
solution: Audience Manager
title: Funzionalità avanzata di Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] Funzionalità avanzata {#audience-lab-advanced-functionality}

Questo articolo descrive due funzioni che forniscono funzionalità avanzate per [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] e [!DNL Segment Holdout].

## Duplica modello di allocazione {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], [!DNL Allocation Template] rappresenta le varie selezioni effettuate durante la creazione di un gruppo di test:

* La distribuzione dei dispositivi tra i segmenti di prova;
* Mappatura dei segmenti di prova alle destinazioni;
* Caratteristiche di conversione utilizzate per un gruppo di test;
* Intervallo di date in cui il gruppo di test pubblica nelle destinazioni selezionate.

Duplicando un modello di allocazione, puoi riutilizzare la stessa distribuzione di segmenti di test e destinazioni per un segmento di base diverso, in un nuovo gruppo di test. Un esempio di modello di allocazione è illustrato di seguito. L’immagine viene tratta dal [!UICONTROL Summary & Finalize] passaggio del flusso di lavoro **Crea gruppo** di test.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Utilizzo di un modello di allocazione duplicato

Create un gruppo di test iniziale, quindi selezionate **[!UICONTROL Duplicate Allocation Template]** per riutilizzare le stesse impostazioni tra più gruppi di test. Ad esempio, puoi utilizzare questa funzione se esegui un test in cui vuoi determinare l'efficacia di diverse destinazioni per più segmenti.

1. Nella vista principale di Audience Lab, cercate il gruppo di test di cui desiderate riprodurre il modello di allocazione in un nuovo gruppo di test. Nella casella a discesa, selezionate **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. Nella [!UICONTROL Create Test Group] procedura guidata potete specificare un segmento di base e, se lo desiderate, rinominare i segmenti di test.
3. Non *è possibile* modificare:

   * La distribuzione dei dispositivi tra i segmenti di prova;
   * caratteristiche di conversione;
   * Mappatura dei segmenti di test alle destinazioni. Puoi compilare solo la chiave di mappatura, per le destinazioni che ne richiedono una.
   * Intervallo di date in cui il gruppo di test pubblicherà le destinazioni selezionate.

4. Rivedete le informazioni aggiunte nei passaggi precedenti e selezionate **[!UICONTROL Finalize Group]**.

## Esclusione segmento test {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] è una funzionalità avanzata, attivata su richiesta del cliente. Contattate [!DNL Customer Care] o [!DNL Adobe Consulting] per attivare questa funzione.

Utilizzate questa funzione per impedire che parte del pubblico venga inclusa nel test. La percentuale selezionata viene esclusa dal test. In questo modo, potete misurare e confrontare il numero di conversioni da tipi di pubblico con targeting (attivato sulle destinazioni) e non mirati (esclusi).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Utilizzo del blocco del segmento di test

1. Create un nuovo gruppo di test utilizzando la [!UICONTROL Create Test Group] procedura guidata.
1. Nel **[!UICONTROL Allocate Test Segment]** passaggio, potete selezionare una parte dell'audience da escludere dai test.

   ![Voce di elenco](assets/test-segment-holdout.png)

1. Usate il cursore per regolare quanti dispositivi desiderate impedire il test. Tenere presente che il segmento di test 1 e il segmento di test 2 ora rappresentano solo il 70% del totale dei dispositivi.

   ![](assets/test-segment-holdout-selected.png)

1. Scorri gli altri passaggi del **[!UICONTROL Create Test Group]** flusso di lavoro e seleziona **[!UICONTROL Finalize Group]** quando sei soddisfatto della selezione. Ora disponete di un gruppo di test con parte del pubblico cui è stato negato il test.
