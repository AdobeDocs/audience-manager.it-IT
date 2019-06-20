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

[!UICONTROL Flash DIL] è una libreria [!DNL ActionScript] di codici che consente di utilizzare i dati di riproduzione video in Audience Manager. [!DNL Flash DIL] funziona acquisendo il contenuto SWF che [!UICONTROL AppMeasurement] la libreria Adobe trasmette ad Analytics. [!DNL Flash DIL] invia tali dati al modulo di [!UICONTROL DIL] raccolta dati javascript separato, che trasmette tali informazioni ad Audience Manager. Dati di Analytics ( [!UICONTROL Props][!UICONTROL eVars], eventi, ecc.) acquisito dal [!DNL FLA] file è disponibile in Audience Manager come caratteristiche o segnali inutilizzati.

## Requisiti per la raccolta dati DIL Flash {#requirements}

Requisiti generali per l&#39;implementazione e il codice.

<!-- 

c_flash_dil_intro.xml

 -->

**Requisiti di implementazione**

[!UICONTROL Flash] La raccolta di dati richiede:

* La [!UICONTROL DIL] libreria di classe ( `dil.swc`). Ottenete la [!UICONTROL DIL] libreria di classe dal contatto Soluzioni partner.

* Codice di raccolta [!UICONTROL DIL] dati javascript sulla pagina.
* [La libreria actionscript DIL](../dil/dil-flash.md#flash-dil-actionscript) caricata nell&#39;oggetto Flash da cui si desidera raccogliere i dati.
* La libreria Adobe [!DNL AppMeasurement][!DNL AS] (versione 3.5.2 o successiva) ha caricato l&#39; [!DNL Flash] oggetto da cui si desidera raccogliere i dati.

**Impostate allowscriptaccess su`Always`o`sameDomain`**

Il `AllowScriptAccess` codice HTML che carica un file SWF controlla la capacità di eseguire l&#39;accesso degli URL in uscita direttamente dal file SWF. Quando configurate un&#39;integrazione [!UICONTROL Flash DIL] di dati, accertatevi che il `AllowScriptAccess` parametro Flash sia impostato `always` su o `sameDomain`. [!UICONTROL Flash DIL] La raccolta dati non funziona se `AllowScriptAccess` è impostata su `never`. Vedere [Controllo dell&#39;accesso agli script o alla pagina Web host](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Posizionamento[!UICONTROL DIL]codice JS**

Provate a posizionare il modulo di raccolta [!UICONTROL DIL] dati JS sulla pagina in modo che venga caricato prima del [!DNL FLA] file. Quando il [!DNL FLA] file viene caricato per primo, prima [!UICONTROL DIL] che la raccolta dati sia pronta, è possibile perderne i segnali iniziali che [!UICONTROL Flash DIL] inviano a tale modulo. Tuttavia, dopo l&#39;istanza, il [!UICONTROL DIL] modulo di raccolta dati acquisirà tutti i dati successivi del file SWF trasmessi da [!UICONTROL Flash DIL].

## Dati raccolti da Flash DIL {#data-collected}

[!UICONTROL Flash DIL] acquisisce la visualizzazione di pagina, il tracciamento dei collegamenti, il tracciamento dei supporti e altri eventi di visualizzazione contenuti multimediali dalla [!UICONTROL AppMeasurement] libreria Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Eventi visualizzazioni pagina**

Se specificato diversamente da `s.trackVars`, [!UICONTROL Flash DIL] raccoglie i seguenti dati da Adobe appmeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Eventi tracciamento collegamenti**

Se specificato diversamente da `s.linkTrackVars`, [!UICONTROL Flash DIL] raccoglie i seguenti dati da Adobe [!UICONTROL AppMeasurement]:

* `pe` (Tipo di collegamento di traccia denominato)
* `pev1` (URL collegamento)
* `pev2`(Collegamento testo)

**Eventi di tracciamento multimediale**

Se specificato diversamente, `s.Media.trackVars`[!UICONTROL Flash DIL] raccoglie tutti i dati enumerati nella sezione Eventi della visualizzazione pagina.

**Altri punti dati**

I dati di questi parametri vengono raccolti per impostazione predefinita:

* `mediaName` (Nome elemento multimediale/video)
* `mediaAdName` (Nome annuncio)
* `mediaAdParentName` (Nome del contenuto multimediale principale, l&#39;annuncio è nidificato sotto)
* `mediaAdParentPod` (Il contenitore o l&#39;interruzione di annunci all&#39;interno del contenuto principale in cui viene riprodotto l&#39;annuncio)
* `mediaAdParentPodPos` (La posizione numerica all&#39;interno del contenitore in cui viene riprodotto l&#39;annuncio. È possibile riprodurre più di un annuncio all&#39;interno di un contenitore.

>[!MORE_ LIKE_ THIS]
>
>* [Guida all&#39;implementazione di appmeasurement Flash, Flex e OSMF](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL Data in Audience Manager {#flash-dil-data}

[!UICONTROL Flash DIL] Il modulo trasforma i dati Adobe appmeasurement in caratteristiche Audience Manager e segnali inutilizzati.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]ed eventi funzionano come caratteristiche in Audience Manager. Le caratteristiche sono coppie chiave-valore e sono utilizzate per creare segmenti. Ad esempio, in un prop Analytics come `c30=foo`, `c30` è la chiave (una costante) ed `foo` è il valore (una variabile).

**Corrispondenza delle caratteristiche di Audience Manager in Analytics**

Per utilizzare i dati di Analytics passati da [!UICONTROL Flash DIL], è necessario creare caratteristiche Audience Manager con `c_`il valore chiave prefissato.

Vedere la tabella per esempi:

| Elemento dati di Analytics | Esempio di Analytics | Come caratteristica Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Dati DIL/Analytics come segnali inutilizzati**

Audience Manager accetta Analytics [!UICONTROL Props], [!UICONTROL eVars]ed eventi anche senza una caratteristica corrispondente. In questo caso, i dati non sono disponibili per la creazione di caratteristiche e appaiono nel rapporto Segnali [non utilizzati](../reporting/dynamic-reports/unused-signals.md) . Per sfruttare al massimo queste informazioni, crea caratteristiche Audience Manager che corrispondano ai dati di Analytics passati dalla [!UICONTROL Flash DIL] libreria.

>[!MORE_ LIKE_ THIS]
>
>* [Caratteristiche](../features/traits/trait-details-page.md)
>* [Segnali, caratteristiche e segmenti](../reference/signal-trait-segment.md)
>* [Coppie chiave-valore spiegate](../reference/key-value-pairs-explained.md)
>* [Requisiti di prefisso per variabili chiave](../features/traits/trait-variable-prefixes.md)


## Libreria actionscript di Flash DIL {#flash-dil-actionscript}

Codice per l&#39; [!DNL Flash] oggetto per inviare dati di Analytics ad Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Per ciascun [!DNL Flash] oggetto, il codice supporta solo un&#39;istanza partner ( `d.partner`).
   >
   >
* Richiede la [!UICONTROL AppMeasurement][!DNL AS] libreria Adobe 3.5.2 o successiva.
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

