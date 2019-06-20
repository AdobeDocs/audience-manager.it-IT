---
description: Aggiornate il codice per utilizzare d_ cid o d_ cid_ ic invece di d_ dpid e d_ dpuuid. Le variabili DPID e DPUUID continueranno a funzionare, ma devi considerarle obsolete. Ciò include varianti DPID e DPUUID senza il prefisso d_.
seo-description: Aggiornate il codice per utilizzare d_ cid o d_ cid_ ic invece di d_ dpid e d_ dpuuid. Le variabili DPID e DPUUID continueranno a funzionare, ma devi considerarle obsolete. Ciò include varianti DPID e DPUUID senza il prefisso d_.
seo-title: CID sostituisce DPID e DPUUID
solution: Audience Manager
title: CID sostituisce DPID e DPUUID
uuid: 3641 eac 5-b 19 e -45 d 5-bc 1 c -35 a 23 b 4 bab 8 c
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# CID sostituisce DPID e DPUUID{#cid-replaces-dpid-and-dpuuid}

Aggiorna il codice da usare `d_cid` , `d_cid_ic` invece `d_dpid` che e `d_dpuuid`. Le variabili DPID e DPUUID continueranno a funzionare, ma devi considerarle obsolete. Include varianti DPID e DPUUID senza `d_ prefix`.

## DPID e DPUUID: Una revisione {#dpid-dpuuid-review}

DPID e DPUUID sono coppie chiave-valore contenenti un ID provider dati e un ID utente. Queste coppie chiave-valore collegate ID di fornitori a ID utente. Essi inviano dati durante le chiamate all&#39;evento, per gli eventi di sincronizzazione in entrata e per le chiamate ID. Senza di essi, [!DNL Audience Manager]e altri servizi o funzionalità, non sarebbe possibile abbinare e sincronizzare gli ID. Queste variabili vengono talvolta espresse con o senza `d_` il prefisso come mostrato di seguito. Nota, nel codice il *corsivo* indica un segnaposto variabile.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Sintassi </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID provider dati (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_ dpid =<i>ID provider dati</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid =<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Provider Unique User ID (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_ dpuuid =<i>provider utente univoco per i dati</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid =<i>ID utente univoco per i dati</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Queste coppie chiave-valore funzionano ancora, ma sono obsolete. È necessario aggiornare il codice per utilizzare CID o CID_ IC.

## CID e CID_ IC: Informazioni {#cid-cidic-about}

Le coppie chiave-valore CID e CID_ IC sostituiscono DPID e DPUUID. Essi forniscono le stesse funzioni di DPID e DPUUID, ma sono più efficienti perché includono l&#39;ID del provider di dati (o codice di integrazione) e l&#39;ID utente in una singola coppia chiave-valore. In ciascuna coppia chiave-valore:

* Il simbolo = separa la chiave dai relativi valori.
* Il carattere ASCII non stampabile % 01 separa i valori.

`d_cid` e `d_cid_ic` utilizzate la sintassi indicata di seguito. Nota, nel codice il *corsivo* indica un segnaposto variabile.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Sintassi </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID cliente (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid =<i>provider di dati ID</i>% 01<i>utente</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice integrazione ID cliente (CID_ IC) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid_ ic =<i>codice di integrazione</i>% 01<i>ID utente</i></code> </p> <p> Un <span class="term"> codice di integrazione</span> è un ID alternativo che puoi utilizzare invece dell'ID origine dati, assegnato da <span class="keyword"> Audience Manager</span>. Per configurare un codice di integrazione, consulta <a href="../features/manage-datasources.md#create-data-source"> Creazione di un'origine</a> dati. </p> </td> 
  </tr> 
 </tbody> 
</table>

Vedi anche Variabili [URL e sintassi per ID dichiarati](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>Puoi utilizzare i codici di integrazione per le tue origini dati e per le origini dati [condivise globali a cui hai accesso](../features/datasources-list-and-settings.md#settings-menu-options). Ad esempio, potete utilizzare i codici di integrazione quando si utilizzano le origini dati per identificatori mobili. Utilizzate i seguenti codici di integrazione, esattamente come indicato di seguito:

* **DSID_ 20914** per GAID, che rappresenta i dispositivi con il sistema operativo Android.
* **DSID_ 20915** per IDFA, che rappresenta i dispositivi con sistema operativo iOS.

**Esempi**

Nella tabella seguente sono riportati gli esempi per tipo di evento.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo evento </th> 
   <th colname="col2" class="entry"> Esempio  </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evento </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">Nuovo: <code> …/event? d_ cid = 123% 01987…</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Obsoleto: <code> …/event? d_ dpid = 123 &amp; d_ dpuuid = 987…</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronizzazione in entrata (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">Nuovo: <code> …/ibs: d_ cid = 123% 01987…</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Obsoleto: <code> …/ibs: d_ dpid = 123 &amp; d_ dpuuid = 987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Genera UUID Audience Manager (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">Nuovo: <code> …/id? d_ cid = 123% 01987…</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Obsoleto: <code> …/id? d_ dpid = 123 &amp; d_ dpuuid = 987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Ogni chiamata può includere anche coppie di valori chiave e `d_cid``d_cid_ic` chiave come questa:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Considerazioni importanti per i team di sviluppo {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Elemento </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Codifica URL </p> </td> 
   <td colname="col2"> <p>I team <i>di sviluppo</i> devono applicare la codifica URL alle seguenti variabili nella coppia chiave-valore CID: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> ID utente</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Nota: Devi codificare l'ID utente e il codice di integrazione <i>prima di</i> concatenarli in una stringa. poiché il carattere ASCII % 01 che separa le due variabili non deve essere acquisito nella codifica URL. </p> </p> <p>La codifica URL assicura che gli ID utente e i codici di integrazione che contengono caratteri riservati o non sicuri, ad esempio, ma non limitati, siano trasmessi correttamente ai nostri server. </p> <p>Utilizzare la <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> tabella di codifica ASCII</a> per riferimento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso dei codici di integrazione per le origini dati condivise globali </p> </td> 
   <td colname="col2"> <p>Puoi utilizzare i codici di integrazione per le tue origini dati e per le origini dati <a href="../features/datasources-list-and-settings.md#settings-menu-options"> condivise globali a cui hai accesso</a>. Ad esempio, potete utilizzare i codici di integrazione quando si utilizzano le origini dati per identificatori mobili. Utilizzate i seguenti codici di integrazione, esattamente come indicato di seguito: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_ 20914</b> per GAID, che rappresenta i dispositivi con il sistema operativo Android. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_ 20915</b> per IDFA, che rappresenta i dispositivi con sistema operativo iOS. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

