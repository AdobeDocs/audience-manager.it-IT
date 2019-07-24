---
description: Descrive le dimensioni del segmento e i requisiti di creazione necessari per il processo di aggiornamento dei rapporti di sovrapposizione.
seo-description: Descrive le dimensioni del segmento e i requisiti di creazione necessari per il processo di aggiornamento dei rapporti di sovrapposizione.
seo-title: Pianificazione aggiornamento rapporti di sovrapposizione e dimensioni minime dei segmenti
solution: Audience Manager
title: Pianificazione aggiornamento rapporti di sovrapposizione e dimensioni minime dei segmenti
uuid: 35 c 1 cb 39-e 28 d -4 d 20-88 c 9-5 ff 4 fe 154 e 9 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

Descrive le dimensioni del segmento e i requisiti di creazione necessari per il processo di aggiornamento dei rapporti di sovrapposizione.

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] i rapporti vengono aggiornati settimanalmente a domenica. L'pre-elaborazione dei report inizia sabato. Questo incide sul modo in cui i segmenti nuovi o esistenti vengono visualizzati in un rapporto di sovrapposizione lunedì. Per essere inclusi in un rapporto di sovrapposizione:

* Durante gli ultimi 14 giorni, un segmento deve contenere almeno 70,000 utenti in tempo reale totale. Read more about [Minimum Unique Visitor Requirements for Traits and Segments](../../reporting/report-sampling.md#data-sampling-ratio).
* Un segmento deve essere stato creato prima di 12 AM UTC (2 giorni interi prima dell'inizio del processo di aggiornamento settimanale del rapporto di sovrapposizione).
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

If you do not see a segment in one of the [!UICONTROL Overlap] reports, it may be because the segment does not meet these minimum requirements.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Dimensioni segmento troppo piccole</b> </p> </td> 
   <td colname="col2"> <p>Diciamo che crei un segmento prima di 12 AM UTC, ma contiene meno di 70,000 utenti in tempo reale. This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. Nota, inoltre, il segmento deve soddisfare il conteggio richiesto per il periodo di taglio del giovedì. If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento creato troppo tardi</b> </p> </td> 
   <td colname="col2"> <p>Supponiamo che tu sia in grado di creare un segmento venerdì e contenga oltre 70,000 utenti in tempo reale. This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Rapporto di sovrapposizione caratteristica-caratteristica](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapporto di sovrapposizione segmento-caratteristica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapporto di sovrapposizione segmento-segmento](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

