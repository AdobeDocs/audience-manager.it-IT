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

Questo articolo descrive due funzionalità che offrono funzionalità avanzate per [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] e [!DNL Segment Holdout].

## Duplica modello di allocazione {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], rappresenta [!DNL Allocation Template] le varie selezioni effettuate durante la creazione di un gruppo di test:

* La distribuzione dei dispositivi tra i segmenti di prova;
* Mappatura dei segmenti di prova alle destinazioni;
* Le caratteristiche di conversione utilizzate per un gruppo di test;
* L&#39;intervallo di date in cui il gruppo di prova viene pubblicato nelle destinazioni selezionate.

Duplicando un modello di assegnazione, potete riutilizzare la stessa distribuzione di segmenti e destinazioni di test per un segmento di base diverso, in un nuovo gruppo di test. Esempio di modello di allocazione illustrato di seguito. L&#39;immagine viene ripresa dal [!UICONTROL Summary & Finalize] passaggio nel flusso di lavoro **Crea gruppo** di test.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Utilizzo del modello di allocazione duplicato

Create un gruppo di test iniziale, quindi selezionate **[!UICONTROL Duplicate Allocation Template]** per riutilizzare le stesse impostazioni tra più gruppi di test. Ad esempio, potete utilizzare questa funzione se state eseguendo un test in cui desiderate determinare l&#39;efficacia di più destinazioni per più segmenti.

1. Nella vista principale di Audience Lab, cercate il gruppo di prova di cui desiderate riprodurre il modello in un nuovo gruppo di test. Nel menu a discesa, selezionate **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. Nella [!UICONTROL Create Test Group] procedura guidata, potete specificare un segmento di base e rinominare i segmenti di test, se lo desiderate.
3. *Non* è possibile modificare:

   * La distribuzione dei dispositivi tra i segmenti di prova;
   * Le caratteristiche di conversione;
   * Mappatura dei segmenti di prova alle destinazioni. Potete compilare la chiave di mappatura solo per le destinazioni che ne richiedono uno.
   * Intervallo di date in cui verrà pubblicato il gruppo di test nelle destinazioni selezionate.

4. Esaminate le informazioni aggiunte nei passaggi precedenti e selezionate **[!UICONTROL Finalize Group]**.

## Test segmento di prova {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] è una funzionalità avanzata attivata sulla richiesta del cliente. Contattate [!DNL Customer Care] o [!DNL Adobe Consulting] per attivare questa funzione.

Utilizzate questa funzione per nascondere parte del pubblico da includere nel test. La percentuale selezionata viene esclusa dal test. In questo modo, puoi misurare e confrontare il numero di conversioni da destinazioni (attivate in destinazioni) e tipi di pubblico senza argetter (gruppo di oldout).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Utilizzo della funzione Holdout segmento di prova

1. Create un nuovo gruppo di test utilizzando la [!UICONTROL Create Test Group] procedura guidata.
1. Nel **[!UICONTROL Allocate Test Segment]** passaggio, puoi selezionare una parte dell&#39;audience da rifiutare dal test.

   ![Elemento elenco](assets/test-segment-holdout.png)

1. Usate il cursore per regolare il numero di dispositivi da sottoporre a test. Osservate come il segmento di prova 1 e il segmento di test 2 ora risalgono solo al 70% dei dispositivi totali.

   ![](assets/test-segment-holdout-selected.png)

1. Seguite il resto dei passaggi nel **[!UICONTROL Create Test Group]** flusso di lavoro e selezionate **[!UICONTROL Finalize Group]** quando siete soddisfatti della selezione. Ora hai un gruppo di test con parte dell&#39;audience trattenuta dai test.
