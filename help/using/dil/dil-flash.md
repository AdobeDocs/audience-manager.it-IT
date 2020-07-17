---
description: Raccogliere i dati inviati dai file FLA a  Analytics e lavorare con tali informazioni in  Audience Manager.
seo-description: Raccogliere i dati inviati dai file FLA a  Analytics e lavorare con tali informazioni in  Audience Manager.
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

Raccogliere i dati inviati dai file FLA a  Analytics e lavorare con tali informazioni in  Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] è una libreria di [!DNL ActionScript] codici che consente di utilizzare i dati di riproduzione video in  Audience Manager. [!DNL Flash DIL] funziona acquisendo il contenuto SWF che la libreria Adobe [!UICONTROL AppMeasurement] trasmette a  Analytics. [!DNL Flash DIL] invia tali dati al modulo di raccolta dati [!UICONTROL DIL] JavaScript separato, che trasmette tali informazioni ad  Audience Manager.  dati Analytics ( [!UICONTROL Props], [!UICONTROL eVars]eventi, ecc.) acquisito dal [!DNL FLA] file è disponibile in  Audience Manager come caratteristiche o segnali inutilizzati.

## Requisiti per la raccolta dati Flash DIL {#requirements}

Implementazione generale e requisiti relativi al codice.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisiti di implementazione**

[!UICONTROL Flash] la raccolta dei dati richiede:

* La libreria [!UICONTROL DIL] di classi ( `dil.swc`). Ottenete la libreria delle [!UICONTROL DIL] classi dal contatto Soluzioni partner.

* Codice di raccolta dati JavaScript [!UICONTROL DIL] sulla pagina.
* [Libreria](../dil/dil-flash.md#flash-dil-actionscript) DIL ActionScript caricata nell&#39;oggetto Flash da cui si desidera raccogliere i dati.
* La [!DNL AppMeasurement] libreria Adobe (versione 3.5.2 o successiva) ha caricato l&#39; [!DNL AS] [!DNL Flash] oggetto da cui si desidera raccogliere i dati.

**Impostate AllowScriptAccess su`Always`o`sameDomain`**

Il codice HTML `AllowScriptAccess` in cui viene caricato un file SWF controlla la capacità di eseguire l&#39;accesso URL in uscita dall&#39;interno del file SWF. Quando configurate un&#39;integrazione dei [!UICONTROL Flash DIL] dati, accertatevi che il `AllowScriptAccess` parametro Flash sia impostato su `always` o `sameDomain`. [!UICONTROL Flash DIL] la raccolta dei dati non funzionerà se `AllowScriptAccess` è impostata su `never`. Vedere [Controllo dell&#39;accesso agli script o alla pagina](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)Web dell&#39;host.

**Posizionamento[!UICONTROL DIL]del codice JS**

Provare a inserire il modulo di raccolta [!UICONTROL DIL] dati JS nella pagina in modo che venga caricato prima del [!DNL FLA] file. Quando il [!DNL FLA] file viene caricato per primo, prima che la raccolta [!UICONTROL DIL] dei dati sia pronta, è possibile che non vengano visualizzati i segnali di dati iniziali [!UICONTROL Flash DIL] inviati al modulo. Tuttavia, una volta creata l&#39;istanza, il modulo di raccolta dei [!UICONTROL DIL] dati acquisirà tutti i dati del file SWF passati successivamente da [!UICONTROL Flash DIL].

## Dati raccolti da Flash DIL {#data-collected}

[!UICONTROL Flash DIL] acquisisce dalla [!UICONTROL AppMeasurement] libreria Adobe la visualizzazione di pagina, il tracciamento dei collegamenti, il tracciamento dei supporti e altri eventi di visualizzazione dei contenuti multimediali.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventi di visualizzazione delle pagine**

Se non diversamente specificato da `s.trackVars`, [!UICONTROL Flash DIL] raccoglie i seguenti dati da Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Tracciamento collegamenti**

Se non diversamente specificato da `s.linkTrackVars`, [!UICONTROL Flash DIL] raccoglie da Adobe i dati seguenti [!UICONTROL AppMeasurement]:

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

## Dati DIL Flash in  Audience Manager {#flash-dil-data}

Il [!UICONTROL Flash DIL] modulo trasforma i dati Adobe AppMeasurement in  caratteristiche Audience Manager e segnali inutilizzati.

<!-- 

c_flash_dil_in_aam.xml

 -->

 Analytics [!UICONTROL Props], [!UICONTROL eVars]e gli eventi funzionano come caratteristiche in  Audience Manager. Le caratteristiche sono coppie chiave-valore e vengono utilizzate per creare segmenti. Ad esempio, in un prop Analytics  come `c30=foo`, `c30` è la chiave (una costante) ed `foo` è il valore (una variabile).

**Corrispondenza  caratteristiche Audience Manager con  variabili Analytics**

Per utilizzare i dati Analytics  passati da [!UICONTROL Flash DIL], è necessario creare  caratteristiche Audience Manager con il valore chiave preceduto da `c_`.

Vedere la tabella per gli esempi:

|  elemento dati Analytics |  Analytics | Come  caratteristica Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/ dati Analytics come segnali non utilizzati**

 Audience Manager accetta  Analytics [!UICONTROL Props], [!UICONTROL eVars]e gli eventi anche senza una caratteristica corrispondente. In questo caso, i dati non sono disponibili per la creazione delle caratteristiche e vengono visualizzati nel rapporto [Segnali](../reporting/dynamic-reports/unused-signals.md) non utilizzati. Per sfruttare al massimo queste informazioni, create  caratteristiche Audience Manager che corrispondano ai dati Analytics  passati dalla [!UICONTROL Flash DIL] libreria.

## Libreria ActionScript DIL Flash {#flash-dil-actionscript}

Codice per l&#39; [!DNL Flash] oggetto da inviare  dati Analytics a  Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Per ciascun [!DNL Flash] oggetto, il codice supporta solo un&#39;istanza partner ( `d.partner`).
   >
   >
* Richiede la versione della [!UICONTROL AppMeasurement] libreria Adobe [!DNL AS] 3.5.2 o successiva.


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

