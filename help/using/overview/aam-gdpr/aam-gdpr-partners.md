---
description: Questa pagina descrive le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a tutte le implicazioni relative alla tua pratica Audience Manager. Le principali implicazioni per i partner che hanno effettuato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018 e del nuovo IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-description: Questa pagina descrive le informazioni fornite direttamente dai nostri partner, man mano che diventano disponibili, insieme a tutte le implicazioni relative alla tua pratica Audience Manager. Le principali implicazioni per i partner che hanno effettuato questi aggiornamenti sono il risultato del GDPR (General Data Protection Regulation, Regolamento generale sulla protezione dei dati), entrato in vigore il 25 maggio 2018 e del nuovo IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: Considerazioni sul GDPR per le destinazioni
solution: Audience Manager
title: Considerazioni sul GDPR per le destinazioni
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

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

Oltre agli aggiornamenti al framework IAB sopra menzionati, Yahoo/Oath/DataX ha aggiunto nuovi parametri, **gdpr** e **gdpr_mode**, alle loro API tassonomia e Pubblico. I loro parametri informano Yahoo/Oath/DataX di avere i diritti per elaborare un determinato segmento come processore dati o come controller dati. Di conseguenza, i clienti Audience Manager che inviano segmenti a una destinazione Yahoo/Oath/DataX devono designare il parametro appropriato (Processore o Controller), in base al loro accordo con Oath.

Rivolgiti al tuo Consulente o all'Assistenza clienti per impostare il parametro corretto. Adobe non può eseguire questo aggiornamento per conto di un cliente a meno che non riceva una corrispondenza scritta, richiedendo questo aggiornamento. Rivolgiti al rappresentante Yahoo/Oath/DataX per conoscere la definizione completa di questi parametri.

## Partner Audience Manager Con Funzionalità Di Separazione {#aam-partners-with-unsegmentation}

Per aiutare i nostri clienti ad automatizzare le richieste GDPR, Audience Manager avvisa i nostri partner di attivazione sulle richieste di eliminazione da oggetti dati inviando loro informazioni non segmentate (o rimuovendo segmenti).

Tuttavia, alcuni dei nostri partner per l'attivazione:

1. Impossibile supportare richieste non segmentate da Adobe e/o
1. Non sono in grado di ricevere aggiornamenti da noi più spesso di una volta in 30 giorni.

In questi casi, non è possibile inviare le richieste di eliminazione ai partner di attivazione in modo automatico tramite Audience Manager. Scarica il nostro foglio [Excel per](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) partner per vedere quali partner di attivazione di Audience Manager supportano il segmento.
