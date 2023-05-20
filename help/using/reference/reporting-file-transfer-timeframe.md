---
description: Audience Manager riceve una quantità enorme di dati ogni giorno. Ciò influisce sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive come questi intervalli di tempo influiscono sul tuo account di Audience Manager. Inoltre, le tempistiche e le pianificazioni qui descritte sono solo linee guida generali. Tali pianificazioni non costituiscono accordi sui livelli di servizio (SLA) o impegni relativi alla distribuzione dei dati. Adobe si riserva il diritto di modificare le tempistiche e i programmi in qualsiasi momento senza preavviso.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: Influenza dei tempi di distribuzione dei dati ed elaborazione dei file sui report
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 4%

---

# Influenza dei tempi di distribuzione dei dati ed elaborazione dei file sui report{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager riceve una quantità enorme di dati ogni giorno. Ciò influisce sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive come questi intervalli di tempo influiscono sul tuo account di Audience Manager. Inoltre, le tempistiche e le pianificazioni qui descritte sono solo linee guida generali. Tali pianificazioni non costituiscono accordi sui livelli di servizio (SLA) o impegni relativi alla distribuzione dei dati. Adobe si riserva il diritto di modificare le tempistiche e i programmi in qualsiasi momento senza preavviso.

## Numeri di reporting {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Nella tabella seguente sono elencati e descritti gli intervalli di tempo nei report generali e in tempo reale.


| Tipo di dati | Descrizione |
|---|---|
| Dati in tempo reale | I numeri in tempo reale per oggi si riferiscono alle ore 00:00-23:59:59 UTC da ieri. |
| Dati generali dei rapporti | I dati in [Rapporti generali](../reporting/general-reports.md#general-reports-overview) dipende dal completamento riuscito di altri processi di processo e dalla quantità di dati ricevuti per un determinato giorno. Nella maggior parte dei casi, [!UICONTROL General Report] I dati devono essere aggiornati entro le 18:00 UTC di ogni giorno. |

## Trasferimenti di file in entrata e in uscita {#inbound-outbound-file-transfers}

[!DNL Audience Manager] elabora e invia in entrata e in uscita [!UICONTROL Server-to-Server (S2S)] trasferimenti di file in base alle pianificazioni descritte in questa sezione. Dati questi programmi e i tempi di cut-off, potresti notare delle discrepanze con i nuovi segmenti tra numeri di segmento in tempo reale e numeri di segmento totali.

| Tipo file | Descrizione |
|---|---|
| Acquisizione di file in entrata (dati offline) | L’elaborazione dei file viene eseguita due volte al giorno. Queste procedure acquisiscono i dati e li preparano per la consegna. I tempi di consegna dei file variano perché dipendono dalla quantità totale di dati del cliente da elaborare. Dovresti aspettarti una latenza massima di 48 ore tra il momento in cui il file viene caricato in Audience Manager e finché i dati non saranno disponibili per il reporting e l’attivazione. |
| File in uscita (esportazione) | L’elaborazione dei file e la consegna avviene una volta al giorno, circa alle 14:00 UTC. Tieni presente che l’elaborazione e la consegna sono influenzate dal numero totale e dalle dimensioni di questi file. In alcuni casi, potrebbe verificarsi un ritardo nell’elaborazione dei file fino a 24 ore. In questo caso, Audience Manager invierà 2 file per una giornata particolare anziché 1. Informeremo i nostri clienti nel raro caso in cui Audience Manager debba interrompere completamente l’elaborazione di un file. Date queste condizioni, è difficile stimare i tempi di consegna dei dati in uscita. Per determinare se hai ricevuto un set completo di file, controlla la marca temporale e cerca eventuali giorni mancanti. Timestamp UNIX UTC a 13 cifre che registra l&#39;ora di creazione del file. Consulta [Trasferimenti di dati in uscita in tempo reale](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| File di registro di Ad Server | L’elaborazione dei file viene eseguita quasi in tempo reale per acquisire i record dei file di registro quando i file orari sono pronti. Il processo di preparazione dei file per il reporting viene eseguito una volta al giorno. I tempi di consegna dei file variano perché dipendono dalla quantità totale di dati del cliente da elaborare. Dovresti aspettarti una latenza massima di 48 ore tra il momento in cui carichi il file in Audience Manager e il momento in cui i dati sono disponibili per il reporting e l’attivazione. |

>[!MORELIKETHIS]
>
>* [Domande frequenti sull’acquisizione dei dati dei clienti in entrata](../faq/faq-inbound-data-ingestion.md)

