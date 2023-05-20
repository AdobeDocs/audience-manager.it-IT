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
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 9%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Come [!UICONTROL declared IDs] lavoro, configurazione di procedure, esempi di codice e variabili.

## [!UICONTROL Declared ID] Targeting {#declared-id-targeting}

Scambia e sincronizza gli ID utente con [!DNL Audience Manager] da dispositivi o browser che non utilizzano o non accettano meccanismi di archiviazione persistenti, ad esempio sistemi di terze parti [!DNL cookies].

## Scopo di [!UICONTROL Declared ID] Targeting {#declared-id-targeting-purpose}

Alcuni browser e la maggior parte dei dispositivi mobili non accettano sistemi di terze parti [!DNL cookies]. Questo rende difficile conservare le informazioni sui visitatori del sito o assegnare ID persistenti. Per risolvere il problema: [!DNL Audience Manager] utilizza [!UICONTROL DIL] per consentire il passaggio [!UICONTROL declared IDs] durante una chiamata evento. Inoltre, un [!UICONTROL declared ID] può fungere da ID universale che si applica allo stesso utente in tutte le soluzioni di [!DNL Experience Cloud]. La tabella seguente descrive il processo di targeting ID/corrispondenza:

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
   <td colname="col2"> <p>Per lavorare, è necessario <span class="wintitle"> DIL </span> e <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Servizio Adobe Experience Platform Identity </a> sulla pagina. <span class="wintitle"> DIL </span> ottiene <span class="wintitle"> ID dichiarati </span> dal <code> setVisitorID </code> funzione fornita da <span class="keyword"> Servizio Adobe Experience Platform Identity </span> e lo trasmette a <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID corrispondenza</b> </td> 
   <td colname="col2"> <p>L’Audience Manager tenta di far corrispondere l’ID del cliente e del visitatore con un ID corrispondente nel nostro sistema. Se non esiste un ID corrispondente, Audience Manager crea un nuovo ID e lo associa all’ID client e visitatore. </p> <p> <p>Nota: viene utilizzata la mappatura più recente se l’ID è mappato su più ID Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID restituito</b> </td> 
   <td colname="col2"> <p>Audience Manager scrive il proprio ID sincronizzato in un cookie di prima parte (o in un altro spazio di archiviazione indirizzabile) nel dominio o nell’applicazione client. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Chiamate evento successive</b> </td>
   <td colname="col2"> <p>Chiamate evento aggiuntive leggono l’ID dell’Audience Manager dal dominio del client e lo inviano all’Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Per iniziare, devi configurare il [!DNL Experience Cloud] Servizio ID e [!UICONTROL DIL] nelle pagine del sito che si desidera utilizzare per la raccolta dati. Consulta [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) e [Variabili ID dichiarate](../features/declared-ids.md#declared-id-variables).

## Chiamate di rinuncia {#opt-out-calls}

Il [!UICONTROL declared ID] il processo rispetta le preferenze del visitatore del sito per la rinuncia a [!DNL Audience Manager] eseguire il targeting in base al sito web. Quando [!DNL Audience Manager] riceve una richiesta di rinuncia, il [!DNL JSON] restituito da [!DNL DCS] contiene il codice di errore 171, con il messaggio `Encountered opt out tag`, invece del [!DNL Audience Manager] ID utente.

* [!DNL Audience Manager] può passare un [!UICONTROL declared ID] rinuncia insieme a un [!DNL Audience Manager] [!UICONTROL UUID] nel [!DNL URL].
* Il [!UICONTROL declared ID] la rinuncia viene memorizzata in [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) per ciascun partner. Non esiste alcuna rinuncia a livello di piattaforma utilizzando [!UICONTROL declared IDs]. Inoltre, [!DNL Audience Manager] rifiuta all’utente di uscire da quella particolare area del bordo (la rinuncia non attraversa [!DNL DCS] regioni).

Consulta [Privacy dei dati](../overview/data-security-and-privacy/data-privacy.md) per ulteriori informazioni sulla rinuncia alla raccolta di dati.

## [!UICONTROL Declared ID] Esempi di rinuncia {#opt-out-examples}

È possibile effettuare una [!UICONTROL declared ID] richieste di rinuncia con `d_cid` e `d_cid_ic` coppie chiave-valore. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consulta [CID Replaces DPID and DPUUID](../reference/cid.md). Negli esempi, il *corsivo* indica un segnaposto variabile.

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
   <td colname="col1"> <p>Più <code> d_cid </code> e <code> d_cid_ic </code> coppie chiave-valore. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Rinunce con [!UICONTROL DPID], [!UICONTROL DPUUID], e [!UICONTROL UUID] (Obsoleto)

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
   <td colname="col1"> <p> <code> d_uuid </code> solo </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rinuncia a livello di partner </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Viene memorizzata una rinuncia a livello di partner per la mappatura più recente di questo <code> dpid </code> + <code> dpuuid </code> associarlo a un UUID AAM. Se non esiste alcuna mappatura precedente, Audience Manager controlla se la richiesta contiene un UUID AAM nel cookie e, in caso affermativo, lo utilizza per memorizzare la rinuncia. In caso contrario, Audience Manager genera un nuovo UUID AAM e memorizza la rinuncia al suo interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> ed esplicito <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> ha sempre la precedenza. Se il <code> dpid </code> + <code> dpuuid </code> viene mappato su un altro AAM UUID, la rinuncia viene memorizzata sotto l’AAM UUID passato nella richiesta ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili e sintassi per [!UICONTROL Declared IDs] {#variables-and-syntax}

Nella tabella seguente sono elencate le coppie chiave-valore che passano nel [!DNL Audience Manager] ID del provider dati e ID utente o codici di integrazione, se utilizzati. Nota: *corsivo* indica un segnaposto variabile. Sono stati aggiunti degli spazi per facilitarne la lettura.

In ogni coppia chiave-valore:

* Il `=` separa la chiave dai valori correlati.
* La non stampa [!DNL ASCII] carattere `%01` separa i valori.

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
   <td colname="col2"> <p>Contiene un ID provider dati e un ID utente univoco associato in una singola coppia chiave-valore. <code> d_cid </code> sostituisce <code> d_dpid </code> e <code> d_dpuuid </code>, considerati obsoleti, ma ancora supportati. Consulta <a href="../reference/cid.md">CID Replaces DPID and DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contiene un codice di integrazione e un ID utente univoco associato in una singola coppia chiave-valore. <code> d_cid_ic </code> sostituisce <code> d_dpid </code> e <code> d_dpuuid </code>, che sono obsoleti, ma sono ancora supportati. Consulta <a href="../reference/cid.md">CID Replaces DPID and DPUUID </a>. </p> </td> 
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
   <td colname="col1"> <p>Più <code> d_cid </code> e <code> d_cid_ic </code> coppie chiave-valore. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variabili {#declared-id-variables}

Descrive le variabili di configurazione utilizzate per trasmettere [!UICONTROL declared IDs] da a [!UICONTROL DIL] a [!DNL Audience Manager.]

## [!UICONTROL DIL] utilizza [!DNL Adobe Experience Platform Identity Service] da superare [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Se utilizzato con [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html), non è più necessario trasmettere [!UICONTROL declared IDs] con il deprecato `dpid` e `dpuuid` variabili. Invece, le versioni correnti di [!UICONTROL DIL] affidarsi a `visitorService` funzione per ottenere [!UICONTROL declared IDs] dal `setCustomerIDs` funzione in [!UICONTROL Adobe Experience Platform Identity Service]. Per ulteriori informazioni, consulta [ID cliente e stati di autenticazione](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). Chiameresti `visitorService` in `DIL.create` come mostrato di seguito.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In `namespace` coppia chiave-valore, `MCORG` è il tuo [!DNL Experience Cloud] ID organizzazione. Se non disponi di questo ID, puoi trovarlo in [!UICONTROL Administration] sezione del [!DNL Experience Cloud] dashboard. Per visualizzare questo dashboard sono necessarie le autorizzazioni di amministratore. Consulta [Amministrazione: servizi core](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## Funzioni obsolete {#deprecated-functions}

Con le versioni più recenti di [!UICONTROL DIL] (6.2+), non è necessario utilizzare queste coppie chiave-valore per passare [!UICONTROL declared IDs]. È perché... [!UICONTROL DIL] ora si basa su `visitorService` come mostrato nell’esempio di codice precedente. Questa funzione ottiene [!UICONTROL declared IDs] dal [!UICONTROL Adobe Experience Platform Identity Service]. Tuttavia, stiamo facendo riferimento a queste variabili qui per scopi storici e legacy. Per un esempio di configurazione, consulta il codice seguente `DIL.create` per ottenere un [!UICONTROL declared ID] dal [!UICONTROL Visitor ID Service].
La tabella seguente descrive le variabili legacy utilizzate da `declaredId` oggetto:

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
   <td colname="col3"> <p>ID partner dati assegnato dall’Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Stringa </td> 
   <td colname="col3"> <p>ID univoco del fornitore di dati per l'utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] e [!UICONTROL DPUUID]

[!DNL Audience Manager] confronta e confronta il `DPID` e `DPUUID` a un ID utente corrispondente nel nostro sistema. Se non esiste un ID, [!DNL Audience Manager] crea un nuovo ID utente e lo sincronizza con `DPID/DPUUID` combinazione. Una volta [!DNL Audience Manager] corrisponde o crea un ID utente (il `UUID`) restituisce tale ID nella [!DNL JSON] risposta al [!DNL cookie] nel dominio del client (prime parti) [!DNL cookie]) o altro tipo di storage locale.

Chiama questa funzione quando utilizzi [!UICONTROL DIL] versione 6.1 o precedente. Tuttavia, questa funzione è stata rimossa a favore della nuova versione che ottiene [!UICONTROL declared IDs] dal [!DNL Adobe Experience Platform Identity Service].

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
>Devi sviluppare in modo programmatico il codice che fornisce i valori ID per il `d_dpuuid` e `d_dpid` tasti.

### Passa ID dopo [!UICONTROL DIL] Istanze

>[!NOTE]
>
>Se si crea un [!DNL API] chiama con un diverso `declaredID` nuova combinazione verrà utilizzata solo per tale chiamata. Ulteriori chiamate regolari di evento utilizzeranno l’originale `DIL.create`  `declaredID` combinazione.

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

La risposta restituisce l’ID Audience Manager (ad esempio, `UUID`) che viene scritto su un cookie di prime parti nel dominio della pagina.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Non eseguire il targeting delle chiamate e delle chiamate di rinuncia {#do-not-target}

Il [!UICONTROL declared ID] il processo rispetta le preferenze del visitatore del sito per la rinuncia a [!DNL Audience Manager] eseguire il targeting in base al sito web. Quando [!DNL Audience Manager] riceve una richiesta di rinuncia, il [!DNL DCS] restituisce un valore vuoto [!DNL JSON] oggetto invece del [!DNL Audience Manager] ID utente.

>[!MORELIKETHIS]
>
>* [CID sostituisce DPID e DPUUID](../reference/cid.md)

