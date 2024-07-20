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
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Panoramica della funzionalità [!UICONTROL Addressable Audience] e casi d&#39;uso.

## Cos&#39;è un [!UICONTROL Addressable Audience]? {#addressable-audience-description}

La funzionalità [!UICONTROL Addressable Audiences] mostra la sovrapposizione tra i tipi di pubblico visualizzati in tutte le proprietà in cui [!DNL Audience Manager] raccoglie i dati e la destinazione selezionata. Per comprendere meglio questo concetto, si veda l’illustrazione di seguito. La sovrapposizione tra ciascun cerchio rappresenta i diversi tipi di pubblico indirizzabile.

![](assets/addressableAudienceVenn.png)


| Metrica | Descrizione |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] per [!UICONTROL Destination] | Un conteggio di tutti i dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che potrebbero corrispondere al [!UICONTROL destination] scelto. <br><br>Questa metrica è utile perché mostra: <ul><li>Dimensione del totale di [!UICONTROL addressable audience] che [!DNL Audience Manager] può raggiungere in un particolare targeting [!UICONTROL destination].</li><li>Dimensioni del pool di profili [!DNL Audience Manager] per una piattaforma di targeting e dimensioni dei relativi tipi di pubblico.</li></ul> |
| [!UICONTROL Customer Total Audience] | Numero di dispositivi che hanno realizzato [!UICONTROL rule-based trait] nelle proprietà o [!UICONTROL onboarded trait] dai file offline durante l&#39;intervallo di look-back. |
| [!UICONTROL Customer Addressable Audience] | Un conteggio di sovrapposizione di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante l&#39;intervallo di look-back e dispositivi per i quali abbiamo una sincronizzazione ID con il [!UICONTROL destination] scelto indipendentemente dal momento delle sincronizzazioni.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante l&#39;intervallo di look-back `AND`</li><li>Disporre di una sincronizzazione ID con [!UICONTROL destination] scelto indipendentemente dall&#39;ora di sincronizzazione.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] espressi in percentuale. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che erano membri di [!UICONTROL segment] durante il periodo di look-back del report. |
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno fatto parte di [!UICONTROL segment] durante il periodo di look-back del report e dispongono di una sincronizzazione ID attiva sul sito. [!UICONTROL Segments] può includere i tuoi dati di prime parti e di seconde e terze parti tramite [!UICONTROL traits] acquisito nell&#39;[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Suggerimento: se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a comprendere lo stato corrente di [!UICONTROL segments]. Questo perché la metrica [!UICONTROL Segment Addressable Audience] rappresenta gli utenti che sono rimasti in un [!UICONTROL segment] per tutto il giorno precedente. Combinalo con il fatto che [!DNL Audience Manager] aggiorna [!UICONTROL Addressable Audiences] al giorno. La combinazione di questa metrica e del periodo di lookback fornisce lo snapshot più aggiornato del tuo [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] espressi in percentuale. |

## Interfaccia [!UICONTROL Addressable Audiences] {#addressable-audience-interface}

La funzionalità [!UICONTROL Addressable Audience] converte questo concetto astratto in dati quantificabili. In [!DNL Audience Manager], questa funzione mostra la sovrapposizione del pubblico con visualizzazioni di dati che forniscono informazioni dettagliate insieme a dati numerici in forma tabulare.

[!UICONTROL Addressable Audiences] si trova in **[!UICONTROL Audience Data > Destinations]**. Selezionare **[!UICONTROL Integrated Platforms > Device-Based]** per visualizzare le metriche dei tipi di pubblico indirizzabili.

![](assets/addressable-audiences-landing.png)

Le tre metriche visualizzate nella pagina di destinazione [!UICONTROL Addressable Audiences] rappresentano:

| Metrica | Descrizione |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Questa metrica rappresenta [!UICONTROL Customer Addressable Audience] (descritto nella tabella precedente) *per gli ultimi 30 giorni.* |
| **[!UICONTROL Match Rate]** | Questa metrica rappresenta [!UICONTROL Addressable Audience Match Rate] (descritto nella tabella precedente) *per gli ultimi 30 giorni*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Un conteggio di tutti i dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che potrebbero corrispondere a [!UICONTROL destination]. Per ulteriori informazioni, consulta [Metriche a livello di piattaforma](/help/using/features/addressable-audiences.md#platform-level-metrics). |

Fai clic sul nome di un [!UICONTROL server-to-server destination] per visualizzare i dati del pubblico di destinazione. Questa funzionalità restituisce dati solo per [!UICONTROL server-to-server destinations] e l&#39;accesso richiede autorizzazioni di amministratore.

![](assets/addressableAudiences.png)

La revisione di questi dati può aiutarti con:

* **Previsione e pianificazione:** i dati di [!UICONTROL Segment Addressable Audience] offrono maggiore granularità nei segmenti che si prevede di inviare a una destinazione per il targeting e l&#39;attivazione del pubblico.

* **Analisi delle prestazioni:** Anche la funzionalità [!UICONTROL Addressable Audiences] è uno strumento per la risoluzione dei problemi. Consente di rivedere le prestazioni della campagna, comprendere la portata della campagna e effettuare controlli incrociati con i partner di targeting/attivazione se non visualizzi i risultati previsti.

### Ricerca di dati di terze parti e relative implicazioni per i tassi di corrispondenza

Prima di acquistare dati di terze parti per l’acquisizione di un pubblico, i clienti possono convalidare la sovrapposizione con altri fornitori di dati. Questo può aiutarti a prendere una decisione informata prima di acquistare nuovi dati. Le sincronizzazioni ID per i dati di terze parti acquistati si basano non solo sulla sovrapposizione dei tuoi dati, ma anche sulle impronte dei provider di terze parti con tutti gli altri clienti [!DNL Audience Manager]. Il tuo consulente [!DNL Adobe] può aiutarti a identificare altre origini dati rilevanti per ottimizzare le campagne di ricerca di potenziali clienti.

### Utenti mobili e percentuali di corrispondenza

Si sono verificate delle lacune durante il tentativo di connettere [!DNL Safari] o gli utenti dell&#39;app mobile in cui non sono presenti [!DNL cookies] di terze parti. Ciò rende difficile sincronizzare gli utenti con alcuni partner, perché nei registri di consegna dei contenuti multimediali vengono forniti solo gli ID [!DNL Adobe] per [!DNL cookies] di terze parti sincronizzati. Questo è un motivo per cui potresti vedere [bassi tassi di corrispondenza](../features/addressable-audiences.md#low-match-rates) per il tuo [!UICONTROL destinations].

## Intervalli di date in [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leggere le sezioni seguenti per conoscere gli intervalli di date disponibili e il modo in cui i dati superano ciascun intervallo nei rapporti per un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalli di date e fusi orari disponibili {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

I report per [!UICONTROL Addressable Audiences] e [destinazioni](../features/destinations/destinations.md) utilizzano gli stessi intervalli di date. Le opzioni dell’intervallo di date includono:

* [!UICONTROL Last 1 Day] (questo intervallo va da mezzanotte a mezzanotte del periodo precedente di 24 ore. Non è una metrica reale o in tempo corrente.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Tutte le date e gli intervalli sono impostati nel fuso orario [!DNL UTC]. Vedi [Fusi orari in Audience Manager](../reference/aam-time-zones.md).

## Dati negli intervalli di date {#date-range-intervals}

Le metriche [!UICONTROL Addressable Audience] e [!UICONTROL Destination] restituiscono un conteggio di utenti univoci per l&#39;intervallo di tempo selezionato. Ad esempio, un visitatore viene conteggiato una sola volta, anche se accede al sito più volte. La prima visita è la visita unica e viene registrata. Le visite successive sono visite di ritorno e non vengono conteggiate perché non sono univoche.

Gli intervalli di date contengono dati per l’intervallo di tempo selezionato o precedente. Inoltre, i dati scadono da ogni intervallo di report con il passare del tempo. Supponiamo ad esempio che dopo aver scelto l&#39;opzione [!UICONTROL Last 30 Days] vengano visualizzati 2 visitatori. Nei rapporti, questi visitatori:

* *Sarà* incluso nei risultati restituiti in base agli intervalli di tempo più lunghi (60 giorni, 90 giorni e Durata).
* *Non sarà* incluso negli intervalli più brevi che precedono l&#39;opzione [!UICONTROL Last 30 Day] (Corrente, 7 giorni e 14 giorni).

E, il giorno 31, questi visitatori vengono visualizzati solo nei risultati di 60 giorni, 90 giorni e [!UICONTROL Lifetime]. Sono invecchiati al di fuori dell’intervallo di 30 giorni. I visitatori non superano l&#39;intervallo [!UICONTROL Lifetime].

## [!UICONTROL Addressable Audiences] metriche {#addressable-audience-metrics}

In questa sezione sono descritti i tipi di metriche forniti da [!UICONTROL Addressable Audiences].

### Metriche a livello di cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Queste metriche restituiscono i dati per le caratteristiche realizzate quando i visitatori arrivano sul tuo sito o quando invii file di dati in entrata a [!DNL Audience Manager]. Queste metriche forniscono una visualizzazione completa delle dimensioni del pubblico per il tuo account.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Un conteggio di sovrapposizione di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante l&#39;intervallo di look-back e dispositivi che hanno una sincronizzazione ID con la destinazione scelta indipendentemente dal tempo di sincronizzazione.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante l&#39;intervallo di look-back `AND`</li><li>Disporre di una sincronizzazione ID con [!UICONTROL destination] scelto indipendentemente dall&#39;ora di sincronizzazione.</li></ul> |
| [!UICONTROL Customer Total Audience] | Numero di dispositivi che hanno realizzato [!UICONTROL rule-based trait] nelle proprietà o [!UICONTROL onboarded trait] dai file offline durante l&#39;intervallo di look-back. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] espressi in percentuale. |

### Metriche di corrispondenza a livello di segmento {#segment-level-metrics}

Queste metriche restituiscono i dati sull&#39;iscrizione a [!UICONTROL segment]. Offrono una visualizzazione più granulare e precisa della dimensione del pubblico per ciascuno dei [!UICONTROL segments].

>[!NOTE]
>
>Il modo in cui l&#39;intervallo di look-back viene applicato al livello [!UICONTROL segment] è diverso da quello a livello del cliente. I visitatori possono visitare il sito e realizzare un [!UICONTROL trait] 10 giorni fa e da allora potrebbero qualificarsi per un [!UICONTROL segment] e hanno abbandonato il [!UICONTROL segment] 2 giorni fa. Quando viene applicato il look-back di 7 giorni, questi visitatori verranno conteggiati al livello [!UICONTROL segment] ma non al livello del cliente.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno fatto parte di [!UICONTROL segment] durante il periodo di look-back del report e dispongono di una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconde e terze parti attraverso [!UICONTROL traits] acquisiti nell&#39;[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Suggerimento: se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a comprendere lo stato corrente di [!UICONTROL segments]. Questo perché la metrica [!UICONTROL Segment Addressable Audience] rappresenta gli utenti che sono rimasti in un [!UICONTROL segment] per tutto il giorno precedente. Combinalo con il fatto che [!DNL Audience Manager] aggiorna [!UICONTROL Addressable Audiences] al giorno. La combinazione di questa metrica e del periodo di lookback fornisce lo snapshot più aggiornato del tuo [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Un conteggio di tutti i dispositivi che erano membri di [!UICONTROL segment] durante il periodo di look-back del report. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] espressi in percentuale. |

### Metriche a livello di piattaforma {#platform-level-metrics}

Questa metrica restituisce i dati sulle attività raccolte tra tutti i clienti [!DNL Audience Manager]. Possono fornire una visione più ampia del pubblico del cliente rispetto ai clienti aggregati [!DNL Audience Manager].

| Metrica | Descrizione |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Un conteggio di tutti i dispositivi che hanno interagito con tutti i clienti [!DNL Audience Manager] a livello di piattaforma durante il periodo di look-back del report e che potrebbero corrispondere al [!UICONTROL destination] scelto. <br><br>Questa metrica è utile perché mostra:<ul><li>Dimensione di [!UICONTROL total addressable audience] che [!DNL Audience Manager] può raggiungere su una particolare destinazione.</li><li>Dimensioni del pool di profili [!DNL Audience Manager] per una piattaforma di targeting e dimensioni dei relativi tipi di pubblico.</li></ul> |

## Confronto tra [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Non confrontare le metriche [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] per determinare se una è più significativa dell&#39;altra. Si tratta di metriche separate, diverse e indipendenti. Come descritto nelle definizioni precedenti, ciascuno di questi è derivato da set di dati diversi. Dato questo, evita di trarre conclusioni se una metrica è più grande dell’altra. Tutto quello che puoi dire quando li confronti è che:

* [!UICONTROL Customer Addressable Audiences] si basa su [!UICONTROL trait] realizzazioni *per i tuoi dati di prime parti*. Questa metrica fornisce una visione ampia e completa dell’integrazione con un partner dati.

* [!UICONTROL Segment Addressable Audiences] si basa sulle qualifiche dei segmenti *per i tuoi dati di prime parti, più dati di seconde e terze parti*. Questa metrica fornisce una visualizzazione granulare e più precisa di [!UICONTROL addressable audiences] in una piattaforma di targeting.

## Cause dei tassi di corrispondenza bassi per [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementi comuni responsabili di bassi tassi di corrispondenza di [!UICONTROL Addressable Audience] o discrepanze nei numeri riportati.

| Causa | Descrizione |
|---|---|
| Traffico mobile | La maggior parte delle integrazioni di [!UICONTROL server-to-server] si basa su processi di sincronizzazione facilitati da [!DNL cookies] di terze parti. Tuttavia, gli ambienti mobili non utilizzano [!DNL cookies] di terze parti. Di conseguenza, i numeri di [!UICONTROL Addressable Audiences] potrebbero sembrare bassi rispetto alle dimensioni di [!UICONTROL segment]. <br><br>A partire da gennaio 2018, è possibile attivare i tipi di pubblico per dispositivi mobili nelle stesse [!DNL Google] e [!DNL Adobe Advertising Cloud] destinazioni impostate per [!UICONTROL cookie-based] tipi di pubblico. Questo significa che puoi inviare [!UICONTROL segments] con l&#39;iscrizione combinata a [!DNL cookie] e ID mobile alle destinazioni [!DNL Google] e [!DNL Advertising Cloud]. Tieni presente che [!UICONTROL Addressable Audiences] visualizza solo la sovrapposizione tra gli ID [!DNL cookie] e le destinazioni. [!DNL Audience Manager] invia il 100% dei tipi di pubblico per dispositivi mobili a [!UICONTROL destinations], ma tali tipi di pubblico non sono misurati dalla metrica [!UICONTROL Addressable Audience]. <br><br>**Nota**: ad esempio, prendi [!UICONTROL segment] con una popolazione di 1.000.000. Se mappi [!UICONTROL segment] a una destinazione [!DNL Google] o [!DNL Adobe Advertising Cloud], potresti vedere un [!UICONTROL Addressable Audience] di 700.000 dispositivi e un [!UICONTROL Match Rate] di 70%. L&#39;appartenenza di 700.000 è costituita da [!DNL cookie] ID che hanno una sincronizzazione ID con [!UICONTROL destination]. [!UICONTROL Addressable Audience] potrebbe essere molto più alto, perché gli ID indirizzabili per dispositivi mobili non vengono visualizzati in questa metrica. |
| [!DNL Safari] traffico | [!DNL Safari] blocca [!DNL cookies] di terze parti. Questo impedisce a [!DNL Audience Manager] di sincronizzare gli ID con [!UICONTROL destination]. Con l&#39;introduzione di [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), è possibile che [!UICONTROL addressable audiences] non includa [!DNL Safari] utenti. |
| Impression dei contenuti multimediali tracciati | A causa delle best practice per gli ad server, le sincronizzazioni ID non vengono effettuate all’interno dei tag annuncio. I clienti che effettuano una grande quantità di pubblicità offsite non sincronizzeranno gli utenti con integrazioni di terze parti in tali ambienti. Inoltre, una grande quantità di dati di impression multimediali raccolti potrebbe ridurre i numeri [!UICONTROL addressable audience]. |

## Risoluzione dei problemi con [!UICONTROL Addressable Audiences] {#troubleshooting}

Oltre alle percentuali di corrispondenza, è possibile utilizzare [!UICONTROL Addressable Audiences] come strumento di risoluzione dei problemi.

Supponiamo ad esempio che tu invii un segmento a [!UICONTROL destination] e che [!UICONTROL destination] mostri numeri di reporting bassi. La verifica dei risultati di [!UICONTROL Addressable Audience] mostrerà se si tratta di un problema tecnico o se si tratta solo di un caso di percentuali di corrispondenza basse. Una bassa percentuale di corrispondenza indica che [!UICONTROL destination] non è così buono per i segmenti selezionati. Tuttavia, una differenza nei numeri [!UICONTROL total addressable audience] tra [!DNL Audience Manager] e [!UICONTROL destination] indica un problema di integrazione, sincronizzazione o altro problema tecnico. In questi casi, contatta il tuo account manager.
