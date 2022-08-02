---
description: Panoramica della funzione Pubblico di riferimento e dei casi d’uso.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Pubblico di riferimento
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Panoramica della [!UICONTROL Addressable Audience] casi di utilizzo e funzionalità.

## Cosa è un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] mostra la sovrapposizione tra i tipi di pubblico visualizzati in tutte le proprietà in cui [!DNL Audience Manager] raccoglie i dati e la destinazione selezionata. Per comprendere meglio questo concetto, consulta l’illustrazione seguente. La sovrapposizione tra ciascun cerchio rappresenta i diversi tipi di pubblico indirizzabili.

![](assets/addressableAudienceVenn.png)


| Metrica | Descrizione |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] per [!UICONTROL Destination] | Un conteggio di tutti i dispositivi che hanno interagito con tutti [!DNL Audience Manager] clienti a livello di piattaforma durante il periodo di look-back del report e che potrebbe essere abbinato al [!UICONTROL destination]. <br><br>Questa metrica è utile perché mostra quanto segue: <ul><li>Dimensione del totale [!UICONTROL addressable audience] che [!DNL Audience Manager] può raggiungere un determinato targeting [!UICONTROL destination].</li><li>Quanto grande è il [!DNL Audience Manager] il pool di profili è per una piattaforma di targeting e le dimensioni del pubblico.</li></ul> |
| [!UICONTROL Customer Total Audience] | Numero di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] sulle proprietà o [!UICONTROL onboarded trait] dai file offline durante la finestra di look-back. |
| [!UICONTROL Customer Addressable Audience] | Numero di sovrapposizioni di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o [!UICONTROL onboarded trait] durante la finestra di look-back e i dispositivi per i quali è stata effettuata una sincronizzazione ID con il [!UICONTROL destination] indipendentemente dal momento delle sincronizzazioni.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato [!UICONTROL rule-based] o [!UICONTROL onboarded trait] durante la finestra di look-back `AND`</li><li>Sincronizza ID con il [!UICONTROL destination] indipendentemente dal momento delle sincronizzazioni.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] espresso in percentuale. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che facevano parte del tuo [!UICONTROL segment] durante il periodo di look-back del rapporto. |
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno fatto parte del [!UICONTROL segment] durante il periodo di look-back del report e dispongono di una sincronizzazione ID attiva sul sito. [!UICONTROL Segments] può includere dati di prime parti e dati di seconde e terze parti, tramite [!UICONTROL traits] acquisiti nel [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a capire lo stato corrente del tuo [!UICONTROL segments]. Questo perché il [!UICONTROL Segment Addressable Audience] rappresenta gli utenti rimasti in un [!UICONTROL segment] per tutto il giorno precedente. Combinare questo con il fatto che [!DNL Audience Manager] rinfresco [!UICONTROL Addressable Audiences] la combinazione giornaliera di questa metrica e del periodo di lookback fornisce lo snapshot più aggiornato del [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] espresso in percentuale. |

## [!UICONTROL Addressable Audiences] Interfaccia {#addressable-audience-interface}

La [!UICONTROL Addressable Audience] questa funzione trasforma questo concetto astratto in dati quantificabili. In [!DNL Audience Manager], questa funzione visualizza la sovrapposizione del pubblico con le visualizzazioni dati che forniscono informazioni a colpo d&#39;occhio insieme ai dati numerici in forma di tabella.

[!UICONTROL Addressable Audiences] si trova in **[!UICONTROL Audience Data > Destinations]**. Seleziona **[!UICONTROL Integrated Platforms > Device-Based]** per visualizzare le metriche dei tipi di pubblico utilizzabili.

![](assets/addressable-audiences-landing.png)

Le tre metriche che puoi visualizzare nel [!UICONTROL Addressable Audiences] la pagina di destinazione rappresenta:

| Metrica | Descrizione |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Questa metrica rappresenta [!UICONTROL Customer Addressable Audience] (descritto nella tabella precedente) *negli ultimi 30 giorni.* |
| **[!UICONTROL Match Rate]** | Questa metrica rappresenta [!UICONTROL Addressable Audience Match Rate] (descritto nella tabella precedente) *per gli ultimi 30 giorni*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Un conteggio di tutti i dispositivi che hanno interagito con tutti [!DNL Audience Manager] clienti a livello di piattaforma durante il periodo di look-back del report che potrebbe essere abbinato a questo [!UICONTROL destination]. Vedi [Metriche a livello di piattaforma](/help/using/features/addressable-audiences.md#platform-level-metrics) per ulteriori informazioni. |

Fai clic sul nome di un [!UICONTROL server-to-server destination] per visualizzare i dati del pubblico di destinazione. Nota: questa funzione restituisce i dati per [!UICONTROL server-to-server destinations] Solo e l&#39;accesso richiede le autorizzazioni di amministratore.

![](assets/addressableAudiences.png)

La revisione di questi dati può aiutarti con:

* **Previsione e pianificazione:** [!UICONTROL Segment Addressable Audience] i dati ti forniscono una maggiore granularità nei segmenti che intendi inviare a una destinazione per il targeting e l’attivazione del pubblico.

* **Recensioni delle prestazioni:** La [!UICONTROL Addressable Audiences] è anche uno strumento per la risoluzione dei problemi. Ti consente di rivedere le prestazioni della campagna, capire la portata della campagna e di effettuare verifiche incrociate con i partner di targeting/attivazione se non vedi i risultati previsti.

### Prospettiva con dati di terze parti e implicazioni per le percentuali di corrispondenza

Prima di acquistare dati di terze parti per l’acquisizione di audience, i clienti possono convalidare la sovrapposizione con altri fornitori di dati. Questo può aiutarti a prendere una decisione informata prima di acquistare nuovi dati. Le sincronizzazioni ID per i dati di terze parti acquistati non si basano solo sulla sovrapposizione dei tuoi dati ma anche sulle impronte dei fornitori di terze parti con tutti gli altri [!DNL Audience Manager] clienti. Le [!DNL Adobe] consulente può aiutarti a identificare altre origini dati rilevanti per ottimizzare le campagne di ricerca.

### Utenti e percentuali di corrispondenza

Ci sono lacune quando si tenta di connettersi [!DNL Safari] o agli utenti di app mobili in cui non sono presenti terze parti [!DNL cookies] presente. Questo rende difficile sincronizzare gli utenti con alcuni partner perché solo quelli [!DNL Adobe] ID per terze parti sincronizzate [!DNL cookies] sono forniti nei registri di consegna dei contenuti multimediali. Questo è un motivo per cui potresti vedere [bassi tassi di corrispondenza](../features/addressable-audiences.md#low-match-rates) per [!UICONTROL destinations].

## Intervalli di date in [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leggi le sezioni seguenti per gli intervalli di date disponibili e come i dati scadono a partire da ogni intervallo nei rapporti per un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalli di date e fusi orari disponibili {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Rapporti per [!UICONTROL Addressable Audiences] e [Destinazioni](../features/destinations/destinations.md) utilizza gli stessi intervalli di date. Le opzioni dell’intervallo di date includono:

* [!UICONTROL Last 1 Day] (Questo intervallo va da mezzanotte a mezzanotte del precedente periodo di 24 ore. Non è una metrica in tempo reale o corrente.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Tutte le date e gli intervalli di date sono impostati nella variabile [!DNL UTC] fuso orario. Vedi [Fusi orari in Audience Manager](../reference/aam-time-zones.md).

## Dati in intervalli di date {#date-range-intervals}

La [!UICONTROL Addressable Audience] e [!UICONTROL Destination] le metriche restituiscono un conteggio di utenti univoci per l’intervallo di tempo selezionato. Ad esempio, un visitatore viene conteggiato una sola volta, anche se visita il sito più volte. La prima visita è la visita unica e viene registrata. Le visite successive sono visite di ritorno e non vengono conteggiate perché non sono univoche.

Gli intervalli di date contengono dati per l&#39;intervallo di tempo selezionato o per la versione precedente. Inoltre, i dati scadono a ogni intervallo di rapporto con il passare del tempo. Ad esempio, supponiamo che tu veda 2 visitatori dopo aver scelto il [!UICONTROL Last 30 Days] opzione . Nei rapporti, i seguenti visitatori:

* *Sarà* inclusi nei risultati restituiti da intervalli di tempo più lunghi (60 giorni, 90 giorni e ciclo di vita).
* *Non sarà* inclusi negli intervalli più brevi che precedono il [!UICONTROL Last 30 Day] (Corrente, 7 giorni e 14 giorni).

E, il giorno 31, questi visitatori compaiono solo nei 60 giorni, 90 giorni, e [!UICONTROL Lifetime] risultati. Sono invecchiati su un intervallo di 30 giorni. I visitatori non invecchiano [!UICONTROL Lifetime] intervallo.

## [!UICONTROL Addressable Audiences] Metriche {#addressable-audience-metrics}

Questa sezione descrive i tipi di metriche forniti da [!UICONTROL Addressable Audiences].

### Metriche a livello di cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Queste metriche restituiscono i dati per le caratteristiche realizzate quando i visitatori accedono al tuo sito o quando invii file di dati in entrata a [!DNL Audience Manager]. Queste metriche forniscono una visualizzazione completa delle dimensioni del pubblico per il tuo account.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Numero di sovrapposizioni di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o [!UICONTROL onboarded trait] durante la finestra di look-back e i dispositivi per i quali è presente una sincronizzazione ID con la destinazione selezionata, indipendentemente dal momento della sincronizzazione.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato [!UICONTROL rule-based] o [!UICONTROL onboarded trait] durante la finestra di look-back `AND`</li><li>Sincronizza ID con il [!UICONTROL destination] indipendentemente dal momento delle sincronizzazioni.</li></ul> |
| [!UICONTROL Customer Total Audience] | Numero di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] sulle proprietà o [!UICONTROL onboarded trait] dai file offline durante la finestra di look-back. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] espresso in percentuale. |

### Metriche di corrispondenza a livello di segmento {#segment-level-metrics}

Queste metriche restituiscono i dati su [!UICONTROL segment] iscrizione. che forniscono una visualizzazione più granulare e precisa delle dimensioni del pubblico per ciascuno dei [!UICONTROL segments].

>[!NOTE]
>
>Modalità di applicazione dell&#39;intervallo di look-back al [!UICONTROL segment] livello è diverso da quello a livello di cliente. I visitatori possono visitare il sito e realizzare un [!UICONTROL trait] 10 giorni fa, e potevano qualificarsi per un [!UICONTROL segment] da allora, abbandonando [!UICONTROL segment] 2 giorni fa. Quando viene applicato lo sguardo di 7 giorni, questi visitatori vengono conteggiati nella [!UICONTROL segment] livello ma non a livello di cliente.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno fatto parte del [!UICONTROL segment] durante il periodo di look-back del report e dispongono di una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconde e terze parti tramite [!UICONTROL traits] acquisiti nel [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a capire lo stato corrente del tuo [!UICONTROL segments]. Questo perché il [!UICONTROL Segment Addressable Audience] rappresenta gli utenti rimasti in un [!UICONTROL segment] per tutto il giorno precedente. Combinare questo con il fatto che [!DNL Audience Manager] rinfresco [!UICONTROL Addressable Audiences] la combinazione giornaliera di questa metrica e del periodo di lookback fornisce lo snapshot più aggiornato del [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che facevano parte del tuo [!UICONTROL segment] durante il periodo di look-back del rapporto. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] espresso in percentuale. |

### Metriche a livello di piattaforma {#platform-level-metrics}

Questa metrica restituisce i dati sulle attività raccolte in tutti [!DNL Audience Manager] clienti. Possono fornire una visione più ampia del pubblico del cliente rispetto all&#39;aggregato [!DNL Audience Manager] clienti.

| Metrica | Descrizione |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Un conteggio di tutti i dispositivi che hanno interagito con tutti [!DNL Audience Manager] clienti a livello di piattaforma durante il periodo di look-back del report e che potrebbe essere abbinato al [!UICONTROL destination]. <br><br>Questa metrica è utile perché mostra quanto segue:<ul><li>La dimensione del [!UICONTROL total addressable audience] che [!DNL Audience Manager] può raggiungere una particolare destinazione di targeting.</li><li>Quanto grande è il [!DNL Audience Manager] il pool di profili è per una piattaforma di targeting e le dimensioni del pubblico.</li></ul> |

## Confronto [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Non devi confrontare le [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] per determinare se uno è più significativo dell’altro. Si tratta di metriche separate, diverse e indipendenti. Come descritto nelle definizioni di cui sopra, ognuna di esse deriva da diversi set di dati. Per questo motivo, evita di trarre conclusioni se una metrica è più grande dell’altra. Tutto quello che si può dire quando si confrontano questi dati è che:

* [!UICONTROL Customer Addressable Audiences] è basato su [!UICONTROL trait] realizzazioni *dati di prime parti personalizzati*. Questa metrica offre una visione ampia e completa dell’integrazione con un partner dati.

* [!UICONTROL Segment Addressable Audiences] si basa sulle qualifiche dei segmenti *per i tuoi dati di prime parti, più dati di seconde e terze parti*. Questa metrica fornisce una visualizzazione granulare e più precisa del tuo [!UICONTROL addressable audiences] in una piattaforma di targeting.

## Cause di bassi tassi di corrispondenza per [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementi comuni responsabili del basso [!UICONTROL Addressable Audience] percentuali di corrispondenza o discrepanze nei numeri segnalati.

| Causa | Descrizione |
|---|---|
| Traffico mobile | Più [!UICONTROL server-to-server] le integrazioni si basano su processi di sincronizzazione facilitati da terze parti [!DNL cookies]. Tuttavia, gli ambienti mobili non utilizzano terze parti [!DNL cookies]. Di conseguenza, il [!UICONTROL Addressable Audiences] i numeri possono sembrare bassi rispetto a [!UICONTROL segment] dimensioni. <br><br>A partire da gennaio 2018, puoi attivare i tipi di pubblico per dispositivi mobili nella stessa posizione [!DNL Google] e [!DNL Adobe Advertising Cloud] destinazioni impostate per [!UICONTROL cookie-based] pubblico. Ciò significa che puoi inviare [!UICONTROL segments] con combinazione [!DNL cookie] e l&#39;iscrizione all&#39;ID mobile [!DNL Google] e [!DNL Advertising Cloud] destinazioni, tieni presente che [!UICONTROL Addressable Audiences] visualizza solo la sovrapposizione tra [!DNL cookie] ID e destinazioni. [!DNL Audience Manager] invia il 100% del pubblico di dispositivi mobili a [!UICONTROL destinations], ma il pubblico mobile non viene misurato dalla [!UICONTROL Addressable Audience] metrica. <br><br>**Nota**: Ad esempio, [!UICONTROL segment] con una popolazione di 1.000.000 abitanti. Se mappi questo [!UICONTROL segment] a [!DNL Google] o [!DNL Adobe Advertising Cloud] destinazione, potresti visualizzare un [!UICONTROL Addressable Audience] di 700.000 dispositivi e [!UICONTROL Match Rate] del 70%. L&#39;adesione di 700.000 consiste in [!DNL cookie] ID con sincronizzazione ID con [!UICONTROL destination]. Le [!UICONTROL Addressable Audience] potrebbe, in realtà, essere molto più alto, perché gli ID mobile indirizzabili non compaiono in questa metrica. |
| [!DNL Safari] Traffico | [!DNL Safari] blocca terze parti [!DNL cookies]. Questo impedisce [!DNL Audience Manager] dalla sincronizzazione degli ID con [!UICONTROL destination]. Con l&#39;introduzione di [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), puoi aspettarti [!UICONTROL addressable audiences] non includere [!DNL Safari] utenti. |
| Impression contenuti multimediali tracciati | A causa delle best practice per il server di annunci, le sincronizzazioni ID non vengono effettuate all’interno dei tag degli annunci. I clienti che fanno una grande quantità di pubblicità offsite non sincronizzeranno gli utenti con le integrazioni di terze parti in quegli ambienti. Inoltre, una grande quantità di dati raccolti sulle impression dei supporti potrebbe ridurre [!UICONTROL addressable audience] numeri. |

## Risoluzione dei problemi con [!UICONTROL Addressable Audiences] {#troubleshooting}

Oltre a visualizzare le percentuali di corrispondenza, puoi anche utilizzare [!UICONTROL Addressable Audiences] come strumento di risoluzione dei problemi.

Ad esempio, supponiamo che tu invii un segmento a un [!UICONTROL destination] e [!UICONTROL destination] mostra numeri di reporting bassi. Controllo della [!UICONTROL Addressable Audience] i risultati ti mostreranno se si tratta di un problema tecnico o solo di un caso di percentuali di corrispondenza basse. Un tasso di corrispondenza basso mostra il tuo [!UICONTROL destination] non è grandioso per i segmenti selezionati. Tuttavia, una differenza nel [!UICONTROL total addressable audience] numeri tra [!DNL Audience Manager] e [!UICONTROL destination] indica un problema di integrazione, sincronizzazione o altro problema tecnico. In questi casi, contatta il tuo account manager.
