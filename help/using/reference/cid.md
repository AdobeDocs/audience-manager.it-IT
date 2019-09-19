---
description: Aggiornate il codice per utilizzare d_cid o d_cid_ic invece di d_dpid e d_dpuuid. Le variabili DPID e DPUUID continueranno a funzionare, ma devi considerarle obsolete. Ciò include varianti DPID e DPUUID senza il prefisso d_.
seo-description: Aggiornate il codice per utilizzare d_cid o d_cid_ic invece di d_dpid e d_dpuuid. Le variabili DPID e DPUUID continueranno a funzionare, ma devi considerarle obsolete. Ciò include varianti DPID e DPUUID senza il prefisso d_.
seo-title: CID sostituisce DPID e DPUUID
solution: Audience Manager
title: CID sostituisce DPID e DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

Aggiornate il codice per utilizzare `d_cid` o `d_cid_ic` invece di `d_dpid` e `d_dpuuid`. Le variabili DPID e DPUUID continueranno a funzionare, ma devi considerarle obsolete. Questo include varianti DPID e DPUUID senza `d_ prefix`.

## DPID e DPUUID: Revisione {#dpid-dpuuid-review}

Il DPID e il DPUUID sono coppie chiave-valore che contengono un ID provider di dati e un ID utente. Queste coppie chiave-valore collegano gli ID del fornitore agli ID utente. Essi inviano dati durante le chiamate dell'evento, per gli eventi di sincronizzazione in ingresso e per le chiamate ID. Senza di essi, [!DNL Audience Manager]e altri servizi o funzionalità, non avrebbe modo di far corrispondere e sincronizzare gli ID. Queste variabili vengono talvolta espresse con o senza il `d_` prefisso come mostrato di seguito. Nota: nel codice il *corsivo* indica un segnaposto variabile.

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
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=ID provider<i>dati</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=ID provider<i>dati</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID utente univoco provider dati (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=ID utente univoco<i>del provider di dati</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=ID utente univoco<i>del provider di dati</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Queste coppie chiave-valore funzionano ancora, ma sono obsolete. Devi aggiornare il codice per usare CID o CID_IC.

## CID e CID_IC: Informazioni {#cid-cidic-about}

Le coppie chiave-valore CID e CID_IC sostituiscono DPID e DPUUID. Forniscono le stesse funzioni del DPID e del DPUUID, ma sono più efficienti perché includono l'ID provider di dati (o codice di integrazione) e l'ID utente in una singola coppia chiave-valore. In ogni coppia chiave-valore:

* Il simbolo = separa la chiave dai relativi valori.
* Il carattere ASCII non stampabile %01 separa i valori.

`d_cid` e `d_cid_ic` utilizzare la sintassi indicata di seguito. Nota: nel codice il *corsivo* indica un segnaposto variabile.

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
   <td colname="col2"> <p> <code>d_cid=ID<i>provider</i>dati%01<i>ID utente</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice integrazione ID cliente (CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=codice<i>di</i>integrazione%01<i>ID utente</i></code> </p> <p> Un codice <span class="term"> di</span> integrazione è un ID alternativo che puoi utilizzare invece dell'ID origine dati, assegnato da <span class="keyword"> Audience Manager</span>. Per configurare un codice di integrazione, consulta <a href="../features/manage-datasources.md#create-data-source"> Creazione di un'origine</a> dati. </p> </td> 
  </tr> 
 </tbody> 
</table>

Vedi anche Variabili [URL e Sintassi per gli ID](../features/declared-ids.md#variables-and-syntax)dichiarati.

>[!NOTE]
>
>È possibile utilizzare codici di integrazione per le proprie origini dati e per le origini [dati](../features/datasources-list-and-settings.md#settings-menu-options)condivise globali a cui si ha accesso. Ad esempio, è possibile utilizzare i codici di integrazione quando si utilizzano le origini dati degli identificatori mobili. Utilizzate i seguenti codici di integrazione, esattamente come specificato di seguito:

* **DSID_20914** per GAID, che rappresenta i dispositivi con sistema operativo Android.
* **DSID_20915** per IDFA, che rappresenta i dispositivi con il sistema operativo iOS.

**Esempi**

Nella tabella seguente sono riportati alcuni esempi per tipo di evento.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry">  Tipo evento </th> 
   <th colname="col2" class="entry"> Esempio  </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evento </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">Nuovo: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Obsoleto: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronizzazione in ingresso (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">Nuovo: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Obsoleto: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Genera UUID Audience Manager (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">Nuovo: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Obsoleto: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Ogni chiamata può anche includere più coppie di valori `d_cid` e `d_cid_ic` chiave come questa:

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
   <td colname="col2"> <p>I team di sviluppo <i>devono</i> applicare la codifica URL alle seguenti variabili nella coppia chiave-valore CID: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> ID</code> utente <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Nota: È necessario codificare l'ID utente e il codice di integrazione <i>prima</i> di concatenarli in una stringa. Questo perché il carattere ASCII %01 che separa le due variabili non deve essere acquisito nella codifica URL. </p> </p> <p>La codifica URL assicura che gli ID utente e i codici di integrazione che contengono caratteri riservati o non sicuri, ad esempio, ma non limitati a, + o =, vengano trasmessi correttamente ai nostri server. </p> <p>Utilizzate la tabella <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> di codifica</a> ASCII come riferimento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso dei codici di integrazione per le origini dati condivise globali </p> </td> 
   <td colname="col2"> <p>È possibile utilizzare codici di integrazione per le proprie origini dati e per le origini <a href="../features/datasources-list-and-settings.md#settings-menu-options"> dati</a>condivise globali a cui si ha accesso. Ad esempio, è possibile utilizzare i codici di integrazione quando si utilizzano le origini dati degli identificatori mobili. Utilizzate i seguenti codici di integrazione, esattamente come specificato di seguito: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> per GAID, che rappresenta i dispositivi con sistema operativo Android. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> per IDFA, che rappresenta i dispositivi con il sistema operativo iOS. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

