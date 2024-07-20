---
description: Un approccio per l’invio di dati multimediali ad Audience Manager utilizza macro di ad server per inviare attributi di campagna ad Audience Manager.
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: Acquisizione dei dati di impression delle campagne attraverso chiamate pixel
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 16%

---

# Acquisizione dei dati di impression delle campagne attraverso chiamate pixel{#capturing-campaign-impression-data-via-pixel-calls}

Un approccio per l’invio di dati multimediali ad Audience Manager utilizza macro di ad server per inviare attributi di campagna ad Audience Manager.

Questa metodologia viene spesso definita &quot;pixeling the creative&quot;. Tali punti dati vengono inseriti dinamicamente nel codice pixel [!DNL Audience Manager] dalle macro del server di annunci di terze parti, che vengono utilizzate per mappare e segnalare tutte le impression e i clic in base agli attributi di reporting chiave della campagna. I dati aggregati forniscono una visualizzazione unificata delle prestazioni della campagna, consentono di identificare percorsi di conversione personalizzati e aiutano i clienti a migliorare la sequenza di eventi del server di annunci che portano alle conversioni.

## Sintassi delle chiamate evento

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi `[ ]` `( )`, ecc.) indicano gli elementi del codice e le opzioni. Per ulteriori informazioni, consulta le [convenzioni di stile per codice ed elementi di testo](../../reference/code-style-elements.md).

La chiamata evento raccoglie i dati sulle impression e di conversione e li invia ai [!DNL Audience Manager] [server di raccolta dati](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Questo processo si basa su server di annunci di terze parti che inseriscono la chiamata nella grafica per controllare quale contenuto viene inserito nel codice. I server di annunci di terze parti (ad esempio, [!DNL DFA]) possono inserire questo codice all&#39;interno di ogni impression pubblicitaria. Inoltre, una ad call non utilizza [!DNL JavaScript] o impiega tecniche di suddivisione dei fotogrammi per accedere ai dati del publisher all&#39;esterno dell&#39;ad tag.

Le chiamate evento sono costituite da coppie chiave-valore con la seguente sintassi:

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

Nella coppia chiave-valore, la variabile valore è un ID o una macro inserita dal server dell’annuncio. Al caricamento del tag dell&#39;annuncio, `%macro%` viene sostituito con i valori richiesti corrispondenti. Questa chiamata non restituisce una risposta.

## Coppie chiave-valore supportate {#supported-key-value-pairs}

Le chiamate dell’evento di impression accettano dati formati in coppie chiave-valore. Nella tabella seguente sono elencate e descritte le chiavi utilizzate per contenere queste variabili. Molti di questi sono necessari se desideri acquisire e analizzare i dati in [Report di Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chiave </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>ID numerico del gruppo di annunci dal server di annunci. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>ID sorgente dei dati o codice di integrazione per l’inserzionista. </p> <p>Obbligatorio per <span class="wintitle"> Audience Optimization </span> report. </p> <p>Facoltativo.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>ID sorgente dei dati o codice di integrazione per la tua business unit. </p> <p>Obbligatorio per <span class="wintitle"> Audience Optimization </span> report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Valore di cache non elaborata. <span class="keyword"> L'Audience Manager </span> invia automaticamente le intestazioni di controllo cache rispettate dalla maggior parte dei browser e dei proxy. Se desideri eseguire un busting aggiuntivo della cache, includi questo parametro in una chiamata evento, seguito da una stringa casuale. </p> <p> Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>ID numerico della campagna dal server di annunci. </p> <p>Obbligatorio per <span class="wintitle"> Audience Optimization </span> report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In questo contesto, <code> d_cid </code> crea un'istanza di una coppia chiave-valore che consente di associare un tipo di dispositivo mobile a un ID utente univoco (DPUUID). Un ID fisso determina il tipo di dispositivo mobile. Il valore, che è l’ID utente, può variare. Separare la coppia chiave-valore con <code> %01 </code>, che è un carattere di controllo non stampabile. Questo parametro accetta le chiavi seguenti: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: identifica un dispositivo Android (GAID). <code> d_cid = 20914 %01 1234 </code>, ad esempio, indica che l'utente 1234 è associato a un dispositivo Android. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: identifica un dispositivo iOS (IDFA). <code> d_cid = 20915 %01 5678 </code>, ad esempio, indica che l'utente 5678 è associato a un dispositivo iOS. </li> 
    </ul> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>ID creativo numerico dall’ad server. </p> <p>Obbligatorio per <span class="wintitle"> Audience Optimization </span> report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifica una chiamata evento come evento di impression. </p> <p>Obbligatorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>ID di posizionamento numerico dall’ad server. </p> <p> Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>ID numerico del sito dall’ad server. </p> <p>Obbligatorio per <span class="wintitle"> Audience Optimization </span> report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>ID sorgente dei dati o codice di integrazione della piattaforma che fornisce i metadati (ad esempio, DFA, Atlas, GBM, Media Math, ecc.). </p> <p>Obbligatorio per <span class="wintitle"> Audience Optimization </span> report. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in Audience Manager per IAB TCF.</a></p> <p><code>gdpr</code> può essere 0 (non si applica il RGPD) o 1 (si applica il RGPD).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p><p>Se <code>gdpr=1</code>, il parametro <code>gdpr_consent</code> deve contenere il parametro di consenso del TC IAB per elaborare correttamente i dati. In caso contrario, tutti i dati verranno eliminati.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">plug-in Audience Manager per IAB TCF.</a></p><p> Se <code>gdpr=1</code>, <code>${gdpr_consent_XXXX}</code> viene sostituito dalla stringa <code>gdpr_consent</code> e dall'ID fornitore (vedere <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> specifica IAB</a>).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Contatta il responsabile dell’account o la consulenza Adobe Audience Manager per l’URL specifico del dominio client.

## Funzionalità aggiuntive - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Puoi usare le chiamate pixel per alimentare [i report Audience Optimization](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Se desideri utilizzare i pixel per alimentare i report, consulta [Panoramica e mappature dei file di metadati](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

>[!MORELIKETHIS]
>
>* [File di dati e metadati per report Audience Optimization](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
