---
description: Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in  Audience Manager.
seo-description: Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in  Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 3%

---


# Flash DIL{#flash-dil}

Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in  Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] è una libreria di  [!DNL ActionScript] codici che consente di utilizzare i dati di riproduzione video in  Audience Manager. [!DNL Flash DIL] funziona acquisendo il contenuto SWF che la  [!UICONTROL AppMeasurement] libreria del Adobe  trasmette ad Analytics. [!DNL Flash DIL] invia tali dati al modulo di raccolta dati  [!UICONTROL DIL] JavaScript separato, che trasmette tali informazioni al Audience Manager . Dati di analisi ( [!UICONTROL Props], [!UICONTROL eVars], eventi, ecc.) acquisito dal file [!DNL FLA] è disponibile  Audience Manager come caratteristiche o segnali inutilizzati.

## Requisiti per la raccolta di dati DIL di Flash {#requirements}

Implementazione generale e requisiti relativi al codice.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisiti di implementazione**

[!UICONTROL Flash] la raccolta dei dati richiede:

* La libreria di classi [!UICONTROL DIL] ( `dil.swc`). Ottenete la libreria di classi [!UICONTROL DIL] dal contatto Soluzioni partner.

* Codice di raccolta dati JavaScript [!UICONTROL DIL] sulla pagina.
* [Libreria DIL  ActionScript ](../dil/dil-flash.md#flash-dil-actionscript) caricata nell&#39;oggetto Flash da cui si desidera raccogliere i dati.
*  libreria [!DNL AppMeasurement] [!DNL AS] dell&#39;Adobe (versione 3.5.2 o successiva) ha caricato l&#39;oggetto [!DNL Flash] da cui si desidera raccogliere i dati.

**Impostate AllowScriptAccess su  `Always` oppure`sameDomain`**

Il codice `AllowScriptAccess` nel codice HTML che carica un file SWF controlla la capacità di eseguire l&#39;accesso URL in uscita dall&#39;interno del file SWF. Quando si configura un&#39;integrazione di dati [!UICONTROL Flash DIL], assicurarsi che il parametro di Flash `AllowScriptAccess` sia impostato su `always` o `sameDomain`. [!UICONTROL Flash DIL] la raccolta dei dati non funzionerà se  `AllowScriptAccess` è impostata su  `never`. Vedere [Controllo dell&#39;accesso agli script o pagina Web host](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Posizionamento  [!UICONTROL DIL] codice JS**

Provare a inserire il modulo di raccolta dati JS [!UICONTROL DIL] nella pagina in modo che venga caricato prima del file [!DNL FLA]. Quando il file [!DNL FLA] viene caricato per primo, prima che la raccolta di dati [!UICONTROL DIL] sia pronta, è possibile che non vengano visualizzati i segnali di dati iniziali inviati da [!UICONTROL Flash DIL] a tale modulo. Tuttavia, una volta creata l&#39;istanza, il modulo di raccolta dei dati [!UICONTROL DIL] acquisirà tutti i dati del file SWF successivi passati da [!UICONTROL Flash DIL].

## Dati raccolti dal DIL Flash {#data-collected}

[!UICONTROL Flash DIL] acquisisce la visualizzazione della pagina, il tracciamento del collegamento, il tracciamento del supporto e altri eventi di visualizzazione multimediale dalla  [!UICONTROL AppMeasurement] libreria Adobe .

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventi di visualizzazione delle pagine**

Se non diversamente specificato da `s.trackVars`, [!UICONTROL Flash DIL] raccoglie i dati seguenti da  Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Tracciamento collegamenti**

Se non diversamente specificato da `s.linkTrackVars`, [!UICONTROL Flash DIL] raccoglie i dati seguenti dal  Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo di collegamento di traccia chiamato)
* `pev1` (URL collegamento)
* `pev2`(Testo collegamento)

**Eventi di tracciamento dei file multimediali**

Se non diversamente specificato da `s.Media.trackVars`, [!UICONTROL Flash DIL] raccoglie tutti i dati enumerati nella sezione Eventi di visualizzazione pagina.

**Altri punti dati**

I dati provenienti da questi parametri vengono raccolti per impostazione predefinita:

* `mediaName` (nome elemento multimediale/video)
* `mediaAdName` (Nome annuncio)
* `mediaAdParentName` (Nome del contenuto multimediale principale in cui è nidificato l&#39;annuncio)
* `mediaAdParentPod` (Il contenitore o l&#39;interruzione dell&#39;annuncio all&#39;interno del contenuto principale in cui viene riprodotto l&#39;annuncio)
* `mediaAdParentPodPos` (La posizione numerica all&#39;interno del contenitore in cui viene riprodotto l&#39;annuncio. Più annunci possono essere riprodotti all&#39;interno di un contenitore.

## Flash DIL Data in  Audience Manager {#flash-dil-data}

Il modulo [!UICONTROL Flash DIL] trasforma  dati Adobe AppMeasurement in caratteristiche  Audience Manager e segnali inutilizzati.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars] e gli eventi funzionano come caratteristiche in  Audience Manager. Le caratteristiche sono coppie chiave-valore e vengono utilizzate per creare segmenti. Ad esempio, in una prop di Analytics come `c30=foo`, `c30` è la chiave (una costante) e `foo` è il valore (una variabile).

**Corrispondenza  caratteristiche Audience Manager alle variabili Analytics**

Per utilizzare i dati di Analytics passati da [!UICONTROL Flash DIL], è necessario creare caratteristiche  Audience Manager con il valore chiave preceduto da `c_`.

Vedere la tabella per gli esempi:

| Elemento dati di Analytics | Esempio di Analytics | Come caratteristica  Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dati DIL/Analytics come segnali non utilizzati**

 Audience Manager accetta gli eventi di Analytics [!UICONTROL Props], [!UICONTROL eVars] e anche senza una caratteristica corrispondente. In questo caso, i dati non sono disponibili per la creazione delle caratteristiche e vengono visualizzati nel [report Segnali inutilizzati](../reporting/dynamic-reports/unused-signals.md). Per sfruttare al massimo queste informazioni, crea caratteristiche  Audience Manager che corrispondono ai dati di Analytics passati dalla libreria [!UICONTROL Flash DIL].

## Libreria di Flash DIL  ActionScript {#flash-dil-actionscript}

Codice per l&#39;oggetto [!DNL Flash] per l&#39;invio di dati Analytics a  Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Per ciascun oggetto [!DNL Flash], il codice supporta solo un&#39;istanza partner ( `d.partner`).
   >
   >
* Richiede l&#39;Adobe  [!UICONTROL AppMeasurement] [!DNL AS] della libreria versione 3.5.2 o successiva.


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [Caratteristiche ](../features/traits/trait-details-page.md)
>* [Segnali, caratteristiche e segmenti](../reference/signal-trait-segment.md)
>* [Spiegazione delle coppie chiave-valore](../reference/key-value-pairs-explained.md)
>* [Requisiti di prefisso delle variabili chiave](../features/traits/trait-variable-prefixes.md)

