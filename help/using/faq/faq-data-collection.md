---
description: Domande e problemi comuni in materia di raccolta e integrazione dei dati.
seo-description: Domande e problemi comuni in materia di raccolta e integrazione dei dati.
seo-title: Domande frequenti sulla raccolta dei dati e l'integrazione dei prodotti
solution: Audience Manager
title: Domande frequenti sulla raccolta dei dati e l'integrazione dei prodotti
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Domande frequenti sulla raccolta dei dati e l&#39;integrazione dei prodotti{#data-collection-and-product-integration-faq}

Domande e problemi comuni in materia di raccolta e integrazione dei dati.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Come è possibile distinguere il traffico in entrata dal[!UICONTROL DCS]traffico nelle esportazioni dei file di[!UICONTROL DCS]registro?**

Le caratteristiche registrate tramite [!UICONTROL Inbound] sono popolate [!UICONTROL Inbound] nello stesso modo in cui vengono popolate [!UICONTROL DCS]. Ci sono alcuni modi diversi per dire che il traffico proveniva da [!UICONTROL Inbound]:

* IP remoto sarà impostato su 68.67.173.18
* DomainID verrà impostato su 5325
* Regione verrà impostata su 0

<br> 

**Puoi fornirmi un elenco di indirizzi IP che posso inserire nella whitelist per dpm.demdex.net?**

Sfortunatamente non possiamo. Questi IP vengono assegnati in modo dinamico, per area geografica, attraverso [!DNL Amazon Web Services]. Di conseguenza, [!DNL Audience Manager] non controlla l&#39;intervallo di IP che è possibile assegnare a questo indirizzo.

<br> 

**Puoi fornirmi un indirizzo IP che posso inserire nella lista bianca per il tuo server FTP in entrata e in uscita?**

Sì, vedi sotto.

| Elemento | Indirizzo |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quali sono i requisiti di posizionamento del codice e di caricamento della pagina per un&#39;integrazione[!UICONTROL DIL]/[!DNL Analytics]dati?**

Per inserire [!DNL Analytics] i dati in [!DNL Audience Manager], caricarli [!UICONTROL DIL] dopo il `s_code` modulo ma *prima* della `s.t()` funzione. Ad esempio, inserite il codice o assicuratevi che venga caricato nell&#39;ordine seguente:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] modulo [!UICONTROL DIL]

3. [!DNL Analytics] `s.t()` funzione

Come procedura ottimale, configurate l&#39; [!DNL Audience Manager]- [!DNL Analytics] integrazione con uno dei due metodi seguenti:

* Metta [!UICONTROL DIL] direttamente nella `s_code`.

* Servire [!UICONTROL DIL] e il `s_code` passante [!DNL Adobe Experience Platform Launch] o [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Perché[!DNL Analytics]le variabili mancanti da una chiamata a un[!DNL Audience Manager]evento?**

Questo accade in genere quando:

* Potete utilizzare [!UICONTROL DIL] un sistema di gestione tag che lo carica in modo asincrono con altri elementi di codice sulla pagina.
* La `s.t()` funzione viene caricata prima [!UICONTROL DIL].

<br> 

**Quali versioni di[!DNL Analytics]lavoro[!UICONTROL DIL]?**

Per funzionare è necessario utilizzare [!DNL Analytics] la versione 20.2 (o successiva) e la versione della [!DNL Adobe AppMeasurement AS] libreria 3.5.2 (o successiva) [!UICONTROL DIL]. Se non conosci la tua [!DNL Analytics] o [!DNL AppMeasurement] la tua versione, controlla la [!DNL Analytics] chiamata effettuata dalla pagina. Informazioni sulla versione visualizzate di seguito:

Questo cliente utilizza la [!DNL Analytics] versione 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Questo cliente utilizza la [!DNL AppMeasurement] versione 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Posso raccogliere i dati della pagina se non sono un[!DNL Analytics]cliente?**

Sì. Il [!UICONTROL DIL] modulo consente di raccogliere i dati di pagina anche se non si utilizza [!DNL Analytics]. Una volta configurati correttamente, [!UICONTROL DIL] è possibile acquisire dati da e su:

* Metadati
* URL e intestazioni URL
* Tipi di motori di ricerca
* Parole chiave

Inoltre, i client possono distribuire un semplice oggetto onsite e compilarlo con coppie chiave-valore su cui si desidera [!UICONTROL DIL] raccogliere i dati. Questo consente di aggiungere e rimuovere punti di dati di audience specifici sul sito senza [!DNL Audience Management] aggiornamenti. Collabora con il rappresentante delle soluzioni partner per configurare correttamente questa configurazione e assicurati che il [!DNL DIL] modulo faccia riferimento correttamente all&#39;oggetto della pagina.

<br> 

**È possibile[!UICONTROL DIL]raccogliere i dati da[!DNL Google Analytics]?**

Sì. [!UICONTROL DIL] può raccogliere alcuni elementi [!DNL Google Analytics] (GA) e trasmettere tali dati a [!DNL Audience Manager]. Consulta:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Posso ottenere dati grezzi da[!DNL Audience Manager]e quanto è granulare?**

Sì, [!DNL Audience Manager] puoi fornire i dati raccolti per gli utenti che abbiamo visto nel tuo inventario. Ciò include:

* L&#39;ID utente univoco (UUID) assegnato da [!DNL Audience Manager]
* ID di caratteristiche e segmenti
* Segnali inutilizzati
* Timestamp
* URL pagina

<br> 

**Desidero raccogliere i dati su un sito e indirizzare gli utenti tramite DFP su un sito diverso. È necessario distribuire il codice sull&#39;altra proprietà se non si desidera raccogliere i dati da tale posizione?**

No. Se la raccolta dei dati sul secondo sito non è un requisito, non è necessario distribuire DIL. Se si dispone dell&#39;accesso all&#39;inventario sul secondo sito tramite DFP, è possibile utilizzare la raccolta dati dal sito iniziale e il targeting tramite DFP.

<br> 

**Qual è il miglior provider di dati di terze parti?**

Ogni provider porta qualcosa di unico al tavolo, quindi la risposta dipende da cosa stai cercando. Possiamo abilitare la funzione di reporting delle sovrapposizioni (senza alcun costo) per aiutarti a capire quale provider potrebbe funzionare meglio per te.

<br> 

**Come[!DNL Audience Manager]impostare i cookie e trasmettere le variabili a DFP?**

[!DNL Audience Manager] imposta 2 cookie: Una invia le variabili del segmento al tag dell’annuncio DFP e l’altra imposta il nostro ID utente univoco (UUID), che viene letto anche da DFP. L&#39;aggiunta dell&#39;UUID al tag dell&#39;annuncio consente di creare report a livello di utente e di individuare l&#39;audience.

<br> 

**È possibile inviare informazioni DSP sui punti nel funnel di conversione raggiunto da un utente?**

Sì. Possiamo inviare i dati del funnel, ma il DSP deve avere la capacità tecnica di utilizzarli. Un DSP deve confermare di poter gestire più segmenti. In caso contrario, potrebbe essere necessario creare segmenti specifici per estrarre un utente da altri segmenti in base al loro avanzamento di conversione (ad esempio, i passaggi 1 e 2 completati ma non il passaggio 3). Potrebbe essere utile inviare queste informazioni a un DSP in modo che possano restituire gli utenti, indirizzarli a una pagina di destinazione specifica o visualizzare specifiche creatività.

<br> 

**Come posso confermare che i dati inviati tramite FTP sono stati raccolti da[!DNL Audience Manager]?**

Un file è stato prelevato quando l’estensione cambia da `.sync` a `.processed`. In questo caso, il file si trova nella coda di assimilazione. Inoltre, il vostro account manager può confermare quando un file è stato caricato.

<br> 

**Voglio testare la funzionalità dell&#39;API[](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)DCS. Sto inviando chiamate evento come quella mostrata di seguito. Le chiamate contengono ID[](../features/declared-ids.md)dichiarati e segnali, che dovrebbero comprendere alcune caratteristiche e alcuni segmenti che ho già configurato. Posso usare il[!UICONTROL General Reports]e[!UICONTROL Trend Reports]per verificare se le caratteristiche e le popolazioni di segmenti stanno aumentando?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, non fate affidamento sul [!UICONTROL General Reports] e [!UICONTROL Trend Reports] in questo caso.

I report calcolano le popolazioni in base ai record di profilo non autenticati (UUID) visualizzati nel backend al momento della generazione dei report.

In una prima chiamata al [!UICONTROL DCS], gli ID dichiarati *non* sono collegati ad alcun UUID (ovvero nessun cookie [](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex è presente sul lato client). L’utente [!UICONTROL DCS] genererà un UUID in modo casuale, imposterà un [!DNL demdex] cookie e lo trasmetterà nella chiamata di risposta, ma non trasmetterà l’UUID al backend.

>[!NOTE]
>
>L&#39;UUID generato verrà materializzato nella memorizzazione dei dati di back-end solo dopo che il dispositivo su cui è impostato il cookie attiverà un&#39;ulteriore attività.

Per questo motivo, i report non rifletteranno gli eventi attivati dagli ID dichiarati nella chiamata. È consigliabile utilizzare UUID, ECID (già MID) o ID dispositivo mobile nelle chiamate di test evento al [!UICONTROL DCS]. Quindi puoi verificare le realizzazioni di caratteristiche e segmenti nella [!UICONTROL General Reports] e nella [!UICONTROL Trend Reports].

Vedi anche [Indice degli ID](../reference/ids-in-aam.md)di Audience Manager.

<br> 

**Quanto tempo è necessario per la sincronizzazione dei profili utente tra[le diverse aree geografiche](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

In genere la sincronizzazione di un profilo utente tra diverse aree richiede fino a 24 ore. Tuttavia, in rari casi, il processo può richiedere fino a 48 ore.
