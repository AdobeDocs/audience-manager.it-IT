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


# Rapporti di sovrapposizione: Aggiorna pianificazione e Dimensioni segmento minime{#overlap-reports-update-schedule-and-minimum-segment-size}

Descrive le dimensioni del segmento e i requisiti di creazione necessari per il processo di aggiornamento dei rapporti di sovrapposizione.

## Aggiorna pianificazione e requisiti {#update-schedule}

[!UICONTROL Overlap] i rapporti vengono aggiornati settimanalmente a domenica. L&#39;pre-elaborazione dei report inizia sabato. Questo incide sul modo in cui i segmenti nuovi o esistenti vengono visualizzati in un rapporto di sovrapposizione lunedì. Per essere inclusi in un rapporto di sovrapposizione:

* Durante gli ultimi 14 giorni, un segmento deve contenere almeno 70,000 utenti in tempo reale totale. Ulteriori informazioni [sui Requisiti minimi di visitatori per Caratteristiche e Segmenti](../../reporting/report-sampling.md#data-sampling-ratio).
* Un segmento deve essere stato creato prima di 12 AM UTC (2 giorni interi prima dell&#39;inizio del processo di aggiornamento settimanale del rapporto di sovrapposizione).
* La tua azienda deve essere un [!DNL Audience Manager] cliente completo. Contatta il [!DNL Audience Manager] tuo consulente o l&#39;Assistenza clienti per saperne di più.

## La dimensione del segmento e/o il tempo di creazione influiscono sui rapporti {#segment-size}

Se non trovi un segmento in uno [!UICONTROL Overlap] dei rapporti, potrebbe esserlo perché il segmento non soddisfa questi requisiti minimi.

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
   <td colname="col2"> <p>Diciamo che crei un segmento prima di 12 AM UTC, ma contiene meno di 70,000 utenti in tempo reale. Questo segmento non verrà visualizzato in un rapporto <span class="wintitle"> di sovrapposizione</span> finché non soddisfa i requisiti di soglia dell'utente. Nota, inoltre, il segmento deve soddisfare il conteggio richiesto per il periodo di taglio del giovedì. Se non soddisfa la scadenza settimanale, il segmento apparirà nei report <span class="wintitle"> di sovrapposizione</span> per la settimana dopo l'esecuzione dei prossimi dati domenica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento creato troppo tardi</b> </p> </td> 
   <td colname="col2"> <p>Supponiamo che tu sia in grado di creare un segmento venerdì e contenga oltre 70,000 utenti in tempo reale. Questo segmento non verrà visualizzato nei rapporti <span class="wintitle"> di sovrapposizione</span> per la settimana successiva, perché è stato creato meno di 2 giorni prima del periodo di aggiornamento del rapporto. Tuttavia, il segmento verrà visualizzato in un rapporto <span class="wintitle"> di sovrapposizione</span> dopo il prossimo aggiornamento settimanale. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Rapporto di sovrapposizione caratteristica-caratteristica](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapporto di sovrapposizione segmento-caratteristica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapporto di sovrapposizione segmento-segmento](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

