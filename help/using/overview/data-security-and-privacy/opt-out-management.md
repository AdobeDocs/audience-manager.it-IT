---
description: Adobe rispetta tutti gli standard di settore relativi alla gestione della rinuncia. Continua a leggere per informazioni complete sui tipi di consenso supportati da Audience Manager.
seo-description: Adobe rispetta tutti gli standard di settore relativi alla gestione della rinuncia. Continua a leggere per informazioni complete sui tipi di consenso supportati da Audience Manager.
seo-title: Gestione della rinuncia
solution: Audience Manager
title: Gestione della rinuncia
uuid: 61 b 43 e 0 e-bfe 3-497 e-ade 2-6 a 942 a 98407 e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Opt-out Management{#opt-out-management}

Adobe rispetta tutti gli standard di settore relativi alla gestione della rinuncia. Continua a leggere per informazioni complete sui tipi di consenso supportati da Audience Manager.

## Global Opt-Out {#global-opt-out}

La rinuncia globale rappresenta una rinuncia in Audience Manager e in altre soluzioni Adobe Experience Cloud per tutti i marchi. La tabella seguente elenca i metodi utilizzati per la rinuncia globale:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rinuncia per </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page </a> provides 1-click features that let your end users control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section </a> of the Privacy Choices page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiamate API dirette ad Audience Manager </p> </td> 
   <td colname="col2"> <p>You can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md"> Audience Manager User ID </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex = 12345678901234567890123456789012345678; dextp = 12; DST = 12 " </code> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivi mobili </p> </td> 
   <td colname="col2"> <p>Consultate le impostazioni di privacy e rinuncia per: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Dispositivi Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Dispositivi iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Gli utenti finali possono anche rifiutare la raccolta dati globale visitando i siti Web dei nostri partner di standard del settore.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Seguendo le richieste di rifiuto descritte in precedenza:

* Audience Manager cesserà tutte le operazioni di raccolta, segmentazione o attivazione di dati.
* I dati della cronologia vengono rimossi dal profilo utente dopo 120 giorni.

## Partner Level Opt-Out {#partner-opt-out}

La rinuncia a livello di partner consente di rifiutare la raccolta dati da parte di specifici partner Audience Manager. The partner-level opt-out works with [Declared ID](../../features/declared-ids.md) calls and Device ID calls, as described in the sections below.

### Rinuncia a livello di partner con chiamate ID dichiarate

Dopo una rinuncia a livello di partner con una chiamata ID dichiarata:

* The last device ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) linked to the [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection.
* Audience Manager cesserà tutte le operazioni di raccolta, segmentazione o attivazione di dati per l'ultimo ID dispositivo collegato all'ID CRM.
* Non vengono eliminati dati storici.

<br/>

**Chiamate di rifiuto**

When Audience Manager receives a partner-level opt-out request, the JSON returned by the DCS contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the Audience Manager user ID.

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

You can make a declared ID opt-out request with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. Consultate [CID sostituisce DPID e DPUUID](../../reference/cid.md) In the examples, *italics* indicates a variable placeholder.

**Rinunce con CID e CID_ IC**

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| Rinuncia | Esempio di codice |
|--- |--- |
| ID di provider dati e ID utente. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| Codice di integrazione e ID utente. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| Coppie chiave-valore multiple d_ cid e d_ cid_ ic. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### Rinuncia a livello di partner con chiamate ID dispositivo

You can opt-out from data collection on a given device ID for a brand by making the following calls to the [DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Rinuncia | Esempio di codice |
|--- |--- |
| An Audience Manager Unique User ID (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| An Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Read more about `uuid`, `mid` and `imsOrgId` in the [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Dopo un opt-out a livello di partner con una chiamata ID dispositivo:

* L'ID dispositivo viene rinunciato alla raccolta di dati.
* Audience Manager cesserà tutte le operazioni di raccolta, segmentazione o attivazione di dati per il partner, andando avanti per l'ID dispositivo.
* Non vengono eliminati dati storici.
