---
description: Il rapporto sullo stato di onboarding verifica i tassi di successo e di errore nell’elaborazione dei record nei file di origine dei dati in entrata. Questo rapporto visualizza i dati sotto forma di grafico a barre interattivo e fornisce metriche di riepilogo sotto forma di tabella. Inoltre, include un’opzione che campiona i file per un intervallo di tempo fisso e visualizza gli errori più comuni per ciascun tipo di errore. Puoi trovare questo rapporto in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando si crea un'origine dati in entrata.
seo-description: The Onboarding Status Report checks success and failure rates for processing records in your inbound data source files. This report displays data in an interactive bar chart and provides summary metrics in tabular form. And, it includes an option that samples files for a fixed time interval and displays the most common errors for each error type. You can find this report in Analytics > Onboarding Status Report. This report is also available when you create an inbound data source.
seo-title: Onboarding Status Report
solution: Audience Manager
title: Rapporto sullo stato di onboarding
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Inbound and Outbound Reports
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 0%

---

# Rapporto sullo stato di onboarding{#onboarding-status-report-about}

Il rapporto sullo stato di onboarding verifica i tassi di successo e di errore nell’elaborazione dei record nei file di origine dei dati in entrata. Questo rapporto visualizza i dati sotto forma di grafico a barre interattivo e fornisce metriche di riepilogo sotto forma di tabella. Inoltre, include un’opzione che campiona i file per un intervallo di tempo fisso e visualizza gli errori più comuni per ciascun tipo di errore. Puoi trovare questo rapporto in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando si crea un&#39;origine dati in entrata.

>[!NOTE]
>
>Solo gli utenti con privilegi di amministratore possono visualizzare questo rapporto nell’interfaccia utente di Audience Manager. Puoi fare in modo che gli utenti non amministratori ricevano una notifica dello stato dei file in entrata caricati aggiungendo le loro e-mail al rapporto. Consulta [Ricevi notifiche e-mail](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Rapporto sullo stato di onboarding: informazioni {#onboarding-status-about}

[!UICONTROL Onboarding Status Report] verifica i tassi di successo e di errore per l&#39;elaborazione dei record nei file di origine dati in entrata. Questo rapporto visualizza i dati sotto forma di grafico a barre interattivo e fornisce metriche di riepilogo sotto forma di tabella. Inoltre, include un’opzione che campiona i file per un intervallo di tempo fisso e visualizza gli errori più comuni per ciascun tipo di errore. Il report è disponibile in **[!UICONTROL Analytics > Onboarding Status Report]**. Questo rapporto è disponibile anche quando si crea un&#39;origine dati in entrata.

## Segnalazione degli errori e campionamento degli errori {#error-reporting-sampling}

Segnalazione errori e campionamento errori sono due funzioni separate del report [!UICONTROL Onboarding Status].

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segnalazione errori</b> </p> </td>
   <td colname="col2"> <p>La segnalazione degli errori mostra i tassi di successo e di errore per il numero di record elaborati in un’origine dati in entrata. Restituisce i dati in un grafico a barre in pila interattivo e come metriche di riepilogo nelle tabelle sotto il grafico. </p> <p>La segnalazione degli errori è automatica. Viene eseguito continuamente per tutte le origini dati in entrata. Restituisce i dati in base all'intervallo di intervalli di tempo predefiniti o a un intervallo di tempo personalizzato impostato con un widget del calendario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Campionamento errori</b> </p> </td>
   <td colname="col2"> <p>Il campionamento degli errori analizza il contenuto dei file di dati e restituisce i 10 errori più comuni per ogni tipo di errore. Gli errori nei file di dati in entrata impediscono l’elaborazione di singoli record. Utilizza questo rapporto come strumento di risoluzione dei problemi per ridurre il numero di errori dei file e migliorare i tassi di elaborazione. </p> <p>Il campionamento degli errori deve essere attivato manualmente. Il programma dura 14 giorni dal giorno dell'attivazione e si spegne automaticamente. È possibile riattivare il campionamento degli errori dopo la scadenza dell’intervallo di 14 giorni. Il campionamento degli errori viene attivato quando si <a href="../features/manage-datasources.md#create-data-source"> crea un'origine dati in entrata</a> o selezionando la casella di controllo <b><span class="uicontrol"> Campionamento errori</span></b> dalla sezione <span class="wintitle"> Impostazioni Data Source</span> di un'origine dati in entrata esistente. </p> <p>Il campionamento degli errori è un processo computazionalmente impegnativo. Di conseguenza, vengono restituiti solo i primi 10 errori per ogni categoria di errore. Non è progettato per restituire tutti gli errori contenuti in un’origine dati in entrata. Questi errori sono un campione rappresentativo di un gruppo potenzialmente più ampio di errori simili. Esamina l’intero file per individuare i tipi di errori segnalati dal report, riformatta il file e invialo di nuovo. </p> <p>Per ulteriori informazioni su come formattare correttamente un file di dati per un'origine dati in entrata, vedere <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Grafico a barre segnalazione errori {#error-report-bar-chart}

Il report degli errori rappresenta le percentuali di successo e di errore per l&#39;elaborazione dei record in un grafico a barre in pila, come illustrato nell&#39;esempio seguente. Il grafico è interattivo. Facendo clic su una barra vengono visualizzate le metriche di riepilogo per quel giorno in una tabella sotto il grafico.

![](assets/stacked-graph.png)

## Tabelle segnalazioni errori {#error-report-tables}

Il rapporto di errore visualizza i dati tabulari sotto il grafico a barre. La tabella mostra i tassi di successo e di errore insieme ai totali e alle percentuali.

**Record riusciti e non riusciti**

Questa visualizzazione predefinita mostra un conteggio delle frequenze dei record totali nel report e include una suddivisione degli errori per tipo di errore.

![](assets/success-failure.png)

**Totali e Percentuali**

Fai clic su **[!UICONTROL Totals & Percentages]** per vedere quale percentuale dei file è stata elaborata correttamente.

![](assets/totals-percentages.png)

## Rapporto di campionamento degli errori per 14 giorni {#error-reporting-14-days}

Con il campionamento degli errori attivo, il rapporto mostra i primi 10 errori per ogni tipo di errore. Fai clic su un pulsante del tipo di errore nella parte superiore del rapporto per visualizzare ogni set di dati campionati.

>[!NOTE]
>
>Il rapporto non evidenzia gli errori di registrazione con questa versione corrente. Per individuare e correggere gli errori dei file, è necessario esaminare i risultati e confrontarli con le specifiche riportate nella documentazione di [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

![](assets/error-samples.png)

## Ricevi notifiche tramite posta elettronica {#receive-email-notifications}

Puoi aggiungere gli indirizzi di posta elettronica dei destinatari a cui desideri ricevere la notifica dello stato dei file in entrata caricati. Tieni presente che puoi selezionare destinatari diversi per diverse origini dati.

![](assets/mail-notifications.png)

## Creare un rapporto sullo stato di onboarding {#create-onboard-status-report}

[!UICONTROL Sample Error Report] restituisce il numero di record in un&#39;origine dati elaborati correttamente e il numero di record con errori. Per generare un [!UICONTROL Sample Error Report], eseguire la procedura seguente.

<!-- 

create-onboarding-status-report.xml

 -->


1. Vai a **[!UICONTROL Analytics > Onboarding Status Report]**. Cercare un&#39;origine dati o sceglierne una dall&#39;elenco.

2. Seleziona un intervallo di date. Le opzioni includono:

   * Un set di intervalli di rapporti fissi.
   * Widget del calendario che consentono di creare un intervallo di date personalizzato.

3. Fare clic su **[!UICONTROL OK]**.

## Termini e definizioni del rapporto sullo stato di onboarding {#report-terms-conditions}

Guida di riferimento per le etichette e i termini utilizzati nel rapporto.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Termine </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Nome file di sincronizzazione dati</b> </p> </td> 
   <td colname="col2"> <p>Elenca i file ricevuti ed elaborati da <span class="keyword"> Audience Manager</span> dall'origine dati in entrata selezionata. </p> <p>L’elaborazione del file non riuscirà se il nome file non viene formattato correttamente. I requisiti relativi al nome file variano a seconda di come vengono inviati questi dati a <span class="keyword"> Audience Manager</span>. I metodi di consegna includono <span class="keyword"> Amazon S3</span> e FTP. Per istruzioni su come denominare i file, vedere: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Requisiti del nome Amazon S3 per i file di dati in entrata </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Errori di formato</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di record la cui elaborazione non è riuscita perché non corrispondono ai requisiti di sintassi o formattazione. Per informazioni su come formattare i dati, vedere <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID AAM non valido</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di ID utente (UUID) di <span class="keyword"> Audience Manager</span> formattati in modo non corretto. Di solito, questo indica gli ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Non corrisponde al formato previsto di 38 cifre. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contengono caratteri alfabetici. Gli ID devono essere solo numeri. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID dispositivo non valido</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di ID dispositivo globali formattati in modo errato. Consulta <a href="../reference/ids-in-aam.md">Indice degli ID in Audience Manager</a> e <a href="../features/global-data-sources.md">Global Data Sources</a> per informazioni dettagliate sulla formattazione degli ID dispositivo e sulle origini dati globali da utilizzare, in base al tipo di dispositivo.</p>
  <p>La sezione di campionamento degli errori del rapporto include informazioni dettagliate sugli ID dispositivo non validi, ad esempio:</p>
   <ul>
    <li>L’ID sorgente dati corrispondente all’ID dispositivo non valido;</li>
    <li>ID dispositivo non valido;</li>
    <li>Tipo di ID dispositivo previsto, in base all’origine dati.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Nessun ID AAM corrispondente</b> </p> </td> 
   <td colname="col2"> <p>Si tratta di ID onboarded <span class="keyword"> Audience Manager</span> non può corrispondere a un ID esistente. Gli ID onboarded possono avere questo stato quando <span class="keyword"> Audience Manager</span> non ha ancora eseguito una sincronizzazione ID o non può ancora corrispondere all'ID anche dopo una sincronizzazione. </p> <p>Nel caso di ID di dispositivi mobili senza corrispondenza, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continua a memorizzare e prova a sincronizzare questo ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Registralo come <span class="wintitle"> record archiviato</span> nel report se l'ID non può essere sincronizzato. </li> 
    </ul> <p>Se il file onboarded contiene ID per dispositivi mobili, allora puoi trattare questi numeri un po' più leggermente rispetto alle altre metriche. Non influiranno sulle percentuali di successo e di corrispondenza dei file successivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nessuna caratteristica realizzata</b> </p> </td> 
   <td colname="col2"> <p>Elenca le caratteristiche che <span class="keyword"> Audience Manager</span> non può corrispondere a una caratteristica onboarded. Questo potrebbe essere il risultato di: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Le caratteristiche non sono formattate correttamente nel file di dati in entrata. Per informazioni su come formattare il file di dati, vedere <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Caratteristiche non ancora definite in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Percentuale completata</b> </p> </td> 
   <td colname="col2"> <p>Percentuale di record del file archiviati correttamente. Percentuale di successo = record elaborati / numero di record in un file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Record ricevuti</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di record ricevuti. Nella maggior parte dei casi, questo numero deve corrispondere al numero totale di record (righe) nel file di dati in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Record archiviati</b> </p> </td> 
   <td colname="col2"> <p>Numero di record archiviati correttamente. A causa di errori di formato del file, alcuni dei record ricevuti potrebbero non essere archiviati da <span class="keyword"> Audience Manager</span>. Il numero di record archiviati può essere inferiore al numero di record ricevuti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche realizzate totali</b> </p> </td> 
   <td colname="col2"> <p>Numero di caratteristiche per tutti gli utenti in tutti i file in entrata archiviati nella piattaforma <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Totale segnali inutilizzati</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di segnali non utilizzati ricevuti nel rapporto. Questo totale si basa sul numero totale di record archiviati correttamente. </p> <p>Per ulteriori informazioni, vedere <a href="../reporting/dynamic-reports/unused-signals.md"> rapporto sui segnali inutilizzati</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
