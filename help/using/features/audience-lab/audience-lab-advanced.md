---
description: Questo articolo descrive due funzioni che forniscono funzionalità avanzate per il modello di allocazione duplicata di Audience Lab e per il blocco dei segmenti.
seo-description: This article describes two features which provide advanced functionality for Audience Lab  Duplicate Allocation Template and Segment Holdout.
seo-title: Audience Lab Advanced Functionality
solution: Audience Manager
title: Funzionalità avanzata di Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# [!DNL Audience Lab] Funzionalità avanzate {#audience-lab-advanced-functionality}

Questo articolo descrive due funzioni che forniscono funzionalità avanzate per [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] e [!DNL Segment Holdout].

## Duplica modello di allocazione {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In entrata [!DNL Audience Lab], il [!DNL Allocation Template] rappresenta le varie selezioni effettuate durante la creazione di un gruppo di test:

* la distribuzione dei dispositivi tra i segmenti di prova;
* La mappatura dei segmenti di prova sulle destinazioni;
* Le caratteristiche di conversione utilizzate per un gruppo di test;
* L’intervallo di date in cui il gruppo di test pubblica le destinazioni selezionate.

Duplicando un modello di allocazione, è possibile riutilizzare la stessa distribuzione di segmenti e destinazioni di test per un segmento di base diverso, in un nuovo gruppo di test. Di seguito è illustrato un esempio di modello di allocazione. L&#39;immagine viene acquisita da [!UICONTROL Summary & Finalize] passaggio nel **Crea gruppo di test** flusso di lavoro.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Utilizzo di un modello di allocazione duplicato

Crea un gruppo di test iniziale, quindi seleziona **[!UICONTROL Duplicate Allocation Template]** per riutilizzare le stesse impostazioni in più gruppi di test. Ad esempio, puoi utilizzare questa funzione se esegui un test in cui desideri determinare l’efficacia di più destinazioni per più segmenti.

1. Nella visualizzazione principale di Audience Lab, cerca il gruppo di test di cui desideri riprodurre il modello di allocazione in un nuovo gruppo di test. Nella casella a discesa, seleziona **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. In [!UICONTROL Create Test Group] procedura guidata, puoi specificare un segmento di base e rinominare i segmenti di test, se lo desideri.
3. Tu *non può* modifica:

   * la distribuzione dei dispositivi tra i segmenti di prova;
   * Le caratteristiche di conversione;
   * Mappatura dei segmenti di test sulle destinazioni. Puoi compilare solo la chiave di mappatura, per le destinazioni che ne richiedono una.
   * L’intervallo di date in cui il gruppo di test pubblicherà le destinazioni selezionate.

4. Rivedi le informazioni aggiunte nei passaggi precedenti e seleziona **[!UICONTROL Finalize Group]**.

## Ritenzione segmento di prova {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] è una funzionalità avanzata, attivata su richiesta del cliente. Contatta [!DNL Customer Care] o [!DNL Adobe Consulting] per attivare questa funzione.

Utilizza questa funzione per impedire che parte del pubblico venga incluso nel test. La percentuale selezionata viene esclusa dal test. In questo modo, puoi misurare e confrontare il numero di conversioni dai tipi di pubblico target (attivati sulle destinazioni) e non target (gruppo di sospensione).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Utilizzo del blocco del segmento di test

1. Creare un nuovo gruppo di test utilizzando [!UICONTROL Create Test Group] procedura guidata.
1. In **[!UICONTROL Allocate Test Segment]** passaggio, puoi selezionare una parte del pubblico da escludere dal test.

   ![Voce di elenco](assets/test-segment-holdout.png)

1. Usare il dispositivo di scorrimento per regolare il numero di dispositivi che si desidera escludere dalla prova. Osserva come il Segmento di test 1 e il Segmento di test 2 ora rappresentano solo il 70% dei dispositivi totali.

   ![](assets/test-segment-holdout-selected.png)

1. Segui gli altri passaggi della sezione **[!UICONTROL Create Test Group]** workflow e selezione **[!UICONTROL Finalize Group]** quando sei soddisfatto della selezione. Ora disponi di un gruppo di test con parte del pubblico nascosta dal test.
