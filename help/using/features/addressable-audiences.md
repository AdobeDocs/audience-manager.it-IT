---
description: Panoramica della funzione Pubblico di riferimento e casi d’uso.
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

Panoramica di [!UICONTROL Addressable Audience] funzionalità e casi di utilizzo.

## Che cos’è un’ [!UICONTROL Addressable Audience]? {#addressable-audience-description}

Il [!UICONTROL Addressable Audiences] Questa funzione mostra la sovrapposizione tra i tipi di pubblico visualizzati in tutte le proprietà in cui [!DNL Audience Manager] raccoglie i dati e la destinazione selezionata. Per comprendere meglio questo concetto, si veda l’illustrazione di seguito. La sovrapposizione tra ciascun cerchio rappresenta i diversi tipi di pubblico indirizzabile.

![](assets/addressableAudienceVenn.png)


| Metrica | Descrizione |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] per un [!UICONTROL Destination] | Un conteggio di tutti i dispositivi che hanno interagito con tutti [!DNL Audience Manager] clienti a livello di piattaforma durante il periodo di look-back del rapporto e che potrebbero corrispondere al [!UICONTROL destination]. <br><br>Questa metrica è utile perché mostra: <ul><li>Dimensione del totale [!UICONTROL addressable audience] che [!DNL Audience Manager] può raggiungere un targeting particolare [!UICONTROL destination].</li><li>Quanto grande è [!DNL Audience Manager] il pool di profili è per una piattaforma di targeting e per la dimensione dei relativi tipi di pubblico.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un conteggio dei dispositivi che hanno realizzato [!UICONTROL rule-based trait] nelle proprietà o in un [!UICONTROL onboarded trait] dai file offline durante l’intervallo di look-back. |
| [!UICONTROL Customer Addressable Audience] | Un conteggio di sovrapposizione di dispositivi che hanno realizzato [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante l’intervallo di look-back e i dispositivi per i quali è stata eseguita una sincronizzazione ID con il dispositivo scelto [!UICONTROL destination] indipendentemente dall&#39;ora di sincronizzazione.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>hanno realizzato una [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante il periodo di look-back `AND`</li><li>Avere una sincronizzazione ID con il prescelto [!UICONTROL destination] indipendentemente dall&#39;ora di sincronizzazione.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] espresso in percentuale. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che facevano parte del tuo [!UICONTROL segment] durante il periodo di look-back del rapporto. |
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che sono appartenuti al [!UICONTROL segment] durante il periodo di look-back del rapporto e disponi di una sincronizzazione ID attiva sul sito. [!UICONTROL Segments] può includere dati di prime parti e dati di seconde e terze parti tramite [!UICONTROL traits] acquisito in [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Suggerimento: se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a comprendere lo stato corrente del tuo [!UICONTROL segments]. Questo perché il [!UICONTROL Segment Addressable Audience] la metrica rappresenta gli utenti che sono rimasti in un [!UICONTROL segment] per tutto il giorno precedente. Combinalo con il fatto che [!DNL Audience Manager] aggiorna [!UICONTROL Addressable Audiences] giornaliera, la combinazione di questa metrica e del periodo di lookback fornisce l’istantanea più aggiornata della [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] espresso in percentuale. |

## [!UICONTROL Addressable Audiences] Interfaccia {#addressable-audience-interface}

Il [!UICONTROL Addressable Audience] questa funzione trasforma questo concetto astratto in dati quantificabili. In entrata [!DNL Audience Manager], questa funzione mostra la sovrapposizione del pubblico con visualizzazioni di dati che forniscono informazioni panoramiche insieme a dati numerici in forma di tabella.

[!UICONTROL Addressable Audiences] si trova in **[!UICONTROL Audience Data > Destinations]**. Seleziona **[!UICONTROL Integrated Platforms > Device-Based]** per visualizzare le metriche dei tipi di pubblico indirizzabili.

![](assets/addressable-audiences-landing.png)

Le tre metriche visibili nel [!UICONTROL Addressable Audiences] la pagina di destinazione rappresenta:

| Metrica | Descrizione |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Questa metrica rappresenta [!UICONTROL Customer Addressable Audience] (descritto nella tabella precedente) *negli ultimi 30 giorni.* |
| **[!UICONTROL Match Rate]** | Questa metrica rappresenta [!UICONTROL Addressable Audience Match Rate] (descritto nella tabella precedente) *negli ultimi 30 giorni*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Un conteggio di tutti i dispositivi che hanno interagito con tutti [!DNL Audience Manager] clienti a livello di piattaforma durante il periodo di look-back del rapporto e che potrebbero corrispondere a questo [!UICONTROL destination]. Consulta [Metriche a livello di piattaforma](/help/using/features/addressable-audiences.md#platform-level-metrics) per ulteriori informazioni. |

Fai clic sul nome di un’ [!UICONTROL server-to-server destination] per visualizzare i dati del pubblico di destinazione. Questa funzione restituisce i dati per [!UICONTROL server-to-server destinations] solo e l&#39;accesso richiede le autorizzazioni di amministratore.

![](assets/addressableAudiences.png)

La revisione di questi dati può aiutarti con:

* **Previsione e pianificazione:** [!UICONTROL Segment Addressable Audience] I dati forniscono maggiore granularità nei segmenti che intendi inviare a una destinazione per il targeting e l’attivazione del pubblico.

* **Valutazione delle prestazioni:** Il [!UICONTROL Addressable Audiences] è anche uno strumento per la risoluzione dei problemi. Consente di rivedere le prestazioni della campagna, comprendere la portata della campagna e effettuare controlli incrociati con i partner di targeting/attivazione se non visualizzi i risultati previsti.

### Ricerca di dati di terze parti e relative implicazioni per i tassi di corrispondenza

Prima di acquistare dati di terze parti per l’acquisizione di un pubblico, i clienti possono convalidare la sovrapposizione con altri fornitori di dati. Questo può aiutarti a prendere una decisione informata prima di acquistare nuovi dati. Le sincronizzazioni ID per i dati di terze parti acquistati si basano non solo sulla sovrapposizione dei tuoi dati, ma anche sull’impronta dei fornitori di terze parti con tutte le altre [!DNL Audience Manager] clienti. Il tuo [!DNL Adobe] Il consulente può aiutarti a identificare ulteriori origini dati rilevanti per ottimizzare le campagne di ricerca di potenziali clienti.

### Utenti mobili e percentuali di corrispondenza

Quando si tenta di connettersi, sono presenti delle lacune [!DNL Safari] o utenti di app mobili in cui non sono presenti terze parti [!DNL cookies] presente. Questo rende difficile sincronizzare gli utenti con alcuni partner, perché solo quelli [!DNL Adobe] ID per terze parti sincronizzate [!DNL cookies] sono fornite nei registri di consegna dei contenuti multimediali. Questo è il motivo per cui potresti vedere [percentuali di corrispondenza basse](../features/addressable-audiences.md#low-match-rates) per [!UICONTROL destinations].

## Intervalli di date in [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leggi le sezioni seguenti per gli intervalli di date disponibili e per vedere come scadono i dati oltre ogni intervallo nei rapporti per un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalli di date e fusi orari disponibili {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Rapporti per [!UICONTROL Addressable Audiences] e [Destinazioni](../features/destinations/destinations.md) utilizza gli stessi intervalli di date. Le opzioni dell’intervallo di date includono:

* [!UICONTROL Last 1 Day] (Questo intervallo va da mezzanotte a mezzanotte del periodo precedente di 24 ore. Non è una metrica reale o in tempo corrente.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Tutte le date e gli intervalli di date sono impostati nel [!DNL UTC] fuso orario. Consulta [Fusi orari in Audience Manager](../reference/aam-time-zones.md).

## Dati negli intervalli di date {#date-range-intervals}

Il [!UICONTROL Addressable Audience] e [!UICONTROL Destination] Le metriche restituiscono un conteggio di utenti univoci per l’intervallo di tempo selezionato. Ad esempio, un visitatore viene conteggiato una sola volta, anche se accede al sito più volte. La prima visita è la visita unica e viene registrata. Le visite successive sono visite di ritorno e non vengono conteggiate perché non sono univoche.

Gli intervalli di date contengono dati per l’intervallo di tempo selezionato o precedente. Inoltre, i dati scadono da ogni intervallo di report con il passare del tempo. Ad esempio, supponiamo che vedrai 2 visitatori dopo aver scelto la [!UICONTROL Last 30 Days] opzione. Nei rapporti, questi visitatori:

* *Sarà* inclusi nei risultati restituiti dagli intervalli di tempo più lunghi (60 giorni, 90 giorni e Durata).
* *Non sarà* inclusi negli intervalli più brevi che precedono [!UICONTROL Last 30 Day] (Corrente, 7 giorni e 14 giorni).

E, il giorno 31, questi visitatori vengono visualizzati solo nei 60, 90 giorni e [!UICONTROL Lifetime] risultati. Sono invecchiati al di fuori dell’intervallo di 30 giorni. I visitatori non invecchiano al di fuori [!UICONTROL Lifetime] intervallo.

## [!UICONTROL Addressable Audiences] Metriche {#addressable-audience-metrics}

In questa sezione sono descritti i tipi di metriche forniti da [!UICONTROL Addressable Audiences].

### Metriche a livello di cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Queste metriche restituiscono i dati per le caratteristiche realizzate quando i visitatori arrivano sul tuo sito o quando invii file di dati in entrata a [!DNL Audience Manager]. Queste metriche forniscono una visualizzazione completa delle dimensioni del pubblico per il tuo account.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Un conteggio di sovrapposizione di dispositivi che hanno realizzato [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante l’intervallo di look-back e sui dispositivi è disponibile una sincronizzazione ID con la destinazione scelta, indipendentemente dal momento delle sincronizzazioni.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>hanno realizzato una [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante il periodo di look-back `AND`</li><li>Avere una sincronizzazione ID con il prescelto [!UICONTROL destination] indipendentemente dall&#39;ora di sincronizzazione.</li></ul> |
| [!UICONTROL Customer Total Audience] | Un conteggio dei dispositivi che hanno realizzato [!UICONTROL rule-based trait] nelle proprietà o in un [!UICONTROL onboarded trait] dai file offline durante l’intervallo di look-back. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] espresso in percentuale. |

### Metriche di corrispondenza a livello di segmento {#segment-level-metrics}

Queste metriche restituiscono i dati su [!UICONTROL segment] iscrizione. Offrono una visualizzazione più granulare e precisa della dimensione del pubblico per ciascuna delle [!UICONTROL segments].

>[!NOTE]
>
>Il modo in cui l’intervallo di look-back viene applicato al [!UICONTROL segment] è diverso da quello del cliente. I visitatori possono visitare il sito e realizzare [!UICONTROL trait] 10 giorni fa, e potevano qualificarsi per un [!UICONTROL segment] da allora e ha abbandonato il [!UICONTROL segment] 2 giorni fa. Quando viene applicato il look-back di 7 giorni, questi visitatori verranno conteggiati nel [!UICONTROL segment] ma non a livello del cliente.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che sono appartenuti al [!UICONTROL segment] durante il periodo di look-back del rapporto e disponi di una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconde e terze parti attraverso [!UICONTROL traits] acquisito in [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Suggerimento: se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a comprendere lo stato corrente del tuo [!UICONTROL segments]. Questo perché il [!UICONTROL Segment Addressable Audience] la metrica rappresenta gli utenti che sono rimasti in un [!UICONTROL segment] per tutto il giorno precedente. Combinalo con il fatto che [!DNL Audience Manager] aggiorna [!UICONTROL Addressable Audiences] giornaliera, la combinazione di questa metrica e del periodo di lookback fornisce l’istantanea più aggiornata della [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che facevano parte del tuo [!UICONTROL segment] durante il periodo di look-back del rapporto. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] espresso in percentuale. |

### Metriche a livello di piattaforma {#platform-level-metrics}

Questa metrica restituisce i dati sulle attività raccolte in tutti [!DNL Audience Manager] clienti. Possono fornire una visione più ampia del pubblico del cliente rispetto al pubblico aggregato [!DNL Audience Manager] clienti.

| Metrica | Descrizione |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Un conteggio di tutti i dispositivi che hanno interagito con tutti [!DNL Audience Manager] clienti a livello di piattaforma durante il periodo di look-back del rapporto e che potrebbero corrispondere al [!UICONTROL destination]. <br><br>Questa metrica è utile perché mostra:<ul><li>Dimensione del [!UICONTROL total addressable audience] che [!DNL Audience Manager] può raggiungere una particolare destinazione di targeting.</li><li>Quanto grande è [!DNL Audience Manager] il pool di profili è per una piattaforma di targeting e per la dimensione dei relativi tipi di pubblico.</li></ul> |

## Confronto [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Non si deve confrontare [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] metriche per determinare se una è più significativa dell’altra. Si tratta di metriche separate, diverse e indipendenti. Come descritto nelle definizioni precedenti, ciascuno di questi è derivato da set di dati diversi. Dato questo, evita di trarre conclusioni se una metrica è più grande dell’altra. Tutto quello che puoi dire quando li confronti è che:

* [!UICONTROL Customer Addressable Audiences] si basa su [!UICONTROL trait] realizzazioni *per i tuoi dati di prime parti*. Questa metrica fornisce una visione ampia e completa dell’integrazione con un partner dati.

* [!UICONTROL Segment Addressable Audiences] si basa sulle qualifiche dei segmenti *per i dati di prime parti e per i dati di seconde e terze parti*. Questa metrica fornisce una visualizzazione granulare e più precisa del [!UICONTROL addressable audiences] in una piattaforma di targeting.

## Cause dei tassi di corrispondenza bassi per [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementi comuni responsabili di bassi [!UICONTROL Addressable Audience] percentuali di corrispondenza o discrepanze nei numeri riportati.

| Causa | Descrizione |
|---|---|
| Traffico mobile | Più [!UICONTROL server-to-server] le integrazioni si basano su processi di sincronizzazione facilitati da terze parti [!DNL cookies]. Tuttavia, gli ambienti mobili non utilizzano sistemi di terze parti [!DNL cookies]. Di conseguenza, il tuo [!UICONTROL Addressable Audiences] i numeri possono sembrare bassi rispetto a [!UICONTROL segment] dimensioni. <br><br>A partire da gennaio 2018, è possibile attivare il pubblico di dispositivi mobili nello stesso [!DNL Google] e [!DNL Adobe Advertising Cloud] destinazioni impostate per [!UICONTROL cookie-based] pubblico. Questo significa che puoi inviare [!UICONTROL segments] con combinazioni [!DNL cookie] e l&#39;iscrizione al tuo servizio ID mobile [!DNL Google] e [!DNL Advertising Cloud] destinazioni, ricorda che [!UICONTROL Addressable Audiences] visualizza solo la sovrapposizione tra [!DNL cookie] ID e destinazioni. [!DNL Audience Manager] invia il 100% del pubblico di dispositivi mobili a [!UICONTROL destinations], ma i tipi di pubblico per dispositivi mobili non vengono misurati dalla [!UICONTROL Addressable Audience] metrica. <br><br>**Nota**: ad esempio, prendi una [!UICONTROL segment] con una popolazione di 1.000.000. Se mappi questo [!UICONTROL segment] a un [!DNL Google] o [!DNL Adobe Advertising Cloud] destinazione, è possibile che venga visualizzata una [!UICONTROL Addressable Audience] di 700.000 dispositivi e un [!UICONTROL Match Rate] del 70%. Il numero di iscritti pari a 700.000 comprende [!DNL cookie] ID che hanno una sincronizzazione ID con [!UICONTROL destination]. Il tuo [!UICONTROL Addressable Audience] potrebbe, in realtà, essere molto più alto, perché gli ID indirizzabili dei dispositivi mobili non compaiono in questa metrica. |
| [!DNL Safari] Traffico | [!DNL Safari] blocca terze parti [!DNL cookies]. Questo impedisce [!DNL Audience Manager] dalla sincronizzazione degli ID con [!UICONTROL destination]. Con l&#39;introduzione di [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), è possibile aspettarsi [!UICONTROL addressable audiences] da non includere [!DNL Safari] utenti. |
| Impression dei contenuti multimediali tracciati | A causa delle best practice per gli ad server, le sincronizzazioni ID non vengono effettuate all’interno dei tag annuncio. I clienti che effettuano una grande quantità di pubblicità offsite non sincronizzeranno gli utenti con integrazioni di terze parti in tali ambienti. Inoltre, una grande quantità di dati raccolti sulle impression multimediali potrebbe ridurre [!UICONTROL addressable audience] numeri. |

## Risoluzione dei problemi con [!UICONTROL Addressable Audiences] {#troubleshooting}

Oltre alle percentuali di corrispondenza, puoi utilizzare [!UICONTROL Addressable Audiences] come strumento di risoluzione dei problemi.

Ad esempio, supponiamo che tu invii un segmento a un [!UICONTROL destination] e che [!UICONTROL destination] mostra numeri di reporting bassi. Controllo del [!UICONTROL Addressable Audience] i risultati ti mostreranno se si tratta di un problema tecnico o solo di un caso di percentuali di corrispondenza basse. Una bassa percentuale di corrispondenza mostra il tuo [!UICONTROL destination] non è tutto questo per i segmenti selezionati. Tuttavia, una differenza nella [!UICONTROL total addressable audience] numeri tra [!DNL Audience Manager] e [!UICONTROL destination] indica un problema di integrazione, sincronizzazione o altro problema tecnico. In questi casi, contatta il tuo account manager.
