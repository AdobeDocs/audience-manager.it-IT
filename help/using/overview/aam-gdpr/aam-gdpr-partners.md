---
description: Questa pagina evidenzia le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a qualsiasi implicazioni correlata alla tua prassi di Audience Manager. Le implicazioni chiave per i partner che hanno apportato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), che è entrato in vigore il 25 maggio 2018 e il nuovo framework IAB GDPR Transparency & Entitlement Framework.
seo-description: Questa pagina evidenzia le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a qualsiasi implicazioni correlata alla tua prassi di Audience Manager. Le implicazioni chiave per i partner che hanno apportato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), che è entrato in vigore il 25 maggio 2018 e il nuovo framework IAB GDPR Transparency & Entitlement Framework.
seo-title: Considerazioni sul GDPR per le destinazioni
solution: Audience Manager
title: Considerazioni sul GDPR per le destinazioni
uuid: e 8 a 40060-086 c -4 f 03-b 48 c -9 c 903 acb 7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

---


# GDPR Considerations for Destinations{#gdpr-considerations-for-destinations}

Questa pagina evidenzia le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a qualsiasi implicazioni correlata alla tua prassi di Audience Manager. Le implicazioni chiave per i partner che hanno apportato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), che è entrato in vigore il 25 maggio 2018 e il nuovo framework IAB GDPR Transparency &amp; Entitlement Framework.

I partner Adobe possiedono i propri processi aziendali e possono decidere di aggiornare di tanto in tanto i requisiti di integrazione con Audience Manager. Stiamo lavorando attivamente con il nostro ecosistema Partner Audience Manager per fare in modo che i nostri clienti vengano informati delle modifiche.

## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Alcuni partner, come elencati nella tabella seguente, hanno modificato i requisiti di integrazione con Audience Manager per includere il supporto basato su IAB Framework, per conformarsi agli standard GDPR.

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
   <td colname="col1"> <p>Yahoo/Oath/datax </p> </td> 
   <td colname="col2"> <p>Le sincronizzazioni ID per gli utenti dell'Unione Europea vengono ignorate dal partner </p> </td> 
   <td colname="col3"> <p>Live dal 22 maggio 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>Le sincronizzazioni ID per gli utenti dell'Unione Europea vengono ignorate dal partner </p> </td> 
   <td colname="col3"> <p>Non live </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>Le sincronizzazioni ID per gli utenti dell'Unione Europea vengono ignorate dal partner </p> </td> 
   <td colname="col3"> <p>Non live </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Liveramp </p> </td> 
   <td colname="col2"> <p>Le sincronizzazioni ID per gli utenti dell'Unione Europea vengono ignorate dal partner </p> </td> 
   <td colname="col3"> <p>Non live </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI Update - Yahoo/Oath/DataX Integration {#ui-update}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, **gdpr** and **gdpr_mode**, to their taxonomy and Audience APIs. I loro parametri informano Yahoo/Oath/datax che dispongono dei diritti necessari per elaborare un determinato segmento come elaboratore dati o come controller dati. Di conseguenza, i clienti Audience Manager che inviano segmenti a una destinazione Yahoo/Oath/datax devono designare il parametro appropriato (Processore o Controller), in base al relativo contratto con Oath.

Rivolgetevi al vostro consulente o a Client Care per impostare il parametro corretto. Adobe non può effettuare questo aggiornamento a nome del cliente, a meno che non riceva la corrispondenza scritta, richiedendo questo aggiornamento. Rivolgetevi al rappresentante Yahoo/Oath/datax per comprendere la definizione completa di questi parametri.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

Per consentire ai nostri clienti di automatizzare le richieste GDPR, Audience Manager avvisa i nostri partner di attivazione riguardo le richieste di eliminazione da dati dati inviandole di unsegmento (o rimuovere il segmento).

Tuttavia, alcuni partner di attivazione:

1. Non è possibile supportare le richieste di segmento da Adobe e/o
1. Non sono in grado di ricevere aggiornamenti più frequenti di una volta in 30 giorni.

In questi casi, non è possibile inviare richieste di eliminazione ai partner di attivazione in modo automatizzato tramite Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) to see which Audience Manager activation partners support unsegment.
