---
description: Ogni volta che viene elaborato un file server-to-server in entrata, viene inviata una conferma via e-mail alle soluzioni partner e, se configurate, al partner.
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: Messaggio di esempio ai partner dopo l’elaborazione in entrata
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# Messaggio di esempio ai partner dopo l’elaborazione in entrata{#sample-message-to-partners-after-inbound-processing}

Ogni volta che viene elaborato un file [!UICONTROL Server-to-Server] in entrata, viene inviata una conferma tramite e-mail alle soluzioni partner e, se configurate, al partner.

<!-- r_inbound_message.xml -->

L’esempio seguente è un messaggio e-mail di esempio. La tabella seguente descrive le varie righe del messaggio.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Da: aam-noreply@adobe.com </b> </p> <p> <b>Oggetto: Risultato Elaborazione Da Server A Server Di Adobe Audience Manager:</b> </p> <p> <b>Gentile partner Adobe: (ID:7)</b> <b></b> </p> <p> <b>È stata ricevuta la consegna dei file server-to-server di Adobe Audience Manager</b> </p> <p> <b>Nome file:</b> <i></i> </p> <p> <b> s3n://&lt;<i>nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>nome_bucket&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>Record ricevuti: 40669900</b> </p> <p><b>Errori di formato: 0</b> </p> <p> <b>ID AAM non valido: 112 </b> </p> <p> <b>Nessun ID AAM corrispondente: 0 </b> </p> <p> <b>Nessuna caratteristica realizzata: 26730823 </b> </p> <p> <b>Record elaborati: 40669900 </b> </p> <p> <b>Record archiviati: 13938958 </b> </p> <p> <b>Dispositivi totali: 21 </b> </p> <p> <b>Totale segnali: 918878926 </b> </p> <p> <b>Totale segnali inutilizzati: 660348376 </b> </p> <p> <b>Caratteristiche realizzate totali: 258086908 </b> </p> <p> <b>Totale caratteristiche rimosse: 0 </b> </p> <p> <b>Totale caratteristiche non convalidate: 0 </b> </p> <p> <b>Totale utenti con caratteristiche non convalidate: 0 </b> </p> <p> <b>Ora di inizio processo: 2018-05-17 18:07:49 </b> </p> <p> <b>Ora di fine processo: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

La tabella seguente contiene le righe corrispondenti alle righe del messaggio e-mail ricevuto.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linee </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome file </td> 
   <td colname="col2"> <p>Elenco di tutti i file in entrata ricevuti da Adobe per questo partner che sono stati elaborati insieme. Nel precedente messaggio e-mail di esempio, l’ID partner è 7 e l’ID proprietario dei dati è 901. </p> <p>Il numero di coda (1,2,3...) è il numero frazionato aggiunto dal cliente o dal distributore in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record ricevuti </td> 
   <td colname="col2"> <p>Numero totale di Adobi di record ricevuti in tutti i file. Nella maggior parte dei casi, dovrebbe corrispondere al numero totale di righe nei file in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errori di formato </td> 
   <td colname="col2"> <p>Numero di righe che non corrispondono al formato previsto. Righe non riconoscibili dal processo in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID AAM non valido </td> 
   <td colname="col2"> <p>Numero di UUID di Audience Manager che non corrispondono al formato di 38 cifre previsto. Oppure gli UUID di Audience Manager inviati nel file non sono numeri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nessun ID AAM corrispondente </td> 
   <td colname="col2"> <p>Numero totale di utenti per i quali Audience Manager non è riuscito a trovare un UUID corrispondente. Questi file non sono stati sincronizzati con l’ID, pertanto Audience Manager non può cercare l’UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nessuna caratteristica realizzata </td> 
   <td colname="col2"> <p>Numero di record in cui nessuno dei segnali sulla linea è associato a una caratteristica Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record elaborati </td> 
   <td colname="col2"> <p>Numero totale di record elaborati dall'Audience Manager. Nella maggior parte dei casi, questo numero deve essere uguale a "Record ricevuti". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record archiviati </td> 
   <td colname="col2"> <p>Numero di record che hanno portato al caricamento dei dati nel sistema = Record elaborati - Errori di formato - ID AAM non validi - Nessun ID AAM corrispondente - Nessuna caratteristica realizzata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dispositivi totali </td> 
   <td colname="col2"> <p>Numero di dispositivi per i quali sono stati caricati dati nel sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segnali totali </td> 
   <td colname="col2"> <p> Numero totale di segnali per tutti gli utenti in tutti i file in entrata (numero totale di coppie chiave/valore nei record elaborati). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segnali inutilizzati totali </td> 
   <td colname="col2"> <p>Numero totale di segnali non utilizzati per tutti gli utenti in tutti i file in entrata (coppie chiave/valore non mappate su caratteristiche Audienci Manager). Nella maggior parte dei casi, ciò significa che l'Audience Manager non ha regole definite per il segnale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caratteristiche realizzate totali </td> 
   <td colname="col2"> <p>Numero di caratteristiche di Audience Manager per tutti gli utenti in tutti i file in entrata in base ai segnali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totale caratteristiche rimosse </td> 
   <td colname="col2"> <p> Numero totale di caratteristiche rimosse per tutti gli utenti in tutti i file in entrata. Per le sincronizzazioni complete, questo accade se l’utente aveva la caratteristica in un’esecuzione precedente ma non in quella corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Convalida delle caratteristiche totali non riuscita </td> 
   <td colname="col2"> <p>Rappresenta il numero di caratteristiche che non appartengono all'origine dati dichiarata nel nome file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totale utenti con caratteristiche non convalidate </td> 
   <td colname="col2"> <p>Numero di record con caratteristiche non convalidate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di inizio processo </td> 
   <td colname="col2"> <p>Ora di inizio del processo in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di fine processo </td> 
   <td colname="col2"> <p>Ora di fine del processo in entrata. </p> </td> 
  </tr> 
 </tbody> 
</table>
