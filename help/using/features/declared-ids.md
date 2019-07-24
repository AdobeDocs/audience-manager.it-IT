---
description: Funzionamento degli ID dichiarati, configurazione delle procedure, esempi di codice e variabili.
keywords: ID id
seo-description: Funzionamento degli ID dichiarati, configurazione delle procedure, esempi di codice e variabili.
seo-title: ID dichiarati
solution: Audience Manager
title: ID dichiarati
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Declared IDs {#declared-ids}

Funzionamento degli ID dichiarati, configurazione delle procedure, esempi di codice e variabili.

## Declared ID Targeting {#declared-id-targeting}

Exchange e sincronizza gli ID utente con Audience Manager da dispositivi o browser che non utilizzano o accettano meccanismi di memorizzazione persistenti, ad esempio cookie di terze parti.

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

Alcuni browser e la maggior parte dei dispositivi mobili non accettano i cookie di terze parti. Ciò rende difficile conservare le informazioni sui visitatori del sito o assegnare ID permanenti. To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. La tabella seguente descrive il targeting/processo di targeting ID:

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
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> DIL </span> richiama <span class="wintitle"> gli ID </span> dalla funzione <code> setvisitorid </code> fornita dal servizio <span class="keyword"> Experience Cloud ID </span> e trasmette così ad <span class="keyword"> Audience Manager </span>. </p> </td> 
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

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. See [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

The [!UICONTROL declared ID] process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message "Encountered opt out tag", instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* The [!UICONTROL declared ID] opt-out is stored in the [!UICONTROL Profile Cache Serveîr ([!UICONTROL PCS]) on a per-partner basis. There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. Consultate [CID sostituisce DPID e DPUUID](../reference/cid.md) In the examples, *italics* indicates a variable placeholder.

### Rinunce con CID e CID_ IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

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
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID &amp; d_ dpid = data provider ID </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. In assenza di mappatura esistente, Audience Manager verifica se la richiesta contiene un UUID AAM nel cookie e, in caso affermativo, utilizza quella per memorizzare la rinuncia. In caso contrario, Audience Manager genera un nuovo UUID AAM e memorizza la rinuncia al suo interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> and explicit <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>utente ID &amp; d_ dpuuid = provider utente e<i>d_ dpid = ID del fornitore di dati</i></code> </p> <p> <code> d_ uuid </code> ha sempre la precedenza. If the <code> dpid </code> + <code> dpuuid </code> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. Gli spazi sono stati aggiunti per facilitarne la lettura.

In ciascuna coppia chiave-valore:

* `=` Il simbolo separa la chiave dai relativi valori.
* The non-printing [!DNL ASCII] character `%01` separates the values.

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

## Sample Event Calls {#sample-event-calls}

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
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nome</i>/evento? d_ cid = 123% 01987 &amp; d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID sostituisce DPID e DPUUID](../reference/cid.md)


## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

When used with the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in [!UICONTROL declared IDs] with the deprecated `dpid` and `dpuuid` variables. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In the `namespace` key-value pair, `MCORG` is your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. Per visualizzare il dashboard, dovete disporre delle autorizzazioni di amministratore. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don't need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That's because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. Tuttavia, stiamo facendo riferimento a queste variabili a scopo storico e legacy. See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

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

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client's domain (first-party cookie) or other local storage.

Call this function when you're using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>DIL. create ({ 
 partner: " partner name ", 
 Declaredid: {{ 
 dpuuid: <i>dpuuid</i>, 
 DPID: <i>dpid</i> 
 } 
 });</code>
</pre>

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### ID passa in ID dopo l'istanza DIL

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

<pre class="js"><code>DIL. getdil ('partner namè). api. segnali ({…}). declaredid ({ 
 dpuuid:<i>dpuuid</i> 
 dpid:<i>dpid</i> }). 
submit ();</code>
</pre>

## Request/Response Examples {#request-response-examples}

La richiesta invia un provider di dati e un ID utente ad Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

The [!UICONTROL declared ID] process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.