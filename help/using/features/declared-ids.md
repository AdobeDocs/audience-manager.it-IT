---
description: Funzionamento degli ID dichiarati, configurazione delle procedure, esempi di codice e variabili.
keywords: ID id
seo-description: Funzionamento degli ID dichiarati, configurazione delle procedure, esempi di codice e variabili.
seo-title: ID dichiarati
solution: Audience Manager
title: ID dichiarati
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# ID dichiarati {#declared-ids}

Funzionamento degli ID dichiarati, configurazione delle procedure, esempi di codice e variabili.

## Targeting ID dichiarato {#declared-id-targeting}

Exchange e sincronizza gli ID utente con Audience Manager da dispositivi o browser che non utilizzano o accettano meccanismi di memorizzazione persistenti, ad esempio cookie di terze parti.

<!-- declared_id_about.xml -->

## Scopo del targeting ID dichiarato {#declared-id-targeting-purpose}

Alcuni browser e la maggior parte dei dispositivi mobili non accettano i cookie di terze parti. Ciò rende difficile conservare le informazioni sui visitatori del sito o assegnare ID permanenti. Per risolvere questo problema, Audience Manager utilizza [!UICONTROL DIL] per passare [!UICONTROL declared IDs] a una chiamata evento. Inoltre, può [!UICONTROL declared ID] fungere da ID universale che si applica allo stesso utente in tutte le soluzioni del [!DNL Experience Cloud]. La tabella seguente descrive il targeting/processo di targeting ID:

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Processo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Chiamata evento</b> </td> 
   <td colname="col2"> <p>Per funzionare, devi disporre <span class="wintitle"> del codice DIL </span><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> e del codice del servizio </a> Experience Cloud ID sulla pagina. <span class="wintitle"> DIL </span> richiama <span class="wintitle"> gli ID </span> dalla funzione <code> setvisitorid </code> fornita dal servizio <span class="keyword"> Experience Cloud ID </span> e trasmette così ad <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Corrispondenza ID</b> </td> 
   <td colname="col2"> <p>Audience Manager cerca di far corrispondere il client e l'ID visitatore a un ID corrispondente nel nostro sistema. Se un ID corrispondente non esiste, Audience Manager crea un nuovo ID e lo associa al client e all'ID visitatore. </p> <p> <p>Nota: La mappatura più recente viene utilizzata se l'ID viene mappato su più di un ID Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Return ID</b> </td> 
   <td colname="col2"> <p>Audience Manager scrive l'ID sincronizzato in un cookie di prime parti (o in un altro spazio di archiviazione indirizzabile) nel dominio client o nell'applicazione. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chiamate evento successive</b> </td>
   <td colname="col2"> <p>Altre chiamate all'evento leggete l'ID Audience Manager dal dominio del client e inviano tale ID ad Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Per iniziare, devi configurare il servizio [!DNL Experience Cloud] ID e [!UICONTROL DIL] tra le pagine sul tuo sito che desideri utilizzare per la raccolta dati. Consultate [Creazione](../dil/dil-class-overview/dil-create.md#dil-create) DIL e Variabili ID [dichiarate](../features/declared-ids.md#declared-id-variables).

## Chiamate di rifiuto {#opt-out-calls}

Il [!UICONTROL declared ID] processo rispetta le preferenze dei visitatori del sito per rifiutare il targeting di Audience Manager dal sito Web. Quando Audience Manager riceve una richiesta di rifiuto, quella [!DNL JSON] restituita dal codice [!UICONTROL DCS] di errore 171, con il messaggio «Tag rifiuto rilevato», anziché l'ID utente di Audience Manager.

* Audience Manager può trasmettere una [!UICONTROL declared ID] rinuncia a Audience Manager [!UICONTROL UUID] nella [!DNL URL].
* La [!UICONTROL declared ID] rinuncia è memorizzata in [! UICONTROL Profile Cache Server ([!UICONTROL PCS]) in base al partner. Non [!UICONTROL declared IDs]è disponibile alcuna rinuncia a livello di piattaforma. Inoltre, Audience Manager opta per l'uscita dell'utente da quella particolare area sul margine (la rinuncia non si estende [!UICONTROL DCS] sulle aree).

Consulta [Privacy](../overview/data-security-and-privacy/data-privacy.md) dei dati per ulteriori informazioni su come rifiutare la raccolta di dati.

## Esempi dichiarati di rinuncia ID {#opt-out-examples}

Potete [!UICONTROL declared ID] effettuare una richiesta di rifiuto con `d_cid` le coppie `d_cid_ic` chiave-valore. I parametri legacy come `d_dpid` e `d_dpuuid` continuano a funzionare, ma sono considerati obsoleti. Consultate [CID sostituisce DPID e DPUUID](../reference/cid.md) In questi esempi, *il corsivo* indica un segnaposto variabile.

### Rinunce con CID e CID_ IC

Per una descrizione e una sintassi, vedi [Variabili URL e sintassi per gli ID dichiarati](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rinuncia </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID di provider dati e ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/demoptout.jpg? d_ cid = 123% 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice di integrazione e ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/decrittografia? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coppie chiave-valore multiple <code> d_ cid </code> e <code> d_ cid_ ic </code> . </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/decrittografia? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Rinuncia con DPID, DPUUID e UUID (obsoleto)

Questi metodi funzionano ma sono considerati obsoleti. Queste informazioni sono fornite per scopi e riferimenti precedenti. Le rinunce legacy includono:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rinuncia (obsoleto) </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid </code> only </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=AAM<i></i>ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rinuncia a livello di partner </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID &amp; d_ dpid = data provider ID </code> </p> <p>La rinuncia a livello di partner viene memorizzata per la mappatura più recente della coppia <code> dpid </code> + <code> dpuuid </code> su un UUID AAM. In assenza di mappatura esistente, Audience Manager verifica se la richiesta contiene un UUID AAM nel cookie e, in caso affermativo, utilizza quella per memorizzare la rinuncia. In caso contrario, Audience Manager genera un nuovo UUID AAM e memorizza la rinuncia al suo interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> and explicit <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>utente ID &amp; d_ dpuuid = provider utente e<i>d_ dpid = ID del fornitore di dati</i></code> </p> <p> <code> d_ uuid </code> ha sempre la precedenza. Se la <code> combinazione dpid </code> + <code> dpuuid </code> viene mappata su un altro UUID AAM, la rinuncia viene memorizzata nell'UUID AAM passato nella richiesta ( <code> d_ uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili e sintassi per ID dichiarati {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

Nella tabella seguente sono elencate le coppie chiave-valore che superano l'ID del fornitore [!DNL Audience Manager] di dati e gli ID utente o i codici di integrazione, se utilizzati. Note, *italics* indicates a variable placeholder. Gli spazi sono stati aggiunti per facilitarne la lettura.

In ciascuna coppia chiave-valore:

* `=` Il simbolo separa la chiave dai relativi valori.
* Il carattere non stampabile [!DNL ASCII]`%01` separa i valori.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid =<i>provider di dati ID</i> % 01<i>utente</i></code> </p> </td> 
   <td colname="col2"> <p>Contiene un ID del fornitore di dati e un ID utente univoco associato in una singola coppia chiave-valore. <code> d_ cid </code> sostituisce <code> d_ dpid </code> e <code> d_ dpuuid </code>, che sono considerati obsoleti, ma continuano a essere supportati. Consultate <a href="../reference/cid.md">CID sostituisce DPID e DPUUID</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic =<i>codice di integrazione</i> % 01<i>ID utente</i></code> </p> </td> 
   <td colname="col2"> <p>Contiene un codice di integrazione e un ID utente univoco associato in una singola coppia chiave-valore. <code> d_ cid_ ic </code> sostituisce <code> d_ dpid </code> e <code> d_ dpuuid </code>, che sono obsoleti, ma continuano a essere supportati. Consultate <a href="../reference/cid.md">CID sostituisce DPID e DPUUID</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Chiamate evento di esempio {#sample-event-calls}

Considerate queste coppie chiave-valore e la sintassi richiesta, effettuerai le chiamate evento come mostrato di seguito.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Invito all'evento </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID di provider dati e ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/evento? d_ cid = 123% 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice di integrazione e ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/evento? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coppie chiave-valore multiple <code> d_ cid </code> e <code> d_ cid_ ic </code> . </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/evento? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID sostituisce DPID e DPUUID](../reference/cid.md)


## Variabili ID dichiarate {#declared-id-variables}

Descrive le variabili di configurazione utilizzate per trasmettere ID dichiarati attraverso [!UICONTROL DIL][!DNL Audience Manager.]

## DIL Usa il servizio Experience Cloud ID per trasmettere gli ID dichiarati {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Quando viene usato con [il servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/), non dovrai più trasmettere [!UICONTROL declared IDs] i dati obsoleti `dpid` e `dpuuid` le variabili. Al contrario, le versioni correnti di [!UICONTROL DIL] affidamento sulla `visitorService` funzione hanno la funzione di ottenere la [!UICONTROL declared IDs]`setCustomerIDs` funzione in [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Effettuerai una chiamata `visitorService``DIL.create` come mostrato di seguito.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Nella coppia `namespace` chiave-valore `MCORG` è il tuo [!DNL Experience Cloud] ID organizzazione. Se non disponete di questo ID, potete trovarlo nella [!UICONTROL Administration] sezione del [!DNL Experience Cloud] dashboard. Per visualizzare il dashboard, dovete disporre delle autorizzazioni di amministratore. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Funzioni obsolete {#deprecated-functions}

Con le versioni più recenti di [!UICONTROL DIL] (6.2 +), non è necessario utilizzare queste coppie chiave-valore per passare [!UICONTROL declared IDs]. Questo perché [!UICONTROL DIL] ora si basa sulla `visitorService` funzione mostrata nell'esempio di codice sopra. Questa funzione deriva [!UICONTROL declared IDs] dal [!UICONTROL Experience Cloud ID Service]metodo. Tuttavia, stiamo facendo riferimento a queste variabili a scopo storico e legacy. Per un esempio di configurazione `DIL.create` , [!UICONTROL declared ID] consultate il codice [!UICONTROL Visitor ID Service]seguente.
La tabella seguente descrive le variabili legacy utilizzate dall' `declaredId` oggetto:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Stringa </td> 
   <td colname="col3"> <p>ID partner dati assegnato da Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Stringa </td> 
   <td colname="col3"> <p>ID univoco del fornitore di dati per l'utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` e `DPUUID`

Audience Manager confronta e corrisponde alla combinazione combinato `DPID` e `DPUUID` a un ID utente corrispondente nel nostro sistema. Se un ID non esiste, Audience Manager crea un nuovo ID utente e lo sincronizza con `DPID/DPUUID` la combinazione. Una volta che Audience Manager corrisponde o crea un ID utente (il `UUID`) restituisce tale ID nella [!DNL JSON] risposta al cookie nel dominio del client (cookie first-party) o altra memorizzazione locale.

Chiamate questa funzione quando utilizzate [!UICONTROL DIL] v 6.1 o versioni precedenti. Tuttavia, questa funzione è stata sconsigliata a favore della nuova versione da [!UICONTROL declared IDs][!UICONTROL Experience Cloud ID Service].

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>Nota, è necessario sviluppare in modo programmatico il codice che fornisce i valori ID per `d_dpuuid` i `d_dpid` tasti e le chiavi.

### ID passa in ID dopo l'istanza DIL

>[!NOTE]
>
>Se effettui [!DNL API] una chiamata con `declaredID` una combinazione diversa, verrà utilizzata la nuova combinazione solo per tale chiamata. Altre chiamate a eventi regolari utilizzeranno la `DIL.create``declaredID` combinazione originale.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Esempi di richiesta/risposta {#request-response-examples}

La richiesta invia un provider di dati e un ID utente ad Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La risposta restituisce l'ID Audience Manager (ad es.) `UUID`che viene scritto in un cookie di prime parti nel dominio della pagina.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Non eseguire il targeting e le chiamate di rifiuto {#do-not-target}

Il [!UICONTROL declared ID] processo rispetta le preferenze dei visitatori del sito per rifiutare il targeting di Audience Manager dal sito Web. Quando Audience Manager riceve una richiesta di rifiuto, restituisce [!UICONTROL DCS] un [!DNL JSON] oggetto vuoto anziché l'ID utente di Audience Manager.
