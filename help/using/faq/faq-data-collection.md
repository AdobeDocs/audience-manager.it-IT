---
description: Domande e problemi comuni sulla raccolta di dati e l'integrazione.
seo-description: Domande e problemi comuni sulla raccolta di dati e l'integrazione.
seo-title: Domande frequenti sulla raccolta di dati e l'integrazione dei prodotti
solution: Audience Manager
title: Domande frequenti sulla raccolta di dati e l'integrazione dei prodotti
uuid: fa 8 e 79 f 4-99 cb -41 fd -8 a 85-d 4 f 92 d 03 c 7 a 5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Data Collection and Product Integration FAQ{#data-collection-and-product-integration-faq}

Domande e problemi comuni sulla raccolta di dati e l'integrazione.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Come si differenziano il traffico in ingresso dal[!UICONTROL DCS]traffico nelle[!UICONTROL DCS]esportazioni dei file di registro?**

Traits onboarded via [!UICONTROL Inbound] are populated by [!UICONTROL Inbound] the same way they get populated by [!UICONTROL DCS]. There are a few different ways to tell that traffic came from [!UICONTROL Inbound]:

* IP remoto impostato su 68.67.173.18
* Domainid sarà impostato su 5325
* L'area sarà impostata su 0

<br> 

**Posso fornire un elenco degli indirizzi IP che posso inserire nella whitelist per dpm. demdex. net?**

Purtroppo, non possiamo. These IPs are assigned dynamically, by geographic region, through [!DNL Amazon Web Services]. As a result, [!DNL Audience Manager] does not control the range of IPs that can be assigned to this address.

<br> 

**Posso fornire un indirizzo IP che posso inserire nella whitelist per il server FTP in entrata e in uscita?**

Sì, vedi di seguito.

| Elemento | Indirizzo |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quali sono i requisiti di posizionamento del codice e di caricamento della pagina per un'integrazione[!UICONTROL DIL]con i[!DNL Analytics]dati?**

To bring [!DNL Analytics] data into [!DNL Audience Manager], load [!UICONTROL DIL] after the `s_code` module but *before* the `s.t()` function. Ad esempio, inserite il codice o assicuratevi che venga caricato in questo ordine:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] modulo

3. [!DNL Analytics]`s.t()` function

As a best practice, set up your [!DNL Audience Manager]- [!DNL Analytics] integration with either of these 2 methods:

* Put [!UICONTROL DIL] directly in the `s_code`.

* Serve [!UICONTROL DIL] and the `s_code` through [!DNL Adobe Launch] or [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Perché le mie[!DNL Analytics]variabili mancano da una[!DNL Audience Manager]chiamata evento?**

In genere si verifica quando:

* You serve [!UICONTROL DIL] through a tag management system that loads it asynchronously with other code elements on the page.
* The `s.t()` function loads before [!UICONTROL DIL].

<br> 

**Che tipo di[!DNL Analytics]operazioni con[!UICONTROL DIL]?**

You must use [!DNL Analytics] version 20.2 (or higher) and the [!DNL Adobe AppMeasurement AS] library version 3.5.2 (or higher) to work with [!UICONTROL DIL]. If you don't know your [!DNL Analytics] or [!DNL AppMeasurement] version, check the [!DNL Analytics] call that gets made from the page. Informazioni sulla versione mostrate di seguito:

This customer uses [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

This customer uses [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Posso raccogliere i dati della pagina se non sono[!DNL Analytics]un cliente?**

Sì. [!UICONTROL DIL] Il modulo consente di raccogliere i dati della pagina anche se non si utilizza [!DNL Analytics]. When set up properly, [!UICONTROL DIL] can capture data from and about:

* Tag meta
* URL e intestazioni URL
* Tipi di motore di ricerca
* Parole chiave

Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want [!UICONTROL DIL] to collect data on. This lets you add and remove specific audience data points on your site without any [!DNL Audience Management] updates. Work with your Partner Solutions representative to properly set this up and ensure the [!DNL DIL] module references the page object correctly.

<br> 

**È possibile[!UICONTROL DIL]raccogliere i dati[!DNL Google Analytics]?**

Sì. [!UICONTROL DIL] possono raccogliere alcuni [!DNL Google Analytics] elementi (GA) e inoltrarli a [!DNL Audience Manager]. Consulta:

* [GA. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**Posso trovare dati non elaborati da[!DNL Audience Manager]e come è dettagliato?**

Yes, [!DNL Audience Manager] can provide you with data collected for users we've seen on your inventory. Ciò include:

* The unique user ID (UUID) assigned by [!DNL Audience Manager]
* Caratteristiche e ID segmento
* Segnali inutilizzati
* Marche temporali
* URL delle pagine

<br> 

**Desidero raccogliere dati su un sito ed eseguire il targeting degli utenti tramite DFP su un altro sito. Do I need to deploy code on the other property if I don't want to collect data from that location?**

No. Se la raccolta dati sul secondo sito non è necessaria, non è necessario distribuire DIL. Se hai accesso all'inventario sul secondo sito tramite DFP, puoi utilizzare la raccolta dati dal sito iniziale e tramite DFP.

<br> 

**Qual è il fornitore di dati di terze parti?**

Ogni fornitore porta qualcosa di univoco alla tabella, quindi la risposta dipende da cosa stai cercando. Possiamo abilitare la generazione di rapporti sovrapposti (senza costi) per aiutarti a capire quale fornitore funziona meglio al tuo posto.

<br> 

**Come[!DNL Audience Manager]impostare i cookie e passare variabili a DFP?**

[!DNL Audience Manager] imposta 2 cookie: Uno invia variabili segmentate al tag di annunci DFP, mentre l'altro imposta il nostro ID utente univoco (UUID), che viene letto anche tramite DFP. L'aggiunta dell'UUID al tag annunci significa che possiamo eseguire reporting a livello di utente e individuazione dell'audience.

<br> 

**Posso inviare una informazione DSP su punti nel funnel di conversione raggiunto da un utente?**

Sì. Possiamo inviare dati funnel, ma il DSP deve avere la capacità tecnica di utilizzarla. Un DSP deve confermare che possono gestire più segmenti. Se non possono, potrebbe essere necessario creare segmenti specifici per estrarre un utente da altri segmenti in base all'avanzamento della conversione (ad es., completare i passaggi 1 e 2 ma non il passaggio 3). Potresti voler inviare queste informazioni a una DSP in modo che possano reindirizzare gli utenti, indirizzarli a una pagina di destinazione specifica o visualizzare alcuni creativi specifici.

<br> 

**Come posso confermare che i dati inviati tramite FTP sono stati prelevati[!DNL Audience Manager]da?**

A file has been picked up when the extension changes from `.sync` to `.processed`. In tal caso, il file si trova nella coda di assimilazione. Inoltre, il manager commerciale può confermare quando un file è stato caricato.

<br> 

**Desidero testare le funzionalità dell'API[DCS](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Sto inviando chiamate evento come quella mostrata di seguito. The calls contain[Declared IDs](../features/declared-ids.md)and signals, which should realize some traits and segments I have already set up. Can I use the[!UICONTROL General Reports]and[!UICONTROL Trend Reports]to verify if the trait and segment populations are increasing?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, do not rely on the [!UICONTROL General Reports] and [!UICONTROL Trend Reports] in this case.

I rapporti calcolano le popolazioni in base ai record di profilo non autenticati (UUID) visualizzati nel backend al momento in cui i rapporti vengono generati.

On a first call to the [!UICONTROL DCS], the declared IDs are *not* linked to any UUID (i.e. no [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The [!UICONTROL DCS] will randomly generate a UUID and set a [!DNL demdex] cookie and pass it on in the response call, but it will not transmit the UUID to the backend.

>[!NOTE]
>
>L'UUID generato verrà materializzato solo nell'archivio dei dati di backend quando il dispositivo su cui viene impostato il cookie attiva ulteriori attività.

Per questo motivo, i report non riflettono gli eventi attivati dagli ID dichiarati nella chiamata. We recommend you use UUID, ECID (formerly MID) or mobile device IDs in event test calls to the [!UICONTROL DCS]. Then, you can verify the trait and segment realizations in the [!UICONTROL General Reports] and in the [!UICONTROL Trend Reports].

See also, the [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**Quanto tempo è necessario sincronizzare tra i profili[utente](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

In genere sono necessarie fino a 24 ore perché un profilo utente possa sincronizzarsi tra più aree. Tuttavia, in rari casi, il processo può richiedere fino a 48 ore.
