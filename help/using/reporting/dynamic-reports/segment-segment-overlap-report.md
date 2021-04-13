---
description: Restituisce dati sul numero di utenti univoci condivisi tra i segmenti.
seo-description: Restituisce dati sul numero di utenti univoci condivisi tra i segmenti.
seo-title: Rapporto di sovrapposizione segmento-segmento
solution: Audience Manager
title: Rapporto di sovrapposizione segmento-segmento
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Rapporti di sovrapposizione
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 11%

---

# Rapporto di sovrapposizione segmento-segmento{#segment-to-segment-overlap-report}

Restituisce dati sul numero di utenti univoci condivisi tra i segmenti.

>[!NOTE]
>
>I rapporti di sovrapposizione in Audience Manager aderiscono ai principi RBAC. Puoi visualizzare solo i segmenti dalle origini dati a cui hai accesso in base al [Gruppo di utenti RBAC](/help/using/features/administration/administration-overview.md) a cui appartieni.

<!-- 

c_segment_segment_overlap.xml

 -->

## Panoramica

Il rapporto [!UICONTROL Segment-to-Segment Overlap] può aiutarti a:

* Identifica i segmenti con sovrapposizione alta o bassa, a seconda delle tue esigenze. Le caratteristiche con elevata sovrapposizione ti danno un pubblico mirato, ma meno visitatori unici. Le caratteristiche con sovrapposizione bassa possono essere utili per raggiungere un set di visitatori unico e più grande.
* Trova sovrapposizioni impreviste e utilizza tali informazioni per creare nuovi segmenti ad alte prestazioni.

## Report di esempio

La figura seguente fornisce una panoramica di alto livello del rapporto [!UICONTROL Segment-to-Segment Overlap] .

>[!NOTE]
>
>Il rapporto [!UICONTROL Segment-to-Segment Overlap] restituisce un campo vuoto se confronta lo stesso segmento con se stesso.

![](assets/segment-to-segment-overlap.png)

## Approfondisci i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Campi pop dati di sovrapposizione segmento-segmento definiti {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La finestra a comparsa del rapporto [!UICONTROL Segment-to-Segment Overlap] contiene le metriche riportate di seguito. La metrica univoca nella tabella rappresenta gli *utenti in tempo reale*.

| Metrica | Descrizione |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numerico univoco per il segmento visualizzato nei risultati del rapporto. Viene visualizzato come ID riga per il segmento. |
| **[!UICONTROL Base Segment Name]** | Nome del segmento visualizzato nella riga dei risultati del rapporto. |
| **[!UICONTROL Overlapping Segment ID]** | ID numerico univoco per il segmento selezionato durante l’esecuzione del rapporto. Viene visualizzato come ID colonna per il segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nome del segmento selezionato durante l’esecuzione del rapporto. Viene visualizzata nella colonna dei risultati del rapporto. |
| **[!UICONTROL Base Segment Uniques]** | Il numero di visitatori unici nel segmento di base. |
| **[!UICONTROL Base Segment Uniques]** | Il numero di visitatori unici nel segmento sovrapposto. |
| **[!UICONTROL Overlapping Uniques]** | Il numero di visitatori univoci condivisi tra segmenti confrontati. |
| **[!UICONTROL Overlap %]** | Per ottenere la percentuale di sovrapposizione, l&#39;Audience Manager utilizza la seguente formula: Sovrapposizione di Uniques / (Unici Segmenti Di Base + Sovrapposizione Di Segmenti Unici - Sovrapposizione Di Uniche Analisi) |



>[!MORELIKETHIS]
>
>* [Filtrare i risultati dei report con i cursori di dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei rapporti interattivi](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Spiegazione di icone e strumenti del rapporto](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento di dati e tassi di errore nei report selezionati di Audience Manager...](../../reporting/report-sampling.md)
>* [File CSV per report di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)

