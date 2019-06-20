---
description: Ogni volta che un file server-to-server in entrata viene elaborato, una ricevuta viene inviata via e-mail alle soluzioni partner e, se configurato, al partner.
seo-description: Ogni volta che un file server-to-server in entrata viene elaborato, una ricevuta viene inviata via e-mail alle soluzioni partner e, se configurato, al partner.
seo-title: Messaggio di esempio ai partner dopo l'elaborazione in entrata
solution: Audience Manager
title: Messaggio di esempio ai partner dopo l'elaborazione in entrata
uuid: 69 e 3 a 8 b 3-8465-4 f 4 c -8005-8 a 9 ff 15 ae 19 a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Messaggio di esempio ai partner dopo l&#39;elaborazione in entrata{#sample-message-to-partners-after-inbound-processing}

Ogni volta che un [!UICONTROL Server-to-Server] file in entrata viene elaborato, una ricevuta viene inviata via e-mail alle soluzioni partner e, se configurato, al partner.

<!-- r_inbound_message.xml -->

L&#39;esempio seguente è un esempio di messaggio e-mail. La tabella sotto il messaggio descrive le varie righe del messaggio.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Da: aam-noreply@adobe.com </b> </p> <p> <b>Oggetto: Risultato elaborazione server Adobe Audience Manager:</b> </p> <p> <b>Gentile Partner Adobe: (ID: 7)</b><b></b> </p> <p> <b>Abbiamo ricevuto la distribuzione di file server-to-server di Adobe Audience Manager</b> </p> <p> <b>Nome file:</b><i></i> </p> <p> <b> s 3 n:// &lt;<i>nome_ pacchetto &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806402. sync</b> </p> <p> <b> s 3 n:// &lt;<i>nome_ pacchetto &gt;</i>/2018-05-16/ftp_ dpm_ 7_ 901_ 1368655202. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ pacchetto &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784804. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ pacchetto &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806403. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ pacchetto &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784802. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ pacchetto &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784803. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nome_ pacchetto &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806404. sync</b> </p> <p> <b>Record ricevuti: 40669900</b> </p> <p><b>Errori formattazione: 0</b> </p> <p> <b>ID AAM non valido: 112 </b> </p> <p> <b>Nessun ID AAM corrispondente: 0 </b> </p> <p> <b>Nessuna caratteristica caratteristica: 26730823 </b> </p> <p> <b>Record elaborati: 40669900 </b> </p> <p> <b>Record memorizzati: 13938958 </b> </p> <p> <b>Dispositivi totali: 21 </b> </p> <p> <b>Segnali totali: 918878926 </b> </p> <p> <b>Totale segnali inutilizzati: 660348376 </b> </p> <p> <b>Caratteristiche totali realizzate: 258086908 </b> </p> <p> <b>Totale caratteristiche rimosse: 0 </b> </p> <p> <b>Totale convalida non riuscita: 0 </b> </p> <p> <b>Totale utenti con caratteristiche che non hanno superato la convalida: 0 </b> </p> <p> <b>Ora di inizio processo: 2018-05-17 18:07:49 </b> </p> <p> <b>Ora di fine processo: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

La tabella seguente contiene righe corrispondenti alle righe nel messaggio e-mail ricevuto.

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
   <td colname="col2"> <p>Elenco di tutti i file in entrata ricevuti da Adobe per questo partner che sono stati elaborati insieme. Nel precedente messaggio e-mail di esempio, l'ID partner è 7 e l'ID proprietario dei dati è 901. </p> <p>Il numero di coda (1,2,3…) è il numero diviso aggiunto dal cliente o dal distributore in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record ricevuti </td> 
   <td colname="col2"> <p>Numero totale di record ricevuti da Adobe in tutti i file. Nella maggior parte dei casi, questo deve essere il numero totale di righe nei file in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errori di formattazione </td> 
   <td colname="col2"> <p>Numero di righe che non corrispondono al formato previsto. Queste righe non erano riconoscibili dal processo in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID AAM non valido </td> 
   <td colname="col2"> <p>Numero di UUID Audience Manager che non corrispondono al formato previsto a 38 cifre. Oppure gli UUID di Audience Manager inviati nel file non sono numeri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nessun ID AAM corrispondente </td> 
   <td colname="col2"> <p>Numero totale di utenti per i quali Audience Manager non riusciva a trovare un UUID corrispondente. Questi file non sono stati sincronizzati, pertanto Audience Manager non è in grado di ricercare l'UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nessuna caratteristica </td> 
   <td colname="col2"> <p>Numero di record in cui nessuno dei segnali sulla riga viene mappato su una caratteristica di Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record elaborati </td> 
   <td colname="col2"> <p>Numero totale di record elaborati da Audience Manager. Nella maggior parte dei casi, questo numero deve corrispondere a «Record ricevuti». </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Record memorizzati </td> 
   <td colname="col2"> <p>Numero di record che generano dati da caricare nel sistema = Record elaborati - Errori format - ID AAM non validi - Nessun ID AAM corrispondente - Nessuna caratteristica realizzata. </p> </td> 
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
   <td colname="col1"> Totale segnali inutilizzati </td> 
   <td colname="col2"> <p>Numero totale di segnali inutilizzati per tutti gli utenti in tutti i file in entrata (coppie chiave/valore che non sono state mappate sulle caratteristiche di Audience Manager). Nella maggior parte dei casi, per Audience Manager non sono previste regole definite per il segnale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totale caratteristiche realizzate </td> 
   <td colname="col2"> <p>Numero di caratteristiche Audience Manager per tutti gli utenti in tutti i file in entrata basati sui segnali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totale caratteristiche rimosse </td> 
   <td colname="col2"> <p> Numero totale di caratteristiche rimosse per tutti gli utenti in tutti i file in entrata. Per le sincronizzazioni complete, questo accade se l'utente aveva la caratteristica in una precedente esecuzione ma non nell'esecuzione corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Convalida totale non riuscita </td> 
   <td colname="col2"> <p>Rappresenta il numero di caratteristiche che non appartengono all'origine dati dichiarata nel nome del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utenti totali con caratteristiche che non hanno superato la convalida </td> 
   <td colname="col2"> <p>Numero di record con caratteristiche che non hanno superato la convalida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di inizio processo </td> 
   <td colname="col2"> <p>L'ora in cui inizia il processo in entrata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di fine processo </td> 
   <td colname="col2"> <p>Termine del processo in ingresso. </p> </td> 
  </tr> 
 </tbody> 
</table>