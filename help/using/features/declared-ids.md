---
description: Funzionamento degli ID dichiarati, configurazione di procedure, esempi di codice e variabili.
keywords: id sync
seo-description: Funzionamento degli ID dichiarati, configurazione di procedure, esempi di codice e variabili.
seo-title: ID dichiarati
solution: Audience Manager
title: ID dichiarati
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# ID dichiarati {#declared-ids}

Funzionamento degli ID dichiarati, configurazione di procedure, esempi di codice e variabili.

##  Targeting degli ID dichiarati {#declared-id-targeting}

Scambiate e sincronizzate gli ID utente con Audience Manager da dispositivi o browser che non utilizzano o accettano meccanismi di memorizzazione persistenti, ad esempio cookie di terze parti.

<!-- declared_id_about.xml -->

## Finalità del targeting con ID dichiarato {#declared-id-targeting-purpose}

Alcuni browser e la maggior parte dei dispositivi mobili non accettano i cookie di terze parti. Ciò rende difficile conservare le informazioni sui visitatori del sito o assegnare ID persistenti. Per risolvere questo problema, Audience Manager utilizza [!UICONTROL DIL] per consentirvi di passare [!UICONTROL declared IDs] a una chiamata dell'evento. Inoltre, un [!UICONTROL declared ID] può fungere da ID universale applicabile allo stesso utente in tutte le soluzioni del [!DNL Experience Cloud]. La tabella seguente descrive il processo di targeting degli ID/corrispondenza:

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
   <td colname="col2"> <p>Per funzionare, hai bisogno di <span class="wintitle"> DIL </span> e del codice del servizio <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID </a> sulla pagina. <span class="wintitle"> DIL </span> riceve gli ID <span class="wintitle"> dichiarati </span> dalla <code> setVisitorID </code> funzione fornita dal servizio <span class="keyword"> Experience Cloud ID </span> e li trasmette ad <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID corrispondenza</b> </td> 
   <td colname="col2"> <p>Audience Manager tenta di far corrispondere l'ID cliente e visitatore con un ID corrispondente nel nostro sistema. Se non esiste un ID corrispondente, Audience Manager crea un nuovo ID e lo associa al client e all’ID visitatore. </p> <p> <p>Nota:  La mappatura più recente viene utilizzata se l'ID viene mappato su più ID Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID restituzione</b> </td> 
   <td colname="col2"> <p>Audience Manager scrive il proprio ID sincronizzato su un cookie di prima parte (o su altro spazio di memorizzazione indirizzabile) nel dominio client o nell’applicazione. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chiamate Di Evento Successive</b> </td>
   <td colname="col2"> <p>Altre chiamate di evento leggono l’ID Audience Manager dal dominio del client e lo inviano ad Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Per iniziare, devi configurare il servizio [!DNL Experience Cloud] ID e [!UICONTROL DIL] le pagine del tuo sito che desideri utilizzare per la raccolta dati. Consulta Variabili [ID](../dil/dil-class-overview/dil-create.md#dil-create) DIL create e [dichiarate](../features/declared-ids.md#declared-id-variables).

## Chiamate di rifiuto {#opt-out-calls}

Il [!UICONTROL declared ID] processo rispetta le preferenze dei visitatori del sito per rinunciare al targeting di Audience Manager dal sito Web. Quando Audience Manager riceve una richiesta di rifiuto, il [!DNL JSON] restituito dal [!UICONTROL DCS] feed contiene il codice di errore 171, con il messaggio "Incontrato tag di rifiuto", invece dell’ID utente di Audience Manager.

* Audience Manager può trasmettere una [!UICONTROL declared ID] rinuncia insieme a Audience Manager [!UICONTROL UUID] nella [!DNL URL].
* Il [!UICONTROL declared ID] rifiuto viene memorizzato nel server cache del profilo [!UICONTROL ([!UICONTROL PCS]) su base individuale. Non esiste un rifiuto a livello di piattaforma tramite [!UICONTROL declared IDs]. Inoltre, Audience Manager esclude l'utente da quella particolare area sul margine (la rinuncia non attraversa [!UICONTROL DCS] aree geografiche).

Consulta Privacy [dei](../overview/data-security-and-privacy/data-privacy.md) dati per ulteriori informazioni sul rifiuto della raccolta dei dati.

## Esempi di rifiuto ID dichiarati {#opt-out-examples}

Potete effettuare una richiesta di [!UICONTROL declared ID] rifiuto con le coppie `d_cid` e `d_cid_ic` chiave-valore. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consultate [CID sostituisce DPID e DPUUID](../reference/cid.md) Negli esempi, il *corsivo* indica un segnaposto variabile.

### Consenso con CID e CID_IC

Per una descrizione e una sintassi, consultate Variabili [URL e sintassi per ID](../features/declared-ids.md#variables-and-syntax)dichiarati.

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rifiuto tramite </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID provider di dati e ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un codice di integrazione e un ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Più coppie <code> d_cid </code> e <code> d_cid_ic </code> chiave-valore. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Consenso con DPID, DPUUID e UUID (obsoleto)

Questi metodi funzionano ancora ma sono considerati obsoleti. Queste informazioni sono fornite per scopi e riferimenti legacy. Le opzioni di rifiuto precedenti includono:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rifiuto (obsoleto) </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> only </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rinuncia a livello di partner </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Viene memorizzata una rinuncia a livello di partner per la mappatura più recente di questa <code> dpid </code> + <code> dpuuid </code> coppia a un UUID AAM. Se in precedenza non esiste alcuna mappatura, Audience Manager verifica se la richiesta contiene un UUID AAM nel cookie e, in caso contrario, lo utilizza per memorizzare la rinuncia. In caso contrario, Audience Manager genera un nuovo UUID AAM e memorizza sotto di esso il rifiuto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> ed esplicito <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> ha sempre la precedenza. Se la combinazione <code> dpid </code> + <code> dpuuid </code> viene mappata su un altro UUID AAM, la rinuncia viene memorizzata nell’UUID AAM passato nella richiesta ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili e sintassi per ID dichiarati {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

Nella tabella seguente sono elencate le coppie chiave-valore che passano agli ID del provider di [!DNL Audience Manager] dati e agli ID utente o ai codici di integrazione, se utilizzati. Note, *italics* indicates a variable placeholder. Sono stati aggiunti spazi per agevolare la lettura.

In ogni coppia chiave-valore:

* Il `=` simbolo separa la chiave dai relativi valori.
* Il [!DNL ASCII] carattere non stampabile `%01` separa i valori.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un ID provider di dati e un ID utente univoco associato in una coppia chiave-valore singola. <code> d_cid </code> sostituisce <code> d_dpid </code> e <code> d_dpuuid </code>, che sono considerati obsoleti, ma sono ancora supportati. Consultate <a href="../reference/cid.md">CID sostituisce DPID e DPUUID</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un codice di integrazione e un ID utente univoco associato in una coppia chiave-valore singola. <code> d_cid_ic </code> sostituisce <code> d_dpid </code> e <code> d_dpuuid </code>, che sono obsoleti, ma sono ancora supportati. Consultate <a href="../reference/cid.md">CID sostituisce DPID e DPUUID</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Chiamate evento di esempio {#sample-event-calls}

Considerate queste coppie chiave-valore e la sintassi richiesta, effettuerete le chiamate evento come mostrato di seguito.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> La chiamata dell'evento include </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID provider di dati e ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un codice di integrazione e un ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Più coppie <code> d_cid </code> e <code> d_cid_ic </code> chiave-valore. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili ID dichiarate {#declared-id-variables}

Descrive le variabili di configurazione utilizzate per trasmettere gli ID dichiarati [!UICONTROL DIL] a [!DNL Audience Manager.]

## DIL usa il servizio Experience Cloud ID per trasmettere gli ID dichiarati {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Quando viene utilizzato con il servizio [](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID, non è più necessario passare [!UICONTROL declared IDs] con le variabili `dpid` e `dpuuid` obsolete. Al contrario, le versioni correnti di [!UICONTROL DIL] si basano sulla `visitorService` funzione per ottenere il [!UICONTROL declared IDs] dalla `setCustomerIDs` funzione in [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Puoi effettuare una chiamata `visitorService` in `DIL.create` base a quanto indicato di seguito.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Nella coppia chiave-valore `namespace` è il tuo `MCORG` [!DNL Experience Cloud] ID organizzazione. Se non disponete di questo ID, potete trovarlo nella [!UICONTROL Administration] sezione del [!DNL Experience Cloud] dashboard. Per visualizzare questo dashboard è necessario disporre delle autorizzazioni di amministratore. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Funzioni obsolete {#deprecated-functions}

Con le versioni più recenti di [!UICONTROL DIL] (6.2+), non è necessario utilizzare queste coppie chiave-valore per passare [!UICONTROL declared IDs]. Questo perché [!UICONTROL DIL] ora si basa sulla `visitorService` funzione mostrata nel codice di esempio sopra. Questa funzione viene [!UICONTROL declared IDs] dal [!UICONTROL Experience Cloud ID Service]. Tuttavia, stiamo facendo riferimento a queste variabili per scopi storici e legacy. Consulta il codice seguente per un esempio di come configurare `DIL.create` per ottenere un [!UICONTROL declared ID] da [!UICONTROL Visitor ID Service].
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

Audience Manager confronta e corrisponde al combinato `DPID` e `DPUUID` a un ID utente corrispondente nel nostro sistema. Se un ID non esiste, Audience Manager crea un nuovo ID utente e lo sincronizza con la `DPID/DPUUID` combinazione. Quando Audience Manager corrisponde o crea un ID utente (il `UUID`), restituisce tale ID nella [!DNL JSON] risposta al cookie nel dominio del client (cookie di prima parte) o in altro archivio locale.

Chiama questa funzione quando utilizzi [!UICONTROL DIL] v6.1 o versioni precedenti. Tuttavia, questa funzione è stata sconsigliata a favore della nuova versione che viene [!UICONTROL declared IDs] dalla [!UICONTROL Experience Cloud ID Service].

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
>Nota: devi sviluppare a livello di programmazione il codice che fornisce i valori ID per le chiavi `d_dpuuid` e `d_dpid` .

### Passa gli ID dopo le istanze DIL

>[!NOTE]
>
>Se effettui una [!DNL API] chiamata con una `declaredID` combinazione diversa, la nuova combinazione verrà utilizzata solo per quella chiamata. Ulteriori chiamate di eventi regolari utilizzeranno la `DIL.create` combinazione originale `declaredID` .

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Esempi di richieste/risposte {#request-response-examples}

La richiesta invia un provider di dati e un ID utente ad Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La risposta restituisce l’ID Audience Manager (ad esempio, `UUID`) scritto in un cookie di prima parte nel dominio della pagina.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Non eseguire il targeting e non eseguire il rifiuto delle chiamate {#do-not-target}

Il [!UICONTROL declared ID] processo rispetta le preferenze dei visitatori del sito per rinunciare al targeting di Audience Manager dal sito Web. Quando Audience Manager riceve una richiesta di rifiuto, [!UICONTROL DCS] restituisce un [!DNL JSON] oggetto vuoto invece dell’ID utente di Audience Manager.

>[!MORELIKETHIS]
>
>* [CID sostituisce DPID e DPUUID](../reference/cid.md)

