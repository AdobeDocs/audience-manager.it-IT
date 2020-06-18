---
description: ' Audience Manager e  Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ricevono i dati dal dominio stesso. Questo può sembrare che Adobe stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.'
seo-description: ' Audience Manager e  Adobe Experience Platform Identity Service effettuano chiamate al dominio demdex.net e ricevono i dati dal dominio stesso. Questo può sembrare che Adobe stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una chiamata demdex.net.'
seo-title: Informazioni sulle chiamate al dominio demdex
solution: Audience Manager
title: Informazioni sulle chiamate al dominio demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d219f6fa1e2a8396b049f86391142c00e263b629
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 4%

---


# Informazioni sulle chiamate al dominio demdex{#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] e il  Adobe Experience Platform Identity Service effettua chiamate al dominio demdex.net e riceve i dati da esso. Questo può sembrare che Adobe stia utilizzando un dominio di terze parti insolito, ma non è così. Questa sezione descrive gli elementi di una `demdex.net` chiamata.

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Riflette <span class="keyword"> nome originale di Audience Manager</span>pre-acquisizione (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> ha acquisito <span class="keyword"> Demdex</span> nel 2011 e ha ridenominato l’azienda come <span class="keyword"> Audience Manager</span>. È difficile cambiare questo dominio perché è strettamente collegato a <span class="keyword"> Audience Manager</span>, al servizio <span class="wintitle"></span>ID e alla nostra base di utenti installata. Vedere <a href="../overview/aam-overview.md#history-and-background"> Cronologia e sfondo</a>. </p> <p>Potrebbero essere presenti altri prefissi collegati alle <code> demdex.net</code> chiamate precedenti (ad esempio, <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>ecc.). Indipendentemente dal prefisso, una chiamata a <code><i>something</i>.demdex.net</code> è sempre una chiamata ad <span class="keyword"> Adobe</span> e non ad alcuni domini di terze parti sconosciuti o sospetti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> è un'abbreviazione di <span class="wintitle"> Data Provider Match</span>. Indica ai sistemi interni <span class="keyword"> Adobe</span> che una chiamata da <span class="keyword">  Audience Manager</span> o dal servizio <span class="wintitle"></span> ID trasmette i dati del cliente per la sincronizzazione o la richiesta di un ID. Questa è la <code> demdex.net</code> chiamata più comune che vedrai da <span class="keyword"> Audience Manager</span> o dal servizio <span class="wintitle"></span>ID. </p> <p><span class="wintitle"> Nozioni di base sulle chiamate DPM</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword">  Audience Manager</span> </b>: Una chiamata <span class="wintitle"> DPM</span> da <span class="keyword">  Audience Manager</span> invia dati ai server <span class="wintitle"> di raccolta dati e ai server</span> cache dei <span class="wintitle"></span>profili. Consulta Componenti <a href="../reference/system-components/components-data-collection.md"></a>per la raccolta dei dati. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> Servizio</span> ID </b>: Una chiamata <span class="wintitle"> DPM</span> dal servizio <span class="wintitle"></span> ID è una richiesta per un ID visitatore. Consulta <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e il  Adobe Experience Platform Identity Service</a> e <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> Come il  Adobe Experience Platform Identity Service richiede e imposta gli ID</a>. </li> 
     </ul> </p> <p> <p>Nota:  <span class="wintitle"> I clienti del servizio</span> ID possono modificare il prefisso <span class="wintitle"> DPM</span> nel nome del dominio. Vedi <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> audienceManager Server e audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [servizio identità Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookie Audience Manager](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

