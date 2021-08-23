---
description: Il tracciamento dei clic consente di misurare il coinvolgimento dei visitatori durante l’intera campagna, in quanto registra l’attività basata sui clic per i creativi di terze parti.
seo-description: Il tracciamento dei clic consente di misurare il coinvolgimento dei visitatori durante l’intera campagna, in quanto registra l’attività basata sui clic per i creativi di terze parti.
seo-title: Acquisizione dei dati di clic delle campagne attraverso chiamate pixel
solution: Audience Manager
title: Acquisizione dei dati di clic delle campagne attraverso chiamate pixel
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Integrazione Adobe Campaign
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 11%

---

# Acquisizione dei dati di clic delle campagne attraverso chiamate pixel {#capturing-campaign-click-data-via-pixel-calls}

Il tracciamento dei clic consente di misurare il coinvolgimento dei visitatori durante l’intera campagna, in quanto registra l’attività basata sui clic per i creativi di terze parti. Analogamente all&#39; [insieme impression](/help/using/integration/media-data-integration/impression-data-pixels.md), una chiamata evento viene inviata ai server di raccolta dati [!DNL Audience Manager] ([!DNL DCS]) per l&#39;elaborazione. Il visitatore viene quindi reindirizzato all&#39;indirizzo Web desiderato.

>[!NOTE]
>
>Contatta il tuo [!DNL Audience Manager] consulente o lead dell&#39;account per sapere esattamente [!DNL URL] specifico per il dominio client.

## Requisiti

Le chiamate di tracciamento dei clic richiedono i seguenti parametri:

* `d_event=click`: Una coppia chiave-valore che identifica una chiamata evento come evento click.
* `d_rd=redirect URL`: Una coppia chiave-valore che contiene un reindirizzamento a doppia codifica  [!DNL URL]. Se utilizzi uno strumento di codifica online, esegui la stringa attraverso il codificatore, quindi codifica di nuovo il risultato, in modo che il reindirizzamento funzioni.

Inoltre, la chiamata può contenere coppie chiave-valore che possono essere utilizzate per la qualifica delle caratteristiche o per fornire dati e metadati per altri rapporti.

## Esempio di richiesta

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Risposta

La risposta reindirizza il browser al [!DNL URL] specificato nel parametro `d_rd` . La stringa di risposta può includere valori generati da una delle macro supportate elencate di seguito.

In base all&#39;esempio precedente, il browser viene reindirizzato al seguente [!DNL URL]:

`https://adobe.com/callback?creative=123`

## Macro supportate

Gli eventi clic supportano le macro elencate nella tabella seguente. Una macro è una piccola unità di codice indipendente che si attiva quando il tag dell&#39;annuncio viene caricato per la campagna e il tracciamento degli utenti. Le macro verranno trasmesse insieme alla destinazione [!DNL URL], purché siano contrassegnate con il seguente formato: `%macro%`. Alcune chiavi non dispongono di macro e accettano un valore ID hardcoded. Le chiavi che accettano valori hardcoded sono necessarie se si desidera analizzare i dati nei [Rapporti di Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

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
   <td colname="col2"> <p>ID inserzionista.</p> <p>Un codice di integrazione per l’origine dati dell’inserzionista. Tieni presente che questo non è correlato alle origini dati di Audience Manager.</p> <p> Obbligatorio per i rapporti <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>ID numerico per la business unit. </p> <p> Obbligatorio per i rapporti <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>ID campagna numerica dal server annunci. </p> <p> Obbligatorio per i rapporti <span class="wintitle"> Audience Optimization</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>ID creativo numerico dal server di annunci. </p> <p>Obbligatorio. </p> </td> 
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
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). Per ulteriori informazioni sull'ECID, consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie e l'ID Experience Cloud</a>. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>ID di posizionamento numerico dal server di annunci. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>ID di regione numerica per il cluster DCS che esegue una richiesta. Per ulteriori informazioni sul DCS, consulta <a href="../../reference/system-components/components-data-collection.md"> Componenti di raccolta dati</a>. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Numero casuale utilizzato per lo svuotamento della cache. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>ID di sito numerico dal server di annunci. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID della sorgente da cui Audience Manager richiama i metadati. </p> <p>Obbligatorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Specifica l'ID del visitatore direttamente nell'URL invece di fare affidamento sul cookie demdex. </p> <p>Facoltativo. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in Audience Manager per IAB TCF.</a> </p><p><code>gdpr</code> può essere 0 (non si applica il RGPD) o 1 (si applica il RGPD).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in Audience Manager per IAB TCF.</a></p><p> Se <code>gdpr=1</code>, <code>${gdpr_consent_XXXX}</code> viene sostituito dalla stringa <code>gdpr_consent</code> e dall'ID fornitore (consulta <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> la specifica IAB</a>).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p></td> 
  </tr> 
 </tbody> 
</table>

## Esempio di macro

Questo esempio illustra come passare le macro creative, di adgroup e di posizionamento. Presuppone che i valori di ciascun parametro vengano passati nella parte non di reindirizzamento della chiamata di tracciamento dei clic.

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
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## Risposta

In base all&#39;esempio precedente, il browser viene reindirizzato al seguente [!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Funzionalità aggiuntive - [!UICONTROL Audience Optimization Reports]

È possibile utilizzare le chiamate pixel per alimentare i [report di Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Per abilitare i rapporti, consulta [Panoramica e mappature per i file di metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) .


>[!MORELIKETHIS]
>
>* [File di dati e metadati per rapporti di Audience Optimization](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

