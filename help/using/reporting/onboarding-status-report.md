---
description: Il rapporto sullo stato di onboarding verifica i tassi di successo e di successo per l'elaborazione dei record nei file di origine dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo in forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando si crea un'origine dati in entrata.
seo-description: Il rapporto sullo stato di onboarding verifica i tassi di successo e di successo per l'elaborazione dei record nei file di origine dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo in forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando si crea un'origine dati in entrata.
seo-title: Rapporto sullo stato di onboarding
solution: Audience Manager
title: Rapporto sullo stato di onboarding
uuid: 6 ca 8 a 90 a -436 b -4 fce-adf 1-48 f 3 b 96 b 3 ed 2
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Rapporto sullo stato di onboarding{#onboarding-status-report-about}

Il rapporto sullo stato di onboarding verifica i tassi di successo e di successo per l&#39;elaborazione dei record nei file di origine dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo in forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics &gt; Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando si crea un&#39;origine dati in entrata.

>[!NOTE]
>
>Solo gli utenti con privilegi Amministratore possono visualizzare questo rapporto nell&#39;interfaccia utente di Audience Manager. Potete ricevere agli utenti non amministratori una notifica dello stato dei file in ingresso caricato aggiungendo le e-mail al rapporto. Consultate [Ricevere notifiche e-mail](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Rapporto sullo stato di onboarding: Informazioni {#onboarding-status-about}

Il [!UICONTROL Onboarding Status Report] (Report errori campione) verifica i tassi d’errore e di successo nell’elaborazione dei record nei propri file di origine dei dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo in forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Puoi trovare il rapporto in **[!UICONTROL Analytics > Onboarding Status Report]**. Questo rapporto è disponibile anche quando si crea un&#39;origine dati in entrata.

## Generazione di rapporti sugli errori e campionamento degli errori {#error-reporting-sampling}

Il reporting degli errori e il campionamento degli errori sono 2 funzioni separate del [!UICONTROL Onboarding Status] rapporto.

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
   <td colname="col2"> <p>Il campionamento degli errori analizza il contenuto dei file di dati e restituisce gli 10 errori più comuni per ogni tipo di errore. Gli errori presenti nei file di dati in entrata impediscono l'elaborazione di singoli record. Utilizzate questo rapporto come strumento di risoluzione dei problemi per ridurre il numero di errori di file e migliorare i tassi di elaborazione. </p> <p>È necessario attivare manualmente il campionamento degli errori. Viene eseguito per 14 giorni dal giorno dell'attivazione e viene disattivato. Potete attivare nuovamente il campionamento degli errori dopo la scadenza dell'intervallo di 14 giorni. Puoi attivare il campionamento degli errori quando <a href="../features/manage-datasources.md#create-data-source"> crei un'origine dati in entrata</a> o selezionando la <b><span class="uicontrol"> casella di controllo Campionamento</span></b> errori dalla <span class="wintitle"> sezione Impostazioni</span> origine dati di un'origine dati in ingresso esistente. </p> <p>Il campionamento degli errori è un processo di elaborazione informatica. Di conseguenza, restituisce solo i primi errori 10 per ogni categoria di errore. Non è progettato per restituire ogni errore contenuto in un'origine dati in entrata. Questi errori sono un esempio rappresentativo di un gruppo potenzialmente più ampio di errori simili. Rivedete l'intero file per i tipi di errori segnalati da questo rapporto, riformattate il file e inviatelo di nuovo. </p> <p>Vedere <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenuto del file di dati in ingresso: Sintassi, Variabili ed Esempi</a> per ulteriori informazioni su come formattare correttamente un file di dati per un'origine dati in entrata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Grafico a barre rapporto errori {#error-report-bar-chart}

L&#39;errore dei report genera i tassi di successo e di successo per l&#39;elaborazione del record in un grafico a barre sovrapposte, come illustrato nell&#39;esempio seguente. Il grafico è interattivo. Facendo clic su una barra, vengono visualizzate le metriche di riepilogo per quel giorno in una tabella sotto il grafico.

![](assets/stacked-graph.png)

## Errori di rapporto sugli errori {#error-report-tables}

Il rapporto di errore visualizza i dati di tabulazione sotto il grafico a barre. La tabella mostra percentuali di successo e di successo insieme ai totali e alle percentuali.

**Record riusciti e non riusciti**

Questa visualizzazione predefinita mostra un conteggio delle frequenze dei record totali nel rapporto e include una suddivisione degli errori per tipo di errore.

![](assets/success-failure.png)

**Totali e percentuali**

Fate clic su **[!UICONTROL Totals & Percentages]** per vedere il % dei file elaborati con successo.

![](assets/totals-percentages.png)

## Rapporto campionamento errori per 14 giorni {#error-reporting-14-days}

Con il campionamento degli errori attivo, il rapporto mostrerà i primi 10 errori per ogni tipo di errore. Fate clic sul pulsante di un tipo di errore nella parte superiore del rapporto per visualizzare ogni insieme di dati campionati.

>[!NOTE]
>
>Il rapporto non evidenzia gli errori di record con la versione corrente. Per trovare e correggere gli errori di file, è necessario esaminare i risultati e confrontarli con le specifiche contenute nella [documentazione relativa al contenuto](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) dei file di dati in ingresso.

![](assets/error-samples.png)

## Ricevere notifiche e-mail {#receive-email-notifications}

Potete aggiungere gli indirizzi e-mail dei destinatari a cui desiderate ricevere una notifica dello stato dei file in ingresso caricato. Puoi selezionare diversi destinatari per diverse origini dati.

![](assets/mail-notifications.png)

## Creare un rapporto sullo stato di onboarding {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] restituisce i record numerici in un&#39;origine dati sono stati elaborati correttamente e il numero di quelli non è riuscito. Per generare un [!UICONTROL Sample Error Report]file, effettuate le seguenti operazioni.

<!-- 

create-onboarding-status-report.xml

 -->


1. **[!UICONTROL Analytics > Onboarding Status Report]** Vai a. Cercare un&#39;origine dati o selezionarne una dall&#39;elenco.

2. Seleziona un intervallo di date. Le opzioni includono:

   * Un insieme di intervalli di report fissi.
   * Widget calendario che consentono di creare un intervallo di date personalizzato.

3. Fai clic su **[!UICONTROL OK]**.

## Termini e definizioni dei report sullo stato di iscrizione {#report-terms-conditions}

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
   <td colname="col2"> <p>Elenca i file ricevuti ed elaborati <span class="keyword"> da Audience Manager</span> dall'origine dati selezionata. </p> <p>L'elaborazione del file non riesce se il nome del file viene formattato in modo errato. I requisiti dei nomi dei file variano a seconda di come vengono inviati i dati ad <span class="keyword"> Audience Manager</span>. I metodi di consegna includono <span class="keyword"> Amazon S 3</span> e FTP. Per istruzioni su come denominare i file, consultate: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Requisiti di nome di Amazon S3 per file di dati in entrata </a> </li> 
      <li id="li_9590241AEC0C482D91C64DB760B32B0D"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md"> Requisiti di nome FTP per file di dati in entrata </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Errori di formattazione</b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero di record che non hanno superato l'elaborazione perché non corrispondono ai requisiti di sintassi o formattazione. Vedere <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenuto del file di dati in ingresso: Sintassi, Variabili ed Esempi</a> per informazioni su come formattare i dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID AAM non valido</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di ID utente <span class="keyword"> di Audience Manager</span> (UUID) formattati in modo errato. In genere indica gli ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Non corrisponde al formato previsto a 38 cifre. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contengono caratteri alfabetici. Gli ID devono essere numeri. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID dispositivo non valido</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di ID dispositivo globali non formattati. Consulta <a href="../reference/ids-in-aam.md">Indice degli ID in Audience Manager</a> e <a href="../features/global-data-sources.md">Origini dati globali</a> per informazioni su come devono essere formattati gli ID dispositivo e quali origini dati globali dovrebbero essere utilizzate, in base al tipo di dispositivo.</p>
  <p>La sezione di campionamento degli errori del rapporto include informazioni dettagliate sugli ID dispositivo non validi, ad esempio:</p>
   <ul>
    <li>L'ID di origine dati corrispondente all'ID dispositivo non valido;</li>
    <li>L'ID dispositivo non valido;</li>
    <li>Il tipo di ID dispositivo previsto, in base all'origine dati.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Nessun ID AAM corrispondente</b> </p> </td> 
   <td colname="col2"> <p>Questi ID <span class="keyword"> non possono corrispondere</span> a un ID esistente. Gli ID caricati possono avere questo stato quando <span class="keyword"> Audience Manager non</span> ha ancora eseguito una sincronizzazione ID o non può ancora corrispondere all'ID anche dopo una sincronizzazione. </p> <p>Nel caso di ID mobili non associati, <span class="keyword"> Audience Manager</span> sarà in grado di: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continuate a memorizzare e cercate di sincronizzare questo ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Registrati come Registrato <span class="wintitle"> memorizzato</span> nel rapporto se l'ID non può essere sincronizzato. </li> 
    </ul> <p>Se il file caricato contiene ID mobili, puoi trattarli un po' più leggero rispetto alle altre metriche. Essi non influenzeranno le percentuali di successo e di corrispondenza dei file successivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nessuna caratteristica</b> </p> </td> 
   <td colname="col2"> <p>Elenca le caratteristiche che <span class="keyword"> Audience Manager</span> non corrisponde a una caratteristica registrata. Potrebbe essere il risultato di: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Caratteristiche formattate in modo errato nel file di dati in entrata. Per informazioni su come formattare il file di dati, vedere <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenuti del file di dati in ingresso: Sintassi, Variabili ed Esempi</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Caratteristiche non ancora definite in <span class="keyword"> Audience Manager</span>. </li> 
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
   <td colname="col2"> <p>Numero di record memorizzati correttamente. A causa degli errori di formato file, alcuni dei record ricevuti potrebbero non essere memorizzati da <span class="keyword"> Audience Manager</span>. Il numero di record memorizzati può essere inferiore al numero di record ricevuti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Totale caratteristiche realizzate</b> </p> </td> 
   <td colname="col2"> <p>Il numero di caratteristiche per tutti gli utenti in tutti i file in entrata che vengono memorizzati nella piattaforma <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Totale segnali non utilizzati</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di segnali inutilizzati ricevuti nel report. Il totale si basa sul numero totale di record memorizzati correttamente. </p> <p>Per <a href="../reporting/dynamic-reports/unused-signals.md"> ulteriori informazioni, consultate Report</a> sui segnali non utilizzati. </p> </td> 
  </tr> 
 </tbody> 
</table>
