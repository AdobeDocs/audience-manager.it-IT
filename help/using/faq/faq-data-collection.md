---
description: Domande e problemi comuni sulla raccolta e l’integrazione dei dati.
seo-description: Domande e problemi comuni sulla raccolta e l’integrazione dei dati.
seo-title: Domande frequenti sulla raccolta dei dati e l’integrazione dei prodotti
solution: Audience Manager
title: Domande frequenti sulla raccolta dei dati e l’integrazione dei prodotti
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
feature: Administration
translation-type: tm+mt
source-git-commit: a1e95f421b725cc93fbedc4c001e34e4291bf828
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 87%

---


# Domande frequenti sulla raccolta dei dati e l’integrazione dei prodotti {#data-collection-and-product-integration-faq}

Domande e problemi comuni sulla raccolta e l’integrazione dei dati.

<br> 

**Come posso distinguere il traffico in entrata dal traffico [!DNL DCS] nelle esportazioni di file di registro [!DNL DCS]?**

Le caratteristiche per cui è stato effettuato l’onboarding tramite [!UICONTROL Inbound] sono popolate da [!UICONTROL Inbound] nello stesso modo in cui vengono popolate da [!DNL DCS]. Ci sono alcuni modi diversi per capire che il traffico proveniva da [!UICONTROL Inbound]:

* L’IP remoto è impostato su 68.67.173.18
* DomainID è impostato su 5325
* L’area geografica è impostata su 0

<br> 

**Puoi fornirmi un elenco di indirizzi IP che posso aggiungere a un elenco consentiti  per dpm.demdex.net?**

Sfortunatamente non possiamo. Questi IP vengono assegnati in modo dinamico, per area geografica, attraverso [!DNL Amazon Web Services]. Di conseguenza, [!DNL Audience Manager] non controlla l’intervallo di IP che può essere assegnato a questo indirizzo.

 

**Puoi fornirmi un indirizzo IP che posso aggiungere a un elenco consentiti  per il tuo server SFTP in entrata e in uscita?**

Sì, vedi sotto.

| Server | Indirizzi IP |
| ---------|----------|
| ftp-in-gtw.demdex.com | 23.22.232.252; 18.211.109.184 |
| ftp-out-gtw.demdex.com | 3.233.68.222; 52.3.74.119 |

 

I server SFTP indicati di seguito sono obsoleti. Non verrà eseguito il provisioning di nuovi account utilizzando questi server.

| Server | Indirizzo IP |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**Come posso configurare la mia istanza  Audience Manager per l&#39;utilizzo dei nuovi server SFTP?**

Contatta il tuo [!DNL Audience Manager] consulente o l&#39;Assistenza clienti e questi configureranno i tuoi nuovi account SFTP.

 

**Qual è il metodo di autenticazione supportato per i nuovi server SFTP?**

I nuovi server (`ftp-in-gtw` e `ftp-out-gtw`) SFTP supportano [!DNL OpenSSH Key-Based Authentication]. Possiamo generare le [!DNL SSH] chiavi per voi, o potete fornirci la vostra chiave pubblica.

 

**Quali sono i requisiti di posizionamento del codice e di caricamento della pagina per un’integrazione tra [!UICONTROL DIL] e dati di [!DNL Analytics]?**

Per inserire i dati di [!DNL Analytics] in [!DNL Audience Manager], carica [!UICONTROL DIL] dopo il modulo `s_code`, ma *prima* della funzione `s.t()`. Ad esempio, inserisci il codice o assicurati che venga caricato nell’ordine seguente:

1. [!DNL Analytics] `s_code`

2. Modulo [!UICONTROL DIL] di [!DNL Audience Manager]

3. Funzione `s.t()` di [!DNL Analytics]

Come best practice, configura l’integrazione [!DNL Audience Manager]- [!DNL Analytics] con uno dei due metodi seguenti:

* Metti [!UICONTROL DIL] direttamente nel `s_code`.

* Distribuisci [!UICONTROL DIL] e `s_code` attraverso [!DNL Adobe Experience Platform Launch] o [!DNL Adobe DTM].

Consulta [Data Integration Library (DIL) API](../dil/dil-overview.md).

 

**Perché le mie variabili di [!DNL Analytics] non sono presenti in una chiamata evento di [!DNL Audience Manager]?**

Questo accade in genere quando:

* Distribuisci [!UICONTROL DIL] attraverso un sistema di gestione dei tag che lo carica in modo asincrono rispetto ad altri elementi di codice sulla pagina.
* La funzione `s.t()` viene caricata prima di [!UICONTROL DIL].

 

**Quali versioni di [!DNL Analytics] funzionano con [!UICONTROL DIL]?**

Devi utilizzare la versione 20.2 (o successiva) di [!DNL Analytics] e la versione 3.5.2 (o successiva) della libreria [!DNL Adobe AppMeasurement AS] per lavorare con [!UICONTROL DIL]. Se non conosci la tua versione di [!DNL Analytics] o [!DNL AppMeasurement], controlla la chiamata di [!DNL Analytics] che viene effettuata dalla pagina. Di seguito sono illustrate le informazioni sulle versioni:

Questo cliente utilizza la versione 24.4 di [!DNL Analytics]:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Questo cliente utilizza la versione 3.5.2 di [!DNL AppMeasurement]:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Posso raccogliere i dati della pagina se non sono un cliente di [!DNL Analytics] ?**

Sì. Il modulo [!UICONTROL DIL] ti consente di raccogliere i dati della pagina anche se non utilizzi [!DNL Analytics]. Una volta configurato correttamente, [!UICONTROL DIL] può acquisire dati da e su:

* Meta tag
* URL e intestazioni URL
* Tipi di motori di ricerca
* Parole chiave

Inoltre, i client possono distribuire un semplice oggetto interno al sito e popolarlo con coppie chiave-valore su cui desideri che [!UICONTROL DIL] raccolga i dati. Questo ti consente di aggiungere e rimuovere punti di dati di pubblico specifici sul sito senza alcun aggiornamento di [!DNL Audience Management]. Collabora con il tuo rappresentante di soluzioni dei partner per effettuare in maniera adeguata questa configurazione e assicurarti che il modulo [!DNL DIL] faccia riferimento correttamente all’oggetto della pagina.

<br> 

**[!UICONTROL DIL] può raccogliere dati da [!DNL Google Analytics]?**

Sì. [!UICONTROL DIL] può raccogliere alcuni elementi di [!DNL Google Analytics] (GA) e trasmettere tali dati a [!DNL Audience Manager]. Consulta:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Posso ottenere dati non elaborati da [!DNL Audience Manager]? E quanto sono granulari?**

Sì, [!DNL Audience Manager] può fornirti i dati raccolti per gli utenti che visti nel tuo inventario. Ciò include:

* L’ID utente univoco (UUID) assegnato da [!DNL Audience Manager]
* ID di caratteristiche e segmenti
* Segnali inutilizzati
* Marche temporali
* URL delle pagine

<br> 

**[!DNL Google Ad Manager]Desidero raccogliere i dati su un sito ed effettuare il targeting degli utenti tramite su un sito diverso. Devo distribuire codice sull’altra proprietà se non desidero raccogliere i dati da tale posizione?**

No. Se la raccolta dei dati sul secondo sito non è un requisito, non è necessario distribuire DIL lì. As long as you have access to the inventory on the second site via [!DNL Google Ad Manager], you can use the data collection from the initial site and target via [!DNL Google Ad Manager].

<br> 

**Qual è il miglior provider di dati di terze parti?**

Ogni provider offre qualcosa di unico, quindi la risposta dipende da cosa stai cercando. Possiamo abilitare la funzione di reporting di sovrapposizione (senza alcun costo) per aiutarti a capire quale provider potrebbe funzionare meglio per te.

<br> 

**In che modo [!DNL Audience Manager] imposta i cookie e trasmette le variabili a[!DNL Google Ad Manager]?**

[!DNL Audience Manager][!DNL Google Ad Manager] imposta 2 cookie: uno invia le variabili del segmento al tag dell’annuncio e l’altro imposta il nostro ID utente univoco (UUID), che viene letto anche da [!DNL Google Ad Manager]. L’aggiunta dell’UUID al tag dell’annuncio consente di effettuare reporting e individuare pubblico a livello di utente.

<br> 

**Posso inviare a una DSP informazioni sui punti nel funnel di conversione raggiunto da un utente?**

Sì. Possiamo inviare i dati del funnel, ma la DSP deve avere la capacità tecnica di utilizzarli. Una DSP deve confermare di poter gestire più segmenti. In caso contrario, potrebbe essere necessario creare segmenti specifici per estrarre un utente da altri segmenti in base al suo avanzamento di conversione (ad esempio, ha completato i passaggi 1 e 2 ma non il passaggio 3). Potrebbe essere utile inviare queste informazioni a una DSP in modo che possa effettuare il retargeting degli utenti, indirizzarli a una pagina di destinazione specifica o mostrare contenuti creativi specifici.

<br> 

**Come posso verificare che i dati inviati tramite FTP sono stati raccolti da [!DNL Audience Manager]?**

Un file è stato raccolto quando l’estensione cambia da `.sync` a `.processed`. Quando ciò succede, il file si trova nella coda di acquisizione. Inoltre, il tuo account manager può verificare quando un file è stato caricato.

<br> 

**Desidero testare la funzionalità dell’[API DCS](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Sto inviando chiamate evento come quella mostrata di seguito. Le chiamate contengono [ID dichiarati](../features/declared-ids.md) e segnali che dovrebbero realizzare alcune caratteristiche e alcuni segmenti che ho già configurato. Posso usare i [!UICONTROL General Reports] e [!UICONTROL Trend Reports] per verificare se le popolazioni di caratteristiche e segmenti stanno aumentando?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, in questo caso non fare affidamento sui [!UICONTROL General Reports] e [!UICONTROL Trend Reports].

I report calcolano le popolazioni in base ai record di profilo non autenticati (UUID) visualizzati nel back-end al momento della generazione dei report.

In una prima chiamata al [!DNL DCS], gli ID dichiarati *non* sono collegati ad alcun UUID (ovvero, nessun [cookie demdex](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) è presente sul lato client). Il [!DNL DCS] genera un UUID in modo casuale, imposta un cookie [!DNL demdex] e lo trasmette nella chiamata di risposta, ma non trasmette l’UUID al back-end.

>[!NOTE]
>
>L’UUID generato verrà materializzato nell’archiviazione di dati del nostro back-end dopo che il dispositivo su cui è impostato il cookie attiverà un’ulteriore attività.

Per questo motivo, i report non riflettono gli eventi attivati dagli ID dichiarati nella chiamata. È consigliabile utilizzare UUID, ECID (precedentemente MID) o ID di dispositivo mobili nelle chiamate di test evento al [!DNL DCS]. Poi, puoi verificare le realizzazioni di caratteristiche e segmenti nei [!UICONTROL General Reports] e nei [!UICONTROL Trend Reports].

Consulta anche [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**Quanto tempo è necessario per la sincronizzazione dei profili utente tra [aree geografiche](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

In genere, la sincronizzazione di un profilo utente tra aree geografiche richiede fino a 24 ore. Tuttavia, in rari casi, il processo può richiedere fino a 48 ore.
