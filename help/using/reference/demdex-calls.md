---
description: Audience Manager e il servizio Experience Cloud ID effettuano chiamate al dominio demdex.net, da cui ricevono i dati. Questo potrebbe sembrare che Adobe stia lavorando con un dominio di terze parti insolito, ma questo non è il caso. In questa sezione sono descritti gli elementi di una chiamata demdex. net.
seo-description: Audience Manager e il servizio Experience Cloud ID effettuano chiamate al dominio demdex.net, da cui ricevono i dati. Questo potrebbe sembrare che Adobe stia lavorando con un dominio di terze parti insolito, ma questo non è il caso. In questa sezione sono descritti gli elementi di una chiamata demdex. net.
seo-title: Informazioni sulle chiamate al dominio demdex
solution: Audience Manager
title: Informazioni sulle chiamate al dominio demdex
uuid: c 06 dae 3 a-f 169-4712-80 fb-d 6 d 448 dce 51 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Informazioni sulle chiamate al dominio demdex{#understanding-calls-to-the-demdex-domain}

Audience Manager e il servizio Experience Cloud ID effettuano chiamate al dominio demdex.net, da cui ricevono i dati. Questo potrebbe sembrare che Adobe stia lavorando con un dominio di terze parti insolito, ma questo non è il caso. In questa sezione sono descritti gli elementi di una chiamata demdex. net.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chiama elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Si tratta di un dominio legacy controllato <span class="keyword"> da Adobe</span>. Riflette <span class="keyword"> il nome originale di Audience Manager</span>(<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> ha acquisito <span class="keyword"> Demdex</span> nel 2011 e ha rinominato la società come <span class="keyword"> Audience Manager</span>. È difficile modificare questo dominio perché è strettamente integrato con <span class="keyword"> Audience Manager</span>, il servizio <span class="wintitle"></span>ID e la base utente installata. Vedere <a href="../overview/aam-overview.md#history-and-background"> Cronologia e Sfondo</a>. </p> <p>Puoi visualizzare altri prefissi associati alle chiamate <code> demdex. net</code> legacy (ad es <code> . dcs. demdex. net</code>, <code> fast. demdex. net</code>, ecc.). A prescindere dal prefisso, una chiamata a <code><i>something</i>. demdex. net</code> è sempre una chiamata <span class="keyword"> ad Adobe</span> e non a un dominio di terze parti sconosciuto o sospetto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> è l'abbreviazione di <span class="wintitle"> Corrispondenza fornitore dati</span>. Indica ai sistemi interni <span class="keyword"> Adobe</span> che una chiamata da <span class="keyword"> Audience Manager</span> o dal <span class="wintitle"> servizio ID</span> trasmette i dati del cliente per la sincronizzazione o richiede un ID. Questa è la chiamata <code> demdex. net</code> più comune che vedrai da <span class="keyword"> Audience Manager</span> o dal <span class="wintitle"> servizio ID</span>. </p> <p><span class="wintitle"> Nozioni di base</span> sulle chiamate DPM: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b><span class="keyword"> Audience Manager</span></b>: Una <span class="wintitle"> chiamata DPM</span> di <span class="keyword"> Audience Manager</span> invia i dati ai server di raccolta <span class="wintitle"> dati</span> e <span class="wintitle"> ai server cache profilo</span>. Consulta <a href="../reference/system-components/components-data-collection.md"> Componenti raccolta dati</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b><span class="wintitle"> Servizio</span> </b>ID: Una <span class="wintitle"> chiamata DPM</span> dal servizio <span class="wintitle"> ID</span> è una richiesta di ID visitatore. Consulta <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookie e il servizio Experience Cloud ID</a> e <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> in che modo il servizio Experience Cloud ID richiede e imposta gli ID</a>. </li> 
     </ul> </p> <p> <p>Nota: <span class="wintitle"> I clienti del servizio</span> ID possono modificare il <span class="wintitle"> prefisso DPM</span> nel nome di dominio. Consultate <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audiencemanager Server e audiencemanagerserversecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookie Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

