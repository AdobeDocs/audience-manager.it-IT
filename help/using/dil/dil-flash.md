---
description: Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 3%

---

# Flash DIL{#flash-dil}

Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] è un [!DNL ActionScript] libreria di codici che consente di lavorare con i dati di riproduzione video in Audience Manager. [!DNL Flash DIL] funziona acquisendo il contenuto SWF dell’Adobe [!UICONTROL AppMeasurement] La libreria passa ad Analytics. [!DNL Flash DIL] invia tali dati a [!UICONTROL DIL] Modulo di raccolta dati JavaScript, che trasmette tali informazioni ad Audience Manager. Dati di Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventi, ecc.) acquisito da [!DNL FLA] Il file è disponibile in Audience Manager come caratteristiche o segnali non utilizzati.

## Requisiti per la raccolta di dati Flash DIL {#requirements}

Requisiti generali di implementazione e relativi al codice.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisiti di implementazione**

[!UICONTROL Flash] la raccolta dei dati richiede:

* Il [!UICONTROL DIL] libreria di classi ( `dil.swc`). Ottenere il [!UICONTROL DIL] libreria di classi dal contatto delle soluzioni dei partner.

* JavaScript [!UICONTROL DIL] codice di raccolta dati sulla pagina.
* [Libreria DIL ActionScript](../dil/dil-flash.md#flash-dil-actionscript) caricato nell’oggetto Flash da cui desideri raccogliere i dati.
* Adobe [!DNL AppMeasurement] [!DNL AS] libreria (versione 3.5.2 o successiva) ha caricato [!DNL Flash] oggetto da cui si desidera raccogliere i dati.

**Imposta AllowScriptAccess su `Always` o`sameDomain`**

Il `AllowScriptAccess` nel codice HTML che carica un file SWF, controlla la capacità di eseguire l’accesso agli URL in uscita dall’interno del file SWF. Quando si configura una [!UICONTROL Flash DIL] integrazione dei dati, assicurati che il Flash `AllowScriptAccess` il parametro è impostato su `always` o `sameDomain`. [!UICONTROL Flash DIL] la raccolta dei dati non funzionerà se `AllowScriptAccess` è impostato su `never`. Consulta [Controlla l&#39;accesso agli script o alla pagina Web host](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Posizionamento del codice**

Prova a inserire JS [!UICONTROL DIL] sulla pagina in modo che venga caricato prima del [!DNL FLA] file. Quando [!DNL FLA] il file viene caricato per primo, prima [!UICONTROL DIL] la raccolta dati è pronta, puoi perdere i segnali di dati iniziali che [!UICONTROL Flash DIL] invia a tale modulo. Tuttavia, una volta creata l’istanza, [!UICONTROL DIL] il modulo di raccolta dati acquisirà tutti i dati successivi del file SWF trasmessi da [!UICONTROL Flash DIL].

## Dati raccolti da Flash DIL {#data-collected}

[!UICONTROL Flash DIL] acquisisce la visualizzazione pagina, il tracciamento dei collegamenti, il tracciamento dei contenuti multimediali e altri eventi di visualizzazione dei contenuti multimediali dall’Adobe [!UICONTROL AppMeasurement] libreria.

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

**Eventi di tracciamento collegamenti**

Se non diversamente specificato da `s.linkTrackVars`, [!UICONTROL Flash DIL] raccoglie i seguenti dati da Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo di collegamento di tracciamento chiamato)
* `pev1` (URL collegamento)
* `pev2`(Testo collegamento)

**Eventi di tracciamento dei contenuti multimediali**

Se non diversamente specificato da `s.Media.trackVars`, [!UICONTROL Flash DIL] raccoglie tutti i dati enumerati nella sezione Page View Events.

**Altri punti dati**

I dati di questi parametri vengono raccolti per impostazione predefinita:

* `mediaName` (Nome elemento multimediale/video)
* `mediaAdName` (Nome annuncio)
* `mediaAdParentName` (Nome del contenuto multimediale principale in cui l’annuncio è nidificato)
* `mediaAdParentPod` (Il pod o l’interruzione pubblicitaria all’interno del contenuto principale in cui viene riprodotto l’annuncio)
* `mediaAdParentPodPos` (La posizione numerica all’interno del pod in cui viene riprodotto l’annuncio. In un pod è possibile riprodurre più annunci.

## Dati Flash DIL in Audience Manager {#flash-dil-data}

Il [!UICONTROL Flash DIL] trasforma i dati di Adobe AppMeasurement in caratteristiche Audienci Manager e segnali non utilizzati.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], e gli eventi funzionano come caratteristiche in Audience Manager. Le caratteristiche sono coppie chiave-valore e vengono utilizzate per creare i segmenti. Ad esempio, in un prop di Analytics come `c30=foo`, `c30` è la chiave (una costante) e `foo` è il valore (una variabile).

**Confrontare caratteristiche Audience Manager con variabili Analytics**

Per utilizzare i dati di Analytics trasmessi da [!UICONTROL Flash DIL], è necessario creare caratteristiche Audienci Manager con il prefisso &quot;key value&quot; `c_`.

Per esempi, consulta la tabella:

| Elemento dati di Analytics | Esempio di Analytics | Come caratteristica Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dati DIL/Analytics come segnali non utilizzati**

Audience Manager accetta Analytics [!UICONTROL Props], [!UICONTROL eVars], e anche senza una caratteristica corrispondente. In questo caso, i dati non sono disponibili per la creazione delle caratteristiche e vengono visualizzati nel [Rapporto sui segnali non utilizzati](../reporting/dynamic-reports/unused-signals.md) invece. Per sfruttare al massimo queste informazioni, crea delle caratteristiche Audienci Manager che corrispondono ai dati di Analytics trasmessi da [!UICONTROL Flash DIL] libreria.

## Libreria ActionScript di Flash DIL {#flash-dil-actionscript}

Codice per [!DNL Flash] oggetto per inviare dati di Analytics ad Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Per ogni [!DNL Flash] , il codice supporta un&#39;istanza partner ( `d.partner`) solo.
>
>* Richiede l&#39;Adobe [!UICONTROL AppMeasurement] [!DNL AS] libreria versione 3.5.2 o successiva.


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

