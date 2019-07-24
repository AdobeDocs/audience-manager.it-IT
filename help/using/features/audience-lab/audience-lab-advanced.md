---
description: Questo articolo descrive due funzionalità che offrono funzionalità avanzate per i modelli di allocazione duplicati di Audience Lab e Segmento.
seo-description: Questo articolo descrive due funzionalità che offrono funzionalità avanzate per i modelli di allocazione duplicati di Audience Lab e Segmento.
seo-title: Funzionalità avanzate di Audience Lab
solution: Audience Manager
title: Funzionalità avanzate di Audience Lab
uuid: 0 f 57 d 634-caa 0-40 da -81 a 2-c 23 fbd 299 bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] Funzionalità avanzate {#audience-lab-advanced-functionality}

This article describes two features which provide advanced functionality for [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] and [!DNL Segment Holdout].

## Duplicate Allocation Template {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], the [!DNL Allocation Template] represents the various selections you make when creating a test group:

* La distribuzione dei dispositivi tra i segmenti di prova;
* Mappatura dei segmenti di prova alle destinazioni;
* Le caratteristiche di conversione utilizzate per un gruppo di test;
* L'intervallo di date in cui il gruppo di prova viene pubblicato nelle destinazioni selezionate.

Duplicando un modello di assegnazione, potete riutilizzare la stessa distribuzione di segmenti e destinazioni di test per un segmento di base diverso, in un nuovo gruppo di test. Esempio di modello di allocazione illustrato di seguito. The image is taken from the [!UICONTROL Summary & Finalize] step in the **Create Test Group** workflow.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Utilizzo del modello di allocazione duplicato

Create an initial test group, then select **[!UICONTROL Duplicate Allocation Template]** to reuse the same settings across multiple test groups. Ad esempio, potete utilizzare questa funzione se state eseguendo un test in cui desiderate determinare l'efficacia di più destinazioni per più segmenti.

1. Nella vista principale di Audience Lab, cercate il gruppo di prova di cui desiderate riprodurre il modello in un nuovo gruppo di test. In the drop-down box, select **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. In the [!UICONTROL Create Test Group] wizard, you can specify a base segment and rename your test segments, if you wish.
3. *Non* è possibile modificare:

   * La distribuzione dei dispositivi tra i segmenti di prova;
   * Le caratteristiche di conversione;
   * Mappatura dei segmenti di prova alle destinazioni. Potete compilare la chiave di mappatura solo per le destinazioni che ne richiedono uno.
   * Intervallo di date in cui verrà pubblicato il gruppo di test nelle destinazioni selezionate.

4. Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.

## Test Segment Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] è una funzionalità avanzata attivata sulla richiesta del cliente. Please contact [!DNL Customer Care] or [!DNL Adobe Consulting] to activate this feature.

Utilizzate questa funzione per nascondere parte del pubblico da includere nel test. La percentuale selezionata viene esclusa dal test. In questo modo, puoi misurare e confrontare il numero di conversioni da destinazioni (attivate in destinazioni) e tipi di pubblico senza argetter (gruppo di oldout).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Utilizzo della funzione Holdout segmento di prova

1. Create a new test group by using the [!UICONTROL Create Test Group] wizard.
1. In the **[!UICONTROL Allocate Test Segment]** step, you can select a part of the audience to be withheld from testing.

   ![Elemento elenco](assets/test-segment-holdout.png)

1. Usate il cursore per regolare il numero di dispositivi da sottoporre a test. Osservate come il segmento di prova 1 e il segmento di test 2 ora risalgono solo al 70% dei dispositivi totali.

   ![](assets/test-segment-holdout-selected.png)

1. Go through the rest of the steps in the **[!UICONTROL Create Test Group]** workflow and select **[!UICONTROL Finalize Group]** when you're satisfied with your selection. Ora hai un gruppo di test con parte dell'audience trattenuta dai test.
