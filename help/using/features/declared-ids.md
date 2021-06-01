---
description: Funzionamento degli ID dichiarati, impostazione di procedure, esempi di codice e variabili.
keywords: sincronizzazione id
seo-description: Funzionamento degli ID dichiarati, impostazione di procedure, esempi di codice e variabili.
seo-title: ID dichiarati
solution: Audience Manager
title: ID dichiarati
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: Sincronizzazioni ID
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 10%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Funzionamento di [!UICONTROL declared IDs], impostazione di procedure, esempi di codice e variabili.

## [!UICONTROL Declared ID] Targeting {#declared-id-targeting}

Scambiare e sincronizzare gli ID utente con [!DNL Audience Manager] da dispositivi o browser che non utilizzano o accettano meccanismi di archiviazione persistenti, ad esempio [!DNL cookies] di terze parti.

## Finalità di [!UICONTROL Declared ID] Targeting {#declared-id-targeting-purpose}

Alcuni browser e la maggior parte dei dispositivi mobili non accettano [!DNL cookies] di terze parti. Questo rende difficile conservare le informazioni sui visitatori del sito o assegnare ID persistenti. Per risolvere questo problema, [!DNL Audience Manager] utilizza [!UICONTROL DIL] per consentire di passare [!UICONTROL declared IDs] a una chiamata dell’evento. Inoltre, un [!UICONTROL declared ID] può fungere da ID universale applicabile allo stesso utente in tutte le soluzioni di [!DNL Experience Cloud]. La tabella seguente descrive il processo di targeting o di corrispondenza degli ID:

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
   <td colname="col2"> <p>Per funzionare, è necessario <span class="wintitle"> DIL </span> e il codice <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> del servizio Adobe Experience Platform Identity </a> sulla pagina. <span class="wintitle"> DIL  </span> ottiene gli ID  <span class="wintitle"> dichiarati  </span> dalla  <code> setVisitorID </code> funzione fornita dal servizio  <span class="keyword"> Adobe Experience Platform Identity  </span> e li trasmette ad  <span class="keyword"> Audience Manager  </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID corrispondenza</b> </td> 
   <td colname="col2"> <p>Audience Manager tenta di far corrispondere l’ID client e visitatore con un ID corrispondente nel nostro sistema. Se non esiste un ID corrispondente, Audience Manager crea un nuovo ID e lo associa al client e all'ID visitatore. </p> <p> <p>Nota:  La mappatura più recente viene utilizzata se l'ID è associato a più di un ID Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID mittente</b> </td> 
   <td colname="col2"> <p>Audience Manager scrive il proprio ID sincronizzato in un cookie di prima parte (o altro spazio di archiviazione indirizzabile) nel dominio o nell’applicazione client. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chiamate evento successive</b> </td>
   <td colname="col2"> <p>Altre chiamate evento leggono l’ID Audience Manager dal dominio del client e lo inviano ad Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Per iniziare, devi configurare il servizio [!DNL Experience Cloud] ID e [!UICONTROL DIL] tra le pagine del sito che desideri utilizzare per la raccolta dei dati. Consulta [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) e [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Chiamate di rinuncia {#opt-out-calls}

Il processo [!UICONTROL declared ID] rispetta le preferenze dei visitatori del sito per rinunciare al targeting [!DNL Audience Manager] da parte del sito web. Quando [!DNL Audience Manager] riceve una richiesta di rinuncia, la [!DNL JSON] restituita da [!DNL DCS] contiene il codice di errore 171, con il messaggio `Encountered opt out tag`, invece dell&#39; [!DNL Audience Manager] ID utente.

* [!DNL Audience Manager] può passare una  [!UICONTROL declared ID] rinuncia insieme a una  [!DNL Audience Manager] [!UICONTROL UUID] nel  [!DNL URL].
* La [!UICONTROL declared ID] rinuncia viene memorizzata in [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) per ciascun partner. Non esiste una rinuncia a livello di piattaforma utilizzando [!UICONTROL declared IDs]. Inoltre, [!DNL Audience Manager] esclude l’utente da quella particolare area sul bordo (la rinuncia non attraversa le [!DNL DCS] aree geografiche).

Per ulteriori informazioni su come rinunciare alla raccolta di dati, consulta [Privacy dei dati](../overview/data-security-and-privacy/data-privacy.md) .

## [!UICONTROL Declared ID] Esempi di rinuncia  {#opt-out-examples}

Puoi effettuare una richiesta di rinuncia [!UICONTROL declared ID] con le coppie chiave-valore `d_cid` e `d_cid_ic`. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consulta [CID Replaces DPID and DPUUID](../reference/cid.md). Negli esempi, il *corsivo* indica un segnaposto variabile.

### Rinunce con [!UICONTROL CID] e [!UICONTROL CID_IC]

Per una descrizione e una sintassi, consulta [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rinuncia tramite </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Un ID provider di dati e un ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un codice di integrazione e un ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Più coppie chiave-valore <code> d_cid </code> e <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Rinunce con [!UICONTROL DPID], [!UICONTROL DPUUID] e [!UICONTROL UUID] (obsoleto)

Questi metodi funzionano ancora ma sono considerati obsoleti. Queste informazioni sono fornite per scopi e riferimenti precedenti. Le rinunce legacy includono:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rinuncia (obsoleta) </th> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Viene memorizzata una rinuncia a livello di partner per la mappatura più recente della coppia <code> dpid </code> + <code> dpuuid </code> a un UUID AAM. Se non esiste una mappatura precedente, Audience Manager controlla se la richiesta contiene un UUID AAM nel cookie e, in caso affermativo, lo utilizza per memorizzare la rinuncia. In caso contrario, Audience Manager genera un nuovo UUID AAM e memorizza la rinuncia sotto di esso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> ed esplicito  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> ha sempre la precedenza. Se la combinazione <code> dpid </code> + <code> dpuuid </code> viene mappata su un altro UUID AAM, la rinuncia viene memorizzata nell’UUID AAM passato nella richiesta ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili e sintassi per [!UICONTROL Declared IDs] {#variables-and-syntax}

Nella tabella seguente sono elencate le coppie chiave-valore che passano l’ [!DNL Audience Manager] ID del provider di dati e gli ID utente o i codici di integrazione, se utilizzati. Nota: *corsivo* indica un segnaposto variabile. Sono stati aggiunti degli spazi per facilitarne la lettura.

In ogni coppia chiave-valore:

* Il simbolo `=` separa la chiave dai relativi valori correlati.
* Il carattere [!DNL ASCII] non stampabile `%01` separa i valori.

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
   <td colname="col2"> <p>Contiene un ID provider di dati e un ID utente univoco associato in una singola coppia chiave-valore. <code> d_cid </code> sostituisce  <code> d_dpid </code> e  <code> d_dpuuid </code>, che sono considerati obsoleti, ma sono ancora supportati. Consulta <a href="../reference/cid.md">CID Replaces DPID and DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un codice di integrazione e un ID utente univoco associato in una singola coppia chiave-valore. <code> d_cid_ic </code> sostituisce  <code> d_dpid </code> e  <code> d_dpuuid </code>, che sono obsoleti, ma sono ancora supportati. Consulta <a href="../reference/cid.md">CID Replaces DPID and DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Chiamate evento di esempio {#sample-event-calls}

Considerate queste coppie chiave-valore e la relativa sintassi richiesta, effettuerai chiamate evento come mostrato di seguito.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Include nella chiamata dell'evento </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Un ID provider di dati e un ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un codice di integrazione e un ID utente. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Più coppie chiave-valore <code> d_cid </code> e <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variabili {#declared-id-variables}

Descrive le variabili di configurazione utilizzate per passare da [!UICONTROL declared IDs] a [!UICONTROL DIL] a [!DNL Audience Manager.]

## [!UICONTROL DIL] utilizza  [!DNL Adobe Experience Platform Identity Service] per passare  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Se utilizzato con il servizio [Adobe Experience Platform Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html), non è più necessario passare [!UICONTROL declared IDs] con le variabili `dpid` e `dpuuid` obsolete. Le versioni correnti di [!UICONTROL DIL] si basano invece sulla funzione `visitorService` per ottenere [!UICONTROL declared IDs] dalla funzione `setCustomerIDs` in [!UICONTROL Adobe Experience Platform Identity Service]. Per ulteriori informazioni, consulta [ID cliente e stati di autenticazione](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Dovresti chiamare `visitorService` in `DIL.create` come mostrato di seguito.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Nella coppia chiave-valore `namespace`, `MCORG` è il tuo [!DNL Experience Cloud] ID organizzazione. Se non disponi di questo ID, puoi trovarlo nella sezione [!UICONTROL Administration] del dashboard [!DNL Experience Cloud]. Per visualizzare questo dashboard è necessario disporre delle autorizzazioni di amministratore. Consulta [Amministrazione: Servizi di base](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Funzioni obsolete {#deprecated-functions}

Con le versioni più recenti di [!UICONTROL DIL] (6.2+), non è necessario utilizzare queste coppie chiave-valore per passare in [!UICONTROL declared IDs]. Questo perché [!UICONTROL DIL] ora si basa sulla funzione `visitorService` mostrata nell&#39;esempio di codice riportato sopra. Questa funzione ottiene [!UICONTROL declared IDs] da [!UICONTROL Adobe Experience Platform Identity Service]. Tuttavia, stiamo facendo riferimento a queste variabili per scopi storici e precedenti. Vedi il codice seguente per un esempio di come configurare `DIL.create` per ottenere un [!UICONTROL declared ID] da [!UICONTROL Visitor ID Service].
La tabella seguente descrive le variabili legacy utilizzate dall&#39;oggetto `declaredId` :

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
   <td colname="col3"> <p>ID del partner dati assegnato dall’Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Stringa </td> 
   <td colname="col3"> <p>ID univoco del fornitore di dati per l'utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] e [!UICONTROL DPUUID]

[!DNL Audience Manager] confronta e corrisponde al combinato  `DPID` e  `DPUUID` a un ID utente corrispondente nel nostro sistema. Se un ID non esiste, [!DNL Audience Manager] crea un nuovo ID utente e lo sincronizza con la combinazione `DPID/DPUUID`. Una volta che [!DNL Audience Manager] corrisponde o crea un ID utente (il `UUID`), restituisce tale ID nella risposta [!DNL JSON] al [!DNL cookie] nel dominio del client (prima parte [!DNL cookie]) o in un altro archivio locale.

Chiama questa funzione quando utilizzi [!UICONTROL DIL] v6.1 o versioni precedenti. Tuttavia, questa funzione è stata rimossa a favore della nuova versione che ottiene [!UICONTROL declared IDs] da [!DNL Adobe Experience Platform Identity Service].

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
>Devi sviluppare programmaticamente il codice che fornisce i valori ID per le chiavi `d_dpuuid` e `d_dpid` .

### Passa gli ID dopo [!UICONTROL DIL] le istanze

>[!NOTE]
>
>Se effettui una chiamata [!DNL API] con una combinazione diversa `declaredID`, la nuova combinazione verrà utilizzata solo per quella chiamata. Ulteriori chiamate regolari agli eventi utilizzeranno la combinazione originale `DIL.create` `declaredID` .

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Esempi di richiesta/risposta {#request-response-examples}

La richiesta invia un provider di dati e un ID utente a [!DNL Audience Manager]:

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

## Non eseguire il targeting e le chiamate di rinuncia {#do-not-target}

Il processo [!UICONTROL declared ID] rispetta le preferenze dei visitatori del sito per rinunciare al targeting [!DNL Audience Manager] da parte del sito web. Quando [!DNL Audience Manager] riceve una richiesta di rinuncia, [!DNL DCS] restituisce un oggetto [!DNL JSON] vuoto invece dell’ [!DNL Audience Manager] ID utente.

>[!MORELIKETHIS]
>
>* [CID sostituisce DPID e DPUUID](../reference/cid.md)

