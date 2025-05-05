---
description: Funzionamento degli ID dichiarati, impostazione di procedure, esempi di codice e variabili.
keywords: sincronizzazione id
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: ID dichiarati
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Funzionamento di [!UICONTROL declared IDs], impostazione di procedure, esempi di codice e variabili.

## Targeting [!UICONTROL Declared ID] {#declared-id-targeting}

Scambia e sincronizza gli ID utente con [!DNL Audience Manager] da dispositivi o browser che non utilizzano o accettano meccanismi di archiviazione persistenti, ad esempio [!DNL cookies] di terze parti.

## Scopo del targeting [!UICONTROL Declared ID] {#declared-id-targeting-purpose}

Alcuni browser e la maggior parte dei dispositivi mobili non accettano [!DNL cookies] di terzi. Questo rende difficile conservare le informazioni sui visitatori del sito o assegnare ID persistenti. Per risolvere il problema, [!DNL Audience Manager] utilizza [!UICONTROL DIL] per consentire il passaggio di [!UICONTROL declared IDs] a una chiamata evento. Inoltre, un [!UICONTROL declared ID] può fungere da ID universale che si applica allo stesso utente in tutte le soluzioni di [!DNL Experience Cloud]. La tabella seguente descrive il processo di targeting ID/corrispondenza:

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
   <td colname="col2"> <p>Per funzionare, è necessario <span class="wintitle"> codice DIL </span> e <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it" format="https" scope="external"> codice Adobe Experience Platform Identity Service </a> nella pagina. <span class="wintitle"> DIL </span> ottiene <span class="wintitle"> ID dichiarati </span> dalla funzione <code> setVisitorID </code> fornita dal servizio Adobe Experience Platform Identity </span> di <span class="keyword"> e lo trasmette a <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID corrispondenza</b> </td> 
   <td colname="col2"> <p>Audience Manager tenta di far corrispondere l’ID cliente e visitatore con un ID corrispondente nel nostro sistema. Se non esiste un ID corrispondente, Audience Manager crea un nuovo ID e lo associa all’ID client e visitatore. </p> <p> <p>Nota: viene utilizzata la mappatura più recente se l’ID è mappato su più di un Audience Manager ID. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID restituito</b> </td> 
   <td colname="col2"> <p>Audience Manager scrive il proprio ID sincronizzato in un cookie di prime parti (o in un altro spazio di archiviazione indirizzabile) nel dominio o nell’applicazione client. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chiamate evento successive</b> </td>
   <td colname="col2"> <p>Chiamate evento aggiuntive leggono l’Audience Manager ID dal dominio del client e lo inviano ad Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Per iniziare, devi configurare il servizio ID [!DNL Experience Cloud] e [!UICONTROL DIL] nelle pagine del sito che desideri utilizzare per la raccolta dati. Consulta [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) e [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Chiamate di rinuncia {#opt-out-calls}

Il processo [!UICONTROL declared ID] rispetta le preferenze del visitatore del sito per la rinuncia al targeting di [!DNL Audience Manager] da parte del sito Web. Quando [!DNL Audience Manager] riceve una richiesta di rinuncia, [!DNL JSON] restituito da [!DNL DCS] contiene il codice di errore 171, con il messaggio `Encountered opt out tag`, invece dell&#39;ID utente [!DNL Audience Manager].

* [!DNL Audience Manager] può passare una rinuncia a [!UICONTROL declared ID] insieme a un [!DNL Audience Manager] [!UICONTROL UUID] in [!DNL URL].
* La rinuncia a [!UICONTROL declared ID] è archiviata in [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) in base al partner. Non esiste alcuna rinuncia a livello di piattaforma utilizzando [!UICONTROL declared IDs]. Inoltre, [!DNL Audience Manager] rinuncia all&#39;utente da quella particolare area sul server Edge di (la rinuncia non attraversa [!DNL DCS] aree).

Consulta [Privacy dei dati](../overview/data-security-and-privacy/data-privacy.md) per ulteriori informazioni sulla rinuncia alla raccolta dei dati.

## [!UICONTROL Declared ID] esempi di rinuncia {#opt-out-examples}

È possibile effettuare una [!UICONTROL declared ID] richiesta di rinuncia con le coppie chiave-valore `d_cid` e `d_cid_ic`. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consulta [CID Replaces DPID and DPUUID](../reference/cid.md). Negli esempi, il *corsivo* indica un segnaposto variabile.

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

Questi metodi continuano a funzionare, ma sono considerati obsoleti. Queste informazioni sono fornite per scopi e riferimenti legacy. Le rinunce legacy includono:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rinuncia (obsoleto) </th> 
   <th colname="col2" class="entry"> Esempio di codice </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Solo <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rinuncia a livello di partner </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Viene archiviata una rinuncia a livello di partner per la mappatura più recente di questa coppia <code> dpid </code> + <code> dpuuid </code> su un UUID di AAM. Se non esiste alcuna mappatura precedente, Audience Manager controlla se la richiesta contiene un UUID di AAM nel cookie e, in caso affermativo, lo utilizza per memorizzare la rinuncia. In caso contrario, Audience Manager genera un nuovo UUID di AAM e memorizza la rinuncia al suo interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> e <code> d_uuid </code> esplicito </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> ha sempre la precedenza. Se la combinazione <code> dpid </code> + <code> dpuuid </code> è mappata a un altro UUID di AAM, la rinuncia viene memorizzata nell'UUID di AAM passato nella richiesta ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili e sintassi per [!UICONTROL Declared IDs] {#variables-and-syntax}

Nella tabella seguente sono elencate le coppie chiave-valore passate nell&#39;ID provider dati [!DNL Audience Manager] e negli ID utente o nei codici di integrazione, se utilizzati. Nota: *corsivo* indica un segnaposto variabile. Sono stati aggiunti degli spazi per facilitarne la lettura.

In ogni coppia chiave-valore:

* Il simbolo `=` separa la chiave dai valori correlati.
* Il carattere `%01` [!DNL ASCII] non stampabile separa i valori.

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
   <td colname="col2"> <p>Contiene un ID provider dati e un ID utente univoco associato in una singola coppia chiave-valore. <code> d_cid </code> sostituisce <code> d_dpid </code> e <code> d_dpuuid </code>, considerati obsoleti ma ancora supportati. Vedere <a href="../reference/cid.md"> CID sostituisce DPID e DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un codice di integrazione e un ID utente univoco associato in una singola coppia chiave-valore. <code> d_cid_ic </code> sostituisce <code> d_dpid </code> e <code> d_dpuuid </code>, che sono obsoleti, ma ancora supportati. Vedere <a href="../reference/cid.md"> CID sostituisce DPID e DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Chiamate evento di esempio {#sample-event-calls}

Considerate queste coppie chiave-valore e la loro sintassi richiesta, dovrai effettuare chiamate evento come mostrato di seguito.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> La chiamata dell'evento include </th> 
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

## [!UICONTROL Declared ID] variabili {#declared-id-variables}

Descrive le variabili di configurazione utilizzate per passare da [!UICONTROL declared IDs] a [!DNL Audience Manager.] tramite [!UICONTROL DIL]

## [!UICONTROL DIL] utilizza [!DNL Adobe Experience Platform Identity Service] per passare [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Se utilizzato con il servizio [Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it), non è più necessario passare [!UICONTROL declared IDs] con le variabili `dpid` e `dpuuid` obsolete. Le versioni correnti di [!UICONTROL DIL] si basano invece sulla funzione `visitorService` per ottenere [!UICONTROL declared IDs] dalla funzione `setCustomerIDs` in [!UICONTROL Adobe Experience Platform Identity Service]. Per ulteriori informazioni, consulta [ID cliente e stati di autenticazione](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=it). Chiameresti `visitorService` in `DIL.create` come mostrato di seguito.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Nella coppia chiave-valore `namespace`, `MCORG` è l&#39;ID organizzazione [!DNL Experience Cloud]. Se non disponi di questo ID, puoi trovarlo nella sezione [!UICONTROL Administration] del dashboard [!DNL Experience Cloud]. Per visualizzare questo dashboard sono necessarie le autorizzazioni di amministratore. Consulta [Introduzione ai servizi Experience Cloud](https://experienceleague.adobe.com/it/docs/core-services/interface/services/getting-started).

## Funzioni obsolete {#deprecated-functions}

Con le versioni più recenti di [!UICONTROL DIL] (6.2+), non è necessario utilizzare queste coppie chiave-valore per passare [!UICONTROL declared IDs]. Questo perché [!UICONTROL DIL] ora si basa sulla funzione `visitorService` mostrata nell&#39;esempio di codice precedente. Questa funzione ottiene [!UICONTROL declared IDs] da [!UICONTROL Adobe Experience Platform Identity Service]. Tuttavia, stiamo facendo riferimento a queste variabili qui per scopi storici e legacy. Vedere il codice seguente per un esempio di configurazione di `DIL.create` per ottenere un [!UICONTROL declared ID] da [!UICONTROL Visitor ID Service].
Nella tabella seguente vengono descritte le variabili legacy utilizzate dall&#39;oggetto `declaredId`:

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

### [!UICONTROL DPID] e [!UICONTROL DPUUID]

[!DNL Audience Manager] confronta e confronta `DPID` e `DPUUID` combinati con un ID utente corrispondente nel nostro sistema. Se un ID non esiste, [!DNL Audience Manager] crea un nuovo ID utente e lo sincronizza con la combinazione `DPID/DPUUID`. Una volta che [!DNL Audience Manager] corrisponde o crea un ID utente (`UUID`), restituisce tale ID nella risposta [!DNL JSON] a [!DNL cookie] nel dominio del client (prime parti [!DNL cookie]) o in un altro archivio locale.

Chiamare questa funzione quando si utilizza [!UICONTROL DIL] v6.1 o versione precedente. Questa funzione è stata tuttavia rimossa a favore della nuova versione che ottiene [!UICONTROL declared IDs] da [!DNL Adobe Experience Platform Identity Service].

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
>È necessario sviluppare a livello di programmazione il codice che fornisce i valori ID per le chiavi `d_dpuuid` e `d_dpid`.

### Passa Gli ID Dopo [!UICONTROL DIL] Istanze

>[!NOTE]
>
>Se effettui una chiamata [!DNL API] con una diversa combinazione di `declaredID`, la nuova combinazione verrà utilizzata solo per tale chiamata. Per ulteriori chiamate di evento regolari verrà utilizzata la combinazione originale di `DIL.create` `declaredID`.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Esempi di richieste/risposte {#request-response-examples}

La richiesta invia un provider di dati e un ID utente a [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La risposta restituisce l&#39;Audience Manager ID (ad esempio, `UUID`) scritto in un cookie di prime parti nel dominio della pagina.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Non eseguire il targeting delle chiamate e delle chiamate di rinuncia {#do-not-target}

Il processo [!UICONTROL declared ID] rispetta le preferenze del visitatore del sito per la rinuncia al targeting di [!DNL Audience Manager] da parte del sito Web. Quando [!DNL Audience Manager] riceve una richiesta di rinuncia, [!DNL DCS] restituisce un oggetto [!DNL JSON] vuoto invece dell&#39;ID utente [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [CID sostituisce DPID e DPUUID](../reference/cid.md)
