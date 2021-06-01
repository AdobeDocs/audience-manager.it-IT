---
description: Il rapporto sullo stato di onboarding verifica i tassi di successo e di errore nell’elaborazione dei record nei file di origine dati in entrata. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo sotto forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando crei un’origine dati in entrata.
seo-description: Il rapporto sullo stato di onboarding verifica i tassi di successo e di errore nell’elaborazione dei record nei file di origine dati in entrata. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo sotto forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando crei un’origine dati in entrata.
seo-title: Rapporto sullo stato di onboarding
solution: Audience Manager
title: Rapporto sullo stato di onboarding
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Rapporti in entrata e in uscita
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 8%

---

# Rapporto sullo stato di onboarding{#onboarding-status-report-about}

Il rapporto sullo stato di onboarding verifica i tassi di successo e di errore nell’elaborazione dei record nei file di origine dati in entrata. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo sotto forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Questo rapporto è disponibile in Analytics > Rapporto sullo stato di onboarding. Questo rapporto è disponibile anche quando crei un’origine dati in entrata.

>[!NOTE]
>
>Solo gli utenti con privilegi di amministratore possono visualizzare questo rapporto nell’interfaccia utente di Audience Manager. Per informare gli utenti non amministratori dello stato dei file in entrata caricati, aggiungi le relative e-mail al rapporto. Consulta [Ricevere notifiche e-mail](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Rapporto sullo stato di onboarding: Informazioni su {#onboarding-status-about}

Il [!UICONTROL Onboarding Status Report] (Report errori campione) verifica i tassi d’errore e di successo nell’elaborazione dei record nei propri file di origine dei dati in ingresso. Questo rapporto visualizza i dati in un grafico a barre interattivo e fornisce metriche di riepilogo sotto forma di tabella. Prevede inoltre un’opzione per il campionamento dei file per un intervallo di tempo prefissato e la visualizzazione degli errori più comuni per ogni tipo di errore. Puoi trovare questo rapporto in **[!UICONTROL Analytics > Onboarding Status Report]**. Questo rapporto è disponibile anche quando crei un’origine dati in entrata.

## Segnalazione errori e campionamento degli errori {#error-reporting-sampling}

La segnalazione degli errori e il campionamento degli errori sono due funzioni separate del rapporto [!UICONTROL Onboarding Status] .

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
   <td colname="col2"> <p>La segnalazione degli errori mostra i tassi di successo e di errore per il numero di record elaborati in un’origine dati in entrata. Restituisce i dati in un grafico a barre interattivo e sovrapposto e come metriche di riepilogo nelle tabelle sotto il grafico. </p> <p>La segnalazione degli errori è automatica. Viene eseguito continuamente per tutte le origini dati in entrata. Restituisce dati in base a una serie di intervalli di tempo preimpostati o a un intervallo di tempo personalizzato impostato con un widget calendario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Campionamento degli errori</b> </p> </td>
   <td colname="col2"> <p>Il campionamento degli errori analizza il contenuto dei file di dati e restituisce i 10 errori più comuni per ogni tipo di errore. Gli errori nei file di dati in entrata impediscono l’elaborazione di singoli record. Utilizza questo rapporto come strumento di risoluzione dei problemi per ridurre il numero di errori dei file e migliorare le percentuali di elaborazione. </p> <p>È necessario attivare manualmente il campionamento degli errori. Viene eseguito per 14 giorni dal giorno dell'attivazione e poi si disattiva. È possibile riattivare il campionamento degli errori dopo la scadenza dell’intervallo di 14 giorni. Puoi attivare il campionamento degli errori quando <a href="../features/manage-datasources.md#create-data-source"> crei un'origine dati in entrata</a> o selezionando la casella di controllo <b><span class="uicontrol"> Campionamento errori</span></b> dalla sezione <span class="wintitle"> Impostazioni origine dati</span> di un'origine dati in entrata esistente. </p> <p>Il campionamento degli errori è un processo che richiede calcoli. Di conseguenza, restituisce solo i primi 10 errori per ogni categoria di errore. Non è progettato per restituire tutti gli errori contenuti in un’origine dati in entrata. Questi errori sono un esempio rappresentativo di un gruppo potenzialmente più ampio di errori simili. Rivedi l'intero file per i tipi di errori che questo report contrassegna, riformatta il file e invialo nuovamente. </p> <p>Consulta <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenuto dei file di dati in entrata : Sintassi, variabili ed esempi</a> per ulteriori informazioni su come formattare correttamente un file di dati per un’origine dati in entrata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Grafico a barre dei rapporti di errore {#error-report-bar-chart}

Il rapporto sugli errori traccia le percentuali di successo e di errore per l’elaborazione dei record in un grafico a barre sovrapposte, come illustrato nell’esempio seguente. Il grafico è interattivo. Facendo clic su una barra vengono visualizzate le metriche di riepilogo per quel giorno in una tabella sotto il grafico.

![](assets/stacked-graph.png)

## Tabelle dei rapporti di errore {#error-report-tables}

Il rapporto di errore visualizza i dati tabulari sotto il grafico a barre. La tabella mostra i tassi di successo e di errore insieme ai totali e alle percentuali.

**Record riusciti e non riusciti**

Questa visualizzazione predefinita mostra un conteggio di frequenza dei record totali nel rapporto e include una suddivisione degli errori in base al tipo di errore.

![](assets/success-failure.png)

**Totali e percentuali**

Fai clic su **[!UICONTROL Totals & Percentages]** per vedere la percentuale di file elaborati correttamente.

![](assets/totals-percentages.png)

## Report di campionamento degli errori per 14 giorni {#error-reporting-14-days}

Attivando il campionamento degli errori, il rapporto mostra i 10 errori principali per ogni tipo di errore. Fai clic su un pulsante del tipo di errore nella parte superiore del rapporto per visualizzare ogni set di dati campionati.

>[!NOTE]
>
>Il rapporto non evidenzia gli errori di record con questa versione corrente. Per trovare e correggere gli errori dei file, è necessario esaminare i risultati e confrontarli con le specifiche contenute nella documentazione [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) .

![](assets/error-samples.png)

## Ricevere notifiche e-mail {#receive-email-notifications}

Puoi aggiungere gli indirizzi e-mail dei destinatari ai quali desideri ricevere una notifica dello stato dei file in entrata caricati. Tieni presente che puoi selezionare destinatari diversi per diverse origini dati.

![](assets/mail-notifications.png)

## Creare un rapporto sullo stato di onboarding {#create-onboard-status-report}

Un [!UICONTROL Sample Error Report] restituisce il numero di record in un&#39;origine dati elaborati correttamente e il numero di record non riusciti. Segui questi passaggi per generare un [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. Vai a **[!UICONTROL Analytics > Onboarding Status Report]**. Cercare un’origine dati o sceglierne una dall’elenco.

2. Seleziona un intervallo di date. Le opzioni includono:

   * Una serie di intervalli di rapporti fissi.
   * Widget del calendario che consentono di creare un intervallo di date personalizzato.

3. Clic **[!UICONTROL OK]**.

## Termini e definizioni dei rapporti sullo stato di onboarding {#report-terms-conditions}

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
   <td colname="col2"> <p>Elenca i file ricevuti ed elaborati da <span class="keyword"> Audience Manager</span> dall'origine dati in entrata selezionata. </p> <p>L'elaborazione del file avrà esito negativo se il nome del file viene formattato in modo errato. I requisiti del nome file variano a seconda della modalità di invio di questi dati a <span class="keyword"> Audience Manager</span>. I metodi di consegna includono <span class="keyword"> Amazon S3</span> e FTP. Per istruzioni su come denominare i file, consulta: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Requisiti di nome di Amazon S3 per file di dati in entrata </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Errori di formato</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di record che non sono stati elaborati perché non corrispondono ai requisiti di sintassi o formattazione. Consulta <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenuto dei file di dati in entrata : Sintassi, variabili ed esempi</a> per informazioni su come formattare i dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID AAM non valido</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di ID utente <span class="keyword"> formattati in modo errato </span> (UUID). Di solito, questo indica gli ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Formato a 38 cifre non corrispondente. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contenere caratteri alfabetici. Gli ID devono essere solo numeri. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID dispositivo non valido</b> </p> </td> 
   <td colname="col2"> <p>Elenca il numero di ID dispositivo globale formattati in modo errato. Consulta <a href="../reference/ids-in-aam.md">Indice degli ID in Audience Manager</a> e <a href="../features/global-data-sources.md">Origini dati globali</a> per informazioni dettagliate su come formattare gli ID dispositivo e quali origini dati globali utilizzare, in base al tipo di dispositivo.</p>
  <p>La sezione sul campionamento degli errori del rapporto include informazioni dettagliate sugli ID dispositivo non validi, ad esempio:</p>
   <ul>
    <li>ID dell'origine dati corrispondente all'ID dispositivo non valido;</li>
    <li>ID dispositivo non valido;</li>
    <li>Il tipo di ID dispositivo previsto, in base all'origine dati.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Nessun ID AAM corrispondente</b> </p> </td> 
   <td colname="col2"> <p>Questi sono ID integrati <span class="keyword"> Audience Manager</span> non possono corrispondere a un ID esistente. Gli ID onboarded possono avere questo stato quando <span class="keyword"> Audience Manager</span> non ha ancora eseguito una sincronizzazione ID o ancora non può corrispondere all'ID anche dopo una sincronizzazione. </p> <p>Nel caso di ID mobili non corrispondenti, <span class="keyword"> Audience Manager</span> : </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continua a memorizzare e prova a sincronizzare questo ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Registralo come <span class="wintitle"> Record memorizzato</span> nel rapporto se l'ID non può essere sincronizzato. </li> 
    </ul> <p>Se il file onboarded contiene ID mobile, puoi trattare questi numeri in modo un po' più leggero rispetto alle altre metriche. Non influiranno sulle percentuali di successo e di corrispondenza per i file successivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nessuna caratteristica realizzata</b> </p> </td> 
   <td colname="col2"> <p>Elenca caratteristiche che <span class="keyword"> Audience Manager</span> non possono corrispondere a una caratteristica onboarded. Questo potrebbe essere il risultato di: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Caratteristiche formattate in modo errato nel file di dati in entrata. Per informazioni su come formattare il file di dati, consulta <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents : Sintassi, variabili ed esempi</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Caratteristiche non ancora definite in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Percentuale di successo</b> </p> </td> 
   <td colname="col2"> <p>Percentuale di record memorizzati correttamente nel file. Percentuale di successo = record elaborati / numero di record in un file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Record ricevuti</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di record ricevuti. Nella maggior parte dei casi, questo numero deve corrispondere al numero totale di record (righe) presenti nel file di dati in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Record memorizzati</b> </p> </td> 
   <td colname="col2"> <p>Numero di record archiviati correttamente. A causa di errori nel formato file, alcuni dei record ricevuti potrebbero non essere memorizzati da <span class="keyword"> Audience Manager</span>. Il numero di record memorizzati può essere inferiore al numero di record ricevuti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caratteristiche totali realizzate</b> </p> </td> 
   <td colname="col2"> <p>Il numero di caratteristiche per tutti gli utenti in tutti i file in entrata memorizzati nella piattaforma <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Totale segnali non utilizzati</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di segnali non utilizzati ricevuti nel rapporto. Questo totale si basa sul numero totale di record archiviati correttamente. </p> <p>Per ulteriori informazioni, consulta <a href="../reporting/dynamic-reports/unused-signals.md"> Rapporto sui segnali inutilizzati</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>
