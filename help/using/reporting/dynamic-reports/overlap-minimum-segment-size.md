---
description: Descrive le dimensioni del segmento e i requisiti relativi al tempo di creazione richiesti dal processo di aggiornamento del rapporto di sovrapposizione.
seo-description: Descrive le dimensioni del segmento e i requisiti relativi al tempo di creazione richiesti dal processo di aggiornamento del rapporto di sovrapposizione.
seo-title: Sovrapponi rapporti Programma di aggiornamento e Dimensione minima del segmento
solution: Audience Manager
title: Sovrapponi rapporti Programma di aggiornamento e Dimensione minima del segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 33d844578c5cd620f9d4c33ec931ae0778aabb07
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---


# Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti{#overlap-reports-update-schedule-and-minimum-segment-size}

Descrive i requisiti di caratteristiche e dimensioni del segmento e tempo di creazione richiesti dal processo di aggiornamento del rapporto di sovrapposizione.

## Aggiorna pianificazione e requisiti {#update-schedule}

[!UICONTROL Overlap] i report vengono aggiornati settimanalmente la domenica. La pre-elaborazione dei report inizia il sabato. Questo incide sul modo in cui i segmenti nuovi o esistenti vengono visualizzati in un rapporto di sovrapposizione lunedì. Per essere incluso in un rapporto di sovrapposizione:

* Un segmento deve contenere almeno 70.000 utenti in tempo reale totali negli ultimi 14 giorni.
* Una caratteristica deve contenere 28.000 [realizzazioni di caratteristiche univoche](/help/using/features/traits/trait-and-segment-qualification-reference.md) negli ultimi 14 giorni.
* Un segmento deve essere stato creato prima delle 12:00 del giovedì UTC (2 giorni interi prima dell’inizio del processo di aggiornamento settimanale del rapporto di sovrapposizione).
* La tua azienda deve essere un cliente [!DNL Audience Manager] completo. Contatta il tuo [!DNL Audience Manager] consulente o l&#39;Assistenza clienti per saperne di più.

## Dimensione del segmento e/o tempo di creazione influisce sul reporting {#segment-size}

Se non visualizzi un segmento in uno dei report [!UICONTROL Overlap], potrebbe essere perché il segmento non soddisfa questi requisiti minimi.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Dimensione segmento troppo piccola</b> </p> </td> 
   <td colname="col2"> <p>Supponiamo che tu crei un segmento prima delle 12:00 del giovedì UTC, ma contiene meno di 70.000 utenti in tempo reale totali. Questo segmento non verrà visualizzato in un <span class="wintitle"> report di sovrapposizione</span> finché non soddisfa i requisiti di soglia dell'utente. Inoltre, il segmento deve soddisfare il numero di utenti richiesto o prima del periodo di interruzione di giovedì. Se non soddisfa la scadenza settimanale, il segmento verrà visualizzato nei <span class="wintitle"> Report di sovrapposizione</span> per la settimana successiva all'esecuzione dei dati della domenica successiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento creato troppo tardi</b> </p> </td> 
   <td colname="col2"> <p>Supponiamo che crei un segmento il venerdì e contenga più di 70.000 utenti in tempo reale. Questo segmento non verrà visualizzato nei <span class="wintitle"> report di sovrapposizione</span> per la settimana successiva perché è stato creato meno di 2 giorni prima del periodo di aggiornamento del report. Tuttavia, il segmento verrà visualizzato in un <span class="wintitle"> report di sovrapposizione</span> dopo il prossimo aggiornamento settimanale. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapporto di sovrapposizione caratteristica-caratteristica](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapporto di sovrapposizione segmento-caratteristica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapporto di sovrapposizione segmento-segmento](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

