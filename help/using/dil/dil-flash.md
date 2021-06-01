---
description: Raccogliere i dati inviati dai file FLA ad Analytics e lavorare con tali informazioni nell’Audience Manager.
seo-description: Raccogliere i dati inviati dai file FLA ad Analytics e lavorare con tali informazioni nell’Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: Implementazione di DIL
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 3%

---

# Flash DIL{#flash-dil}

Raccogliere i dati inviati dai file FLA ad Analytics e lavorare con tali informazioni nell’Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] è una libreria di  [!DNL ActionScript] codici che consente di lavorare con i dati di riproduzione video in Audience Manager. [!DNL Flash DIL] funziona acquisendo il contenuto SWF che la  [!UICONTROL AppMeasurement] libreria Adobe trasmette ad Analytics. [!DNL Flash DIL] invia tali dati al modulo di raccolta dati  [!UICONTROL DIL] JavaScript separato, che trasmette tali informazioni ad Audience Manager. Dati di Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventi, ecc.) catturato dal file [!DNL FLA] è disponibile in Audience Manager come caratteristiche o segnali non utilizzati.

## Requisiti per la raccolta dati di Flash DIL {#requirements}

Implementazione generale e requisiti relativi al codice.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisiti di implementazione**

[!UICONTROL Flash] la raccolta dati richiede:

* La libreria delle classi [!UICONTROL DIL] ( `dil.swc`). Ottieni la libreria delle classi [!UICONTROL DIL] dal contatto delle soluzioni dei partner.

* Codice di raccolta dati JavaScript [!UICONTROL DIL] nella pagina.
* [Libreria di DIL ActionScript ](../dil/dil-flash.md#flash-dil-actionscript) caricata nell’oggetto Flash da cui si desidera raccogliere i dati.
* La libreria [!DNL AppMeasurement] [!DNL AS] di Adobe (versione 3.5.2 o successiva) ha caricato l&#39;oggetto [!DNL Flash] da cui si desidera raccogliere i dati.

**Imposta AllowScriptAccess su  `Always` o`sameDomain`**

Il `AllowScriptAccess` nel codice HTML che carica un file SWF controlla la capacità di eseguire l&#39;accesso URL in uscita dall&#39;interno del file SWF. Quando configuri un’integrazione di dati [!UICONTROL Flash DIL], assicurati che il parametro Flash `AllowScriptAccess` sia impostato su `always` o `sameDomain`. [!UICONTROL Flash DIL] la raccolta dati non funzionerà se  `AllowScriptAccess` è impostato su  `never`. Consultare [Controllo dell&#39;accesso agli script o alla pagina Web host](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Posizionamento  [!UICONTROL DIL] del codice JS**

Cerca di inserire il modulo di raccolta dati JS [!UICONTROL DIL] nella pagina in modo che venga caricato prima del file [!DNL FLA]. Quando il file [!DNL FLA] viene caricato per primo, prima che la raccolta dati [!UICONTROL DIL] sia pronta, è possibile perdere i segnali di dati iniziali inviati da [!UICONTROL Flash DIL] a tale modulo. Tuttavia, una volta creata l&#39;istanza, il modulo di raccolta dati [!UICONTROL DIL] acquisirà tutti i dati successivi del file SWF trasmessi da [!UICONTROL Flash DIL].

## Dati raccolti da Flash DIL {#data-collected}

[!UICONTROL Flash DIL] acquisisce la visualizzazione della pagina, il tracciamento dei collegamenti, il tracciamento dei contenuti multimediali e altri eventi di visualizzazione multimediali dalla  [!UICONTROL AppMeasurement] libreria Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventi di visualizzazione pagina**

Se non diversamente specificato da `s.trackVars`, [!UICONTROL Flash DIL] raccoglie i seguenti dati da Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventi di tracciamento dei collegamenti**

Se non diversamente specificato da `s.linkTrackVars`, [!UICONTROL Flash DIL] raccoglie i seguenti dati dall&#39;Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo di collegamento di tracciamento chiamato)
* `pev1` (URL collegamento)
* `pev2`(Testo collegamento)

**Eventi di tracciamento dei file multimediali**

Se non diversamente specificato da `s.Media.trackVars`, [!UICONTROL Flash DIL] raccoglie tutti i dati enumerati nella sezione Eventi visualizzazione pagina .

**Altri punti dati**

I dati da questi parametri vengono raccolti per impostazione predefinita:

* `mediaName` (Nome elemento multimediale/video)
* `mediaAdName` (Nome annuncio)
* `mediaAdParentName` (Nome del contenuto multimediale principale in cui si trova l’annuncio)
* `mediaAdParentPod` (Il pod o l’interruzione pubblicitaria all’interno del contenuto principale in cui viene riprodotto l’annuncio)
* `mediaAdParentPodPos` La posizione numerica all’interno del contenitore in cui viene riprodotto l’annuncio. Più annunci possono essere riprodotti all’interno di un pod.

## Dati di Flash DIL nell’Audience Manager {#flash-dil-data}

Il modulo [!UICONTROL Flash DIL] trasforma i dati di Adobe AppMeasurement in caratteristiche di Audience Manager e segnali non utilizzati.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars] e gli eventi funzionano come caratteristiche nell’Audience Manager. Le caratteristiche sono coppie chiave-valore e vengono utilizzate per creare segmenti. Ad esempio, in un prop di Analytics come `c30=foo`, `c30` è la chiave (una costante) e `foo` è il valore (una variabile).

**Abbinare le caratteristiche di Audience Manager alle variabili di Analytics**

Per utilizzare i dati di Analytics passati da [!UICONTROL Flash DIL], devi creare caratteristiche di Audience Manager con il valore chiave con prefisso `c_`.

Vedi la tabella per gli esempi:

| Elemento dati di Analytics | Esempio di Analytics | Come caratteristica Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dati di DIL/Analytics come segnali non utilizzati**

Audience Manager accetta gli eventi di Analytics [!UICONTROL Props], [!UICONTROL eVars] e anche senza una caratteristica corrispondente. In questo caso, i dati non sono disponibili per la creazione delle caratteristiche e vengono visualizzati nel [rapporto Segnali non utilizzati](../reporting/dynamic-reports/unused-signals.md). Per sfruttare al meglio queste informazioni, crea caratteristiche di Audience Manager corrispondenti ai dati di Analytics trasmessi dalla libreria [!UICONTROL Flash DIL].

## Libreria Flash ActionScript {#flash-dil-actionscript}

Codice per l&#39;oggetto [!DNL Flash] da inviare ad Audience Manager i dati di Analytics.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Per ogni oggetto [!DNL Flash], il codice supporta una sola istanza partner ( `d.partner`).
   >
   >
* Richiede la versione 3.5.2 o successiva della libreria Adobe [!UICONTROL AppMeasurement] [!DNL AS].


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
* [Segnali, caratteristiche e segmenti](../reference/signal-trait-segment.md)
* [Spiegazione delle coppie chiave-valore](../reference/key-value-pairs-explained.md)
* [Requisiti di prefisso delle variabili chiave](../features/traits/trait-variable-prefixes.md)

