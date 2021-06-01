---
description: Panoramica della funzione Pubblico di riferimento e dei casi d’uso.
keywords: DIL
seo-description: Panoramica della funzione Pubblico di riferimento e dei casi d’uso.
seo-title: Pubblico di riferimento
solution: Audience Manager
title: Pubblico di riferimento
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Percentuali di corrispondenza
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Panoramica della funzione [!UICONTROL Addressable Audience] e dei casi d’uso.

## Cos&#39;è un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La funzione [!UICONTROL Addressable Audiences] mostra la sovrapposizione tra i tipi di pubblico visualizzati in tutte le proprietà in cui [!DNL Audience Manager] raccoglie i dati e la destinazione selezionata. Per comprendere meglio questo concetto, consulta l’illustrazione seguente. La sovrapposizione tra ciascun cerchio rappresenta i diversi tipi di pubblico indirizzabili.

![](assets/addressableAudienceVenn.png)


| Metrica | Descrizione |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] per  [!UICONTROL Destination] | Un conteggio di tutti i dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che possono essere associati al [!UICONTROL destination] scelto. <br><br>Questa metrica è utile perché mostra quanto segue: <ul><li>Dimensione del totale [!UICONTROL addressable audience] che [!DNL Audience Manager] può raggiungere su un determinato targeting [!UICONTROL destination].</li><li>Dimensioni del pool di profili [!DNL Audience Manager] per una piattaforma di targeting e dimensioni del pubblico.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un conteggio dei dispositivi che hanno realizzato un [!UICONTROL rule-based trait] sulle proprietà o un [!UICONTROL onboarded trait] dai file offline durante l&#39;intervallo di look-back. |
| [!UICONTROL Addressable Audience Match Rate] | Numero di sovrapposizioni di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante l&#39;intervallo di look-back e dispositivi per i quali è stata effettuata una sincronizzazione ID con il [!UICONTROL destination] scelto, indipendentemente dal momento in cui vengono sincronizzate.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante l&#39;intervallo di look-back `AND`</li><li>Disporre di una sincronizzazione ID con il [!UICONTROL destination] scelto, indipendentemente dal momento della sincronizzazione.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷  [!UICONTROL Customer Total Audience] espressa in percentuale. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che facevano parte del [!UICONTROL segment] durante il periodo di look-back del report. |
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno fatto parte del [!UICONTROL segment] durante il periodo di look-back del report e hanno una sincronizzazione ID attiva sul sito. [!UICONTROL Segments] può includere dati di prime parti e dati di seconde e terze parti, tramite  [!UICONTROL traits] acquisiti nell’ [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a capire lo stato corrente del tuo  [!UICONTROL segments]. Questo perché la metrica [!UICONTROL Segment Addressable Audience] rappresenta gli utenti che hanno soggiornato in un [!UICONTROL segment] durante il giorno precedente. Combinare questo con il fatto che [!DNL Audience Manager] aggiorna [!UICONTROL Addressable Audiences] ogni giorno, combinando questa metrica e il periodo di lookback fornisce lo snapshot più aggiornato del [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷  [!UICONTROL Total Segment Population] espressa in percentuale. |

## [!UICONTROL Addressable Audiences] Interfaccia {#addressable-audience-interface}

La funzione [!UICONTROL Addressable Audience] trasforma questo concetto astratto in dati quantificabili. In [!DNL Audience Manager], questa funzione visualizza la sovrapposizione del pubblico con le visualizzazioni dei dati che forniscono informazioni a colpo d&#39;occhio insieme ai dati numerici in forma di tabella.

[!UICONTROL Addressable Audiences] si trova in  **[!UICONTROL Audience Data > Destinations]**. Seleziona **[!UICONTROL Integrated Platforms > Device-Based]** per visualizzare le metriche dei tipi di pubblico utilizzabili.

![](assets/addressable-audiences-landing.png)

Le tre metriche che puoi visualizzare nella pagina di destinazione [!UICONTROL Addressable Audiences] rappresentano:

| Metrica | Descrizione |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Questa metrica rappresenta la [!UICONTROL Customer Addressable Audience] (descritta nella tabella precedente) *per gli ultimi 30 giorni.* |
| **[!UICONTROL Match Rate]** | Questa metrica rappresenta la [!UICONTROL Addressable Audience Match Rate] (descritta nella tabella precedente) *per gli ultimi 30 giorni*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Numero di dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che possono essere associati a questo [!UICONTROL destination]. Per ulteriori informazioni, consulta [Metriche a livello di piattaforma](/help/using/features/addressable-audiences.md#platform-level-metrics) . |

Fai clic sul nome di un [!UICONTROL server-to-server destination] per visualizzare i dati del pubblico di destinazione. Nota: questa funzione restituisce i dati solo per [!UICONTROL server-to-server destinations] e l&#39;accesso richiede le autorizzazioni di amministratore.

![](assets/addressableAudiences.png)

La revisione di questi dati può aiutarti con:

* **Previsione e pianificazione:** [!UICONTROL Segment Addressable Audience] i dati ti forniscono maggiore granularità nei segmenti che intendi inviare a una destinazione per il targeting e l’attivazione del pubblico.

* **Recensioni delle prestazioni:** la  [!UICONTROL Addressable Audiences] funzione è anche uno strumento per la risoluzione dei problemi. Ti consente di rivedere le prestazioni della campagna, capire la portata della campagna e di effettuare verifiche incrociate con i partner di targeting/attivazione se non vedi i risultati previsti.

### Prospettiva con dati di terze parti e implicazioni per le percentuali di corrispondenza

Prima di acquistare dati di terze parti per l’acquisizione di audience, i clienti possono convalidare la sovrapposizione con altri fornitori di dati. Questo può aiutarti a prendere una decisione informata prima di acquistare nuovi dati. Le sincronizzazioni ID per i dati di terze parti acquistati non si basano solo sulla sovrapposizione dei tuoi dati ma anche sulle impronte dei fornitori di terze parti con tutti gli altri clienti [!DNL Audience Manager]. Il tuo consulente [!DNL Adobe] può aiutarti a identificare altre sorgenti di dati rilevanti per ottimizzare le campagne di ricerca.

### Utenti e percentuali di corrispondenza

Ci sono lacune quando si tenta di collegare [!DNL Safari] o gli utenti di app mobili in cui non sono presenti [!DNL cookies] di terze parti. Questo rende difficile la sincronizzazione degli utenti con alcuni partner perché solo gli [!DNL Adobe] ID per le terze parti sincronizzate [!DNL cookies] sono forniti nei registri di consegna dei contenuti multimediali. Questo è un motivo per cui potresti vedere [percentuali di corrispondenza basse](../features/addressable-audiences.md#low-match-rates) per il tuo [!UICONTROL destinations].

## Intervalli di date in [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leggi le sezioni seguenti per gli intervalli di date disponibili e come i dati scadono a partire da ogni intervallo nei rapporti per un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalli di date e fusi orari disponibili {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

I rapporti per le [!UICONTROL Addressable Audiences] e [Destinazioni](../features/destinations/destinations.md) utilizzano gli stessi intervalli di date. Le opzioni dell’intervallo di date includono:

* [!UICONTROL Last 1 Day] (Questo intervallo va da mezzanotte a mezzanotte del precedente periodo di 24 ore. Non è una metrica in tempo reale o corrente.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Tutte le date e gli intervalli di date sono impostati nel fuso orario [!DNL UTC]. Vedere [Fusi orari in Audience Manager](../reference/aam-time-zones.md).

## Dati in intervalli di date {#date-range-intervals}

Le metriche [!UICONTROL Addressable Audience] e [!UICONTROL Destination] restituiscono un conteggio di utenti univoci per l’intervallo di tempo selezionato. Ad esempio, un visitatore viene conteggiato una sola volta, anche se visita il sito più volte. La prima visita è la visita unica e viene registrata. Le visite successive sono visite di ritorno e non vengono conteggiate perché non sono univoche.

Gli intervalli di date contengono dati per l&#39;intervallo di tempo selezionato o per la versione precedente. Inoltre, i dati scadono a ogni intervallo di rapporto con il passare del tempo. Ad esempio, supponiamo che dopo aver scelto l’opzione [!UICONTROL Last 30 Days] vengano visualizzati 2 visitatori. Nei rapporti, i seguenti visitatori:

* *Sarà* incluso nei risultati restituiti da intervalli di tempo più lunghi (60 giorni, 90 giorni e ciclo di vita).
* *Non viene* incluso negli intervalli più brevi che precedono l’ [!UICONTROL Last 30 Day] opzione (Corrente, 7 giorni e 14 giorni).

E, il giorno 31, questi visitatori compaiono solo nei risultati di 60 giorni, 90 giorni e [!UICONTROL Lifetime]. Sono invecchiati su un intervallo di 30 giorni. I visitatori non scadono nell&#39;intervallo [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] Metriche {#addressable-audience-metrics}

Questa sezione descrive i tipi di metriche forniti da [!UICONTROL Addressable Audiences].

### Metriche a livello di cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Queste metriche restituiscono i dati per le caratteristiche realizzate quando i visitatori accedono al tuo sito o quando invii file di dati in entrata a [!DNL Audience Manager]. Queste metriche forniscono una visualizzazione completa delle dimensioni del pubblico per il tuo account.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Un conteggio di sovrapposizione di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante l&#39;intervallo di look-back e dispositivi per i quali è presente una sincronizzazione ID con la destinazione selezionata, indipendentemente dal momento di sincronizzazione.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante l&#39;intervallo di look-back `AND`</li><li>Disporre di una sincronizzazione ID con il [!UICONTROL destination] scelto, indipendentemente dal momento della sincronizzazione.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un conteggio dei dispositivi che hanno realizzato un [!UICONTROL rule-based trait] sulle proprietà o un [!UICONTROL onboarded trait] dai file offline durante l&#39;intervallo di look-back. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷  [!UICONTROL Customer Total Audience] espressa in percentuale. |

### Metriche di corrispondenza a livello di segmento {#segment-level-metrics}

Queste metriche restituiscono i dati sull&#39;appartenenza a [!UICONTROL segment]. che forniscono una visualizzazione più granulare e precisa delle dimensioni del pubblico per ciascuno dei [!UICONTROL segments].

>[!NOTE]
>
>Il modo in cui l’intervallo di look-back viene applicato a livello di [!UICONTROL segment] è diverso da quello a livello di cliente. I visitatori possono visitare il sito e realizzare un [!UICONTROL trait] 10 giorni fa, e da allora si sono qualificati per un [!UICONTROL segment] e sono usciti dal [!UICONTROL segment] 2 giorni fa. Quando viene applicato il look-back di 7 giorni, questi visitatori verranno conteggiati a livello di [!UICONTROL segment] ma non a livello di cliente.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno fatto parte del [!UICONTROL segment] durante il periodo di look-back del report e hanno una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconde e terze parti tramite [!UICONTROL traits] acquisiti in [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a capire lo stato corrente del tuo  [!UICONTROL segments]. Questo perché la metrica [!UICONTROL Segment Addressable Audience] rappresenta gli utenti che hanno soggiornato in un [!UICONTROL segment] durante il giorno precedente. Combinare questo con il fatto che [!DNL Audience Manager] aggiorna [!UICONTROL Addressable Audiences] ogni giorno, combinando questa metrica e il periodo di lookback fornisce lo snapshot più aggiornato del [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che facevano parte del [!UICONTROL segment] durante il periodo di look-back del report. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷  [!UICONTROL Total Segment Population] espressa in percentuale. |

### Metriche a livello di piattaforma {#platform-level-metrics}

Questa metrica restituisce i dati sulle attività raccolte tra tutti i clienti [!DNL Audience Manager]. Possono fornire una visione più ampia del pubblico del cliente rispetto ai clienti aggregati [!DNL Audience Manager].

| Metrica | Descrizione |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Un conteggio di tutti i dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che possono essere associati al [!UICONTROL destination] scelto. <br><br>Questa metrica è utile perché mostra quanto segue:<ul><li>Dimensione del [!UICONTROL total addressable audience] che [!DNL Audience Manager] può raggiungere su una particolare destinazione di targeting.</li><li>Dimensioni del pool di profili [!DNL Audience Manager] per una piattaforma di targeting e dimensioni del pubblico.</li></ul> |

## Confronto tra [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Non devi confrontare le metriche [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] per determinare se una è più significativa dell&#39;altra. Si tratta di metriche separate, diverse e indipendenti. Come descritto nelle definizioni di cui sopra, ognuna di esse deriva da diversi set di dati. Per questo motivo, evita di trarre conclusioni se una metrica è più grande dell’altra. Tutto quello che si può dire quando si confrontano questi dati è che:

* [!UICONTROL Customer Addressable Audiences] è basato sulle  [!UICONTROL trait] realizzazioni  *per i tuoi dati* di prime parti. Questa metrica offre una visione ampia e completa dell’integrazione con un partner dati.

* [!UICONTROL Segment Addressable Audiences] si basa sulle qualifiche dei segmenti  *per i tuoi dati di prime parti, oltre ai dati* di seconde e terze parti. Questa metrica fornisce una visualizzazione granulare e più precisa del tuo [!UICONTROL addressable audiences] in una piattaforma di targeting.

## Cause di percentuali di corrispondenza basse per [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementi comuni responsabili di percentuali di corrispondenza basse [!UICONTROL Addressable Audience] o discrepanze nei numeri riportati.

| Causa | Descrizione |
|---|---|
| Traffico mobile | La maggior parte delle integrazioni [!UICONTROL server-to-server] si basa su processi di sincronizzazione facilitati da terze parti [!DNL cookies]. Tuttavia, gli ambienti mobili non utilizzano [!DNL cookies] di terze parti. Di conseguenza, i numeri [!UICONTROL Addressable Audiences] possono sembrare bassi rispetto alle dimensioni [!UICONTROL segment]. <br><br>A partire da gennaio 2018, puoi attivare il pubblico mobile nelle stesse  [!DNL Google] e  [!DNL Adobe Advertising Cloud] destinazioni configurate per  [!UICONTROL cookie-based] il pubblico. Anche se questo significa che puoi inviare [!UICONTROL segments] con l&#39;iscrizione combinata [!DNL cookie] e l&#39;appartenenza all&#39;ID mobile alle destinazioni [!DNL Google] e [!DNL Advertising Cloud], ricorda che [!UICONTROL Addressable Audiences] mostra solo la sovrapposizione tra gli ID [!DNL cookie] e le destinazioni. [!DNL Audience Manager] invia il 100% del pubblico mobile a  [!UICONTROL destinations], ma il pubblico mobile non viene misurato dalla  [!UICONTROL Addressable Audience] metrica. <br><br>**Nota**: Ad esempio, prendete una  [!UICONTROL segment] con una popolazione di 1.000.000. Se mappi questo elemento [!UICONTROL segment] a una destinazione [!DNL Google] o [!DNL Adobe Advertising Cloud], potresti visualizzare un valore [!UICONTROL Addressable Audience] di 700.000 dispositivi e un valore [!UICONTROL Match Rate] del 70%. L&#39;appartenenza a 700.000 è costituita da [!DNL cookie] ID che hanno una sincronizzazione ID con [!UICONTROL destination]. In realtà, il tuo [!UICONTROL Addressable Audience] potrebbe essere molto più alto, perché gli ID mobile indirizzabili non compaiono in questa metrica. |
| [!DNL Safari] Traffico | [!DNL Safari] blocca terze parti  [!DNL cookies]. Questo impedisce a [!DNL Audience Manager] di sincronizzare gli ID con [!UICONTROL destination]. Con l’introduzione di [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), puoi aspettarti che [!UICONTROL addressable audiences] non includa gli utenti [!DNL Safari]. |
| Impression contenuti multimediali tracciati | A causa delle best practice per il server di annunci, le sincronizzazioni ID non vengono effettuate all’interno dei tag degli annunci. I clienti che fanno una grande quantità di pubblicità offsite non sincronizzeranno gli utenti con le integrazioni di terze parti in quegli ambienti. Inoltre, una grande quantità di dati raccolti sulle impression multimediali potrebbe ridurre i numeri [!UICONTROL addressable audience]. |

## Risoluzione dei problemi relativi a [!UICONTROL Addressable Audiences] {#troubleshooting}

Oltre a riportare le percentuali di corrispondenza, puoi anche utilizzare [!UICONTROL Addressable Audiences] come strumento per la risoluzione dei problemi.

Ad esempio, supponiamo che tu invii un segmento a [!UICONTROL destination] e che [!UICONTROL destination] mostri numeri di reporting bassi. Controllando i risultati di [!UICONTROL Addressable Audience] si vedrà se si tratta di un problema tecnico o se si tratta solo di un caso di percentuali di corrispondenza basse. Una percentuale bassa indica che il tuo [!UICONTROL destination] non è così ottimo per i segmenti selezionati. Tuttavia, una differenza nei numeri [!UICONTROL total addressable audience] tra [!DNL Audience Manager] e [!UICONTROL destination] indica un&#39;integrazione, una sincronizzazione o altri problemi tecnici. In questi casi, contatta il tuo account manager.
