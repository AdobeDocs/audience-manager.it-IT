---
description: Audience Manager riceve ogni giorno un'enorme quantità di dati. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive come questi intervalli di tempo influiscono sul tuo account Audience Manager. Inoltre, i fotogrammi e le pianificazioni temporali descritti qui sono linee guida generali. Queste pianificazioni non sono contratti a livello di servizio (SLAS) o relativi alla consegna dei dati. Adobe si riserva il diritto di cambiare i tempi e le pianificazioni in qualsiasi momento senza preavviso.
seo-description: Audience Manager riceve ogni giorno un'enorme quantità di dati. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive come questi intervalli di tempo influiscono sul tuo account Audience Manager. Inoltre, i fotogrammi e le pianificazioni temporali descritti qui sono linee guida generali. Queste pianificazioni non sono contratti a livello di servizio (SLAS) o relativi alla consegna dei dati. Adobe si riserva il diritto di cambiare i tempi e le pianificazioni in qualsiasi momento senza preavviso.
seo-title: Come la distribuzione dei dati e i tempi di elaborazione dei file influiscono sui rapporti
solution: Audience Manager
title: Come la distribuzione dei dati e i tempi di elaborazione dei file influiscono sui rapporti
uuid: 4 b 975512-f 67 e -4749-a 7 ef -168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Come la distribuzione dei dati e i tempi di elaborazione dei file influiscono sui rapporti{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager riceve ogni giorno un&#39;enorme quantità di dati. Questo incide sul tempo necessario per elaborare i dati e generare i risultati del rapporto. Il contenuto di questa sezione descrive come questi intervalli di tempo influiscono sul tuo account Audience Manager. Inoltre, i fotogrammi e le pianificazioni temporali descritti qui sono linee guida generali. Queste pianificazioni non sono contratti a livello di servizio (SLAS) o relativi alla consegna dei dati. Adobe si riserva il diritto di cambiare i tempi e le pianificazioni in qualsiasi momento senza preavviso.

## Numeri di reporting {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Nella tabella seguente sono elencati e descritti gli intervalli temporali nei report generali e in tempo reale.

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
   <td colname="col2"> <p> I numeri in tempo reale per oggi sono per le ore 00:00 e 23:59:59 UTC da ieri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Dati rapporto generale</b> </p> </td> 
   <td colname="col2"> <p>I dati nei Report <a href="../reporting/general-reports.md#general-reports-overview"> generali</a> dipendono dal completamento di altri processi di processo e dalla quantità di dati ricevuti per un giorno particolare. La maggior parte dei casi, i dati <span class="wintitle"> generali del report</span> devono essere aggiornati da 18:00 UTC ogni giorno. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trasferimenti di file in ingresso e in uscita {#inbound-outbound-file-transfers}

[!DNL Audience Manager] elabora e invia trasferimenti [!UICONTROL Server-to-Server (S2S)] di file in entrata e in uscita in base alle pianificazioni descritte in questa sezione. Date queste pianificazioni e i tempi di taglio, potresti vedere discrepanze con i nuovi segmenti tra i numeri in tempo reale e totale.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo file </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Inserimento file in ingresso (dati offline)</b> </p> </td> 
   <td colname="col2"> <p>L'elaborazione del file viene eseguita due volte al giorno. Queste procedure assimilano i dati e preparano la distribuzione. </p> <p>I tempi di consegna dei file variano in base alla quantità totale di dati cliente da elaborare. Si dovrebbe prevedere una latenza massima di 48 ore tra il momento in cui il file viene caricato in <span class="keyword"> Audience Manager</span> e finché i dati non saranno disponibili per il reporting e l'attivazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>File in uscita (esportazione)</b> </p> </td> 
   <td colname="col2"> <p>L'elaborazione e la consegna dei file avvengono una volta al giorno, a circa 14:00 UTC. Tenere presente che l'elaborazione e la consegna sono influenzate dal numero totale e dalle dimensioni di questi file. In alcuni casi, potrebbe verificarsi un ritardo nell'elaborazione del file fino a un massimo di 24 ore. In tal caso <span class="keyword"> , Audience Manager</span> invierà 2 file per un giorno particolare invece di 1. Forniremo ai nostri clienti il raro caso in cui <span class="keyword"> Audience Manager</span> deve interrompere l'elaborazione di un file. Considerate queste condizioni, è difficile stimare i tempi di consegna per i dati in uscita. </p> <p>Per determinare se avete ricevuto un set completo di file, controllate la marca temporale e cercate eventuali giorni mancanti. Si tratta di una marca temporale UNIX UTC a 13 cifre che registra l'ora in cui è stato creato il file. Consultate <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Trasferimento di dati in tempo reale</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Domande frequenti sull&#39;assimilazione dei dati cliente](../faq/faq-inbound-data-ingestion.md)

