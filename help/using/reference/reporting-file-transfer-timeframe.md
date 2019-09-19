---
description: Audience Manager riceve una quantità enorme di dati ogni giorno. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive in che modo questi intervalli temporali influiscono sul vostro account Audience Manager. Inoltre, i tempi e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.
seo-description: Audience Manager riceve una quantità enorme di dati ogni giorno. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive in che modo questi intervalli temporali influiscono sul vostro account Audience Manager. Inoltre, i tempi e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.
seo-title: Come la consegna dei dati e i tempi di elaborazione dei file influiscono sui report
solution: Audience Manager
title: Come la consegna dei dati e i tempi di elaborazione dei file influiscono sui report
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Come la consegna dei dati e i tempi di elaborazione dei file influiscono sui report{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager riceve una quantità enorme di dati ogni giorno. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive in che modo questi intervalli temporali influiscono sul vostro account Audience Manager. Inoltre, i tempi e i programmi qui descritti sono solo linee guida generali. Tali programmi non costituiscono accordi a livello di servizio (SLA) o impegni relativi alla consegna dei dati. Adobe si riserva il diritto di modificare i tempi e gli orari in qualsiasi momento senza preavviso.

## Numeri di reporting {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Nella tabella seguente sono elencati e descritti gli intervalli temporali nei nostri rapporti in tempo reale e generale.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di dati </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Dati in tempo reale</b> </p> </td> 
   <td colname="col2"> <p> I numeri in tempo reale per oggi sono per le ore da 00:00 a 23:59:59 UTC da ieri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Dati generali del rapporto</b> </p> </td> 
   <td colname="col2"> <p>I dati contenuti nei <a href="../reporting/general-reports.md#general-reports-overview"> Rapporti</a> generali dipendono dal completamento riuscito di altri processi di lavoro e dalla quantità di dati ricevuti per un giorno specifico. Nella maggior parte dei casi, i dati del rapporto <span class="wintitle"></span> generale devono essere aggiornati ogni giorno alle 18:00 UTC. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trasferimenti di file in entrata e in uscita {#inbound-outbound-file-transfers}

[!DNL Audience Manager] elabora e invia trasferimenti di [!UICONTROL Server-to-Server (S2S)] file in entrata e in uscita in base ai programmi descritti in questa sezione. Date queste pianificazioni e i tempi di interruzione, potrebbero verificarsi discrepanze con i nuovi segmenti tra i numeri dei segmenti in tempo reale e totale.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Ingestione file in ingresso (dati offline)</b> </p> </td> 
   <td colname="col2"> <p>L'elaborazione del file viene eseguita due volte al giorno. Queste procedure consentono di acquisire i dati e prepararli per la consegna. </p> <p>I tempi di consegna dei file variano a causa della quantità totale di dati cliente che devono essere elaborati. Dovrebbe essere prevista una latenza massima di 48 ore tra il momento in cui il file viene caricato in <span class="keyword"> Audience Manager</span> e fino a quando i dati non sono disponibili per il reporting e l’attivazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>File in uscita (esportazione)</b> </p> </td> 
   <td colname="col2"> <p>L'elaborazione e la consegna dei file avviene una volta al giorno, alle 14:00 UTC circa. Tenere presente che l'elaborazione e la consegna sono influenzate dal numero totale e dalla dimensione di questi file. In alcuni casi, potrebbe verificarsi un ritardo nell'elaborazione del file per un periodo di 24 ore. In questo caso, <span class="keyword"> Audience Manager</span> invierà 2 file per un giorno particolare invece di 1. Informeremo i nostri clienti nel raro caso in cui <span class="keyword"> Audience Manager</span> debba interrompere completamente l'elaborazione di un file. Date queste condizioni, è difficile stimare i tempi di consegna per i dati in uscita. </p> <p>Per determinare se hai ricevuto un set completo di file, controlla la marca temporale e cerca eventuali giorni mancanti. Marca temporale UNIX UTC di 13 cifre che registra l'ora di creazione del file. Consulta Trasferimenti <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"></a>di dati in uscita in tempo reale. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_this]
>
>* [Domande frequenti sull'inserimento dei dati dei clienti in entrata](../faq/faq-inbound-data-ingestion.md)

