---
description: Audience Manager e Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ricevono dati da esso. Questo può sembrare che Adobe stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.
seo-description: Audience Manager e Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ricevono dati da esso. Questo può sembrare che Adobe stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.
seo-title: Informazioni sulle chiamate al dominio demdex
solution: Audience Manager
title: Informazioni sulle chiamate al dominio demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Informazioni sulle chiamate al dominio demdex{#understanding-calls-to-the-demdex-domain}

Audience Manager e Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ricevono dati da esso. Questo può sembrare che Adobe stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento di chiamata </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Riflette il nome originale e pre-acquisizione di <span class="keyword"> Audience Manager</span>(<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> ha acquisito <span class="keyword"> Demdex</span> nel 2011 e ha rinominato l’azienda come <span class="keyword"> Audience Manager</span>. È difficile cambiare questo dominio perché è strettamente connesso con <span class="keyword"> Audience Manager</span>, con il servizio <span class="wintitle"></span>ID e con la nostra base di utenti installata. Vedere <a href="../overview/aam-overview.md#history-and-background"> Cronologia e sfondo</a>. </p> <p>Potrebbero essere presenti altri prefissi collegati alle <code> demdex.net</code> chiamate precedenti (ad esempio, <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>ecc.). Indipendentemente dal prefisso, una chiamata a <code><i>something</i>.demdex.net</code> è sempre una chiamata ad <span class="keyword"> Adobe</span> e non ad alcuni domini di terze parti sconosciuti o sospetti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> è un'abbreviazione di <span class="wintitle"> Data Provider Match</span>. Indica ai sistemi interni <span class="keyword"> Adobe</span> che una chiamata da <span class="keyword"> Audience Manager</span> o dal servizio <span class="wintitle"></span> ID trasmette i dati del cliente per la sincronizzazione o richiede un ID. Questa è la <code> demdex.net</code> chiamata più comune che vedrai da <span class="keyword"> Audience Manager</span> o dal servizio <span class="wintitle"></span>ID. </p> <p><span class="wintitle"> Nozioni di base sulle chiamate DPM</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Una chiamata <span class="wintitle"> DPM</span> da <span class="keyword"> Audience Manager</span> invia i dati ai server <span class="wintitle"> di raccolta dati e ai server</span> cache dei <span class="wintitle"></span>profili. Consulta Componenti <a href="../reference/system-components/components-data-collection.md"></a>per la raccolta dei dati. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> Servizio <span class="wintitle"> ID</span> </b>: Una chiamata <span class="wintitle"> DPM</span> dal servizio <span class="wintitle"></span> ID è una richiesta per un ID visitatore. Consulta <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookie e Adobe Experience Platform Identity Service</a> e <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> How the Adobe Experience Platform Identity Service Request and Sets ID</a>(Richiesta e impostazione di ID da parte del servizio identità Adobe Experience Platform). </li> 
     </ul> </p> <p> <p>Nota:  I clienti del servizio <span class="wintitle"></span> ID possono modificare il prefisso <span class="wintitle"> DPM</span> nel nome del dominio. Vedi <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audienceManager Server e audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookie di Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

