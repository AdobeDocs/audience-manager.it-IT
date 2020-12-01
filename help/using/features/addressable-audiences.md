---
description: Panoramica della funzione Pubblico di riferimento e dei casi di utilizzo.
keywords: DIL
seo-description: Panoramica della funzione Pubblico di riferimento e dei casi di utilizzo.
seo-title: Pubblico di riferimento
solution: Audience Manager
title: Pubblico di riferimento
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 0%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Panoramica della funzione [!UICONTROL Addressable Audience] e dei casi di utilizzo.

## Cos&#39;è un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La funzione [!UICONTROL Addressable Audiences] mostra la sovrapposizione tra le audience visualizzate in tutte le proprietà in cui [!DNL Audience Manager] raccoglie i dati e la destinazione selezionata. Per comprendere meglio questo concetto, osservate l&#39;illustrazione seguente. La sovrapposizione tra ciascun cerchio rappresenta i diversi tipi di pubblico indirizzabile.

![](assets/addressableAudienceVenn.png)


| Metrica | Descrizione |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] per  [!UICONTROL Destination] | Numero totale di dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che possono essere associati al [!UICONTROL destination] selezionato. <br><br>Questa metrica è utile perché mostra: <ul><li>La dimensione del totale [!UICONTROL addressable audience] che [!DNL Audience Manager] può raggiungere su un particolare targeting [!UICONTROL destination].</li><li>Dimensioni del pool di profili [!DNL Audience Manager] per una piattaforma di targeting e dimensioni del pubblico.</li></ul> |
| [!UICONTROL Customer Total Audience] | Numero di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] sulle proprietà o un [!UICONTROL onboarded trait] dai file offline durante la finestra di look-back. |
| [!UICONTROL Addressable Audience Match Rate] | Numero di sovrapposizioni di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la finestra di look-back e dispositivi per i quali è presente una sincronizzazione ID con il [!UICONTROL destination] selezionato, indipendentemente dal tempo di sincronizzazione.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la finestra di look-back `AND`</li><li>Sincronizzate l&#39;ID con la [!UICONTROL destination] selezionata, indipendentemente dal tempo di sincronizzazione.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] espressa in percentuale. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che appartenevano al [!UICONTROL segment] durante il periodo di look-back del report. |
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno fatto parte del [!UICONTROL segment] durante il periodo di look-back del report e che hanno una sincronizzazione ID attiva sul sito. [!UICONTROL Segments] può includere dati di prime parti e dati di seconda e terza parte, tramite  [!UICONTROL traits] acquisiti nel  [ Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a capire lo stato corrente del tuo  [!UICONTROL segments]. Questo perché la metrica [!UICONTROL Segment Addressable Audience] rappresenta gli utenti che hanno soggiornato in un [!UICONTROL segment] durante l&#39;intero giorno precedente. Combinate questo con il fatto che [!DNL Audience Manager] aggiorna [!UICONTROL Addressable Audiences] ogni giorno, combinando questa metrica e il periodo di lookback fornisce lo snapshot più aggiornato del [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] espressa in percentuale. |

## [!UICONTROL Addressable Audiences] Interfaccia {#addressable-audience-interface}

La funzione [!UICONTROL Addressable Audience] trasforma questo concetto astratto in dati quantificabili. In [!DNL Audience Manager], questa funzione visualizza la sovrapposizione dell&#39;audience con le visualizzazioni dati che forniscono informazioni a colpo d&#39;occhio insieme ai dati numerici in forma di tabella.

[!UICONTROL Addressable Audiences] si trova in  **[!UICONTROL Audience Data > Destinations]**. Seleziona **[!UICONTROL Integrated Platforms > Device-Based]** per visualizzare le metriche relative alle audience indirizzabili.

![](assets/addressable-audiences-landing.png)

Le tre metriche visualizzate sulla pagina di destinazione [!UICONTROL Addressable Audiences] rappresentano:

| Metrica | Descrizione |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Questa metrica rappresenta la [!UICONTROL Customer Addressable Audience] (descritta nella tabella precedente) *per gli ultimi 30 giorni.* |
| **[!UICONTROL Match Rate]** | Questa metrica rappresenta la [!UICONTROL Addressable Audience Match Rate] (descritta nella tabella precedente) *per gli ultimi 30 giorni*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Numero totale di dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che possono essere associati a questo [!UICONTROL destination]. Per ulteriori informazioni, vedere [Metriche a livello di piattaforma](/help/using/features/addressable-audiences.md#platform-level-metrics). |

Fare clic sul nome di un [!UICONTROL server-to-server destination] per visualizzare i dati del pubblico indirizzabile. Nota: questa funzione restituisce i dati solo per [!UICONTROL server-to-server destinations] e l&#39;accesso richiede le autorizzazioni dell&#39;amministratore.

![](assets/addressableAudiences.png)

La revisione di questi dati può essere utile per:

* **Previsione e pianificazione:** [!UICONTROL Segment Addressable Audience] i dati forniscono maggiore granularità nei segmenti che pianificate di inviare a una destinazione per il targeting e l&#39;attivazione dell&#39;audience.

* **Recensioni delle prestazioni:** La  [!UICONTROL Addressable Audiences] funzione è anche uno strumento per la risoluzione dei problemi. Consente di esaminare le prestazioni della campagna, comprendere il raggio d&#39;azione della campagna e di effettuare verifiche incrociate con i partner di targeting/attivazione se non vengono visualizzati i risultati previsti.

### Prospettiva con dati di terze parti e implicazioni per le percentuali di corrispondenza

Prima di acquistare dati di terze parti per l&#39;acquisizione di audience, i clienti possono convalidare la sovrapposizione con altri fornitori di dati. Questo può aiutarti a prendere una decisione informata prima di acquistare nuovi dati. Le sincronizzazioni ID per i dati di terze parti acquistati non si basano solo sulla sovrapposizione dei dati, ma anche sulle impronte dei fornitori di terze parti con tutti gli altri [!DNL Audience Manager] clienti. Il consulente [!DNL Adobe] può aiutarti a identificare ulteriori origini dati rilevanti per ottimizzare le campagne di ricerca.

### Utenti per dispositivi mobili e percentuali di corrispondenza

Esistono degli spazi vuoti quando si tenta di connettere [!DNL Safari] o gli utenti di app mobili in cui non sono presenti [!DNL cookies] di terze parti. Ciò rende difficile la sincronizzazione degli utenti con alcuni partner, perché solo gli [!DNL Adobe] ID per [!DNL cookies] di terze parti sincronizzate sono forniti nei registri di distribuzione dei supporti. Questo è un motivo per cui è possibile visualizzare [percentuali di corrispondenza basse](../features/addressable-audiences.md#low-match-rates) per il [!UICONTROL destinations].

## Intervalli di date in [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leggi le sezioni seguenti per gli intervalli di date disponibili e per sapere in che modo i dati si estendono oltre ogni intervallo nei report per un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalli di date e Fusi orari disponibili {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

I report per le [!UICONTROL Addressable Audiences] e [Destinations](../features/destinations/destinations.md) utilizzano gli stessi intervalli di date. Le opzioni dell&#39;intervallo di date includono:

* [!UICONTROL Last 1 Day] (Questo intervallo va da mezzanotte a mezzanotte del precedente periodo di 24 ore. Non si tratta di una metrica in tempo reale o corrente.
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Tutte le date e gli intervalli di date sono impostati nel fuso orario [!DNL UTC]. Vedere [Fusi orari in  Audience Manager](../reference/aam-time-zones.md).

## Dati negli intervalli di date {#date-range-intervals}

Le metriche [!UICONTROL Addressable Audience] e [!UICONTROL Destination] restituiscono un conteggio di utenti univoci per l&#39;intervallo di tempo selezionato. Ad esempio, un visitatore viene conteggiato una sola volta, anche se visita più volte il sito. La prima visita è la visita unica e viene registrata. Le visite successive sono visite di ritorno e non sono conteggiate perché non sono univoche.

Gli intervalli di date contengono i dati per l&#39;intervallo di tempo selezionato o per la versione precedente. Inoltre, i dati si estinguono a partire da ogni intervallo di rapporto non appena il tempo passa. Ad esempio, supponiamo di vedere 2 visitatori dopo aver scelto l&#39;opzione [!UICONTROL Last 30 Days]. Nei rapporti, questi visitatori:

* *Sarà* incluso nei risultati restituiti dagli intervalli di tempo più lunghi (60 giorni, 90 giorni e Durata).
* *Non verrà* incluso negli intervalli più brevi che precedono l&#39; [!UICONTROL Last 30 Day] opzione (Corrente, 7 giorni e 14 giorni).

E, il giorno 31, questi visitatori vengono visualizzati solo nei risultati di 60 giorni, 90 giorni e [!UICONTROL Lifetime]. Sono invecchiati rispetto all&#39;intervallo di 30 giorni. I visitatori non superano l&#39;intervallo [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] Metriche {#addressable-audience-metrics}

Questa sezione descrive i tipi di metriche forniti da [!UICONTROL Addressable Audiences].

### Metriche a livello di cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Queste metriche restituiscono i dati per le caratteristiche realizzate quando i visitatori arrivano sul tuo sito o quando invii file di dati in entrata a [!DNL Audience Manager]. Queste metriche forniscono una visualizzazione completa delle dimensioni dell&#39;audience per l&#39;account.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Conteggio di sovrapposizioni di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la finestra di look-back e dispositivi per i quali è presente una sincronizzazione ID con la destinazione scelta, indipendentemente dal tempo di sincronizzazione.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la finestra di look-back `AND`</li><li>Sincronizzate l&#39;ID con la [!UICONTROL destination] selezionata, indipendentemente dal tempo di sincronizzazione.</li></ul> |
| [!UICONTROL Customer Total Audience] | Numero di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] sulle proprietà o un [!UICONTROL onboarded trait] dai file offline durante la finestra di look-back. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] espressa in percentuale. |

### Metriche di corrispondenza a livello di segmento {#segment-level-metrics}

Queste metriche restituiscono i dati sull&#39;appartenenza a [!UICONTROL segment]. che consentono di ottenere una visualizzazione più granulare e accurata delle dimensioni del pubblico per ciascun [!UICONTROL segments].

>[!NOTE]
>
>Il modo in cui la finestra di look-back viene applicata a livello [!UICONTROL segment] è diverso da quello a livello di cliente. I visitatori possono visitare il sito e realizzare un [!UICONTROL trait] 10 giorni fa, e da allora potrebbero qualificarsi per un [!UICONTROL segment] e abbandonarlo dal [!UICONTROL segment] 2 giorni fa. Quando viene applicato l&#39;aspetto &quot;look-back&quot; di 7 giorni, questi visitatori saranno contati a livello di [!UICONTROL segment] ma non a livello di cliente.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno fatto parte del [!UICONTROL segment] durante il periodo di look-back del report e che hanno una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconda e terza parte, tramite [!UICONTROL traits] acquisiti nel Audience Marketplace [](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a capire lo stato corrente del tuo  [!UICONTROL segments]. Questo perché la metrica [!UICONTROL Segment Addressable Audience] rappresenta gli utenti che hanno soggiornato in un [!UICONTROL segment] durante l&#39;intero giorno precedente. Combinate questo con il fatto che [!DNL Audience Manager] aggiorna [!UICONTROL Addressable Audiences] ogni giorno, combinando questa metrica e il periodo di lookback fornisce lo snapshot più aggiornato del [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che appartenevano al [!UICONTROL segment] durante il periodo di look-back del report. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] espressa in percentuale. |

### Metriche a livello di piattaforma {#platform-level-metrics}

Questa metrica restituisce i dati sulle attività raccolte tra tutti i clienti [!DNL Audience Manager]. Possono fornire una visione più ampia del pubblico del cliente rispetto ai clienti [!DNL Audience Manager] aggregati.

| Metrica | Descrizione |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Numero totale di dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che possono essere associati al [!UICONTROL destination] selezionato. <br><br>Questa metrica è utile perché mostra:<ul><li>La dimensione della [!UICONTROL total addressable audience] che [!DNL Audience Manager] può raggiungere su una particolare destinazione di destinazione.</li><li>Dimensioni del pool di profili [!DNL Audience Manager] per una piattaforma di targeting e dimensioni del pubblico.</li></ul> |

## Confronto tra [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Non devi confrontare le metriche [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] per determinare se una è più significativa dell&#39;altra. Si tratta di metriche separate, diverse e indipendenti. Come descritto nelle definizioni di cui sopra, ciascuno di questi è derivato da set di dati diversi. Per questo motivo, è necessario evitare di trarre conclusioni se una metrica è più grande dell&#39;altra. Tutto quello che si può dire quando si confrontano questi è che:

* [!UICONTROL Customer Addressable Audiences] è basato sulle  [!UICONTROL trait] realizzazioni  *per i tuoi dati* di prime parti. Questa metrica fornisce una visione ampia e completa dell&#39;integrazione con un partner dati.

* [!UICONTROL Segment Addressable Audiences] si basa sulle qualifiche del segmento  *per i dati di prime parti, più i dati* di seconda e terza parte. Questa metrica fornisce una visualizzazione granulare e più accurata della [!UICONTROL addressable audiences] in una piattaforma di targeting.

## Cause di percentuali di corrispondenza basse per [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementi comuni responsabili di basse [!UICONTROL Addressable Audience] percentuali di corrispondenza o discrepanze nei numeri riportati.

| Causa | Descrizione |
|---|---|
| Traffico mobile | La maggior parte delle integrazioni [!UICONTROL server-to-server] si basa su processi di sincronizzazione facilitati da [!DNL cookies] di terze parti. Tuttavia, gli ambienti mobili non utilizzano [!DNL cookies] di terze parti. Di conseguenza, i numeri [!UICONTROL Addressable Audiences] potrebbero sembrare bassi rispetto alle dimensioni [!UICONTROL segment]. <br><br>A partire da gennaio 2018, potete attivare il pubblico mobile nelle stesse  [!DNL Google] e  [!DNL Adobe Advertising Cloud] destinazioni configurate per il  [!UICONTROL cookie-based] pubblico. Questo significa che è possibile inviare [!UICONTROL segments] con l&#39;iscrizione combinata [!DNL cookie] e l&#39;ID mobile alle destinazioni [!DNL Google] e [!DNL Advertising Cloud], ma tenere presente che [!UICONTROL Addressable Audiences] visualizza solo la sovrapposizione tra gli ID [!DNL cookie] e le destinazioni. [!DNL Audience Manager] invia il 100% del pubblico mobile a  [!UICONTROL destinations], ma il pubblico mobile non viene misurato dalla  [!UICONTROL Addressable Audience] metrica. <br><br>**Nota**: Ad esempio, prendete un esempio  [!UICONTROL segment] con una popolazione di 1.000.000 persone. Se mappate questo [!UICONTROL segment] su una [!DNL Google] o [!DNL Adobe Advertising Cloud] destinazione, potreste visualizzare un [!UICONTROL Addressable Audience] di 700.000 dispositivi e un [!UICONTROL Match Rate] del 70%. L&#39;iscrizione di 700.000 è composta da [!DNL cookie] ID con cui è sincronizzata l&#39;ID con [!UICONTROL destination]. In realtà, [!UICONTROL Addressable Audience] potrebbe essere molto più alto, perché gli ID mobili indirizzabili non vengono visualizzati in questa metrica. |
| [!DNL Safari] Traffico | [!DNL Safari] blocchi di terze parti  [!DNL cookies]. Ciò impedisce a [!DNL Audience Manager] di sincronizzare gli ID con [!UICONTROL destination]. Con l&#39;introduzione di [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), è possibile che [!UICONTROL addressable audiences] non includa gli utenti [!DNL Safari]. |
| Impression file multimediali tracciati | A causa delle procedure ottimali del server di annunci, le sincronizzazioni ID non vengono effettuate all’interno dei tag degli annunci. I clienti che fanno una grande quantità di pubblicità offsite non sincronizzeranno gli utenti con le integrazioni di terze parti in tali ambienti. Inoltre, una grande quantità di dati raccolti sull&#39;impression multimediale potrebbe ridurre i numeri [!UICONTROL addressable audience]. |

## Risoluzione dei problemi relativi a [!UICONTROL Addressable Audiences] {#troubleshooting}

Oltre a riportare le percentuali di corrispondenza, è anche possibile utilizzare [!UICONTROL Addressable Audiences] come strumento per la risoluzione dei problemi.

Ad esempio, supponiamo che tu invii un segmento a [!UICONTROL destination] e che [!UICONTROL destination] contenga numeri di reporting bassi. Selezionando i risultati di [!UICONTROL Addressable Audience] si verificherà se si tratta di un problema tecnico o se si tratta solo di un caso di percentuali di corrispondenza basse. Un tasso di corrispondenza basso indica che il [!UICONTROL destination] non è così ottimo per i segmenti selezionati. Tuttavia, una differenza nei numeri [!UICONTROL total addressable audience] tra [!DNL Audience Manager] e [!UICONTROL destination] indica un&#39;integrazione, una sincronizzazione o altri problemi tecnici. In questi casi, contatta il tuo account manager.
