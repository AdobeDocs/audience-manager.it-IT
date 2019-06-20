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


# Domande frequenti sulla raccolta di dati e l&#39;integrazione dei prodotti{#data-collection-and-product-integration-faq}

Domande e problemi comuni sulla raccolta di dati e l&#39;integrazione.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Come si differenziano il traffico in ingresso dal[!UICONTROL DCS]traffico nelle[!UICONTROL DCS]esportazioni dei file di registro?**

Le caratteristiche caricate sono [!UICONTROL Inbound] popolate con [!UICONTROL Inbound] la stessa modalità [!UICONTROL DCS]con cui vengono popolate. Esistono diversi modi per comunicare che il traffico proviene [!UICONTROL Inbound]da:

* IP remoto impostato su 68.67.173.18
* Domainid sarà impostato su 5325
* L&#39;area sarà impostata su 0

<br> 

**Posso fornire un elenco degli indirizzi IP che posso inserire nella whitelist per dpm. demdex. net?**

Purtroppo, non possiamo. Questi IP vengono assegnati in modo dinamico, tramite area geografica, tramite [!DNL Amazon Web Services]. Di conseguenza, [!DNL Audience Manager] non controlla l&#39;intervallo di ips che può essere assegnato a questo indirizzo.

<br> 

**Posso fornire un indirizzo IP che posso inserire nella whitelist per il server FTP in entrata e in uscita?**

Sì, vedi di seguito.

| Elemento | Indirizzo |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quali sono i requisiti di posizionamento del codice e di caricamento della pagina per un&#39;integrazione[!UICONTROL DIL]con i[!DNL Analytics]dati?**

Per inserire [!DNL Analytics][!DNL Audience Manager]dati, caricare [!UICONTROL DIL] dopo il `s_code` modulo ma *prima* della `s.t()` funzione. Ad esempio, inserite il codice o assicuratevi che venga caricato in questo ordine:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] modulo

3. [!DNL Analytics]`s.t()` function

Come procedura ottimale, impostate [!DNL Audience Manager]l [!DNL Analytics] &#39;integrazione con uno di questi due metodi:

* Inserisci [!UICONTROL DIL] direttamente `s_code`in.

* Trasmissione [!UICONTROL DIL] , `s_code`[!DNL Adobe Launch][!DNL Adobe DTM]ecc.

Consultate [API Library Integration Library (DIL)](../dil/dil-overview.md).

<br> 

**Perché le mie[!DNL Analytics]variabili mancano da una[!DNL Audience Manager]chiamata evento?**

In genere si verifica quando:

* Utilizzate [!UICONTROL DIL] un sistema di gestione tag che lo carica in modo asincrono con altri elementi del codice sulla pagina.
* La `s.t()` funzione viene caricata prima [!UICONTROL DIL].

<br> 

**Che tipo di[!DNL Analytics]operazioni con[!UICONTROL DIL]?**

È necessario utilizzare [!DNL Analytics] la versione 20.2 (o successiva) e la [!DNL Adobe AppMeasurement AS] versione della libreria 3.5.2 (o successiva) con [!UICONTROL DIL]cui lavorare. Se non conosci la tua versione [!DNL Analytics] o [!DNL AppMeasurement] la tua versione, controlla la [!DNL Analytics] chiamata che viene effettuata dalla pagina. Informazioni sulla versione mostrate di seguito:

Il cliente utilizza [!DNL Analytics] la versione 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Il cliente utilizza [!DNL AppMeasurement] la versione 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Posso raccogliere i dati della pagina se non sono[!DNL Analytics]un cliente?**

Sì. [!UICONTROL DIL] Il modulo consente di raccogliere i dati della pagina anche se non si utilizza [!DNL Analytics]. Se configurato correttamente, [!UICONTROL DIL] può acquisire dati da e su:

* Tag meta
* URL e intestazioni URL
* Tipi di motore di ricerca
* Parole chiave

Inoltre, i client possono implementare un semplice oggetto onsite e compilarlo con coppie chiave-valore a cui [!UICONTROL DIL] si desidera raccogliere i dati. Questo consente di aggiungere e rimuovere specifici punti dati di audience sul sito senza [!DNL Audience Management] aggiornamenti. Collabora con il rappresentante delle soluzioni Partner per impostarlo correttamente e accertati che [!DNL DIL] il modulo faccia correttamente riferimento all&#39;oggetto della pagina.

<br> 

**È possibile[!UICONTROL DIL]raccogliere i dati[!DNL Google Analytics]?**

Sì. [!UICONTROL DIL] possono raccogliere alcuni [!DNL Google Analytics] elementi (GA) e inoltrarli a [!DNL Audience Manager]. Consulta:

* [GA. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**Posso trovare dati non elaborati da[!DNL Audience Manager]e come è dettagliato?**

Sì, [!DNL Audience Manager] puoi fornire dati raccolti per gli utenti che sono stati visti nell&#39;inventario. Ciò include:

* L&#39;ID utente univoco (UUID) assegnato da [!DNL Audience Manager]
* Caratteristiche e ID segmento
* Segnali inutilizzati
* Marche temporali
* URL delle pagine

<br> 

**Desidero raccogliere dati su un sito ed eseguire il targeting degli utenti tramite DFP su un altro sito. È necessario distribuire il codice sull&#39;altra proprietà se non desidero raccogliere dati da tale posizione?**

No. Se la raccolta dati sul secondo sito non è necessaria, non è necessario distribuire DIL. Se hai accesso all&#39;inventario sul secondo sito tramite DFP, puoi utilizzare la raccolta dati dal sito iniziale e tramite DFP.

<br> 

**Qual è il fornitore di dati di terze parti?**

Ogni fornitore porta qualcosa di univoco alla tabella, quindi la risposta dipende da cosa stai cercando. Possiamo abilitare la generazione di rapporti sovrapposti (senza costi) per aiutarti a capire quale fornitore funziona meglio al tuo posto.

<br> 

**Come[!DNL Audience Manager]impostare i cookie e passare variabili a DFP?**

[!DNL Audience Manager] imposta 2 cookie: Uno invia variabili segmentate al tag di annunci DFP, mentre l&#39;altro imposta il nostro ID utente univoco (UUID), che viene letto anche tramite DFP. L&#39;aggiunta dell&#39;UUID al tag annunci significa che possiamo eseguire reporting a livello di utente e individuazione dell&#39;audience.

<br> 

**Posso inviare una informazione DSP su punti nel funnel di conversione raggiunto da un utente?**

Sì. Possiamo inviare dati funnel, ma il DSP deve avere la capacità tecnica di utilizzarla. Un DSP deve confermare che possono gestire più segmenti. Se non possono, potrebbe essere necessario creare segmenti specifici per estrarre un utente da altri segmenti in base all&#39;avanzamento della conversione (ad es., completare i passaggi 1 e 2 ma non il passaggio 3). Potresti voler inviare queste informazioni a una DSP in modo che possano reindirizzare gli utenti, indirizzarli a una pagina di destinazione specifica o visualizzare alcuni creativi specifici.

<br> 

**Come posso confermare che i dati inviati tramite FTP sono stati prelevati[!DNL Audience Manager]da?**

Un file è stato prelevato quando l&#39;estensione cambia da `.sync``.processed`. In tal caso, il file si trova nella coda di assimilazione. Inoltre, il manager commerciale può confermare quando un file è stato caricato.

<br> 

**Desidero testare le funzionalità dell&#39;API[DCS](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Sto inviando chiamate evento come quella mostrata di seguito. Le chiamate contengono[ID dichiarati](../features/declared-ids.md)e segnali, che devono realizzare alcune caratteristiche e segmenti già configurati. Posso usare[!UICONTROL General Reports]e[!UICONTROL Trend Reports]verificare se le caratteristiche delle caratteristiche e dei segmenti aumentano?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, non fai affidamento sull&#39; [!UICONTROL General Reports] e [!UICONTROL Trend Reports] in questo caso.

I rapporti calcolano le popolazioni in base ai record di profilo non autenticati (UUID) visualizzati nel backend al momento in cui i rapporti vengono generati.

In una prima chiamata agli [!UICONTROL DCS], gli ID dichiarati *non* sono collegati a UUID (i [cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex non sono presenti sul lato client). L&#39; [!UICONTROL DCS] UUID genera in modo casuale un UUID e imposta un [!DNL demdex] cookie e lo trasmette nella chiamata di risposta, ma non trasmetterà l&#39;UUID al backend.

>[!NOTE]
>
>L&#39;UUID generato verrà materializzato solo nell&#39;archivio dei dati di backend quando il dispositivo su cui viene impostato il cookie attiva ulteriori attività.

Per questo motivo, i report non riflettono gli eventi attivati dagli ID dichiarati nella chiamata. Consigliamo di utilizzare UUID, ECID (ex MID) o ID dispositivo mobili nelle chiamate di test dell&#39;evento a [!UICONTROL DCS]. Quindi, puoi verificare le caratteristiche di segmenti e segmenti nell&#39; [!UICONTROL General Reports][!UICONTROL Trend Reports]e in.

Vedi anche [Indice degli ID di Audience Manager](../reference/ids-in-aam.md).

<br> 

**Quanto tempo è necessario sincronizzare tra i profili[utente](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

In genere sono necessarie fino a 24 ore perché un profilo utente possa sincronizzarsi tra più aree. Tuttavia, in rari casi, il processo può richiedere fino a 48 ore.
