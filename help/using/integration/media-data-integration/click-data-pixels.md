---
description: nulle
seo-description: nulle
seo-title: Acquisizione dei dati di clic sulla campagna tramite chiamate pixel
solution: Audience Manager
title: Acquisizione dei dati di clic sulla campagna tramite chiamate pixel
uuid: 7c3797f7-9674-493d-972b-38be0584feed
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

Il monitoraggio dei clic consente di misurare il livello di coinvolgimento dei visitatori durante l’intera campagna, registrando l’attività basata sui clic per i creativi di terze parti. Analogamente all'insieme impression, una chiamata evento viene inviata ai server di raccolta dati ([!UICONTROL DCS]) di Audience Manager per l'elaborazione. Il visitatore viene quindi reindirizzato all'indirizzo Web desiderato.

## Requisiti

Le chiamate di tracciamento dei clic richiedono i seguenti parametri:

* `d_event=click`: Coppia chiave-valore che identifica una chiamata evento come evento click.
* `d_rd=redirect URL`: Coppia chiave-valore contenente un reindirizzamento codificato [!DNL URL].

Inoltre, la chiamata può contenere coppie chiave-valore che possono essere utilizzate per la qualifica delle caratteristiche o per fornire dati e metadati per altri rapporti.

## Esempio di richiesta

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Risposta

La risposta reindirizzerà il browser a [!DNL URL] quello specificato nel `d_rd` parametro. La stringa di risposta può includere valori generati da una delle macro supportate elencate di seguito.

In base all'esempio precedente, il browser viene reindirizzato a quanto segue [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## Macro supportate

Gli eventi Click supportano le macro elencate nella tabella seguente. Una macro è una piccola unità di codice standalone che si attiva quando il tag dell'annuncio viene caricato per la campagna e il tracciamento dell'utente. Le macro verranno trasmesse insieme alla destinazione [!DNL URL]purché siano contrassegnate con il seguente formato: `%macro%`. Alcune chiavi non dispongono di macro e accettano un valore ID hardcoded. Le chiavi che accettano valori hardcoded sono necessarie se desiderate analizzare i dati nei report [di ottimizzazione dell'](../../reporting/audience-optimization-reports/audience-optimization-reports.md)audience.

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
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>ID gruppo di annunci numerici dal server di annunci. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Nessuna macro. </p> <p>Accetta un valore ID hardcoded. </p> </td> 
   <td colname="col2"> <p>ID inserzionista.</p> <p>Un codice di integrazione per l'origine dati dell'inserzionista. Questo non è correlato alle origini dati di Audience Manager.</p> <p> Obbligatorio per i report <span class="wintitle"> Audience Optimization</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numerico per l'unità aziendale. </p> <p> Obbligatorio per i report <span class="wintitle"> Audience Optimization</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>ID campagna numerica dal server annunci. </p> <p> Obbligatorio per i report <span class="wintitle"> Audience Optimization</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>ID creativo numerico dal server annunci. </p> <p>Obbligatorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>ID provider dati. </p> <p>Spesso utilizzato con <code> d_dpuuid</code> per collegare un ID provider di dati a un ID utente. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>ID utente univoco fornito dal provider di dati. </p> <p>Spesso utilizzato con <code> d_dpid</code> per collegare un ID utente a un ID fornitore di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span> For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>ID posizionamento numerico dal server annunci. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>L'ID di regione numerica per il cluster DCS che fornisce servizi a una richiesta. Per ulteriori informazioni sul DCS, vedi <a href="../../reference/system-components/components-data-collection.md"> Componenti</a>per la raccolta dati. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Numero casuale utilizzato per l'arresto della cache. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>ID sito numerico dal server annunci. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID dell’origine da cui Audience Manager estrae i metadati. </p> <p>Obbligatorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Specificate l'ID del visitatore direttamente nell'URL invece di affidarsi al cookie Demdex. </p> <p>Facoltativo. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_applies%</code> </p> </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/aam-gdpr/aam-iab-plugin.md">plug-in Audience Manager per IAB TCF.</a> </p><p><code>gdpr</code> può essere 0 (non si applica il GDPR) o 1 (si applica il GDPR).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_consent%</code> </p> </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/aam-gdpr/aam-iab-plugin.md">plug-in Audience Manager per IAB TCF.</a></p><p> Se <code>gdpr=1</code>, allora <code>%gdpr_consent%</code> viene sostituito dalla stringa <code>gdpr_consent</code> (vedi le <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> specifiche IAB</a>).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p></td> 
  </tr> 
 </tbody> 
</table>

## Esempio di macro

Questo esempio illustra come passare le macro creative, adgroup e placement. Presuppone che i valori di ciascun parametro vengano passati nella parte non di reindirizzamento della chiamata di tracciamento dei clic.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## Richiesta

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## Risposta

In base all'esempio precedente, il browser viene reindirizzato a quanto segue [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORELIKETHIS]
>
>* [File di dati e metadati per report di ottimizzazione dell'audience](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

