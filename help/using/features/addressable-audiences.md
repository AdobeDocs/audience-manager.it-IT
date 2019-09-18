---
description: Panoramica della funzione Pubblico di riferimento e dei casi di utilizzo.
keywords: DIL
seo-description: Panoramica della funzione Pubblico di riferimento e dei casi di utilizzo.
seo-title: Pubblico di riferimento
solution: Audience Manager
title: Pubblico di riferimento
topic: API DIL
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Pubblico di riferimento {#addressable-audiences}

Panoramica della funzione Pubblico di riferimento e dei casi di utilizzo.

## Cos'è un pubblico indirizzabile? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] funzione mostra la sovrapposizione tra i tipi di pubblico visualizzati in tutte le proprietà in cui [!DNL Audience Manager] vengono raccolti i dati e la destinazione selezionata. Per comprendere meglio questo concetto, osservate l'illustrazione seguente. La sovrapposizione tra ciascun cerchio rappresenta i diversi tipi di pubblico indirizzabile.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Audience Manager indirizzabile a una destinazione</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di dispositivi che hanno interagito con tutti i clienti di Audience Manager a livello di piattaforma durante il periodo di look-back del report e che possono essere associati alla destinazione scelta. </p> <p>Questa metrica è utile perché mostra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Dimensione dell'audience indirizzabile totale che <span class="keyword"> Audience Manager</span> può raggiungere su una particolare destinazione di targeting. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Dimensioni del pool di profili <span class="keyword"> Audience Manager</span> per una piattaforma di targeting e dimensioni del pubblico. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico totale cliente</b> </p> </td> 
   <td colname="col2"> <p>Numero di dispositivi che hanno acquisito una caratteristica basata su regola sulle proprietà o una caratteristica integrata dai file offline durante la finestra di look-back. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Frequenza di corrispondenza pubblico indirizzabile</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Numero di sovrapposizioni di dispositivi che hanno realizzato una caratteristica basata su regola o una caratteristica integrata durante la finestra di look-back e dispositivi per i quali è presente una sincronizzazione ID con la destinazione scelta, indipendentemente dal tempo di sincronizzazione. </p> 
    </draft-comment> <p>Questa metrica rappresenta i dispositivi che: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Hanno realizzato una caratteristica basata su regola o integrata durante la finestra di look-back <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Sincronizza ID con la destinazione selezionata, indipendentemente dal tempo di sincronizzazione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasso di corrispondenza cliente</b> </p> </td> 
   <td colname="col2"> <p>Pubblico indirizzabile al cliente* Pubblico totale cliente espresso in %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Popolazione segmento totale</b> </p> </td> 
   <td colname="col2"> <p>Un conteggio di tutti i dispositivi che facevano parte del segmento durante il periodo di look-back del report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico indirizzabile al segmento</b> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che sono apparsi al segmento durante il periodo di look-back del report e hanno una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconda e terza parte, attraverso caratteristiche acquisite in <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a comprendere lo stato corrente dei tuoi segmenti. Questo perché la metrica <span class="wintitle"> Segmento Pubblico</span> indirizzabile rappresenta gli utenti che hanno soggiornato in un segmento nel corso del giorno precedente. Combinate questo con il fatto che <span class="keyword"> Audience Manager</span> aggiorna <span class="wintitle"> Pubblico</span> indirizzabile ogni giorno, combinando questa metrica e il periodo di lookback fornisce lo snapshot più aggiornato dei segmenti. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Frequenza corrispondenza segmento</b> </p> </td> 
   <td colname="col2"> <p>Pubblico indirizzabile segmento/popolazione segmento totale espressa in %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Interfaccia Pubblico Di Destinazione {#addressable-audience-interface}

La [!UICONTROL Addressable Audience] funzione trasforma questo concetto astratto in dati quantificabili. In [!DNL Audience Manager]questa funzione, il pubblico si sovrappone alle visualizzazioni dati che forniscono informazioni a colpo d'occhio insieme ai dati numerici in forma di tabella.

[!UICONTROL Addressable Audiences] si trova in **[!UICONTROL Audience Data > Destinations]**. Seleziona questa opzione **[!UICONTROL Integrated Platforms > Device-Based]** per visualizzare le metriche di audience indirizzabili.

![](assets/addressable-audiences-landing.png)

Le tre metriche visualizzate nella pagina di destinazione Pubblico di riferimento rappresentano:

| Metrica | Descrizione |
---------|----------|
| **Pubblico indirizzabile (dispositivi)** | Questa metrica rappresenta l'audience indirizzabile al cliente (descritta nella tabella precedente) *per gli ultimi 30 giorni.* |
| **Frequenza corrispondenza** | Questa metrica rappresenta la percentuale di corrispondenza dell'audience indirizzabile (descritta nella tabella precedente) *per gli ultimi 30 giorni*. |
| **Pubblico indirizzabile al ciclo di vita (dispositivi)** | Numero totale di dispositivi che hanno interagito con tutti i clienti di Audience Manager a livello di piattaforma durante il periodo di look-back del report e che possono essere associati a questa destinazione. Per ulteriori informazioni, consulta Metriche [a livello di](/help/using/features/addressable-audiences.md#platform-level-metrics) piattaforma. |

Fare clic sul nome di una destinazione server-to-server per visualizzare i dati del pubblico indirizzabile. Nota: questa funzione restituisce i dati solo per le destinazioni da server a server e l'accesso richiede le autorizzazioni dell'amministratore.

![](assets/addressableAudiences.png)

La revisione di questi dati può essere utile per:

* **** Previsione e pianificazione: i [!UICONTROL Segment Addressable Audience] dati forniscono maggiore granularità nei segmenti che pianificate di inviare a una destinazione per il targeting dell'audience e l'attivazione.

* **** Recensioni delle prestazioni: La [!UICONTROL Addressable Audiences] funzione è anche uno strumento per la risoluzione dei problemi. Consente di esaminare le prestazioni della campagna, comprendere il raggio d'azione della campagna e di effettuare verifiche incrociate con i partner di targeting/attivazione se non vengono visualizzati i risultati previsti.

### Prospettiva con dati di terze parti e implicazioni per le percentuali di corrispondenza

Prima di acquistare dati di terze parti per l'acquisizione di audience, i clienti possono convalidare la sovrapposizione con altri fornitori di dati. Questo può aiutarti a prendere una decisione informata prima di acquistare nuovi dati. Le sincronizzazioni ID per i dati di terze parti acquistati non si basano solo sulla sovrapposizione dei dati ma anche sulle impronte dei fornitori di terze parti con tutti gli altri [!DNL Audience Manager] clienti. Il tuo [!DNL Adobe] consulente può aiutarti a identificare ulteriori origini dati rilevanti per ottimizzare le campagne di ricerca.

### Utenti mobili e percentuali di corrispondenza

Ci sono degli spazi vuoti quando si tenta di connettere gli utenti delle app [!DNL Safari] o per dispositivi mobili in cui non sono presenti cookie di terze parti. Questo rende difficile la sincronizzazione degli utenti con alcuni partner, perché solo questi [!DNL Adobe] ID per i cookie di terze parti sincronizzati sono forniti nei registri di distribuzione dei supporti. Questo è un motivo per cui potresti vedere percentuali [di corrispondenza](../features/addressable-audiences.md#low-match-rates) basse per le tue destinazioni.

## Intervalli di date in Pubblico indirizzabile e Destinazioni {#date-ranges}

Leggi le sezioni seguenti per conoscere gli intervalli di date disponibili e come i dati scadono a ogni intervallo nei rapporti per un [!UICONTROL Addressable Audience] o [!UICONTROL Destination].

## Intervalli di date e Fusi orari disponibili {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

I report per le tue [!UICONTROL Addressable Audiences] e [Destinazioni](../features/destinations/destinations.md) utilizzano gli stessi intervalli di date. Le opzioni dell'intervallo di date includono:

* [!UICONTROL Last 1 Day] (Questo intervallo va da mezzanotte a mezzanotte del precedente periodo di 24 ore. Non si tratta di una metrica in tempo reale o corrente.
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Tutte le date e gli intervalli di date sono impostati nel fuso [!DNL UTC] orario. Consultate Fusi [temporali in Audience Manager](../reference/aam-time-zones.md).

## Dati in intervalli di date {#date-range-intervals}

Le [!UICONTROL Addressable Audience] metriche e [!UICONTROL Destination] restituiscono un conteggio di utenti univoci per l'intervallo di tempo selezionato. Ad esempio, un visitatore viene conteggiato una sola volta, anche se visita più volte il sito. La prima visita è la visita unica e viene registrata. Le visite successive sono visite di ritorno e non sono conteggiate perché non sono univoche.

Gli intervalli di date contengono i dati per l'intervallo di tempo selezionato o per la versione precedente. Inoltre, i dati si estinguono a partire da ogni intervallo di rapporto non appena il tempo passa. Ad esempio, supponiamo di vedere 2 visitatori dopo aver scelto l’ [!UICONTROL Last 30 Days] opzione. Nei rapporti, questi visitatori:

* *Saranno* inclusi nei risultati restituiti dagli intervalli di tempo più lunghi (60 giorni, 90 giorni e Durata).
* *Non verrà* incluso negli intervalli più brevi che precedono l' [!UICONTROL Last 30 Day] opzione (Corrente, 7 giorni e 14 giorni).

E, il giorno 31, questi visitatori arrivano solo nei 60 giorni, 90 giorni, e [!UICONTROL Lifetime] risultati. Sono invecchiati di 30 giorni. I visitatori non superano l' [!UICONTROL Lifetime] intervallo.

## Metriche indirizzabili dell'audience {#addressable-audience-metrics}

Questa sezione descrive i tipi di metriche forniti da [!UICONTROL Addressable Audiences].

### Metriche a livello di cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Queste metriche restituiscono i dati per le caratteristiche realizzate quando i visitatori arrivano sul tuo sito o quando invii file di dati in ingresso a [!DNL Audience Manager]. Queste metriche forniscono una visualizzazione completa delle dimensioni dell'audience per l'account.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico indirizzabile al cliente</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Numero di sovrapposizioni di dispositivi che hanno realizzato una caratteristica basata su regola o una caratteristica integrata durante la finestra di look-back e dispositivi per i quali è presente una sincronizzazione ID con la destinazione scelta, indipendentemente dal tempo di sincronizzazione. </p> 
    </draft-comment> <p>Questa metrica rappresenta i dispositivi che: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Hanno realizzato una caratteristica basata su regola o integrata durante la finestra di look-back <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Sincronizza ID con la destinazione selezionata, indipendentemente dal tempo di sincronizzazione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico totale cliente</b> </p> </td> 
   <td colname="col2"> <p>Numero di dispositivi che hanno acquisito una caratteristica basata su regola sulle proprietà o una caratteristica integrata dai file offline durante la finestra di look-back. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasso di corrispondenza cliente</b> </p> </td> 
   <td colname="col2"> <p>Pubblico indirizzabile al cliente* Pubblico totale cliente espresso in %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Metriche di corrispondenza a livello di segmento {#segment-level-metrics}

Queste metriche restituiscono i dati sull’appartenenza al segmento. che consentono di ottenere una visualizzazione più granulare e accurata delle dimensioni del pubblico per ciascun segmento.

>[!NOTE]
>
>Il modo in cui la finestra di look-back viene applicata a livello di segmento è diverso da quello a livello di cliente. I visitatori possono visitare il sito e realizzare una caratteristica 10 giorni fa, e da allora potrebbero qualificarsi per un segmento e abbandonarlo 2 giorni fa. Quando viene applicato l'aspetto di 7 giorni, questi visitatori vengono contati a livello di segmento ma non a livello di cliente.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico indirizzabile al segmento</b> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che sono apparsi al segmento durante il periodo di look-back del report e hanno una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e dati di seconda e terza parte, attraverso caratteristiche acquisite in <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorno, questa metrica può aiutarti a comprendere lo stato corrente dei tuoi segmenti. Questo perché la metrica <span class="wintitle"> Segmento Pubblico</span> indirizzabile rappresenta gli utenti che hanno soggiornato in un segmento nel corso del giorno precedente. Combinate questo con il fatto che <span class="keyword"> Audience Manager</span> aggiorna <span class="wintitle"> Pubblico</span> indirizzabile ogni giorno, combinando questa metrica e il periodo di lookback fornisce lo snapshot più aggiornato dei segmenti. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Popolazione segmento totale</b> </p> </td> 
   <td colname="col2"> <p>Un conteggio di tutti i dispositivi che facevano parte del segmento durante il periodo di look-back del report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Frequenza corrispondenza segmento</b> </p> </td> 
   <td colname="col2"> <p>Pubblico indirizzabile segmento/popolazione segmento totale espressa in %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Metriche a livello di piattaforma {#platform-level-metrics}

Questa metrica restituisce i dati sulle attività raccolte tra tutti i clienti di Audience Manager. Possono fornire una visione più ampia del pubblico del cliente rispetto ai clienti aggregati di Audience Manager.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico di riferimento di Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Numero totale di dispositivi che hanno interagito con tutti i clienti di Audience Manager a livello di piattaforma durante il periodo di look-back del report e che possono essere associati alla destinazione scelta. </p> <p>Questa metrica è utile perché mostra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Dimensione dell'audience indirizzabile totale che <span class="keyword"> Audience Manager</span> può raggiungere su una particolare destinazione di targeting. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Dimensioni del pool di profili <span class="keyword"> Audience Manager</span> per una piattaforma di targeting e dimensioni del pubblico. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Confronto tra pubblico indirizzabile a clienti e segmenti{#comparing-metrics}

Non devi confrontare le metriche [!UICONTROL Customer Addressable Audience] e [!UICONTROL Segment Addressable Audience] per determinare se una è più significativa dell'altra. Si tratta di metriche separate, diverse e indipendenti. Come descritto nelle definizioni di cui sopra, ciascuno di questi è derivato da set di dati diversi. Per questo motivo, è necessario evitare di trarre conclusioni se una metrica è più grande dell'altra. Tutto quello che si può dire quando si confrontano questi è che:

* [!UICONTROL Customer Addressable Audiences] è basato sulle realizzazioni *di caratteristiche per i tuoi dati* di prime parti. Questa metrica fornisce una visione ampia e completa dell'integrazione con un partner dati.

* [!UICONTROL Segment Addressable Audiences] si basa sulle qualifiche del segmento *per i dati di prime parti, più i dati* di seconda e terza parte. Questa metrica fornisce una visualizzazione granulare e più accurata dei tipi di pubblico indirizzabili in una piattaforma di targeting.

## Cause di percentuali di corrispondenza basse per il pubblico indirizzabile {#low-match-rates}

Elementi comuni responsabili di basse percentuali di [!UICONTROL Addressable Audience] corrispondenza o discrepanze nei numeri segnalati.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Causa </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Traffico mobile</b> </p> </td> 
   <td colname="col2"> <p>La maggior parte delle integrazioni server-to-server si basa su processi di sincronizzazione facilitati da cookie di terze parti. Tuttavia, gli ambienti mobili non utilizzano cookie di terze parti. Di conseguenza, i tuoi numeri Pubblico di riferimento potrebbero sembrare bassi rispetto alle dimensioni del segmento. </p> <p>A partire da gennaio 2018, potete attivare il pubblico mobile nelle stesse destinazioni Google e Adobe Advertising Cloud configurate per il pubblico basato su cookie. Anche se questo significa che puoi inviare segmenti con cookie combinati e iscrizione ID mobile alle tue destinazioni Google e Advertising Cloud, tieni presente che Pubblico pubblicitario visualizza solo la sovrapposizione tra ID cookie e destinazioni. Audience Manager invia il 100% del pubblico mobile alle destinazioni, ma il pubblico mobile non viene misurato dalla metrica Pubblico indirizzabile. </p> <p> <p><b>Nota</b>:  Ad esempio, prendete un segmento con una popolazione di 1.000.000. Se mappate questo segmento a una destinazione Google o Adobe Advertising Cloud, potreste visualizzare un pubblico indirizzabile di 700.000 dispositivi e un tasso di corrispondenza del 70%. L’iscrizione di 700.000 è costituita da ID di cookie con un ID sincronizzato con la destinazione. Il Pubblico di riferimento potrebbe, in realtà, essere molto più alto, perché gli ID mobili indirizzabili non vengono visualizzati in questa metrica. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traffico Safari</b> </p> </td> 
   <td colname="col2"> <p>Safari blocca i cookie di terze parti. Questo impedisce ad Audience Manager di sincronizzare gli ID con la destinazione. Con l'introduzione di <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, è possibile che le audience indirizzabili non includano gli utenti di Safari. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impression file multimediali tracciati</b> </p> </td> 
   <td colname="col2"> <p>A causa delle procedure ottimali del server di annunci, le sincronizzazioni ID non vengono effettuate all’interno dei tag degli annunci. I clienti che fanno una grande quantità di pubblicità offsite non sincronizzeranno gli utenti con le integrazioni di terze parti in tali ambienti. Inoltre, una grande quantità di dati raccolti sulle impression dei supporti potrebbe ridurre i numeri di destinatari indirizzabili. </p> </td>
  </tr> 
 </tbody> 
</table>

## Risoluzione dei problemi con i tipi di pubblico utilizzabili {#troubleshooting}

Oltre a supportare percentuali di corrispondenza, potete anche utilizzare [!UICONTROL Addressable Audiences] come strumento di risoluzione dei problemi.

<!-- addressable-audiences-troubleshooting.xml -->

Ad esempio, supponiamo che tu invii un segmento a una destinazione e che la destinazione mostri numeri di reporting bassi. La verifica dei [!UICONTROL Addressable Audience] risultati mostrerà se si tratta di un problema tecnico o se si tratta solo di percentuali di corrispondenza basse. Un tasso di corrispondenza basso indica che la destinazione non è poi così ottima per i segmenti selezionati. Tuttavia, una differenza nei numeri di audience totali indirizzabili tra Audience Manager e la destinazione indica un problema tecnico di integrazione, sincronizzazione o altro. In questi casi, contatta il tuo account manager.