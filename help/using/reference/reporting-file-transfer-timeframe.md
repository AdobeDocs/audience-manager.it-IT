---
description: ' Audience Manager riceve un''enorme quantità di dati ogni giorno. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive in che modo questi intervalli temporali influiscono sul vostro account Audience Manager . Inoltre, i tempi e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.'
seo-description: ' Audience Manager riceve un''enorme quantità di dati ogni giorno. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive in che modo questi intervalli temporali influiscono sul vostro account Audience Manager . Inoltre, i tempi e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.'
seo-title: Come la consegna dei dati e i tempi di elaborazione dei file influiscono sui report
solution: Audience Manager
title: Come la consegna dei dati e i tempi di elaborazione dei file influiscono sui report
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---


# Come la consegna dei dati e i tempi di elaborazione dei file influiscono sui report{#how-data-delivery-and-file-processing-times-affect-reports}

 Audience Manager riceve un&#39;enorme quantità di dati ogni giorno. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive in che modo questi intervalli temporali influiscono sul vostro account Audience Manager . Inoltre, i tempi e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.

## Numeri di reporting {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Nella tabella seguente sono elencati e descritti gli intervalli temporali nei nostri rapporti in tempo reale e generale.


| Tipo di dati | Descrizione |
|---|---|
| Dati in tempo reale | I numeri in tempo reale per oggi sono per le ore da 00:00 a 23:59:59 UTC da ieri. |
| Dati generali del rapporto | I dati contenuti nei Rapporti [](../reporting/general-reports.md#general-reports-overview) generali dipendono dal completamento riuscito di altri processi di lavoro e dalla quantità di dati ricevuti per un giorno specifico. Nella maggior parte dei casi, [!UICONTROL General Report] i dati devono essere aggiornati ogni giorno entro le 18:00 UTC. |

## Trasferimenti di file in entrata e in uscita {#inbound-outbound-file-transfers}

[!DNL Audience Manager] elabora e invia trasferimenti di [!UICONTROL Server-to-Server (S2S)] file in entrata e in uscita in base ai programmi descritti in questa sezione. Date queste pianificazioni e i tempi di interruzione, potrebbero verificarsi discrepanze con i nuovi segmenti tra i numeri dei segmenti in tempo reale e totale.

| Tipo file | Descrizione |
|---|---|
| Ingestione file in ingresso (dati offline) | L&#39;elaborazione del file viene eseguita due volte al giorno. Queste procedure consentono di acquisire i dati e prepararli per la consegna. I tempi di consegna dei file variano a causa della quantità totale di dati cliente che devono essere elaborati. È prevista una latenza massima di 48 ore tra il momento in cui il file viene caricato in  Audience Manager e fino a quando i dati non sono disponibili per il reporting e l’attivazione. |
| File in uscita (esportazione) | L&#39;elaborazione e la consegna dei file avvengono una volta al giorno, alle 14:00 UTC circa. Tenere presente che l&#39;elaborazione e la consegna sono influenzate dal numero totale e dalla dimensione di questi file. In alcuni casi, potrebbe verificarsi un ritardo nell&#39;elaborazione del file per un periodo di 24 ore. In questo caso,  Audience Manager invierà 2 file per un giorno particolare invece di 1. Nel raro caso in cui  Audience Manager debba interrompere l&#39;elaborazione di un file, verrà inviata una notifica ai nostri clienti. Date queste condizioni, è difficile stimare i tempi di consegna per i dati in uscita. Per determinare se hai ricevuto un set completo di file, controlla la marca temporale e cerca eventuali giorni mancanti. Marca temporale UNIX UTC di 13 cifre che registra l&#39;ora di creazione del file. Consulta Trasferimenti [di dati in uscita in tempo](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)reale. |
| File di registro Ad Server | L&#39;elaborazione dei file viene eseguita in tempo quasi reale per l&#39;acquisizione dei record dei file di registro quando i file orari sono pronti. Il processo di preparazione dei file per il reporting viene eseguito una volta al giorno. I tempi di consegna dei file variano a causa della quantità totale di dati cliente che devono essere elaborati. È prevista una latenza massima di 48 ore tra il momento in cui caricate il file su  Audience Manager e il momento in cui i dati sono disponibili per il reporting e l’attivazione. |

>[!MORELIKETHIS]
>
>* [Domande frequenti sull&#39;inserimento dei dati dei clienti in entrata](../faq/faq-inbound-data-ingestion.md)

