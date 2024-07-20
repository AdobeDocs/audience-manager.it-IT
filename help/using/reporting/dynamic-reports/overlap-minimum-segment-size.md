---
description: Descrive le dimensioni del segmento e i requisiti di tempo di creazione richiesti dal processo di aggiornamento del rapporto di sovrapposizione.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Pianificazione di aggiornamento dei rapporti di sovrapposizione e dimensione minima del segmento
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti{#overlap-reports-update-schedule-and-minimum-segment-size}

Descrive i requisiti relativi a dimensioni di caratteristiche e segmenti e tempi di creazione richiesti dal processo di aggiornamento del rapporto di sovrapposizione.

## Aggiorna pianificazione e requisiti {#update-schedule}

[!UICONTROL Overlap] rapporti vengono aggiornati settimanalmente la domenica. La pre-elaborazione del rapporto inizia sabato. Questo influisce sul modo in cui i segmenti nuovi o esistenti vengono visualizzati in un rapporto di sovrapposizione lunedì. Da includere in un rapporto di sovrapposizione:

* Un segmento deve contenere almeno 70.000 utenti in tempo reale totali negli ultimi 14 giorni.
* Una caratteristica deve contenere 28.000 [realizzazioni di caratteristica univoche](/help/using/features/traits/trait-and-segment-qualification-reference.md) negli ultimi 14 giorni.
* Un segmento deve essere stato creato prima delle 00:00 del giovedì UTC (2 giorni interi prima dell’inizio del processo di aggiornamento del rapporto di sovrapposizione settimanale).
* La società deve essere un cliente completo di [!DNL Audience Manager]. Contatta il tuo consulente [!DNL Audience Manager] o l&#39;Assistenza clienti per ulteriori informazioni.

## La dimensione del segmento e/o il tempo di creazione influiscono sul reporting {#segment-size}

Se in uno dei report [!UICONTROL Overlap] non viene visualizzato alcun segmento, è possibile che il segmento non soddisfi questi requisiti minimi.

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
   <td colname="col2"> <p>Supponiamo che tu crei un segmento prima delle 12 del giovedì UTC, ma contiene meno di 70.000 utenti in tempo reale totali. Questo segmento non verrà visualizzato in un report di sovrapposizione <span class="wintitle"></span> finché non soddisfa i requisiti di soglia utente. Inoltre, il segmento deve soddisfare il conteggio degli utenti richiesto per il periodo limite di giovedì o prima di esso. Se non rispetta la scadenza settimanale, il segmento verrà visualizzato nei <span class="wintitle"> rapporti di sovrapposizione</span> per la settimana successiva alla prossima esecuzione dei dati di domenica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmento Creato Troppo Tardi</b> </p> </td> 
   <td colname="col2"> <p>Supponiamo che tu crei un segmento venerdì che contiene più di 70.000 utenti in tempo reale totali. Questo segmento non verrà visualizzato nei <span class="wintitle"> report di sovrapposizione</span> per la settimana successiva perché è stato creato meno di 2 giorni prima del periodo di aggiornamento del report. Tuttavia, il segmento verrà visualizzato in un report di sovrapposizione <span class="wintitle"></span> dopo il prossimo aggiornamento settimanale. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapporto di sovrapposizione caratteristica-caratteristica](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapporto di sovrapposizione segmento-caratteristica](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapporto di sovrapposizione segmento-segmento](../../reporting/dynamic-reports/segment-segment-overlap-report.md)
