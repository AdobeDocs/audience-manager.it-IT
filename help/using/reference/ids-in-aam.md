---
description: Consultate questo documento per l'elenco completo degli ID di Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid
seo-description: Consultate questo documento per l'elenco completo degli ID di Adobe Audience Manager.
seo-title: Indice degli ID in Audience Manager
solution: Audience Manager
title: Indice degli ID in Audience Manager
uuid: 292185 ec -7 c 6 a -414 b-ab 17-800 c 21 cb 1 f 01
translation-type: tm+mt
source-git-commit: cf0cec2fdf1272f075a825b09cf2fa11a3815432

---


# Index of IDs in Audience Manager{#index-of-ids-in-audience-manager}

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
   <td colname="col2"> <p> <b><span class="keyword"> ID utente</span> univoco di Audience Manager </b> </p> <p> A numerical, 38-digit device ID that <span class="keyword"> Audience Manager</span> associates to each device it interacts with. Pensa a questo ID ogni volta che vedi un nome di utenti univoci nell'interfaccia utente di Audience Manager.<p><span class="keyword"> Audience Manager</span> tenta di salvare questo ID come cookie nel dominio di terze parti «demdex. net».</p> </p> <p>L'UUID Audience Manager viene inviato nelle chiamate dell'evento come segnale d_ uuid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imsorgid </p> </td> 
   <td colname="col2"> <p> <b>ID organizzazione</b> </p> <p>Si tratta dell'ID fornito da una società al momento della registrazione a Experience Cloud. To learn how you can find your company's Organization ID, read <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizations and Account Linking</a> and scroll down to Find your Organization ID.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID partner</b> </p> <p> The PID is a company's ID in <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> associa un imsorgid a un PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>The Experience Cloud ID (ECID, legacy abbreviations MID or MCID) is derived mathematically from your Organization ID and the <span class="keyword"> Audience Manager</span> Unique User ID. Fintanto che questi ID rimangono costanti, generare l'ECID corretto per un utente specifico è semplicemente un problema matematico. Con lo stesso ID organizzazione e l'UUID di Audience Manager ricevi lo stesso valore ECID ogni volta. You can read more about the ECID in the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and Experience Cloud ID</a> document. </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID caratteristica</b> </p> <p>The Trait ID uniquely identifies traits in the <span class="keyword"> Audience Manager</span> environment. Un ID caratteristica viene assegnato a ogni caratteristica nell'interfaccia utente (interfaccia utente). </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID segmento </b> </p> <p>The Segment ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. Un ID segmento viene assegnato a ogni segmento nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Csegid </p> </td> 
   <td colname="col2"> <p> <b>ID segmento precedente </b> </p> <p>This ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. Un ID segmento legacy viene assegnato a ogni segmento nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destid </p> </td> 
   <td colname="col2"> <p> <b>ID destinazione </b> </p> <p>The Destination ID uniquely identifies destinations in the <span class="keyword"> Audience Manager</span> environment. Un ID viene assegnato a ciascuna destinazione nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>ID origine dati (altrimenti denominato ID provider dati)</b> </p> <p>L'ID origine dati è uno spazio nomi per ID o caratteristiche. Un ID viene assegnato a ciascuna origine dati (provider di dati) nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>Data Provider Unique User ID </b><b>(denominato anche ID CRM)</b> </p> <p>Un ID di terze parti. Questo è l'ID per il quale identificare gli utenti finali nel sistema CRM. You can sync DPUUIDs with <span class="keyword"> Audience Manager</span> UUIDs and you can sync DPUUIDs from your different <span class="wintitle"> Data Sources</span> (DPIDs) in the <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> ID synchronization process</a>. </p> </td> 
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
   <td colname="col3"> <p> The format strictly consists of 32 <i>uppercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p><code> AEBE 52 E 7-03 EE -455 A-B 3 C 4-E 57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID pubblicità dispositivo - GAID - dispositivi Android</b> </p> <p><b>Gli</b> ID GAID sono identificatori dispositivo mobili, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema operativo Android. </p> </td> 
   <td colname="col3"> <p>The format strictly consists of 32 <i>lowercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p> <code> e 4 fe 9 bde-caa 0-47 b 6-908 d-ffba 3 fa 184 f 2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Dispositivi di streaming Roku</b> </p> <p><b>Gli ID GAID</b> RIDA sono identificatori dispositivo di streaming forniti dal produttore dei dispositivi Roku.</p> </td>
   <td colname="col3"> <p>The format strictly consists of 32 <i>lowercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p> <code> fcb 2 a 29 c -315 a -5 e 6 b-bcfd-d 889 ba 19 aada</code> </p> </td> 
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