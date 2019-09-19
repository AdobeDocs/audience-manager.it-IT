---
description: Adobe rispetta tutti gli standard di settore per la gestione delle rinunce. Continua a leggere per informazioni complete sui tipi di rinuncia supportati da Audience Manager.
seo-description: Adobe rispetta tutti gli standard di settore per la gestione delle rinunce. Continua a leggere per informazioni complete sui tipi di rinuncia supportati da Audience Manager.
seo-title: Gestione del rifiuto
solution: Audience Manager
title: Gestione del rifiuto
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Gestione del rifiuto{#opt-out-management}

Adobe rispetta tutti gli standard di settore per la gestione delle rinunce. Continua a leggere per informazioni complete sui tipi di rinuncia supportati da Audience Manager.

## Rifiuto globale {#global-opt-out}

La rinuncia globale rappresenta un rifiuto tra Audience Manager e altre soluzioni Adobe Experience Cloud per tutti i marchi. Nella tabella seguente sono elencati i metodi utilizzati per la rinuncia globale:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rifiuto per </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>La pagina <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices </a> offre funzionalità con un clic che consentono agli utenti finali di controllare e rifiutare la raccolta di dati dalle soluzioni pubblicitarie Adobe Experience Cloud (incluso Audience Manager). Nello specifico, consulta la sezione <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Business customer </a> della pagina Privacy Choices. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiamate API dirette ad Audience Manager </p> </td> 
   <td colname="col2"> <p>Puoi rifiutare la raccolta di dati da parte di tutti i marchi di Audience Manager effettuando una chiamata all’API DCS di seguito e includendo l’ID utente <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Di conseguenza, imposteremo i cookie <code>demdex=NOTARGET</code> e <code>dextp=NOTARGET</code> per l’ID utente di Audience Manager inviato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivi mobili </p> </td> 
   <td colname="col2"> <p>Consulta le impostazioni di privacy e rinuncia per: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Dispositivi Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Dispositivi iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Gli utenti finali possono anche scegliere di non partecipare alla raccolta dati globale visitando i siti web dei nostri partner di settore.

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

In base alle richieste di rifiuto descritte sopra:

* Audience Manager cesserà tutte le attività di raccolta, segmentazione o attivazione dei dati.
* I dati storici vengono rimossi dal profilo utente dopo 120 giorni.

## Rinuncia a livello di partner {#partner-opt-out}

La rinuncia a livello di partner consente di rifiutare la raccolta di dati da parte di partner Audience Manager specifici. La rinuncia a livello di partner funziona con le chiamate ID [](../../features/declared-ids.md) dichiarati e con le chiamate ID dispositivo, come descritto nelle sezioni seguenti.

### Rinuncia a livello di partner con chiamate ID dichiarate

A seguito di una rinuncia a livello di partner con una chiamata ID dichiarata:

* L'ultimo ID dispositivo (ID[utente univoco di](../../reference/ids-in-aam.md)Audience Manager) collegato all'ID [](../../reference/ids-in-aam.md) CRM viene escluso dalla raccolta dati.
* Audience Manager cesserà tutte le attività di raccolta, segmentazione o attivazione dei dati in corso per l'ultimo ID dispositivo collegato all'ID CRM.
* Nessun dato storico viene eliminato.

<br/>

**Chiamate di rifiuto**

Quando Audience Manager riceve una richiesta di rifiuto a livello di partner, il JSON restituito dal DCS contiene il codice di [errore 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con il messaggio [!UICONTROL "Encountered opt out tag"], invece dell’ID utente di Audience Manager.

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**Esempi**

Puoi effettuare una richiesta di rifiuto con ID dichiarato con le coppie `d_cid` `d_cid_ic` e valore chiave. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consultate [CID sostituisce DPID e DPUUID](../../reference/cid.md) Negli esempi, il *corsivo* indica un segnaposto variabile.

**Consenso con CID e CID_IC**

Per una descrizione e una sintassi, consultate Variabili [URL e sintassi per ID](../../features/declared-ids.md#variables-and-syntax)dichiarati.

| Rifiuto tramite | Esempio di codice |
|--- |--- |
| ID provider di dati e ID utente. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| Un codice di integrazione e un ID utente. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| Più coppie d_cid e d_cid_ic chiave-valore. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### Rinuncia a livello di partner con chiamate ID dispositivo

Puoi rifiutare la raccolta di dati su un determinato ID dispositivo per un marchio effettuando le seguenti chiamate all'API [](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS:

| Rifiuto tramite | Esempio di codice |
|--- |--- |
| Un ID Utente Univoco Audience Manager (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Ulteriori informazioni `uuid`e informazioni `mid` e `imsOrgId` informazioni sull’ [indice degli ID in Audience Manager](/help/using/reference/ids-in-aam.md).

In seguito a una rinuncia a livello di partner con una chiamata ID dispositivo:

* L'ID dispositivo viene escluso dalla raccolta dati.
* Audience Manager cesserà tutte le attività di raccolta, segmentazione o attivazione dei dati per il partner, andando avanti per l'ID dispositivo.
* Nessun dato storico viene eliminato.
