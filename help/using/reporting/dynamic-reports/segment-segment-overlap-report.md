---
description: Restituisce i dati sul numero di utenti univoci condivisi tra i segmenti.
seo-description: Restituisce i dati sul numero di utenti univoci condivisi tra i segmenti.
seo-title: Rapporto di sovrapposizione segmento-segmento
solution: Audience Manager
title: Rapporto di sovrapposizione segmento-segmento
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 4%

---


# Rapporto di sovrapposizione segmento-segmento{#segment-to-segment-overlap-report}

Restituisce i dati sul numero di utenti univoci condivisi tra i segmenti.

>[!NOTE]
>
>I rapporti di sovrapposizione in  Audience Manager rispettano i principi RBAC. Puoi visualizzare solo i segmenti provenienti da origini dati a cui hai accesso in base al gruppo [di utenti](/help/using/features/administration/administration-overview.md) RBAC a cui appartieni.

<!-- 

c_segment_segment_overlap.xml

 -->

## Panoramica

Il [!UICONTROL Segment-to-Segment Overlap] rapporto può essere utile:

* Identifica i segmenti con sovrapposizione alta o bassa, a seconda delle tue esigenze. Le caratteristiche con sovrapposizione elevata ti consentono di ottenere un pubblico mirato, ma meno visitatori unici. Le caratteristiche con una sovrapposizione ridotta possono essere utili per raggiungere un set di visitatori unico e più grande.
* Trovate sovrapposizioni impreviste e utilizzate tali informazioni per creare nuovi segmenti ad alte prestazioni.

## Report di esempio

L&#39;illustrazione seguente fornisce una panoramica di alto livello del [!UICONTROL Segment-to-Segment Overlap] rapporto.

>[!NOTE]
>
>Il [!UICONTROL Segment-to-Segment Overlap] rapporto restituisce un campo vuoto se confronta lo stesso segmento con se stesso.

![](assets/segment-to-segment-overlap.png)

## Approfondisci i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Segment-to-Segment Overlap Data Fields Definito {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La finestra a comparsa per il [!UICONTROL Segment-to-Segment Overlap] rapporto contiene le metriche riportate di seguito. La metrica univoca nella tabella rappresenta gli utenti *in tempo* reale.

| Metrica | Descrizione |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numerico univoco per il segmento che viene visualizzato nei risultati del rapporto. Viene visualizzato come ID riga per il segmento. |
| **[!UICONTROL Base Segment Name]** | Nome del segmento visualizzato nella riga dei risultati del rapporto. |
| **[!UICONTROL Overlapping Segment ID]** | ID numerico univoco per il segmento selezionato durante l&#39;esecuzione del rapporto. Viene visualizzato come ID colonna per il segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nome del segmento selezionato durante l&#39;esecuzione del rapporto. Viene visualizzata nella colonna dei risultati del rapporto. |
| **[!UICONTROL Base Segment Uniques]** | Il numero di visitatori unici nel segmento di base. |
| **[!UICONTROL Base Segment Uniques]** | Numero di visitatori univoci nel segmento sovrapposto. |
| **[!UICONTROL Overlapping Uniques]** | Il numero di visitatori univoci condivisi tra segmenti confrontati. |
| **[!UICONTROL Overlap %]** | Per ottenere la sovrapposizione %,  Audience Manager utilizza la seguente formula: Sovrapposizione Di Uniche / (Uniche Segmenti Di Base + Sovrapposizione Di Segmenti - Sovrapposizione Di Uniche Analisi) |



>[!MORELIKETHIS]
>
>* [Filtra i risultati dei report con i cursori dei dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei rapporti interattivi](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Informazioni su icone e strumenti del rapporto](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: Aggiorna pianificazione e dimensione minima del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento dei dati e tassi di errore in report selezionati  Audience Manager...](../../reporting/report-sampling.md)
>* [File CSV per rapporti di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)