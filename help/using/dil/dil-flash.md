---
description: Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in Audience Manager.
seo-description: Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] è una libreria di [!DNL ActionScript] codici che consente di utilizzare i dati di riproduzione video in Audience Manager. [!DNL Flash DIL] funziona acquisendo il contenuto SWF che la libreria Adobe [!UICONTROL AppMeasurement] trasmette ad Analytics. [!DNL Flash DIL] invia tali dati al modulo di raccolta dati [!UICONTROL DIL] JavaScript separato, che trasmette tali informazioni ad Audience Manager. Dati di analisi ( [!UICONTROL Props], [!UICONTROL eVars]eventi, ecc.) acquisito dal [!DNL FLA] file è disponibile in Audience Manager come caratteristiche o segnali inutilizzati.

## Requisiti per la raccolta dati Flash DIL {#requirements}

Implementazione generale e requisiti relativi al codice.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisiti di implementazione**

[!UICONTROL Flash] la raccolta dei dati richiede:

* La libreria [!UICONTROL DIL] di classi ( `dil.swc`). Ottenete la libreria delle [!UICONTROL DIL] classi dal contatto Soluzioni partner.

* Codice di raccolta dati JavaScript [!UICONTROL DIL] sulla pagina.
* [Libreria](../dil/dil-flash.md#flash-dil-actionscript) DIL ActionScript caricata nell'oggetto Flash da cui si desidera raccogliere i dati.
* La [!DNL AppMeasurement] libreria Adobe (versione 3.5.2 o successiva) ha caricato l' [!DNL AS] [!DNL Flash] oggetto da cui si desidera raccogliere i dati.

**Imposta AllowScriptAccess su`Always`o`sameDomain`**

Il codice HTML `AllowScriptAccess` in cui viene caricato un file SWF controlla la capacità di eseguire l'accesso URL in uscita dall'interno del file SWF. Quando configurate un'integrazione dei [!UICONTROL Flash DIL] dati, accertatevi che il `AllowScriptAccess` parametro Flash sia impostato su `always` o `sameDomain`. [!UICONTROL Flash DIL] la raccolta dei dati non funzionerà se `AllowScriptAccess` è impostata su `never`. Vedere [Controllo dell'accesso agli script o alla pagina](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)Web dell'host.

**Posizionamento[!UICONTROL DIL]del codice JS**

Provare a inserire il modulo di raccolta [!UICONTROL DIL] dati JS nella pagina in modo che venga caricato prima del [!DNL FLA] file. Quando il [!DNL FLA] file viene caricato per primo, prima che la raccolta [!UICONTROL DIL] dei dati sia pronta, è possibile che non vengano visualizzati i segnali di dati iniziali [!UICONTROL Flash DIL] inviati al modulo. Tuttavia, una volta creata l'istanza, il modulo di raccolta dei [!UICONTROL DIL] dati acquisirà tutti i dati del file SWF passati successivamente da [!UICONTROL Flash DIL].

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
* `mediaAdParentName` (Nome del contenuto multimediale principale in cui è nidificato l'annuncio)
* `mediaAdParentPod` (Il contenitore o l'interruzione dell'annuncio all'interno del contenuto principale in cui viene riprodotto l'annuncio)
* `mediaAdParentPodPos` (La posizione numerica all'interno del contenitore in cui viene riprodotto l'annuncio. Più annunci possono essere riprodotti all'interno di un contenitore.

>[!MORE_LIKE_this]
>
>* [Guida all'implementazione di AppMeasurement Flash, Flex e OSMF](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Dati DIL Flash in Audience Manager {#flash-dil-data}

Il [!UICONTROL Flash DIL] modulo trasforma i dati Adobe AppMeasurement in caratteristiche e segnali non utilizzati di Audience Manager.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]ed eventi funzionano come caratteristiche in Audience Manager. Le caratteristiche sono coppie chiave-valore e vengono utilizzate per creare segmenti. Ad esempio, in un prop di Analytics come `c30=foo`, `c30` è la chiave (una costante) ed `foo` è il valore (una variabile).

**Corrispondenza delle caratteristiche di Audience Manager con le variabili Analytics**

Per utilizzare i dati di Analytics passati da [!UICONTROL Flash DIL], devi creare caratteristiche di Audience Manager con il valore chiave preceduto da `c_`.

Vedere la tabella per gli esempi:

| Elemento dati di Analytics | Esempio di Analytics | Come caratteristica di Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dati DIL/Analytics come segnali non utilizzati**

Audience Manager accetta analisi [!UICONTROL Props], [!UICONTROL eVars]e eventi anche senza una caratteristica corrispondente. In questo caso, i dati non sono disponibili per la creazione delle caratteristiche e vengono visualizzati nel rapporto [Segnali](../reporting/dynamic-reports/unused-signals.md) non utilizzati. Per trarre il massimo da queste informazioni, crea caratteristiche di Audience Manager che corrispondono ai dati di Analytics passati dalla [!UICONTROL Flash DIL] libreria.

>[!MORE_LIKE_this]
>
>* [Caratteristiche](../features/traits/trait-details-page.md)
>* [Segnali, caratteristiche e segmenti](../reference/signal-trait-segment.md)
>* [Spiegazione delle coppie chiave-valore](../reference/key-value-pairs-explained.md)
>* [Requisiti del prefisso per le variabili chiave](../features/traits/trait-variable-prefixes.md)


## Libreria ActionScript DIL Flash {#flash-dil-actionscript}

Codice per l’ [!DNL Flash] oggetto da inviare ai manager di Audience Manager i dati di Analytics.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Per ogni [!DNL Flash] oggetto, il codice supporta solo un'istanza partner ( `d.partner`).
   >
   >
* Richiede la versione della [!UICONTROL AppMeasurement] libreria Adobe [!DNL AS] 3.5.2 o successiva.
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

