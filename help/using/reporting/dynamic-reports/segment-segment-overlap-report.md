---
description: Restituisce i dati sul numero di utenti univoci condivisi tra i segmenti.
seo-description: Restituisce i dati sul numero di utenti univoci condivisi tra i segmenti.
seo-title: Rapporto di sovrapposizione segmento-segmento
solution: Audience Manager
title: Rapporto di sovrapposizione segmento-segmento
uuid: 0339 eb 6 c -6355-44 a 3-9 c 46-f 159485449 d 1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# Rapporto di sovrapposizione segmento-segmento{#segment-to-segment-overlap-report}

Restituisce i dati sul numero di utenti univoci condivisi tra i segmenti.

>[!NOTE]
>
>I rapporti di sovrapposizione in Audience Manager aderiscono ai principi RBAC. Puoi visualizzare solo segmenti dalle origini dati a cui hai accesso in base al [gruppo RBAC a](/help/using/features/administration/administration-overview.md) cui appartieni.

<!-- 

c_segment_segment_overlap.xml

 -->

## Panoramica

[!UICONTROL Segment-to-Segment Overlap] Il rapporto può essere utile per:

* Identifica i segmenti con sovrapposizione elevata o bassa, a seconda delle tue esigenze. Le caratteristiche con sovrapposizione elevata offrono un pubblico di destinazione, ma meno visitatori univoci. Le caratteristiche con sovrapposizione ridotta possono essere utili per raggiungere un set di visitatori più ampio e univoco.
* Trovate sovrapposizioni impreviste e utilizzate tali informazioni per creare segmenti nuovi e ad alte prestazioni.

## Report di esempio

La seguente illustrazione fornisce una panoramica di alto livello del [!UICONTROL Segment-to-Segment Overlap] rapporto.

>[!NOTE]
>
>[!UICONTROL Segment-to-Segment Overlap] Il rapporto restituisce un campo vuoto quando confronta lo stesso segmento con se stesso.

![](assets/segment-to-segment-overlap.png)

## Approfondire i singoli punti di dati

Selezionate un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Campi pop-to-segmento di sovrapposizione segmenti definiti {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La finestra a comparsa del [!UICONTROL Segment-to-Segment Overlap] rapporto contiene le metriche riportate di seguito. Tieni presente che la metrica unificata nella tabella rappresenta gli *utenti in tempo reale*.

| Metrica | Descrizione |
|---|---|
| **[!UICONTROL Segment ID1]** | ID numerico univoco per il segmento visualizzato nei risultati del rapporto. Viene visualizzato come ID riga per il segmento. |
| **[!UICONTROL Segment ID2]** | ID numerico univoco per il segmento selezionato durante l&#39;esecuzione del rapporto. Viene visualizzato come ID colonna per il segmento. |
| **[!UICONTROL Segment Name1]** | Nome del segmento che viene visualizzato nella riga dei risultati del rapporto. |
| **[!UICONTROL Segment Name2]** | Nome del segmento selezionato durante l&#39;esecuzione del rapporto. Viene visualizzata nella colonna dei risultati del rapporto. |
| **[!UICONTROL Overlap %]** | Per ottenere la sovrapposizione %, Audience Manager usa la formula seguente: Unificazione sovrapposizione/(Uniques segmento base + Unione segmento sovrapposizione - Unificazione sovrapposizione) |
| **[!UICONTROL Overlap Uniques]** | Numero di visitatori univoci condivisi tra segmenti confrontati. |
| **[!UICONTROL Segment Uniques1]** | Numero di visitatori unici nel segmento 1. |
| **[!UICONTROL Segment Uniques2]** | Numero di visitatori unici nel segmento 2. |

>[!MORE_ LIKE_ THIS]
>
>* [Filtrare i risultati del rapporto con i cursori dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei report interattivi](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Icone e strumenti per report descritti](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: Aggiorna pianificazione e Dimensioni segmento minime](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento dei dati ed errori in Report Audience Manager selezionati…](../../reporting/report-sampling.md)
>* [File CSV per rapporti di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)