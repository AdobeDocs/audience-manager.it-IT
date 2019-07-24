---
description: Il rapporto sullo stato di onboarding verifica i tassi di successo e di successo per l'elaborazione dei record nei file di origine dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo in forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando si crea un'origine dati in entrata.
seo-description: Il rapporto sullo stato di onboarding verifica i tassi di successo e di successo per l'elaborazione dei record nei file di origine dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo in forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando si crea un'origine dati in entrata.
seo-title: Rapporto sullo stato di onboarding
solution: Audience Manager
title: Rapporto sullo stato di onboarding
uuid: 6 ca 8 a 90 a -436 b -4 fce-adf 1-48 f 3 b 96 b 3 ed 2
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Onboarding Status Report{#onboarding-status-report-about}

Il rapporto sullo stato di onboarding verifica i tassi di successo e di successo per l'elaborazione dei record nei file di origine dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo in forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics &gt; Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando si crea un'origine dati in entrata.

>[!NOTE]
>
>Solo gli utenti con privilegi Amministratore possono visualizzare questo rapporto nell'interfaccia utente di Audience Manager. Potete ricevere agli utenti non amministratori una notifica dello stato dei file in ingresso caricato aggiungendo le e-mail al rapporto. See [Receive E-mail Notifications](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding Status Report: About {#onboarding-status-about}

Il [!UICONTROL Onboarding Status Report] (Report errori campione) verifica i tassi d’errore e di successo nell’elaborazione dei record nei propri file di origine dei dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo in forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. You can find this report in **[!UICONTROL Analytics > Onboarding Status Report]**. Questo rapporto è disponibile anche quando si crea un'origine dati in entrata.

## Error Reporting and Error Sampling {#error-reporting-sampling}

Error reporting and error sampling are 2 separate features of the [!UICONTROL Onboarding Status] report.

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Generazione di rapporti sugli errori</b> </p> </td>
   <td colname="col2"> <p>La generazione di rapporti sugli errori mostra i tassi di successo e di successo per il numero di record elaborati in un'origine dati in entrata. Restituisce i dati in un grafico a barre interattivo, a barre e come metriche di riepilogo nelle tabelle sotto il grafico. </p> <p>Il reporting degli errori è automatico. Viene eseguito continuamente per tutte le origini dati in entrata. Restituisce i dati in base a intervalli di tempo predefiniti o a un intervallo di tempo personalizzato impostato con un widget calendario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Campionamento errori</b> </p> </td>
   <td colname="col2"> <p>Il campionamento degli errori analizza il contenuto dei file di dati e restituisce gli 10 errori più comuni per ogni tipo di errore. Gli errori presenti nei file di dati in entrata impediscono l'elaborazione di singoli record. Utilizzate questo rapporto come strumento di risoluzione dei problemi per ridurre il numero di errori di file e migliorare i tassi di elaborazione. </p> <p>È necessario attivare manualmente il campionamento degli errori. Viene eseguito per 14 giorni dal giorno dell'attivazione e viene disattivato. Potete attivare nuovamente il campionamento degli errori dopo la scadenza dell'intervallo di 14 giorni. You activate error sampling when you <a href="../features/manage-datasources.md#create-data-source"> create an inbound data source</a> or by checking the <b><span class="uicontrol"> Error Sampling</span></b> check box from the <span class="wintitle"> Data Source Settings</span> section of an existing inbound data source. </p> <p>Il campionamento degli errori è un processo di elaborazione informatica. Di conseguenza, restituisce solo i primi errori 10 per ogni categoria di errore. Non è progettato per restituire ogni errore contenuto in un'origine dati in entrata. Questi errori sono un esempio rappresentativo di un gruppo potenzialmente più ampio di errori simili. Rivedete l'intero file per i tipi di errori segnalati da questo rapporto, riformattate il file e inviatelo di nuovo. </p> <p>See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for more information about how to properly format an data file for an inbound data source. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Error Report Bar Chart {#error-report-bar-chart}

L'errore dei report genera i tassi di successo e di successo per l'elaborazione del record in un grafico a barre sovrapposte, come illustrato nell'esempio seguente. Il grafico è interattivo. Facendo clic su una barra, vengono visualizzate le metriche di riepilogo per quel giorno in una tabella sotto il grafico.

![](assets/stacked-graph.png)

## Error Report Tables {#error-report-tables}

Il rapporto di errore visualizza i dati di tabulazione sotto il grafico a barre. La tabella mostra percentuali di successo e di successo insieme ai totali e alle percentuali.

**Record riusciti e non riusciti**

Questa visualizzazione predefinita mostra un conteggio delle frequenze dei record totali nel rapporto e include una suddivisione degli errori per tipo di errore.

![](assets/success-failure.png)

**Totali e percentuali**

Click **[!UICONTROL Totals & Percentages]** to see what % of your files were processed successfully.

![](assets/totals-percentages.png)

## Error Sampling Report for 14 Days {#error-reporting-14-days}

Con il campionamento degli errori attivo, il rapporto mostrerà i primi 10 errori per ogni tipo di errore. Fate clic sul pulsante di un tipo di errore nella parte superiore del rapporto per visualizzare ogni insieme di dati campionati.

>[!NOTE]
>
>Il rapporto non evidenzia gli errori di record con la versione corrente. To find and fix file errors, you should review the results and compare those to the specifications in the [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) documentation.

![](assets/error-samples.png)

## Receive E-mail Notifications {#receive-email-notifications}

Potete aggiungere gli indirizzi e-mail dei destinatari a cui desiderate ricevere una notifica dello stato dei file in ingresso caricato. Puoi selezionare diversi destinatari per diverse origini dati.

![](assets/mail-notifications.png)

## Create an Onboarding Status Report {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] returns the number records in a data source were processed successfully and how many failed. Follow these steps to generate a [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. **[!UICONTROL Analytics > Onboarding Status Report]** Vai a. Cercare un'origine dati o selezionarne una dall'elenco.

2. Seleziona un intervallo di date. Le opzioni includono:

   * Un insieme di intervalli di report fissi.
   * Widget calendario che consentono di creare un intervallo di date personalizzato.

3. Fai clic su **[!UICONTROL OK]**.

## Onboarding Status Report Terms and Definitions {#report-terms-conditions}

Guida di riferimento per le etichette e i termini utilizzati in questo rapporto.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Termine </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Nome file sincronizzazione dati</b> </p> </td> 
   <td colname="col2"> <p>Lists files that <span class="keyword"> Audience Manager</span> received and processed from you selected inbound data source. </p> <p>L'elaborazione del file non riesce se il nome del file viene formattato in modo errato. File name requirements vary depending on how you send this data to <span class="keyword"> Audience Manager</span>. Delivery methods include <span class="keyword"> Amazon S3</span> and FTP. Per istruzioni su come denominare i file, consultate: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Requisiti di nome di Amazon S3 per file di dati in entrata </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Errori di formattazione</b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero di record che non hanno superato l'elaborazione perché non corrispondono ai requisiti di sintassi o formattazione. See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for information on how to format your data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID AAM non valido</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of improperly formatted <span class="keyword"> Audience Manager</span> user IDs (UUID). In genere indica gli ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Non corrisponde al formato previsto a 38 cifre. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contengono caratteri alfabetici. Gli ID devono essere numeri. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID dispositivo non valido</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di ID dispositivo globali non formattati. See <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a> and <a href="../features/global-data-sources.md">Global Data Sources</a>  for details on how device IDs should be formatted and what global data sources you should use, based on the device type.</p>
  <p>La sezione di campionamento degli errori del rapporto include informazioni dettagliate sugli ID dispositivo non validi, ad esempio:</p>
   <ul>
    <li>L'ID di origine dati corrispondente all'ID dispositivo non valido;</li>
    <li>L'ID dispositivo non valido;</li>
    <li>Il tipo di ID dispositivo previsto, in base all'origine dati.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Nessun ID AAM corrispondente</b> </p> </td> 
   <td colname="col2"> <p>These are onboarded IDs <span class="keyword"> Audience Manager</span> cannot match to an existing ID. Onboarded IDs can have this status when <span class="keyword"> Audience Manager</span> has not yet performed an ID sync or it still can't match the ID even after a synch. </p> <p>In the case of unmatched mobile IDs, <span class="keyword"> Audience Manager</span> will: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continuate a memorizzare e cercate di sincronizzare questo ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Record it as a <span class="wintitle"> Stored Record</span> in the report if the ID cannot be synched. </li> 
    </ul> <p>Se il file caricato contiene ID mobili, puoi trattarli un po' più leggero rispetto alle altre metriche. Essi non influenzeranno le percentuali di successo e di corrispondenza dei file successivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nessuna caratteristica</b> </p> </td> 
   <td colname="col2"> <p>Lists traits that <span class="keyword"> Audience Manager</span> cannot match to an onboarded trait. Potrebbe essere il risultato di: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Caratteristiche formattate in modo errato nel file di dati in entrata. For on how to format your data file, see <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Traits that have not yet been defined in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Percentuale di successo</b> </p> </td> 
   <td colname="col2"> <p>Percentuale di record registrati nel file. Percentuale percentuale = record elaborati/numero di record in un file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Record ricevuti</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di record ricevuti. Nella maggior parte dei casi, questo numero deve corrispondere al numero totale di record (righe) nel file di dati in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Record memorizzati</b> </p> </td> 
   <td colname="col2"> <p>Numero di record memorizzati correttamente. Because of file format errors, some of the records received may not be stored by <span class="keyword"> Audience Manager</span>. Il numero di record memorizzati può essere inferiore al numero di record ricevuti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Totale caratteristiche realizzate</b> </p> </td> 
   <td colname="col2"> <p>The number of traits for all users across all inbound files that get stored in the <span class="keyword"> Audience Manager</span> platform. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Totale segnali non utilizzati</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di segnali inutilizzati ricevuti nel report. Il totale si basa sul numero totale di record memorizzati correttamente. </p> <p>See <a href="../reporting/dynamic-reports/unused-signals.md"> Unused Signals Report</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>
