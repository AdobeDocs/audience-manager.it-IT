---
description: Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 2%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo di [!DNL Data Integration Library (DIL)] e dell&#39;estensione [!DNL DIL].
>
>I clienti esistenti possono continuare a utilizzare l&#39;implementazione [!DNL DIL]. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

Raccogli i dati inviati dai file FLA ad Analytics e utilizza tali informazioni in Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] è una libreria di codici [!DNL ActionScript] che consente di utilizzare i dati di riproduzione video in Audience Manager. [!DNL Flash DIL] funziona acquisendo il contenuto di SWF che la libreria Adobe [!UICONTROL AppMeasurement] trasmette ad Analytics. [!DNL Flash DIL] invia tali dati al modulo separato di raccolta dati di JavaScript [!UICONTROL DIL], che trasmette tali informazioni ad Audience Manager. Dati di Analytics ( [!UICONTROL Props], [!UICONTROL eVars], eventi, ecc.) i dati acquisiti dal file [!DNL FLA] sono disponibili in Audience Manager come caratteristiche o segnali non utilizzati.

## Requisiti per la raccolta di dati Flash DIL {#requirements}

Requisiti generali di implementazione e relativi al codice.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisiti di implementazione**

La raccolta dati [!UICONTROL Flash] richiede:

* Libreria di classi [!UICONTROL DIL] ( `dil.swc`). Ottieni la libreria di classi [!UICONTROL DIL] dal contatto delle soluzioni partner.

* Codice di raccolta dati di JavaScript [!UICONTROL DIL] nella pagina.
* [Libreria ActionScript DIL](../dil/dil-flash.md#flash-dil-actionscript) caricata nell&#39;oggetto Flash da cui si desidera raccogliere i dati.
* La libreria dell&#39;Adobe [!DNL AppMeasurement] [!DNL AS] (versione 3.5.2 o successiva) ha caricato l&#39;oggetto [!DNL Flash] da cui si desidera raccogliere i dati.

**Imposta AllowScriptAccess su `Always` o`sameDomain`**

`AllowScriptAccess` nel codice HTML che carica un file SWF controlla la possibilità di eseguire l&#39;accesso agli URL in uscita dall&#39;interno del file SWF. Quando configuri un&#39;integrazione dei dati [!UICONTROL Flash DIL], assicurati che il parametro di Flash `AllowScriptAccess` sia impostato su `always` o `sameDomain`. La raccolta dati [!UICONTROL Flash DIL] non funzionerà se `AllowScriptAccess` è impostato su `never`. Vedere [Controlla l&#39;accesso agli script o alla pagina Web host](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] posizionamento codice**

Provare a inserire il modulo di raccolta dati JS [!UICONTROL DIL] nella pagina in modo che venga caricato prima del file [!DNL FLA]. Quando il file [!DNL FLA] viene caricato per primo, prima che la raccolta dati [!UICONTROL DIL] sia pronta, è possibile che i segnali di dati iniziali inviati da [!UICONTROL Flash DIL] al modulo non vengano visualizzati. Tuttavia, una volta creata l&#39;istanza, il modulo di raccolta dati [!UICONTROL DIL] acquisirà tutti i dati successivi del file SWF passati da [!UICONTROL Flash DIL].

## Dati raccolti da Flash DIL {#data-collected}

[!UICONTROL Flash DIL] acquisisce la visualizzazione pagina, il tracciamento dei collegamenti, il tracciamento dei contenuti multimediali e altri eventi di visualizzazione dei contenuti multimediali dalla libreria Adobe [!UICONTROL AppMeasurement].

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventi Visualizzazione Pagina**

Se non diversamente specificato da `s.trackVars`, [!UICONTROL Flash DIL] raccoglie i seguenti dati da Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventi di tracciamento collegamenti**

Se non diversamente specificato da `s.linkTrackVars`, [!UICONTROL Flash DIL] raccoglie i dati seguenti dall&#39;Adobe [!UICONTROL AppMeasurement]:

* `pe` (tipo di collegamento traccia chiamato)
* `pev1` (URL collegamento)
* `pev2`(testo collegamento)

**Eventi di tracciamento dei contenuti multimediali**

Se non diversamente specificato da `s.Media.trackVars`, [!UICONTROL Flash DIL] raccoglie tutti i dati enumerati nella sezione Page View Events.

**Altri punti dati**

I dati di questi parametri vengono raccolti per impostazione predefinita:

* `mediaName` (nome elemento multimediale/video)
* `mediaAdName` (nome annuncio)
* `mediaAdParentName` (nome del contenuto multimediale principale in cui l&#39;annuncio è nidificato)
* `mediaAdParentPod` (il pod o l&#39;interruzione pubblicitaria all&#39;interno del contenuto principale in cui viene riprodotto l&#39;annuncio)
* `mediaAdParentPodPos` (posizione numerica all&#39;interno del pod in cui viene riprodotto l&#39;annuncio. In un pod è possibile riprodurre più annunci.

## Dati Flash DIL in Audience Manager {#flash-dil-data}

Il modulo [!UICONTROL Flash DIL] trasforma i dati di Adobe AppMeasurement in caratteristiche Audienci Manager e segnali inutilizzati.

<!-- 

c_flash_dil_in_aam.xml

 -->

Gli eventi [!UICONTROL Props], [!UICONTROL eVars] e di Analytics funzionano come le caratteristiche in Audience Manager. Le caratteristiche sono coppie chiave-valore e vengono utilizzate per creare i segmenti. Ad esempio, in un prop di Analytics come `c30=foo`, `c30` è la chiave (una costante) e `foo` è il valore (una variabile).

**Corrispondenza delle caratteristiche Audienci Manager con le variabili di Analytics**

Per utilizzare i dati di Analytics passati da [!UICONTROL Flash DIL], è necessario creare caratteristiche Audience Manager con il valore chiave preceduto da `c_`.

Per esempi, consulta la tabella:

| Elemento dati di Analytics | Esempio di Analytics | Come caratteristica Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **eventi** | `events=event10` | `c_events=event10` |

**Dati DIL/Analytics come segnali non utilizzati**

L&#39;Audience Manager accetta gli eventi Analytics [!UICONTROL Props], [!UICONTROL eVars] e anche senza una caratteristica corrispondente. In questo caso, i dati non sono disponibili per la creazione delle caratteristiche e vengono invece visualizzati nel report [Segnali inutilizzati](../reporting/dynamic-reports/unused-signals.md). Per trarre il massimo da queste informazioni, creare caratteristiche Audience Manager corrispondenti ai dati di Analytics trasmessi dalla libreria [!UICONTROL Flash DIL].

## Libreria ActionScript di Flash DIL {#flash-dil-actionscript}

Codice per l&#39;oggetto [!DNL Flash] per inviare dati Analytics ad Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Per ogni oggetto [!DNL Flash], il codice supporta una sola istanza partner ( `d.partner`).
>
>* Richiede la libreria dell&#39;Adobe [!UICONTROL AppMeasurement] [!DNL AS] versione 3.5.2 o successiva.

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
>* [Caratteristiche](../features/traits/trait-details-page.md)
>* [Segnali, caratteristiche e segmenti](../reference/signal-trait-segment.md)
>* [Spiegazione delle coppie chiave-valore](../reference/key-value-pairs-explained.md)
>* [Requisiti di prefisso delle variabili chiave](../features/traits/trait-variable-prefixes.md)
