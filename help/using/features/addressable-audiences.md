---
description: Panoramica della funzione Pubblico di riferimento e dei casi di utilizzo.
keywords: DIL
seo-description: Panoramica della funzione Pubblico di riferimento e dei casi di utilizzo.
seo-title: Pubblico di riferimento
solution: Audience Manager
title: Pubblico di riferimento
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 0%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Panoramica della [!UICONTROL Addressable Audience] funzione e dei casi di utilizzo.

## Cos&#39;è un [!UICONTROL Addressable Audience]cane? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] funzione mostra la sovrapposizione tra i tipi di pubblico visualizzati in tutte le proprietà in cui [!DNL Audience Manager] vengono raccolti i dati e la destinazione selezionata. Per comprendere meglio questo concetto, osservate l&#39;illustrazione seguente. La sovrapposizione tra ciascun cerchio rappresenta i diversi tipi di pubblico indirizzabile.

![](assets/addressableAudienceVenn.png)


| Metrica | Descrizione |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] per [!UICONTROL Destination] | Numero totale di dispositivi che hanno interagito con tutti [!DNL Audience Manager] i clienti a livello di piattaforma durante il periodo di look-back del report e che possono essere associati al [!UICONTROL destination]dispositivo scelto. <br><br>Questa metrica è utile perché mostra: <ul><li>Dimensione del totale [!UICONTROL addressable audience] che [!DNL Audience Manager] può raggiungere un particolare targeting [!UICONTROL destination].</li><li>Dimensioni del pool di [!DNL Audience Manager] profili per una piattaforma di targeting e dimensioni del pubblico.</li></ul> |
| [!UICONTROL Customer Total Audience] | Numero di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] sulle proprietà o un file [!UICONTROL onboarded trait] dai file offline durante la finestra di look-back. |
| [!UICONTROL Addressable Audience Match Rate] | Conteggio di sovrapposizioni di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la finestra di look-back e dispositivi per i quali è presente una sincronizzazione ID con i dispositivi selezionati, [!UICONTROL destination] indipendentemente dal tempo di sincronizzazione.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la finestra di look-back `AND`</li><li>Sincronizzate l’ID con l’ID scelto [!UICONTROL destination] indipendentemente dal tempo di sincronizzazione.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] espressa in percentuale. |
| [!UICONTROL Total Segment Population] | Numero totale di tutti i dispositivi che erano membri dell&#39;utente [!UICONTROL segment] durante il periodo di look-back del report. |
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno aderito al report [!UICONTROL segment] durante il periodo di look-back e hanno una sincronizzazione ID attiva sul sito. [!UICONTROL Segments] può includere dati di prime parti e dati di seconda e terza parte, tramite [!UICONTROL traits] acquisiti nell&#39; [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a capire lo stato corrente del tuo [!UICONTROL segments]. Questo perché la [!UICONTROL Segment Addressable Audience] metrica rappresenta gli utenti che hanno soggiornato in un [!UICONTROL segment] giorno precedente. Combinate questo con il fatto che [!DNL Audience Manager] l&#39;aggiornamento [!UICONTROL Addressable Audiences] giornaliero, combinando questa metrica e il periodo di lookback fornisce lo snapshot più aggiornato del [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] espressa in percentuale. |

## [!UICONTROL Addressable Audiences] Interfaccia {#addressable-audience-interface}

La [!UICONTROL Addressable Audience] funzione trasforma questo concetto astratto in dati quantificabili. In [!DNL Audience Manager]questa funzione, il pubblico si sovrappone alle visualizzazioni dati che forniscono informazioni a colpo d&#39;occhio insieme ai dati numerici in forma di tabella.

[!UICONTROL Addressable Audiences] si trova in **[!UICONTROL Audience Data > Destinations]**. Seleziona questa opzione **[!UICONTROL Integrated Platforms > Device-Based]** per visualizzare le metriche di audience indirizzabili.

![](assets/addressable-audiences-landing.png)

Le tre metriche che puoi vedere sulla pagina di [!UICONTROL Addressable Audiences] destinazione rappresentano:

| Metrica | Descrizione |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Questa metrica rappresenta la [!UICONTROL Customer Addressable Audience] (descritta nella tabella precedente) *per gli ultimi 30 giorni.* |
| **[!UICONTROL Match Rate]** | Questa metrica rappresenta la [!UICONTROL Addressable Audience Match Rate] (descritta nella tabella precedente) *per gli ultimi 30 giorni*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Numero totale di dispositivi che hanno interagito con tutti [!DNL Audience Manager] i clienti a livello di piattaforma durante il periodo di look-back del report e che possono essere associati a questo [!UICONTROL destination]. Per ulteriori informazioni, consulta Metriche [a livello di](/help/using/features/addressable-audiences.md#platform-level-metrics) Platform. |

Fai clic sul nome di un [!UICONTROL server-to-server destination] utente per visualizzare i dati del pubblico di destinazione. Nota: questa funzione restituisce i dati solo per [!UICONTROL server-to-server destinations] l&#39;accesso e richiede le autorizzazioni dell&#39;amministratore.

![](assets/addressableAudiences.png)

La revisione di questi dati può essere utile per:

* **Previsione e pianificazione:** [!UICONTROL Segment Addressable Audience] i dati forniscono maggiore granularità nei segmenti che pianificate di inviare a una destinazione per il targeting dell&#39;audience e l&#39;attivazione.

* **Recensioni delle prestazioni:** La [!UICONTROL Addressable Audiences] funzione è anche uno strumento per la risoluzione dei problemi. Consente di esaminare le prestazioni della campagna, comprendere il raggio d&#39;azione della campagna e di effettuare verifiche incrociate con i partner di targeting/attivazione se non vengono visualizzati i risultati previsti.

### Prospettiva con dati di terze parti e implicazioni per le percentuali di corrispondenza

Prima di acquistare dati di terze parti per l&#39;acquisizione di audience, i clienti possono convalidare la sovrapposizione con altri fornitori di dati. Questo può aiutarti a prendere una decisione informata prima di acquistare nuovi dati. Le sincronizzazioni ID per i dati di terze parti acquistati non si basano solo sulla sovrapposizione dei dati ma anche sulle impronte dei fornitori di terze parti con tutti gli altri [!DNL Audience Manager] clienti. Il tuo [!DNL Adobe] consulente può aiutarti a identificare ulteriori origini dati rilevanti per ottimizzare le campagne di ricerca.

### Utenti per dispositivi mobili e percentuali di corrispondenza

Ci sono degli spazi vuoti quando si tenta di connettere [!DNL Safari] o creare app mobili gli utenti in cui non sono presenti [!DNL cookies] terze parti. Questo rende difficile la sincronizzazione degli utenti con alcuni partner, perché solo questi [!DNL Adobe] ID per terze parti sincronizzate [!DNL cookies] sono forniti nei registri di distribuzione dei supporti. Questo è un motivo per cui potresti vedere [bassi tassi](../features/addressable-audiences.md#low-match-rates) di corrispondenza per il tuo [!UICONTROL destinations].

## Intervalli di date in [!UICONTROL Addressable Audiences] e [!UICONTROL Destinations] {#date-ranges}

Leggi le sezioni seguenti per conoscere gli intervalli di date disponibili e come i dati scadono a ogni intervallo nei rapporti per un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalli di date e Fusi orari disponibili {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

I report per le tue [!UICONTROL Addressable Audiences] e [Destinazioni](../features/destinations/destinations.md) utilizzano gli stessi intervalli di date. Le opzioni dell&#39;intervallo di date includono:

* [!UICONTROL Last 1 Day] (Questo intervallo va da mezzanotte a mezzanotte del precedente periodo di 24 ore. Non si tratta di una metrica in tempo reale o corrente.
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Tutte le date e gli intervalli di date sono impostati nel fuso [!DNL UTC] orario. Consultate Fusi [temporali in  Audience Manager](../reference/aam-time-zones.md).

## Dati in intervalli di date {#date-range-intervals}

Le [!UICONTROL Addressable Audience] metriche e [!UICONTROL Destination] restituiscono un conteggio di utenti univoci per l&#39;intervallo di tempo selezionato. Ad esempio, un visitatore viene conteggiato una sola volta, anche se visita più volte il sito. La prima visita è la visita unica e viene registrata. Le visite successive sono visite di ritorno e non sono conteggiate perché non sono univoche.

Gli intervalli di date contengono i dati per l&#39;intervallo di tempo selezionato o per la versione precedente. Inoltre, i dati si estinguono a partire da ogni intervallo di rapporto non appena il tempo passa. Ad esempio, supponiamo di vedere 2 visitatori dopo aver scelto l’ [!UICONTROL Last 30 Days] opzione. Nei rapporti, questi visitatori:

* *Saranno* inclusi nei risultati restituiti dagli intervalli di tempo più lunghi (60 giorni, 90 giorni e Durata).
* *Non verrà* incluso negli intervalli più brevi che precedono l&#39; [!UICONTROL Last 30 Day] opzione (Corrente, 7 giorni e 14 giorni).

E, il giorno 31, questi visitatori arrivano solo nei 60 giorni, 90 giorni, e [!UICONTROL Lifetime] risultati. Sono invecchiati rispetto all&#39;intervallo di 30 giorni. I visitatori non superano l&#39; [!UICONTROL Lifetime] intervallo.

## [!UICONTROL Addressable Audiences] Metriche {#addressable-audience-metrics}

Questa sezione descrive i tipi di metriche forniti da [!UICONTROL Addressable Audiences].

### Metriche a livello di cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Queste metriche restituiscono i dati per le caratteristiche realizzate quando i visitatori arrivano sul tuo sito o quando invii file di dati in ingresso a [!DNL Audience Manager]. Queste metriche forniscono una visualizzazione completa delle dimensioni dell&#39;audience per l&#39;account.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Numero di sovrapposizioni di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] o un [!UICONTROL onboarded trait] durante la finestra di look-back e dispositivi per i quali è presente una sincronizzazione ID con la destinazione scelta, indipendentemente dal tempo di sincronizzazione.<br><br>Questa metrica rappresenta i dispositivi che:<ul><li>Hanno realizzato un [!UICONTROL rule-based] o un [!UICONTROL onboarded trait] durante la finestra di look-back `AND`</li><li>Sincronizzate l’ID con l’ID scelto [!UICONTROL destination] indipendentemente dal tempo di sincronizzazione.</li></ul> |
| [!UICONTROL Customer Total Audience] | Numero di dispositivi che hanno realizzato un [!UICONTROL rule-based trait] sulle proprietà o un file [!UICONTROL onboarded trait] dai file offline durante la finestra di look-back. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] espressa in percentuale. |

### Metriche di corrispondenza a livello di segmento {#segment-level-metrics}

Queste metriche restituiscono i dati sull&#39; [!UICONTROL segment] appartenenza. che consentono di ottenere una visualizzazione più granulare e accurata delle dimensioni del pubblico per ogni [!UICONTROL segments]utente.

>[!NOTE]
>
>Il modo in cui la finestra di look-back viene applicata a [!UICONTROL segment] livello di cliente è diverso da quello di cliente. I visitatori possono visitare il sito e realizzare un [!UICONTROL trait] 10 giorni fa, e da allora potrebbero qualificarsi per un [!UICONTROL segment] giorno e lasciarsi andare dai [!UICONTROL segment] 2 giorni fa. Quando viene applicato l&#39;aspetto di 7 giorni, questi visitatori vengono contati a [!UICONTROL segment] livello di cliente, ma non a livello di cliente.

| Metrica | Descrizione |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Il numero di utenti che hanno aderito al report [!UICONTROL segment] durante il periodo di look-back e hanno una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconda e terza parte, tramite [!UICONTROL traits] acquisiti nell&#39; [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a capire lo stato corrente del tuo [!UICONTROL segments]. Questo perché la [!UICONTROL Segment Addressable Audience] metrica rappresenta gli utenti che hanno soggiornato in un [!UICONTROL segment] giorno precedente. Combinate questo con il fatto che [!DNL Audience Manager] l&#39;aggiornamento [!UICONTROL Addressable Audiences] giornaliero, combinando questa metrica e il periodo di lookback fornisce lo snapshot più aggiornato del [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Numero totale di tutti i dispositivi che erano membri dell&#39;utente [!UICONTROL segment] durante il periodo di look-back del report. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] espressa in percentuale. |

### Metriche a livello di Platform {#platform-level-metrics}

Questa metrica restituisce i dati sulle attività raccolte tra tutti [!DNL Audience Manager] i clienti. Possono fornire una visione più ampia del pubblico del cliente rispetto ai [!DNL Audience Manager] clienti aggregati.

| Metrica | Descrizione |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Numero totale di dispositivi che hanno interagito con tutti [!DNL Audience Manager] i clienti a livello di piattaforma durante il periodo di look-back del report e che possono essere associati al [!UICONTROL destination]dispositivo scelto. <br><br>Questa metrica è utile perché mostra:<ul><li>Dimensione del [!UICONTROL total addressable audience] raggio che [!DNL Audience Manager] può raggiungere una particolare destinazione di destinazione.</li><li>Dimensioni del pool di [!DNL Audience Manager] profili per una piattaforma di targeting e dimensioni del pubblico.</li></ul> |

## Confronto [!UICONTROL Customer] e [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Non devi confrontare le metriche [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] per determinare se una è più significativa dell&#39;altra. Si tratta di metriche separate, diverse e indipendenti. Come descritto nelle definizioni di cui sopra, ciascuno di questi è derivato da set di dati diversi. Per questo motivo, è necessario evitare di trarre conclusioni se una metrica è più grande dell&#39;altra. Tutto quello che si può dire quando si confrontano questi è che:

* [!UICONTROL Customer Addressable Audiences] è basato sulle [!UICONTROL trait] realizzazioni *per i tuoi dati* di prime parti. Questa metrica fornisce una visione ampia e completa dell&#39;integrazione con un partner dati.

* [!UICONTROL Segment Addressable Audiences] si basa sulle qualifiche del segmento *per i dati di prime parti, più i dati* di seconda e terza parte. Questa metrica fornisce una visualizzazione granulare e più accurata del [!UICONTROL addressable audiences] contenuto in una piattaforma di targeting.

## Cause di basse percentuali di corrispondenza per [!UICONTROL Addressable Audiences] {#low-match-rates}

Elementi comuni responsabili di basse percentuali di [!UICONTROL Addressable Audience] corrispondenza o discrepanze nei numeri segnalati.

| Causa | Descrizione |
|---|---|
| Traffico mobile | La maggior parte delle [!UICONTROL server-to-server] integrazioni si basa su processi di sincronizzazione facilitati da terze parti [!DNL cookies]. Tuttavia, gli ambienti mobili non utilizzano terze parti [!DNL cookies]. Di conseguenza, [!UICONTROL Addressable Audiences] i numeri possono sembrare bassi rispetto alle [!UICONTROL segment] dimensioni. <br><br>A partire da gennaio 2018, potete attivare il pubblico mobile nelle stesse [!DNL Google] e [!DNL Adobe Advertising Cloud] destinazioni configurate per il [!UICONTROL cookie-based] pubblico. Anche se questo significa che puoi inviare [!UICONTROL segments] con l’ID combinato [!DNL cookie] e mobile alle tue [!DNL Google] e [!DNL Advertising Cloud] destinazioni, ricorda che [!UICONTROL Addressable Audiences] solo la sovrapposizione tra [!DNL cookie] ID e destinazioni è visibile. [!DNL Audience Manager] invia il 100% del pubblico mobile a [!UICONTROL destinations], ma il pubblico mobile non viene misurato dalla [!UICONTROL Addressable Audience] metrica. <br><br>**Nota **: Ad esempio, prendete un esempio[!UICONTROL segment]con una popolazione di 1.000.000 persone. Se mappate questo[!UICONTROL segment]a una[!DNL Google]o[!DNL Adobe Advertising Cloud]destinazione, potreste vedere un[!UICONTROL Addressable Audience]di 700.000 dispositivi e un[!UICONTROL Match Rate]70%. L’iscrizione di 700.000 è costituita da[!DNL cookie]ID con cui è sincronizzata l’ID con l’ID[!UICONTROL destination]. In realtà[!UICONTROL Addressable Audience]potrebbe essere molto più alto, perché gli ID per dispositivi mobili indirizzabili non vengono visualizzati in questa metrica. |
| [!DNL Safari] Traffico | [!DNL Safari] blocchi di terze parti [!DNL cookies]. Questo impedisce [!DNL Audience Manager] la sincronizzazione degli ID con il [!UICONTROL destination]. Con l&#39;introduzione di [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), [!UICONTROL addressable audiences] non includerete [!DNL Safari] utenti. |
| Impression file multimediali tracciati | A causa delle procedure ottimali del server di annunci, le sincronizzazioni ID non vengono effettuate all’interno dei tag degli annunci. I clienti che fanno una grande quantità di pubblicità offsite non sincronizzeranno gli utenti con le integrazioni di terze parti in tali ambienti. Inoltre, un&#39;ampia quantità di dati raccolti sull&#39;impression dei supporti potrebbe ridurre [!UICONTROL addressable audience] i numeri. |

## Risoluzione dei problemi con [!UICONTROL Addressable Audiences] {#troubleshooting}

Oltre a riportare le percentuali di corrispondenza, potete anche utilizzare [!UICONTROL Addressable Audiences] come strumento di risoluzione dei problemi.

Ad esempio, supponiamo che tu invii un segmento a [!UICONTROL destination] e che [!UICONTROL destination] mostri numeri di reporting bassi. La verifica dei [!UICONTROL Addressable Audience] risultati mostrerà se si tratta di un problema tecnico o se si tratta solo di percentuali di corrispondenza basse. Un tasso di corrispondenza basso indica che [!UICONTROL destination] non è granché per i segmenti selezionati. Tuttavia, una differenza nei [!UICONTROL total addressable audience] numeri tra [!DNL Audience Manager] e [!UICONTROL destination] indica un problema tecnico di integrazione, sincronizzazione o altro. In questi casi, contatta il tuo account manager.
