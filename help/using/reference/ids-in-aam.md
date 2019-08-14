---
description: Consultate questo documento per l'elenco completo degli ID di Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consultate questo documento per l'elenco completo degli ID di Adobe Audience Manager.
seo-title: Indice degli ID in Audience Manager
solution: Audience Manager
title: Indice degli ID in Audience Manager
uuid: 292185 ec -7 c 6 a -414 b-ab 17-800 c 21 cb 1 f 01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Indice degli ID in Audience Manager{#index-of-ids-in-audience-manager}

Consultate questo documento per l'elenco completo degli ID di Adobe Audience Manager.

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Nome e descrizione </th> 
   <th colname="col3" class="entry"> Esempio  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> ID utente</span> univoco di Audience Manager </b> </p> <p> Un ID dispositivo numerico di 38 cifre che <span class="keyword"> Audience Manager</span> associa a ogni dispositivo con cui interagisce. Pensa a questo ID ogni volta che vedi un nome di utenti univoci nell'interfaccia utente di Audience Manager.<p><span class="keyword"> Audience Manager</span> tenta di salvare questo ID come cookie nel dominio di terze parti «demdex. net».</p> </p> <p>L'UUID Audience Manager viene inviato nelle chiamate dell'evento come segnale d_ uuid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imsorgid </p> </td> 
   <td colname="col2"> <p> <b>ID organizzazione</b> </p> <p>Si tratta dell'ID fornito da una società al momento della registrazione a Experience Cloud. Per informazioni su come trovare l'ID organizzazione della tua società, leggi <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizzazioni e collegamento account</a> e scorri verso il basso per trovare il tuo ID organizzazione.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID partner</b> </p> <p> Il PID è l'ID di una società in <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> associa un imsorgid a un PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>L'ID Experience Cloud (ECID, MID abbreviazioni legacy o MCID) viene derivato matematicamente dall'ID organizzazione e dall' <span class="keyword"> ID utente</span> univoco Audience Manager. Fintanto che questi ID rimangono costanti, generare l'ECID corretto per un utente specifico è semplicemente un problema matematico. Con lo stesso ID organizzazione e l'UUID di Audience Manager ricevi lo stesso valore ECID ogni volta. Puoi leggere ulteriori informazioni sull'ECID nel documento <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookie e Experience</a> Cloud ID. </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID caratteristica</b> </p> <p>L'ID caratteristica identifica in modo univoco le caratteristiche nell'ambiente <span class="keyword"> Audience Manager</span> . Un ID caratteristica viene assegnato a ogni caratteristica nell'interfaccia utente (interfaccia utente). </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID segmento </b> </p> <p>L'ID segmento identifica i segmenti in maniera univoca nell'ambiente <span class="keyword"> Audience Manager</span> . Un ID segmento viene assegnato a ogni segmento nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Csegid </p> </td> 
   <td colname="col2"> <p> <b>ID segmento precedente </b> </p> <p>Questo ID identifica in modo univoco i segmenti nell'ambiente <span class="keyword"> Audience Manager</span> . Un ID segmento legacy viene assegnato a ogni segmento nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destid </p> </td> 
   <td colname="col2"> <p> <b>ID destinazione </b> </p> <p>L'ID di destinazione identifica in modo univoco le destinazioni nell'ambiente <span class="keyword"> Audience Manager</span> . Un ID viene assegnato a ciascuna destinazione nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>ID origine dati (altrimenti denominato ID provider dati)</b> </p> <p>L'ID origine dati è uno spazio nomi per ID o caratteristiche. Un ID viene assegnato a ciascuna origine dati (provider di dati) nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>Data Provider Unique User ID </b><b>(denominato anche ID CRM)</b> </p> <p>Un ID di terze parti. Questo è l'ID per il quale identificare gli utenti finali nel sistema CRM. Puoi sincronizzare dpuuid con <span class="keyword"> Audience Manager</span> UUID e sincronizzare dpuuid dalle diverse <span class="wintitle"> Origini dati</span> (DPID) nel processo di sincronizzazione <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> ID</a>. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -3432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID CRM </p> </td> 
   <td colname="col2"> <p>Vedi DPUUID sopra. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -3432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_ IC </p> </td>
   <td colname="col2"> <p> <b>ID cliente, codice integrazione ID cliente</b> </p> <p> <b>Le coppie chiave-valore CID e CID_ IC <a href="../reference/cid.md"> sostituiscono DPID e DPUUID</a>.</b> Essi forniscono le stesse funzioni di DPID e DPUUID, ma sono più efficienti perché includono l'ID del fornitore di dati e l'ID utente (o codice di integrazione) in una singola coppia chiave-valore. </p> </td> 
   <td colname="col3"> <p><code> 81841% 013 ad 2948 b 1570 a 7 e 408 a 7 cfb 7 ff 4879 e 4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDA</li>
      <li>ABS</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>ID pubblicità dispositivo</b> </p> <p>Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Generalmente fornito dal produttore del dispositivo o del sistema operativo del dispositivo. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID pubblicità dispositivo - IDFA - dispositivi iOS</b> </p> <p> <b>Gli</b> ID IDFA sono identificatori dispositivo mobili, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema operativo iOS. </p> </td> 
   <td colname="col3"> <p> Il formato è costituito da 32 <i>cifre</i> esadecimali maiuscole, visualizzate in cinque gruppi e separate da trattini, nel modulo 8-4-4-4-12, per un totale di 36 caratteri. </p> <p><code> AEBE 52 E 7-03 EE -455 A-B 3 C 4-E 57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID pubblicità dispositivo - GAID - dispositivi Android</b> </p> <p><b>Gli</b> ID GAID sono identificatori dispositivo mobili, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema operativo Android. </p> </td> 
   <td colname="col3"> <p>Il formato è costituito da 32 <i>cifre</i> esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nel modulo 8-4-4-4-12, per un totale di 36 caratteri. </p> <p> <code> e 4 fe 9 bde-caa 0-47 b 6-908 d-ffba 3 fa 184 f 2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Dispositivi di streaming Roku</b> </p> <p><b>Gli ID GAID</b> RIDA sono identificatori dispositivo di streaming forniti dal produttore dei dispositivi Roku.</p> </td>
   <td colname="col3"> <p>Il formato è costituito da 32 <i>cifre</i> esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nel modulo 8-4-4-4-12, per un totale di 36 caratteri. </p> <p> <code> fcb 2 a 29 c -315 a -5 e 6 b-bcfd-d 889 ba 19 aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>ID pubblicità Microsoft - SHUTTLE - Dispositivi Windows 10</b> </p> <p><b>Gli</b> ID delle aule virtuali sono identificatori dispositivo generati da Windows 10 su base individuale e per utente.</p> </td>
   <td colname="col3"> <p>I maid vengono formattati come stringhe alfanumeriche.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Dispositivi Samsung</b> </p> Samsung DUIDS sono identificatori dispositivo forniti dai televisori Samsung.</p> </td>
   <td colname="col3"> <p>Samsung DUIDS sono formattati come stringhe alfanumeriche.</p></td>
  </tr>
 </tbody> 
</table>