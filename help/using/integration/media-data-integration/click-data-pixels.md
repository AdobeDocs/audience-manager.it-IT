---
description: nulle
seo-description: nulle
seo-title: Acquisizione di dati su una campagna tramite chiamate pixel
solution: Audience Manager
title: Acquisizione di dati su una campagna tramite chiamate pixel
uuid: 7 c 3797 f 7-9674-493 d -972 b -38 be 0584 lu
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

Il monitoraggio consente di misurare il coinvolgimento dei visitatori in tutta la tua campagna, in quanto registra l'attività basata su clic per i creativi di terze parti. Similar to impressions collection, an event call is sent to the Audience Manager data collection servers ([!UICONTROL DCS]) for processing. Il visitatore viene quindi reindirizzato all'indirizzo Web desiderato.

## Requisiti

Per le chiamate di monitoraggio sono necessari i seguenti parametri:

* `d_event=click`: Una coppia chiave-valore che identifica una chiamata evento come evento click.
* `d_rd=redirect URL`: Una coppia chiave-valore contenente un reindirizzamento [!DNL URL]codificato.

Inoltre, la chiamata può contenere coppie chiave-valore che possono essere utilizzate per la qualifica delle caratteristiche o per fornire dati e metadati per altri rapporti.

## Esempio di richiesta

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Risposta

The response redirects the browser to the [!DNL URL] specified in the `d_rd` parameter. La stringa di risposta può includere valori generati da una delle macro supportate elencate di seguito.

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## Macro supportate

Gli eventi di clic supportano le macro elencate nella tabella seguente. Una macro è una piccola unità di codice indipendente che viene attivata quando l'annuncio viene caricato per la campagna e il tracciamento degli utenti. The macros will be passed along with the destination [!DNL URL], as long as they are marked with the following format: `%macro%`. Alcune chiavi non dispongono di macro e accettano invece un valore ID codificato. Keys that accept hard coded values are required if you want to analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chiave </th> 
   <th colname="col02" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ adgroup %</code> </p> </td> 
   <td colname="col2"> <p>ID gruppo numerico numerico dall'ad server. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col02"> <p>Nessuna macro. </p> <p>Accetta un valore ID codificato rigido. </p> </td> 
   <td colname="col2"> <p> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> ID di origine</a> dati o codice di integrazione per l'inserzionista. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ bu %</code> </p> </td> 
   <td colname="col2"> <p>ID numerico per l'unità aziendale. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ campaign %</code> </p> </td> 
   <td colname="col2"> <p>ID campagna numerico dall'ad server. </p> <p> Required for <span class="wintitle"> Audience Optimization</span> reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ creative %</code> </p> </td> 
   <td colname="col2"> <p>ID creativi numerico dall'ad server. </p> <p>Obbligatorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ id %</code> </p> </td> 
   <td colname="col2"> <p>ID del fornitore di dati. </p> <p>Often used with <code> d_dpuuid</code> to link a data provider ID to a user ID. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ dpuuid %</code> </p> </td> 
   <td colname="col2"> <p>ID utente univoco fornito dal provider di dati. </p> <p>Often used with <code> d_dpid</code> to link a user ID to a data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ placement</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ placement %</code> </p> </td> 
   <td colname="col2"> <p>ID posizionamento numerico dall'ad server. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ region</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ region %</code> </p> </td> 
   <td colname="col2"> <p>L'ID di regione numerica per il cluster DCS che i servizi richiedono. For more information about the DCS, see <a href="../../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_ rand</code> </p> </td> 
   <td colname="col02"> <p> <code> % r_ rand %</code> </p> </td> 
   <td colname="col2"> <p>Numero casuale utilizzato per svuotare la cache. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ site</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ site %</code> </p> </td> 
   <td colname="col2"> <p>ID del sito numerico dall'ad server. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ src %</code> </p> </td> 
   <td colname="col2"> <p>DPID dell'origine da cui Audience Manager estrae i metadati. </p> <p>Obbligatorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> % d_ uuid %</code> </p> </td> 
   <td colname="col2"> <p>Specificate l'ID del visitatore direttamente nell'URL invece di fare affidamento sul cookie Demdex. </p> <p>Facoltativo. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>% gdpr_ apply %</code> </p> </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/aam-gdpr/aam-iab-plugin.md">plug-in Audience Manager per IAB TCF.</a> </p><p><code>gdpr</code> can be 0 (GDPR does not apply) or 1 (GDPR apply).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_ permission</code> </p> </td> 
   <td colname="col02"> <p> <code>% gdpr_ permission %</code> </p> </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/aam-gdpr/aam-iab-plugin.md">plug-in Audience Manager per IAB TCF.</a></p><p> Se <code>gdpr=1</code>, <code>%gdpr_permission%</code> viene sostituito dalla stringa <code>gdpr_permission</code> (consulta la <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">Specifica IAB</a>).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p></td> 
  </tr> 
 </tbody> 
</table>

## Esempio macro

Questo esempio illustra come passare le macro creative, di gruppo e di posizionamento. Presuppone che i valori di ciascun parametro vengano passati nella parte non-reindirizzata della chiamata di clic di clic.

<ul class="simplelist"> 
 <li> <code> creative = 1235 </code> </li> 
 <li> <code> campaign = 4709 </code> </li> 
 <li> <code> adgroup = 3408 </code> </li> 
 <li> <code> placement = 1001 </code> </li> 
 <li> <code> src = 203 </code> </li> 
</ul>

## Richiesta

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## Risposta

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_ LIKE_ THIS]
>
>* [Dati e file di metadati per report di ottimizzazione pubblico](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

