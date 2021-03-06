---
description: Ogni volta che viene elaborato un file server-to-server in entrata, una ricevuta viene inviata tramite e-mail alle soluzioni partner e, se configurata, al partner.
seo-description: Ogni volta che viene elaborato un file server-to-server in entrata, una ricevuta viene inviata tramite e-mail alle soluzioni partner e, se configurata, al partner.
seo-title: Messaggio di esempio ai partner dopo l’elaborazione in entrata
solution: Audience Manager
title: Messaggio di esempio ai partner dopo l’elaborazione in entrata
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Trasferimenti di dati in entrata
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 3%

---

# Messaggio di esempio ai partner dopo l’elaborazione in entrata{#sample-message-to-partners-after-inbound-processing}

Ogni volta che viene elaborato un file in entrata [!UICONTROL Server-to-Server], una ricevuta viene inviata tramite e-mail alle soluzioni partner e, se configurata, al partner.

<!-- r_inbound_message.xml -->

L’esempio seguente è un messaggio e-mail di esempio. La tabella sottostante il messaggio descrive le varie righe del messaggio.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Da: aam-noreply@adobe.com  </b> </p> <p> <b>Oggetto: Risultato elaborazione server-to-server di Adobe Audience Manager:</b> </p> <p> <b>Gentile Partner Adobe: (ID:7)</b> <b></b> </p> <p> <b>È stata ricevuta la consegna dei file server-to-server di Adobe Audience Manager</b> </p> <p> <b>Nome file:</b> <i></i> </p> <p> <b> s3n://&lt;&gt;nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b><i> </i></p> <p> <b> s3n://&lt;&gt;nome_bucket&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nome_bucket&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b><i> </i></p> <p> <b>Record ricevuti: 40669900</b> </p> <p><b>Errori di formato: 0</b> </p> <p> <b>ID AAM non valido: 112  </b> </p> <p> <b>Nessun ID AAM corrispondente: 0  </b> </p> <p> <b>Nessuna caratteristica realizzata: 26730823  </b> </p> <p> <b>Record elaborati: 40669900  </b> </p> <p> <b>Record memorizzati: 13938958  </b> </p> <p> <b>Dispositivi totali: 21  </b> </p> <p> <b>Segnali totali: 918878926  </b> </p> <p> <b>Segnali non utilizzati totali: 660348376  </b> </p> <p> <b>Caratteristiche totali realizzate: 258086908  </b> </p> <p> <b>Caratteristiche totali rimosse: 0  </b> </p> <p> <b>Convalida delle caratteristiche totali non riuscita: 0  </b> </p> <p> <b>Totale utenti con caratteristiche non convalidate: 0  </b> </p> <p> <b>Ora inizio processo: 2018-05-17 18:07:49  </b> </p> <p> <b>Ora fine processo: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

La tabella seguente contiene le righe corrispondenti alle righe nel messaggio e-mail ricevuto.

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
   <td colname="col2"> <p>Elenco di tutti i file in entrata ricevuti dall’Adobe per questo partner che sono stati elaborati insieme. Nel messaggio e-mail di esempio precedente, l’ID partner è 7 e l’ID del proprietario dei dati è 901. </p> <p>Il numero di coda (1,2,3...) è il numero di divisione aggiunto dal cliente o dal distributore in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record ricevuti </td> 
   <td colname="col2"> <p>Numero totale di Adobi di record ricevuti in tutti i file. Nella maggior parte dei casi, dovrebbe essere il numero totale di righe nei file in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errori di formato </td> 
   <td colname="col2"> <p>Numero di righe che non corrispondono al formato previsto. Queste righe non erano riconoscibili dal processo in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID AAM non valido </td> 
   <td colname="col2"> <p>Numero di UUID Audienci Manager che non corrispondono al formato previsto a 38 cifre. Oppure gli UUID Audienci Manager inviati nel file non sono numeri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nessun ID AAM corrispondente </td> 
   <td colname="col2"> <p>Numero totale di utenti per i quali Audience Manager non è riuscito a trovare un UUID corrispondente. Questi file non sono stati sincronizzati con ID, pertanto Audience Manager non può cercare l'UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nessuna caratteristica realizzata </td> 
   <td colname="col2"> <p>Numero di record in cui nessuno dei segnali sulla linea è associato a una caratteristica di Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record elaborati </td> 
   <td colname="col2"> <p>Numero totale di Audienci Manager di record elaborati. Nella maggior parte dei casi, questo numero dovrebbe essere lo stesso di "Record ricevuti". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record memorizzati </td> 
   <td colname="col2"> <p>Numero di record che determinano il caricamento di dati nel sistema = Record elaborati - Errori di formato - ID AAM non validi - Nessun ID AAM corrispondente - Nessuna caratteristica realizzata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dispositivi totali </td> 
   <td colname="col2"> <p>Numero di dispositivi per i quali i dati sono stati caricati nel sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segnali totali </td> 
   <td colname="col2"> <p> Numero totale di segnali per tutti gli utenti in tutti i file in entrata (numero totale di coppie chiave/valore nei record elaborati). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totale segnali non utilizzati </td> 
   <td colname="col2"> <p>Numero totale di segnali non utilizzati per tutti gli utenti in tutti i file in entrata (coppie chiave/valore che non sono state mappate sulle caratteristiche di Audience Manager). Nella maggior parte dei casi, ciò significa che l’Audience Manager non dispone di regole definite per il segnale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caratteristiche totali realizzate </td> 
   <td colname="col2"> <p>Numero di caratteristiche di Audience Manager per tutti gli utenti in tutti i file in entrata in base ai segnali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caratteristiche totali rimosse </td> 
   <td colname="col2"> <p> Numero totale di caratteristiche rimosse per tutti gli utenti in tutti i file in entrata. Per le sincronizzazioni complete, questo accade se l'utente ha avuto la caratteristica in un'esecuzione precedente ma non nell'esecuzione corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Convalida delle caratteristiche totali non riuscita </td> 
   <td colname="col2"> <p>Rappresenta il numero di caratteristiche che non appartengono all'origine dati dichiarata nel nome del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totale utenti con caratteristiche non riuscite di convalida </td> 
   <td colname="col2"> <p>Numero di record con caratteristiche non convalidate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di inizio del processo </td> 
   <td colname="col2"> <p>Ora di inizio del processo in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di fine del processo </td> 
   <td colname="col2"> <p>Data di fine del processo in entrata. </p> </td> 
  </tr> 
 </tbody> 
</table>
