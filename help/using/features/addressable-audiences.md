---
description: Panoramica della funzionalità e dei casi di utilizzo di Addressable Audience.
keywords: DIL
seo-description: Panoramica della funzionalità e dei casi di utilizzo di Addressable Audience.
seo-title: Pubblico di riferimento
solution: Audience Manager
title: Pubblico di riferimento
topic: API DIL
uuid: 3 eb 1335 a -6949-452 b-b 77 a -697 c 22856 cb 3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Pubblico indirizzabile {#addressable-audiences}

Panoramica della funzionalità e dei casi di utilizzo di Addressable Audience.

## Che cos&#39;è un pubblico indirizzabile? {#addressable-audience-description}

La [!UICONTROL Addressable Audiences] funzione mostra la sovrapposizione tra le audience che vedi tra tutte le proprietà in cui [!DNL Audience Manager] raccoglie i dati e la destinazione selezionata. Per comprendere questo concetto, consulta l&#39;illustrazione seguente. La sovrapposizione tra ciascun cerchio rappresenta i diversi tipi di pubblico indirizzabili.

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
   <td colname="col1"> <p> <b>Pubblico indirizzabile di Audience Manager per una destinazione</b> </p> </td> 
   <td colname="col2"> <p>Un totale di tutti i dispositivi che hanno interagito con tutti i clienti Audience Manager a livello di piattaforma durante il periodo di look-back del rapporto e che possono essere associati alla destinazione scelta. </p> <p>Questa metrica è utile perché mostra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> La dimensione del pubblico indirizzabile totale che <span class="keyword"> Audience Manager</span> può raggiungere su una particolare destinazione di targeting. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">La dimensione del pool di profilo <span class="keyword"> Audience Manager</span> per una piattaforma di targeting e la dimensione del loro pubblico. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico totale cliente</b> </p> </td> 
   <td colname="col2"> <p>Un numero di dispositivi che hanno realizzato una caratteristica basata su regole sulle proprietà o su una caratteristica registrata dai file offline durante la finestra di look-back. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasso di corrispondenza pubblico indirizzabile</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Un totale di sovrapposizioni di dispositivi che hanno generato una caratteristica basata su regole o una caratteristica registrata durante la finestra del look-back e i dispositivi che si sincronizzano con la destinazione selezionata, indipendentemente dal tempo di sincronizzazione. </p> 
    </draft-comment> <p>Questa metrica rappresenta i dispositivi che: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">È stata creata una caratteristica basata su regole o su una caratteristica registrata durante la finestra di look-back <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Disponete di una sincronizzazione ID con la destinazione selezionata, indipendentemente dal tempo di sincronizzazione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasso di corrispondenza cliente</b> </p> </td> 
   <td colname="col2"> <p>Pubblico indirizzabile cliente‡ Pubblico totale cliente espresso come percentuale. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Popolazione segmento totale</b> </p> </td> 
   <td colname="col2"> <p>Un conteggio di tutti i dispositivi che erano membri del segmento durante il periodo di look-back. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico indirizzabile segmento</b> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno partecipato al segmento durante il periodo di look-back e che dispongono di una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e di terze parti e di terze parti, tramite tratti acquisiti in <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorni, questa metrica può aiutarti a capire lo stato corrente dei tuoi segmenti. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasso di corrispondenza segmento</b> </p> </td> 
   <td colname="col2"> <p>Segmento indirizzabile segmento ÷ Popolazione segmento totale espressa come percentuale. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Interfaccia pubblico indirizzabile {#addressable-audience-interface}

La [!UICONTROL Addressable Audience] funzione trasforma questo concetto abstract in dati quantificabili. In [!DNL Audience Manager], questa funzione visualizza la sovrapposizione dell&#39;audience con visualizzazioni dati che forniscono informazioni puntuali insieme ai dati numerici in forma di tabella.

[!UICONTROL Addressable Audiences] si trova in **[!UICONTROL Audience Data > Destinations]**. Seleziona **[!UICONTROL Integrated Platforms > Device-Based]** per visualizzare metriche di pubblico indirizzabili.

![](assets/addressable-audiences-landing.png)

Le tre metriche che puoi vedere sulla pagina di destinazione Pubblico indirizzabile rappresentano:

| Metrica | Descrizione |
---------|----------|
| **Pubblico indirizzabile (dispositivi)** | Questa metrica rappresenta il pubblico indirizzabile cliente (descritto nella tabella sopra) *per gli ultimi 30 giorni.* |
| **Tasso di corrispondenza** | Questa metrica rappresenta il tasso di corrispondenza pubblico indirizzabile (descritto nella tabella sopra) *per gli ultimi 30 giorni*. |
| **Pubblico indirizzabile del ciclo di vita (dispositivi)** | Un totale di tutti i dispositivi che hanno interagito con tutti i clienti Audience Manager a livello di piattaforma durante il periodo di look-back del rapporto e che potrebbero essere associati a questa destinazione. Per [ulteriori informazioni, vedi Metriche](/help/using/features/addressable-audiences.md#platform-level-metrics) a livello di piattaforma. |

Fai clic sul nome di una destinazione server-to-server per visualizzare i dati di pubblico indirizzabili. Nota, questa funzione restituisce solo i dati per le destinazioni server-to-server e l&#39;accesso richiede autorizzazioni amministratore.

![](assets/addressableAudiences.png)

La revisione di questi dati può essere utile per:

* **Previsioni e pianificazione:**[!UICONTROL Segment Addressable Audience] I dati offrono maggiore granularità nei segmenti che si intende inviare a una destinazione per targeting e attivazione dell&#39;audience.

* **Recensioni sulle prestazioni:** La [!UICONTROL Addressable Audiences] funzione è anche uno strumento di risoluzione dei problemi. Consente di analizzare le prestazioni delle campagne, comprendere la portata della campagna e passare con i partner di targeting/attivazione se non si vedono i risultati previsti.

### Pianificazione con dati e implicazioni di terze parti per percentuali di corrispondenza

Prima di acquistare dati di terze parti per l&#39;acquisizione di audience, i clienti possono convalidare la sovrapposizione con altri provider di dati. Questo può aiutarti a prendere una decisione informata prima di acquistare nuovi dati. Le sincronizzazioni ID per i dati di terze parti acquistati dipendono non solo dalla sovrapposizione dei dati, ma anche da quelle dei fornitori di terze parti con tutti gli altri [!DNL Audience Manager] clienti. Il [!DNL Adobe] tuo consulente può aiutarti a identificare ulteriori origini dati pertinenti per ottimizzare la pianificazione delle campagne.

### Utenti e percentuali di corrispondenza

Esistono degli spazi vuoti quando si tenta di connettersi [!DNL Safari] o creare utenti di app mobili in cui non sono presenti cookie di terze parti. Questo rende difficile sincronizzare gli utenti con alcuni partner perché solo tali [!DNL Adobe] ID per i cookie di terze parti sincronizzati sono forniti nei registri di consegna dei supporti. Questo è un motivo per cui potreste vedere [percentuali di corrispondenza basse](../features/addressable-audiences.md#low-match-rates) per le destinazioni.

## Intervalli di date in audience e destinazioni utilizzabili {#date-ranges}

Leggi le sezioni di seguito per gli intervalli di date disponibili e come i dati vengono inclusi in ogni intervallo nei rapporti per un o [!UICONTROL Addressable Audience][!UICONTROL Destination].

## Intervalli di date e fuso orario disponibili {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

I rapporti per le destinazioni [!UICONTROL Addressable Audiences][usano gli](../features/destinations/destinations.md) stessi intervalli di intervallo di date. Le opzioni dell&#39;intervallo di date includono:

* [!UICONTROL Last 1 Day] (L&#39;intervallo va da Mezzanotte a Mezzanotte del precedente periodo di 24 ore. Non si tratta di una metrica in tempo reale o corrente.
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Tutte le date e gli intervalli di date sono impostati nel [!DNL UTC] fuso orario. Consultate [Fuso orario in Audience Manager](../reference/aam-time-zones.md).

## Dati intervalli intervalli di date {#date-range-intervals}

Le [!UICONTROL Addressable Audience][!UICONTROL Destination] metriche restituiscono un numero di utenti univoci per l&#39;intervallo di tempo selezionato. Ad esempio, un visitatore viene conteggiato solo una volta, anche se accedono più volte al sito. La prima visita è l&#39;unica visita e viene registrata. Le visite successive restituiscono visite e non vengono conteggiate perché non sono univoche.

Gli intervalli di date contengono dati per l&#39;intervallo di tempo selezionato o precedente. Inoltre, i dati risalgono a ciascun intervallo di report durante la trasmissione del tempo. Ad esempio, supponiamo che vengano mostrati 2 visitatori dopo aver scelto l [!UICONTROL Last 30 Days] &#39;opzione. Nei rapporti, questi visitatori:

* *Verrà* incluso nei risultati restituiti entro intervalli lunghi (60 giorni, 90 giorni e Lifetime).
* *Non verrà* incluso negli intervalli più brevi che precedono l [!UICONTROL Last 30 Day] &#39;opzione (corrente, 7 giorni e 14 giorni).

E, nel giorno 31, questi visitatori vengono visualizzati solo nel giorno 60, 90 giorno e [!UICONTROL Lifetime] nei risultati. Hanno invecchiato con un intervallo di 30 giorni. I visitatori non vanno oltre l&#39; [!UICONTROL Lifetime] intervallo.

## Metriche pubblico indirizzabili {#addressable-audience-metrics}

In questa sezione sono descritti i tipi di metriche forniti [!UICONTROL Addressable Audiences].

### Metriche a livello di cliente {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL Audience Manager]. Queste metriche forniscono una visualizzazione completa delle dimensioni del pubblico per l&#39;account.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico indirizzabile cliente</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Un totale di sovrapposizioni di dispositivi che hanno generato una caratteristica basata su regole o una caratteristica registrata durante la finestra del look-back e i dispositivi che si sincronizzano con la destinazione selezionata, indipendentemente dal tempo di sincronizzazione. </p> 
    </draft-comment> <p>Questa metrica rappresenta i dispositivi che: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">È stata creata una caratteristica basata su regole o su una caratteristica registrata durante la finestra di look-back <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Disponete di una sincronizzazione ID con la destinazione selezionata, indipendentemente dal tempo di sincronizzazione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico totale cliente</b> </p> </td> 
   <td colname="col2"> <p>Un numero di dispositivi che hanno realizzato una caratteristica basata su regole sulle proprietà o su una caratteristica registrata dai file offline durante la finestra di look-back. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasso di corrispondenza cliente</b> </p> </td> 
   <td colname="col2"> <p>Pubblico indirizzabile cliente‡ Pubblico totale cliente espresso come percentuale. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Metriche corrispondenza a livello di segmento {#segment-level-metrics}

Queste metriche restituiscono dati sull&#39;appartenenza al segmento. Consentono di fornire una vista più granulare e precisa della dimensione del pubblico per ogni segmento.

>[!NOTE]
>
>Il modo in cui la finestra di look-back viene applicata a livello di segmento è diverso da quello a livello del cliente. I visitatori possono visitare il sito e realizzare una caratteristica 10 giorni fa e possono qualificarsi per un segmento da quel momento in poi abbandonato dal segmento 2 giorni fa. Quando viene applicato il look-back di 7 giorni, questi visitatori saranno conteggiati a livello di segmento ma non a livello del cliente.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico indirizzabile segmento</b> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno partecipato al segmento durante il periodo di look-back e che dispongono di una sincronizzazione ID attiva sul sito. I segmenti possono includere dati di prime parti e di terze parti e di terze parti, tramite tratti acquisiti in <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Suggerimento: Se utilizzata con il periodo di look-back di 1 giorni, questa metrica può aiutarti a capire lo stato corrente dei tuoi segmenti. This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Popolazione segmento totale</b> </p> </td> 
   <td colname="col2"> <p>Un conteggio di tutti i dispositivi che erano membri del segmento durante il periodo di look-back. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tasso di corrispondenza segmento</b> </p> </td> 
   <td colname="col2"> <p>Segmento indirizzabile segmento ÷ Popolazione segmento totale espressa come percentuale. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Metriche a livello di piattaforma {#platform-level-metrics}

Questa metrica restituisce dati sulle attività raccolte in tutti i clienti di Audience Manager. Possono fornire una visualizzazione più ampia dei destinatari del cliente rispetto ai clienti aggregati di Audience Manager.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Pubblico indirizzabile di Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Un totale di tutti i dispositivi che hanno interagito con tutti i clienti Audience Manager a livello di piattaforma durante il periodo di look-back del rapporto e che possono essere associati alla destinazione scelta. </p> <p>Questa metrica è utile perché mostra: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> La dimensione del pubblico indirizzabile totale che <span class="keyword"> Audience Manager</span> può raggiungere su una particolare destinazione di targeting. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">La dimensione del pool di profilo <span class="keyword"> Audience Manager</span> per una piattaforma di targeting e la dimensione del loro pubblico. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Confronto dei tipi di pubblico indirizzabili tra clienti e segmenti{#comparing-metrics}

Non dovresti confrontare le [!UICONTROL Customer Addressable Audience][!UICONTROL Segment Addressable Audience] metriche per determinare se uno è più significativo dell&#39;altro. Queste metriche separate, diverse e indipendenti. Come descritto nelle definizioni sopra, ciascuna di esse viene derivata da set di dati diversi. In tal caso, evitate di derivare conclusioni se una metrica è più grande dell&#39;altro. Quando confrontate questi è tutto ciò che potete dire:

* [!UICONTROL Customer Addressable Audiences] si basa sulle realioni delle caratteristiche *per i tuoi dati di prime parti*. Questa metrica fornisce una panoramica completa e completa dell&#39;integrazione con un partner dati.

* [!UICONTROL Segment Addressable Audiences] si basa sulle qualifiche del segmento *per i dati di prime parti, oltre che per i dati secondo e terzo*. Questa metrica fornisce una visualizzazione granulare e più precisa dei tipi di pubblico indirizzabili in una piattaforma di targeting.

## Cause di percentuali di corrispondenza basse per i tipi di pubblico utilizzabili {#low-match-rates}

Elementi comuni responsabili per percentuali di [!UICONTROL Addressable Audience] corrispondenza ridotte o discrepanze nei numeri segnalati.

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
   <td colname="col2"> <p>La maggior parte delle integrazioni server-to-server si basano su processi di sincronizzazione facilitate dai cookie di terze parti. Tuttavia, gli ambienti mobili non utilizzano cookie di terze parti. Di conseguenza, i numeri di Pubblico indirizzabili potrebbero apparire bassi rispetto alle dimensioni del segmento. </p> <p>A partire da gennaio 2018, potete attivare i tipi di pubblico mobili nelle stesse destinazioni Google e Adobe Advertising Cloud configurate per i tipi di pubblico basati su cookie. Se questo significa che puoi inviare segmenti con cookie combinato e l'iscrizione ID mobile alle destinazioni Google e Advertising Cloud, tieni presente che l'audience di riferimento visualizza solo la sovrapposizione tra ID cookie e destinazioni. Audience Manager invia il 100% dei tipi di pubblico per dispositivi mobili alle destinazioni, ma le audience per dispositivi mobili non sono misurate dalla metrica Pubblico indirizzabile. </p> <p> <p><b>Nota</b>: Ad esempio, prendi un segmento con una popolazione di 1,000,000. Se mappate questo segmento su una destinazione Google o Adobe Advertising Cloud, potrebbe essere visualizzato un pubblico indirizzabile di 700,000 dispositivi e una percentuale di corrispondenza pari a 70%. L'iscrizione a 700,000 è composta da ID cookie con una sincronizzazione ID con la destinazione. L'audience indirizzabile potrebbe, in realtà, essere molto più alta, perché gli ID mobili indirizzabili non vengono visualizzati in questa metrica. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traffico Safari</b> </p> </td> 
   <td colname="col2"> <p>Safari blocca i cookie di terze parti. In questo modo Audience Manager non sincronizza gli ID con la destinazione. Con l'introduzione <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> di ITP 2.0</a>, i tipi di pubblico indirizzabili non devono includere utenti Safari. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Impressioni multimediali tracciate</b> </p> </td> 
   <td colname="col2"> <p>A causa delle best practice del server di annunci, le sincronizzazioni ID non vengono effettuate all'interno di tag pubblicitari. I clienti che eseguono una grande quantità di pubblicità offsite non sincronizzeranno gli utenti con integrazioni di terze parti in tali ambienti. Inoltre, una grande quantità di dati relativi alle impression multimediali raccolti potrebbe ridurre i numeri di pubblico indirizzabili. </p> </td>
  </tr> 
 </tbody> 
</table>

## Risoluzione dei problemi relativi ai tipi di pubblico utilizzabili {#troubleshooting}

Oltre a raggiungere percentuali di corrispondenza, puoi anche usare [!UICONTROL Addressable Audiences] come strumento di risoluzione dei problemi.

<!-- addressable-audiences-troubleshooting.xml -->

Ad esempio, supponiamo che tu mandi un segmento a una destinazione e che la destinazione mostri numeri di reporting ridotti. Il controllo [!UICONTROL Addressable Audience] dei risultati vi mostrerà se si tratta di un problema tecnico o di percentuali di corrispondenza ridotte. Una frequenza di corrispondenza bassa indica che la destinazione non è tutto molto grande per i segmenti selezionati. Tuttavia, una differenza nel numero totale dei destinatari indirizzabili tra Audience Manager e la destinazione indica un&#39;integrazione, la sincronizzazione o un altro problema tecnico. In questi casi, contattate il responsabile commerciale.