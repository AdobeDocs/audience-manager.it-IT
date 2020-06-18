---
description: Questa pagina descrive le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a tutte le implicazioni relative alla vostra pratica Audience Manager . Le principali implicazioni per i partner che hanno effettuato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018 e del nuovo IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-description: Questa pagina descrive le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a tutte le implicazioni relative alla vostra pratica Audience Manager . Le principali implicazioni per i partner che hanno effettuato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018 e del nuovo IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: Considerazioni sul GDPR per le destinazioni
solution: Audience Manager
title: Considerazioni sul GDPR per le destinazioni
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---


# Considerazioni sul GDPR per le destinazioni{#gdpr-considerations-for-destinations}

Questa pagina descrive le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a tutte le implicazioni relative alla vostra pratica Audience Manager . Le principali implicazioni per i partner che hanno effettuato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018 e del nuovo IAB GDPR Transparency &amp; Consent Framework (IAB Framework).

I partner Adobe possiedono i propri processi aziendali e possono decidere di aggiornare i propri requisiti di integrazione con  Audience Manager di tanto in tanto. Stiamo lavorando in modo proattivo con il nostro ecosistema  partner Audience Manager per informare i nostri clienti sui cambiamenti.

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table> -->

##  Aggiornamento dell&#39;interfaccia utente Audience Manager - Integrazione Yahoo/Oath/DataX {#ui-update}

Oltre agli aggiornamenti al framework IAB sopra menzionati, Yahoo/Oath/DataX ha aggiunto nuovi parametri, **gdpr** e **gdpr_mode**, alle loro API tassonomia e Pubblico. I loro parametri informano Yahoo/Oath/DataX di avere i diritti per elaborare un determinato segmento come processore dati o come controller dati. Di conseguenza,  clienti Audience Manager che inviano segmenti a una destinazione Yahoo/Oath/DataX devono designare il parametro appropriato (Processore o Controller), in base al loro accordo con Oath.

Rivolgiti al tuo Consulente o all&#39;Assistenza clienti per impostare il parametro corretto. Adobe non può eseguire questo aggiornamento per conto di un cliente a meno che non riceva una corrispondenza scritta, richiedendo questo aggiornamento. Rivolgiti al tuo rappresentante Yahoo/Oath/DataX per conoscere la definizione completa di questi parametri.
