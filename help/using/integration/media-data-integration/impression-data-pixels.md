---
description: Un approccio per l'invio di dati multimediali ad Audience Manager utilizza le macro del server di annunci per inviare gli attributi della campagna ad Audience Manager.
seo-description: Un approccio per l'invio di dati multimediali ad Audience Manager utilizza le macro del server di annunci per inviare gli attributi della campagna ad Audience Manager.
seo-title: Acquisizione dei dati di impressione della campagna attraverso Pixel Calls (Chiamate pixel)
solution: Audience Manager
title: Acquisizione dei dati di impressione della campagna attraverso Pixel Calls (Chiamate pixel)
uuid: 6 ac 44100-4 c 55-4992-8835-0 d 578 bb 4 e 5 c 2
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Acquisizione dei dati di impressione della campagna attraverso Pixel Calls (Chiamate pixel){#capturing-campaign-impression-data-via-pixel-calls}

Un approccio per l&#39;invio di dati multimediali ad Audience Manager utilizza le macro del server di annunci per inviare gli attributi della campagna ad Audience Manager.

Questa metodologia viene spesso definita «pixelizzazione delle credenziali». Tali punti dati vengono inseriti in modo dinamico nel codice [!DNL Audience Manager] pixel dalle macro del server di terze parti, che vengono utilizzate per mappare e segnalare tutte le impression e i clic in base agli attributi di reporting chiave della campagna. I dati aggregati forniscono una visualizzazione unificata delle prestazioni delle campagne, facilitano l&#39;identificazione dei percorsi di conversione personalizzati e aiutano i clienti a migliorare la sequenza di eventi di annunci pubblicitari che portano a conversioni.

## Sintassi eventi evento

>[!NOTE]
>
>Gli stili di testo (`monospaced text`, *corsivo*, parentesi quadre `[ ]` `( )`, ecc.) indicano gli elementi del codice e le opzioni. Per ulteriori informazioni, consulta [Convenzioni di stile per Codice e Elementi di testo](../../reference/code-style-elements.md).

La chiamata dell&#39;evento raccoglie i dati sulle impression e di conversione e li invia ai [!DNL Audience Manager] [server di raccolta dati](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS]). Questo processo si basa su server di annunci di terze parti che mettono in pratica la chiamata per controllare quale contenuto viene inserito nel codice. I server di annunci di terze parti (ad esempio, [!DNL DFA]) possono inserire questo codice all&#39;interno di ogni ad impression. Inoltre, una ad call non utilizza [!DNL JavaScript] o impiega tecniche di suddivisione dei fotogrammi per accedere ai dati del publisher all&#39;esterno dell&#39;ad tag.

Le chiamate evento sono coppie chiave-valore che utilizzano la sintassi seguente:

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;
d_ creative =<i>creative_ id</i>&amp; d_ adgroup =<i>adgroup_ id</i>&amp; d_ placement =<i>placement_ id</i>
&amp; d_ campaign =<i>campaign_ id</i>[&amp; d_ cid = (GAID | IDFA) % 01 DPUUID] &amp; d_ bust = cache buster
</pre>

Nella coppia chiave-valore, la variabile value è un ID o una macro inserita dall&#39;annuncio. Quando l&#39;annuncio viene caricato, viene `%macro%` sostituito con i valori corrispondenti e corrispondenti. Questa chiamata non restituisce una risposta.

## Coppie chiave-valore supportate {#supported-key-value-pairs}

Le chiamate dell&#39;evento Impression accettano i dati formati in coppie chiave-valore. Nella tabella seguente sono elencate e descritte le chiavi utilizzate per contenere queste variabili. Molte di queste sono necessarie per acquisire e analizzare i dati nei report di ottimizzazione [pubblico](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Chiave </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_ adgroup </code> </td> 
   <td colname="col2"> <p>ID gruppo numerico numerico dall'ad server. </p> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ adsrc </code> </td> 
   <td colname="col2"> <p>ID di origine dati o codice di integrazione per l'inserzionista. </p> <p>Richiesto per <span class="wintitle"> i report di ottimizzazione </span> pubblico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ bu </code> </td> 
   <td colname="col2"> <p>ID di origine dati o codice integrazione per l'unità aziendale. </p> <p>Richiesto per <span class="wintitle"> i report di ottimizzazione </span> pubblico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bust </code> </p> </td> 
   <td colname="col2"> <p>Valore sfocato nella cache. <span class="keyword"> Audience Manager invia </span> automaticamente intestazioni di controllo della cache che vengono rispettate dalla maggior parte dei browser e dei proxy. Se desiderate eseguire ulteriore svuotamento della cache, includete questo parametro in una chiamata evento, seguita da una stringa casuale. </p> <p> Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ campaign </code> </td> 
   <td colname="col2"> <p>ID campagna numerico dall'ad server. </p> <p>Richiesto per <span class="wintitle"> i report di ottimizzazione </span> pubblico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In questo contesto <code> , d_ cid </code> crea un'istanza di una coppia chiave-valore che consente di associare un tipo di dispositivo mobile a un ID utente univoco (DPUUID). Un ID fisso determina il tipo di dispositivo mobile. Il valore, che è l'ID utente, può variare. Separare la coppia chiave-valore con <code> % 01 </code>, che è un carattere di controllo non stampabile. Questo parametro accetta le chiavi seguenti: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identifica un dispositivo Android (GAID). Ad esempio, <code> d_ cid = 20914% 01 1234 </code> indica che l'utente 1234 è associato a un dispositivo Android. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identifica un dispositivo iOS (IDFA). Ad esempio, <code> d_ cid = 20915% 01 5678 </code> indica che l'utente 5678 è associato a un dispositivo iOS. </li> 
    </ul> <p>Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ creative </code> </td> 
   <td colname="col2"> <p>ID creativi numerico dall'ad server. </p> <p>Richiesto per <span class="wintitle"> i report di ottimizzazione </span> pubblico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ event = imp </code> </td> 
   <td colname="col2"> <p>Identifica una chiamata evento come evento di impression. </p> <p>Obbligatorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ placement </code> </td> 
   <td colname="col2"> <p>ID posizionamento numerico dall'ad server. </p> <p> Facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ site </code> </td> 
   <td colname="col2"> <p>ID del sito numerico dall'ad server. </p> <p>Richiesto per <span class="wintitle"> i report di ottimizzazione </span> pubblico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ src </code> </td> 
   <td colname="col2"> <p>ID di origine dati o codice di integrazione della piattaforma che fornisce i metadati (ad es. DFA, Atlas, GBM, Media Math, ecc.). </p> <p>Richiesto per <span class="wintitle"> i report di ottimizzazione </span> pubblico. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/aam-gdpr/aam-iab-plugin.md">plug-in Audience Manager  per IAB TCF.</a></p> <p><code>gdpr</code> can be 0 (GDPR does not apply) or 1 (GDPR apply).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_ permission</code> </td> 
   <td colname="col2"> <p>Correlato al <a href="../../overview/aam-gdpr/aam-iab-plugin.md">plug-in Audience Manager  per IAB TCF.</a></p><p> Se <code>gdpr=1</code>, <code>%gdpr_permission%</code> viene sostituito dalla stringa <code>gdpr_permission</code> (consulta la <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">Specifica IAB</a>).</p> <p>Il valore predefinito è 0.</p><p>Facoltativo.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Contattate la vostra consulenza o il vostro account Adobe Audience Manager per l&#39;URL esatto specifico del dominio client.

>[!MORE_ LIKE_ THIS]
>
>* [Dati e file di metadati per report di ottimizzazione pubblico](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

