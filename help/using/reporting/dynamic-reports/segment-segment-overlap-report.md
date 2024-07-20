---
description: Restituisce i dati sul numero di utenti univoci condivisi tra i segmenti.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Rapporto di sovrapposizione segmento-segmento
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 6%

---

# Rapporto di sovrapposizione segmento-segmento{#segment-to-segment-overlap-report}

Restituisce i dati sul numero di utenti univoci condivisi tra i segmenti.

>[!NOTE]
>
>I rapporti di sovrapposizione di cui all’Audience Manager rispettano i principi RBAC. Puoi visualizzare solo i segmenti dalle origini dati a cui hai accesso in base al [gruppo di utenti RBAC](/help/using/features/administration/administration-overview.md) a cui appartieni.

<!-- 

c_segment_segment_overlap.xml

 -->

## Panoramica

Il report [!UICONTROL Segment-to-Segment Overlap] consente di:

* Identifica i segmenti con sovrapposizione alta o bassa, a seconda delle tue esigenze. Le caratteristiche con sovrapposizione elevata forniscono un pubblico mirato, ma meno visitatori univoci. Le caratteristiche con una bassa sovrapposizione possono essere utili per raggiungere un set di visitatori più grande e univoco.
* Trova sovrapposizioni impreviste e utilizza tali informazioni per creare nuovi segmenti ad alte prestazioni.

## Report di esempio

Nella figura seguente viene fornita una panoramica di alto livello del report [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>Il report [!UICONTROL Segment-to-Segment Overlap] restituisce un campo vuoto quando confronta lo stesso segmento con se stesso.

![](assets/segment-to-segment-overlap.png)

## Espandere i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra popup. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Campi pop dati di sovrapposizione segmento-segmento definiti {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La finestra a comparsa per il report [!UICONTROL Segment-to-Segment Overlap] contiene le metriche seguenti. La metrica Unique nella tabella rappresenta i tuoi *utenti in tempo reale*.

| Metrica | Descrizione |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numerico univoco per il segmento visualizzato nei risultati del rapporto. Viene visualizzato come ID riga per il segmento. |
| **[!UICONTROL Base Segment Name]** | Nome del segmento visualizzato nella riga dei risultati del rapporto. |
| **[!UICONTROL Overlapping Segment ID]** | ID numerico univoco per il segmento selezionato durante l’esecuzione del rapporto. Viene visualizzato come ID di colonna per il segmento. |
| **[!UICONTROL Overlapping Segment Name]** | Nome del segmento selezionato durante l’esecuzione del rapporto. Viene visualizzato nella colonna dei risultati del report. |
| **[!UICONTROL Base Segment Uniques]** | Il numero di visitatori univoci nel segmento di base. |
| **[!UICONTROL Base Segment Uniques]** | Il numero di visitatori univoci nel segmento sovrapposto. |
| **[!UICONTROL Overlapping Uniques]** | Il numero di visitatori univoci condivisi tra i segmenti confrontati. |
| **[!UICONTROL Overlap %]** | Per ottenere la percentuale di sovrapposizione, Audience Manager utilizza la seguente formula: Univoci sovrapposti / (Univoci segmento di base + Univoci segmento sovrapposti - Univoci sovrapposti) |



>[!MORELIKETHIS]
>
>* [Filtrare i risultati dei report con i cursori di dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei report interattivi](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Icone e strumenti di report spiegati](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento di dati e tassi di errore nei report di Audienci Manager selezionati...](../../reporting/report-sampling.md)
>* [File CSV per report di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)
