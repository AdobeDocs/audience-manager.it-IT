---
description: Questa pagina descrive le informazioni fornite direttamente dai nostri partner man mano che diventano disponibili, insieme a tutte le implicazioni relative al tuo utilizzo di Audience Manager. Le principali implicazioni per i partner che effettuano questi aggiornamenti sono il risultato del RGPD (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018, e del nuovo IAB RGPD Transparency & Consent Framework (Framework IAB).
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: Considerazioni sul RGPD per le destinazioni
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
TQID: https://experienceleague.adobe.com/QJr4SR9ZcwBH-xkX-0CJ23GQ09SDmkgTeN7Vl4djSb4
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 3c88464c2249b7848c9ae80ca4c0ed58fcb81070
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 96%

---

# Considerazioni sul RGPD per le destinazioni{#gdpr-considerations-for-destinations}

Questa pagina descrive le informazioni fornite direttamente dai nostri partner man mano che diventano disponibili, insieme a tutte le implicazioni relative al tuo utilizzo di Audience Manager. Le principali implicazioni per i partner che effettuano questi aggiornamenti sono il risultato del RGPD (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018, e del nuovo IAB RGPD Transparency &amp; Consent Framework (Framework IAB).

I partner Adobe possiedono i propri processi aziendali e possono decidere di aggiornare i propri requisiti di integrazione con Audience Manager di tanto in tanto. Stiamo lavorando in modo proattivo con il nostro ecosistema partner di Audience Manager per tenere i nostri clienti informati sui cambiamenti.

<!--
## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

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
</table>
-->

## Aggiornamento dell’interfaccia utente di Audience Manager - Integrazione Yahoo/Oath/DataX {#ui-update}

Oltre agli aggiornamenti al framework IAB sopra menzionati, Yahoo/Oath/DataX ha aggiunto nuovi parametri, **gdpr** e **gdpr_mode**, alle proprie API di tassonomia e pubblico. I parametri informano Yahoo/Oath/DataX di avere i diritti per elaborare un determinato segmento come responsabile del trattamento dei dati o come titolare del trattamento dei dati. Di conseguenza, i clienti Audience Manager che inviano segmenti a una destinazione Yahoo/Oath/DataX devono designare il parametro appropriato (Processor o Controller), in base al loro contratto con Oath.

Rivolgiti al tuo consulente o all’Assistenza clienti per impostare il parametro corretto. Adobe non può eseguire questo aggiornamento per conto di un cliente a meno che non riceva una comunicazione scritta in cui si richiede questo aggiornamento. Rivolgiti al tuo rappresentante Yahoo/Oath/DataX per conoscere la definizione completa di questi parametri.
