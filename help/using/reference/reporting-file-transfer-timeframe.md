---
description: L'Audience Manager riceve una quantità enorme di dati ogni giorno. Questo influisce sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive come questi intervalli di tempo influiscono sul tuo account di Audience Manager. Inoltre, le tempistiche e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. L'Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.
seo-description: L'Audience Manager riceve una quantità enorme di dati ogni giorno. Questo influisce sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive come questi intervalli di tempo influiscono sul tuo account di Audience Manager. Inoltre, le tempistiche e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. L'Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.
seo-title: Influenza dei tempi di distribuzione dei dati ed elaborazione dei file sui report
solution: Audience Manager
title: Influenza dei tempi di distribuzione dei dati ed elaborazione dei file sui report
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: riferimento
translation-type: tm+mt
source-git-commit: c3c2f32dda7535b182ea3638a016fe245ed4894c
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 5%

---


# Influenza dei tempi di distribuzione dei dati ed elaborazione dei file sui report{#how-data-delivery-and-file-processing-times-affect-reports}

L&#39;Audience Manager riceve una quantità enorme di dati ogni giorno. Questo influisce sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive come questi intervalli di tempo influiscono sul tuo account di Audience Manager. Inoltre, le tempistiche e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. L&#39;Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.

## Numeri di reporting {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

La tabella seguente elenca e descrive gli intervalli di tempo nei nostri rapporti in tempo generale e in tempo reale.


| Tipo di dati | Descrizione |
|---|---|
| Dati in tempo reale | I numeri in tempo reale per oggi sono per le ore 00:00 - 23:59:59 UTC da ieri. |
| Dati generali dei rapporti | I dati contenuti nei [Rapporti generali](../reporting/general-reports.md#general-reports-overview) dipendono dal completamento corretto di altri processi di lavoro e dalla quantità di dati ricevuti per un giorno specifico. Nella maggior parte dei casi, i dati [!UICONTROL General Report] devono essere aggiornati ogni giorno entro le 18:00 UTC. |

## Trasferimenti di file in entrata e in uscita {#inbound-outbound-file-transfers}

[!DNL Audience Manager] elabora e invia i trasferimenti di  [!UICONTROL Server-to-Server (S2S)] file in entrata e in uscita in base ai programmi descritti in questa sezione. Dati questi programmi e i tempi di cut-off, potresti notare discrepanze con i nuovi segmenti tra i numeri dei segmenti in tempo reale e totale.

| Tipo file | Descrizione |
|---|---|
| Acquisizione file in entrata (dati offline) | L’elaborazione dei file viene eseguita due volte al giorno. Queste procedure acquisiscono i dati e li preparano per la consegna. I tempi di consegna dei file variano perché sono influenzati dalla quantità totale di dati cliente che devono essere elaborati. È prevista una latenza massima di 48 ore tra il momento in cui il file viene caricato in Audience Manager e fino a quando i dati non sono disponibili per la generazione di rapporti e l’attivazione. |
| File in uscita (esportazione) | L’elaborazione e la consegna dei file avviene una volta al giorno, alle 14:00 UTC circa. Tieni presente che l’elaborazione e la consegna sono influenzate dal numero totale e dalle dimensioni di questi file. In alcuni casi, potrebbe verificarsi un ritardo nell’elaborazione dei file per un periodo di 24 ore. In questo caso, Audience Manager invierà 2 file per un giorno specifico invece di 1. Informeremo i nostri clienti nel raro caso in cui Audience Manager debba interrompere l’elaborazione di un file. Date queste condizioni, è difficile stimare i tempi di consegna per i dati in uscita. Per determinare se hai ricevuto un set completo di file, controlla la marca temporale e cerca eventuali giorni mancanti. Si tratta di un timestamp UNIX UTC a 13 cifre che registra l’ora in cui è stato creato il file. Consulta [Trasferimenti di dati in uscita in tempo reale](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| File di registro di Ad Server | L&#39;elaborazione dei file viene eseguita in tempo quasi reale per acquisire i record dei file di registro quando i file orari sono pronti. Il processo di preparazione dei file per il reporting viene eseguito una volta al giorno. I tempi di consegna dei file variano perché sono influenzati dalla quantità totale di dati cliente che devono essere elaborati. Dovresti aspettarti una latenza massima di 48 ore tra il momento in cui carichi il file in Audience Manager e il momento in cui i dati sono disponibili per la generazione di rapporti e l’attivazione. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>
>* [Domande frequenti sull’acquisizione dei dati dei clienti in entrata](../faq/faq-inbound-data-ingestion.md)

