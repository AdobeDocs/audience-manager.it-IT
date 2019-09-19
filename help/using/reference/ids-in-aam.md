---
description: Consulta questo documento per l’elenco completo degli ID di Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uid, uid, uuid, uid, uid, uid, uuid, uuid, uuid, uuid, uuid, uid, uid, uid, uid, uid, uuid, uuid, uid, uuid
seo-description: Consulta questo documento per l’elenco completo degli ID di Adobe Audience Manager.
seo-title: Indice degli ID in Audience Manager
solution: Audience Manager
title: Indice degli ID in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Indice degli ID in Audience Manager{#index-of-ids-in-audience-manager}

Consulta questo documento per l’elenco completo degli ID di Adobe Audience Manager.

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
   <td colname="col2"> <p> <b><span class="keyword"> ID utente univoco di Audience Manager</span></b> </p> <p> Un ID dispositivo numerico a 38 cifre che <span class="keyword"> Audience Manager</span> associa a ogni dispositivo con cui interagisce. Pensa a questo ID ogni volta che viene indicato un riferimento a utenti univoci nell’interfaccia utente di Audience Manager.<p><span class="keyword"> Audience Manager</span> tenta di salvare questo ID come cookie nel dominio di terze parti "demdex.net".</p> </p> <p>L'UUID di Audience Manager viene inviato nelle chiamate dell'evento come segnale d_uid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>ID organizzazione</b> </p> <p>Questo è l'ID fornito da una società al momento della registrazione a Experience Cloud. Per informazioni su come trovare l'ID organizzazione della società, leggi <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizzazioni e collegamento</a> account e scorri verso il basso per trovare l'ID organizzazione.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID partner</b> </p> <p> Il PID è l'ID di una società in <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> associa un imsOrgId a un PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>L’Experience Cloud ID (ECID, abbreviazioni MID o MCID) viene derivato matematicamente dall’ID organizzazione e dall’ID utente univoco di <span class="keyword"> Audience Manager</span> . Fintanto che questi ID rimangono costanti, generare l'ECID corretto per un utente specifico è semplicemente un problema matematico. Con lo stesso ID organizzazione e UUID Audience Manager ottenete sempre lo stesso valore ECID. Per ulteriori informazioni sull’ECID, consulta il documento <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and Experience Cloud ID</a> . </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID caratteristica</b> </p> <p>L'ID caratteristica identifica in modo univoco le caratteristiche nell'ambiente <span class="keyword"> Audience Manager</span> . A ogni caratteristica dell’interfaccia utente (interfaccia utente) viene assegnato un ID caratteristica. </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID segmento </b> </p> <p>L’ID segmento identifica in modo univoco i segmenti nell’ambiente <span class="keyword"> Audience Manager</span> . Un ID segmento viene assegnato a ciascun segmento nell’interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>ID segmento legacy </b> </p> <p>Questo ID identifica in modo univoco i segmenti nell'ambiente <span class="keyword"> Audience Manager</span> . A ogni segmento dell’interfaccia utente viene assegnato un ID segmento legacy. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>ID destinazione </b> </p> <p>L'ID di destinazione identifica in modo univoco le destinazioni nell'ambiente <span class="keyword"> Audience Manager</span> . Un ID è assegnato a ciascuna destinazione nell’interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>ID origine dati (altrimenti denominato ID provider dati)</b> </p> <p>L'ID origine dati è uno spazio dei nomi per ID o caratteristiche. Un ID viene assegnato a ogni origine dati (provider di dati) nell'interfaccia utente. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>ID utente univoco fornitore dati </b> <b>(denominato anche ID CRM)</b> </p> <p>Un ID di terze parti. Questo è l'ID tramite il quale si identificano gli utenti finali nel proprio sistema CRM. Puoi sincronizzare i DPUUID con gli UUID <span class="keyword"> di Audience Manager</span> e sincronizzare i DPUUID dalle diverse <span class="wintitle"> Origini</span> dati (DPID) nel processo <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> di sincronizzazione degli</a>ID. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID CRM </p> </td> 
   <td colname="col2"> <p>Consulta DPUUID qui sopra. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_IC </p> </td>
   <td colname="col2"> <p> <b>ID cliente, codice integrazione ID cliente</b> </p> <p> <b>Le coppie chiave-valore CID e CID_IC <a href="../reference/cid.md"> sostituiscono DPID e DPUUID</a>.</b> Forniscono le stesse funzioni del DPID e del DPUUID, ma sono più efficienti perché includono l'ID provider di dati e l'ID utente (o codice di integrazione) in una singola coppia chiave-valore. </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>Device Advertising ID</b> </p> <p>Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Generalmente fornito dal fabbricante del dispositivo o del sistema operativo del dispositivo. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID pubblicità dispositivo - IDFA - Dispositivi iOS</b> </p> <p> <b>Gli ID IDFA</b> sono identificatori del dispositivo mobile, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema operativo iOS. </p> </td> 
   <td colname="col3"> <p> Il formato è rigorosamente costituito da 32 cifre esadecimali <i>maiuscolari</i> , visualizzate in cinque gruppi e separate da trattini, nel formato 8-4-4-4-12, per un totale di 36 caratteri. </p> <p><code> AEBE52E7-03EE-455A-B3C4-E57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID pubblicità dispositivo - GAID - Dispositivi Android</b> </p> <p><b>Gli ID GAID</b> sono identificatori del dispositivo mobile, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema operativo Android. </p> </td> 
   <td colname="col3"> <p>Il formato è rigorosamente costituito da 32 cifre esadecimali <i>minuscole</i> , visualizzate in cinque gruppi e separate da trattini, nel formato 8-4-4-4-12, per un totale di 36 caratteri. </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Dispositivi di streaming Roku</b> </p> <p><b>Gli ID RIDA GAID</b> sono identificatori dispositivo in streaming forniti dal produttore dei dispositivi Roku.</p> </td>
   <td colname="col3"> <p>Il formato è rigorosamente costituito da 32 cifre esadecimali <i>minuscole</i> , visualizzate in cinque gruppi e separate da trattini, nel formato 8-4-4-4-12, per un totale di 36 caratteri. </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID - MAID - Windows 10 Devices</b> </p> <p><b>Gli ID MAID</b> sono identificatori dispositivo generati da Windows 10 per dispositivo e per utente.</p> </td>
   <td colname="col3"> <p>I MAID sono formattati come stringhe alfanumeriche.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Dispositivi Samsung</b> </p> Samsung DUID sono identificatori dispositivo forniti dai Samsung TV.</p> </td>
   <td colname="col3"> <p>I DUID Samsung sono formattati come stringhe alfanumeriche.</p></td>
  </tr>
 </tbody> 
</table>