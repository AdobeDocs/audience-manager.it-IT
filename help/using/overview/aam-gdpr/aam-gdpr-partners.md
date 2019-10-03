---
description: Questa pagina descrive le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a tutte le implicazioni relative alla tua pratica Audience Manager. Le principali implicazioni per i partner che hanno effettuato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018 e del nuovo IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-description: Questa pagina descrive le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a tutte le implicazioni relative alla tua pratica Audience Manager. Le principali implicazioni per i partner che hanno effettuato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018 e del nuovo IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: Considerazioni sul GDPR per le destinazioni
solution: Audience Manager
title: Considerazioni sul GDPR per le destinazioni
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# Considerazioni sul GDPR per le destinazioni{#gdpr-considerations-for-destinations}

Questa pagina descrive le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a tutte le implicazioni relative alla tua pratica Audience Manager. Le principali implicazioni per i partner che hanno effettuato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018 e del nuovo IAB GDPR Transparency &amp; Consent Framework (IAB Framework).

I partner Adobe possiedono i propri processi aziendali e possono decidere di aggiornare i propri requisiti di integrazione con Audience Manager di tanto in tanto. Stiamo lavorando in modo proattivo con il nostro ecosistema partner Audience Manager per informare i nostri clienti sui cambiamenti.

## Aggiornamenti dei partner Audience Manager - Sincronizzazioni ID {#partner-updates-id-syncs}

Alcuni partner, elencati nella tabella seguente, hanno modificato i propri requisiti di integrazione con Audience Manager per includere il supporto basato sul framework IAB, al fine di rispettare gli standard GDPR.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nome partner </p> </th> 
   <th colname="col2" class="entry"> <p>Impatto previsto </p> </th> 
   <th colname="col3" class="entry"> <p>Stato della modifica </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>Le sincronizzazioni ID per gli utenti nell'Unione Europea vengono ignorate dal partner </p> </td> 
   <td colname="col3"> <p>Live dal 22 maggio 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scrivania </p> </td> 
   <td colname="col2"> <p>Le sincronizzazioni ID per gli utenti nell'Unione Europea vengono ignorate dal partner </p> </td> 
   <td colname="col3"> <p>Non ancora vivo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>Le sincronizzazioni ID per gli utenti nell'Unione Europea vengono ignorate dal partner </p> </td> 
   <td colname="col3"> <p>Non ancora vivo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>Le sincronizzazioni ID per gli utenti nell'Unione Europea vengono ignorate dal partner </p> </td> 
   <td colname="col3"> <p>Non ancora vivo </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiornamento dell'interfaccia utente di Audience Manager - Integrazione Yahoo/Oath/DataX {#ui-update}

Oltre agli aggiornamenti al framework IAB sopra menzionati, Yahoo/Oath/DataX ha aggiunto nuovi parametri, **gdpr** e **gdpr_mode**, alle loro API tassonomia e Pubblico. Their parameters inform Yahoo/Oath/DataX that they have the rights to process a certain segment as a Data Processor or as a Data Controller. As a result, Audience Manager customers sending segments to a Yahoo/Oath/DataX destination must designate the appropriate parameter (Processor or Controller), based on their agreement with Oath.

Please reach out to your Consultant or Client Care to set the correct parameter. Adobe cannot make this update on behalf of a customer unless we receive written correspondence, requesting this update. Please reach out to your Yahoo/Oath/DataX representative to understand the full definition of these parameters.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

In order to help our customers automate GDPR requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager. Download our Partner Excel sheet to see which Audience Manager activation partners support unsegment.[](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx)
