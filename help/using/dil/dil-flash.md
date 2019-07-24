---
description: Raccogliere i dati inviati dai file FLA ad Analytics e lavorare con tali informazioni in Audience Manager.
seo-description: Raccogliere i dati inviati dai file FLA ad Analytics e lavorare con tali informazioni in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833 cfd -768 e -4 b 16-95 c 5-debd 8411 df 38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

Raccogliere i dati inviati dai file FLA ad Analytics e lavorare con tali informazioni in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] è una libreria [!DNL ActionScript] di codici che consente di utilizzare i dati di riproduzione video in Audience Manager. [!DNL Flash DIL] funziona acquisendo il contenuto SWF che [!UICONTROL AppMeasurement] la libreria Adobe trasmette ad Analytics. [!DNL Flash DIL] invia tali dati al modulo di [!UICONTROL DIL] raccolta dati javascript separato, che trasmette tali informazioni ad Audience Manager. Analytics data ( [!UICONTROL Props], [!UICONTROL eVars], events, etc.) captured from the [!DNL FLA] file is available in Audience Manager as traits or unused signals.

## Requirements for Flash DIL Data Collection {#requirements}

Requisiti generali per l'implementazione e il codice.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisiti di implementazione**

[!UICONTROL Flash] La raccolta di dati richiede:

* The [!UICONTROL DIL] class library ( `dil.swc`). Obtain the [!UICONTROL DIL] class library from your Partner Solutions contact.

* JavaScript [!UICONTROL DIL] data collection code on the page.
* [La libreria actionscript DIL](../dil/dil-flash.md#flash-dil-actionscript) caricata nell'oggetto Flash da cui si desidera raccogliere i dati.
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2, or later) loaded the [!DNL Flash] object you want to collect data from.

**Impostate allowscriptaccess su`Always`o`sameDomain`**

The `AllowScriptAccess` in HTML code that loads a SWF file controls the ability to perform outbound URL access from within the SWF file. When you configure a [!UICONTROL Flash DIL] data integration, make sure the Flash `AllowScriptAccess` parameter is set to `always` or `sameDomain`. [!UICONTROL Flash DIL] La raccolta dati non funziona se `AllowScriptAccess` è impostata su `never`. See [Control Access to Scripts or Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Posizionamento[!UICONTROL DIL]codice JS**

Try to place the JS [!UICONTROL DIL] data collection module on the page so it loads before the [!DNL FLA] file. When the [!DNL FLA] file loads first, before [!UICONTROL DIL] data collection is ready, you can miss the initial data signals that [!UICONTROL Flash DIL] sends to that module. However, once instantiated, the [!UICONTROL DIL] data collection module will capture all subsequent SWF file data passed in by [!UICONTROL Flash DIL].

## Data Collected by Flash DIL {#data-collected}

[!UICONTROL Flash DIL] acquisisce la visualizzazione di pagina, il tracciamento dei collegamenti, il tracciamento dei supporti e altri eventi di visualizzazione contenuti multimediali dalla [!UICONTROL AppMeasurement] libreria Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventi visualizzazioni pagina**

Unless specified otherwise by `s.trackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventi tracciamento collegamenti**

Unless specified otherwise by `s.linkTrackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo di collegamento di traccia denominato)
* `pev1` (URL collegamento)
* `pev2`(Collegamento testo)

**Eventi di tracciamento multimediale**

Unless specified otherwise by `s.Media.trackVars`, [!UICONTROL Flash DIL] collects all the data enumerated in the Page View Events section.

**Altri punti dati**

I dati di questi parametri vengono raccolti per impostazione predefinita:

* `mediaName` (Nome elemento multimediale/video)
* `mediaAdName` (Nome annuncio)
* `mediaAdParentName` (Nome del contenuto multimediale principale, l'annuncio è nidificato sotto)
* `mediaAdParentPod` (Il contenitore o l'interruzione di annunci all'interno del contenuto principale in cui viene riprodotto l'annuncio)
* `mediaAdParentPodPos` (La posizione numerica all'interno del contenitore in cui viene riprodotto l'annuncio. È possibile riprodurre più di un annuncio all'interno di un contenitore.

>[!MORE_ LIKE_ THIS]
>
>* [Guida all'implementazione di appmeasurement Flash, Flex e OSMF](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL Data in Audience Manager {#flash-dil-data}

[!UICONTROL Flash DIL] Il modulo trasforma i dati Adobe appmeasurement in caratteristiche Audience Manager e segnali inutilizzati.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], and events work like traits in Audience Manager. Le caratteristiche sono coppie chiave-valore e sono utilizzate per creare segmenti. For example, in an Analytics prop like `c30=foo`, `c30` is the key (a constant) and `foo` is the value (a variable).

**Corrispondenza delle caratteristiche di Audience Manager in Analytics**

To use the Analytics data passed by [!UICONTROL Flash DIL], you should create Audience Manager traits that have the key value prefixed with `c_`.

Vedere la tabella per esempi:

| Elemento dati di Analytics | Esempio di Analytics | Come caratteristica Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dati DIL/Analytics come segnali inutilizzati**

Audience Manager accepts Analytics [!UICONTROL Props], [!UICONTROL eVars], and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the [!UICONTROL Flash DIL] library.

>[!MORE_ LIKE_ THIS]
>
>* [Caratteristiche](../features/traits/trait-details-page.md)
>* [Segnali, caratteristiche e segmenti](../reference/signal-trait-segment.md)
>* [Coppie chiave-valore spiegate](../reference/key-value-pairs-explained.md)
>* [Requisiti di prefisso per variabili chiave](../features/traits/trait-variable-prefixes.md)


## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code for your [!DNL Flash] object to send Analytics data to Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* For each [!DNL Flash] object, the code supports one partner instance ( `d.partner`) only.
   >
   >
* Requires the Adobe [!UICONTROL AppMeasurement] [!DNL AS] library version 3.5.2 or higher.
>



```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

