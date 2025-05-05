---
description: Utilizza le destinazioni basate sulle persone per inviare segmenti di pubblico primario ad ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un’entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come Facebook e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato.
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Panoramica e casi d’uso
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Panoramica e casi d’uso {#overview-use-cases}

Utilizza [!DNL People-Based Destinations] per inviare segmenti di pubblico primario ad ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un’entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come [!DNL Facebook] e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato.

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

## Panoramica {#overview}

[!DNL People-Based Destinations] consente di applicare la segmentazione ai dati online e offline per creare segmenti di pubblico in base a [identificatori con hash](people-based-destinations-prerequisites.md#hashing-requirements), ad esempio indirizzi e-mail. Quindi puoi inviare questi segmenti ai &quot;giardini murati&quot; come [!DNL Facebook], dove puoi indirizzare il tuo pubblico sulle piattaforme social. [!DNL People-Based Destinations] può aiutarti a:

* Eseguire il targeting di tipi di pubblico offline e online in piattaforme come [!DNL Facebook], in base a indirizzi e-mail con hash;
* Completa le attuali capacità di Audience Manager di targeting di dispositivi e cookie;
* Eliminazione dei costi associati alle soluzioni di onboarding dei dati di terze parti;
* Eliminare i costi associati allo sviluppo di flussi di lavoro personalizzati per l’onboarding dei dati;
* Tipi di pubblico target in ambienti senza cookie;
* Puoi indirizzare l’attività a tipi di pubblico deduplicando indirizzi e-mail con hash che corrispondono a ID cliente.

È possibile utilizzare [!DNL People-Based Destinations] per segmentare ed eseguire il targeting di clienti di alto valore che potrebbero non visitare il sito Web o interrompere il targeting di quelli che si sono già convertiti offline. Inoltre, puoi sfruttare [!DNL Profile Merge Rules] per combinare i tuoi dati offline di prime parti con i tuoi dati online di prime parti, inclusi i dati dei clienti provenienti da altre soluzioni Adobe Experience Cloud, per ottimizzare le tue attività pubblicitarie sui social media.

![pbd-overview](assets/pbd-overview.png)

## Disponibilità {#availability}

[!DNL People-Based Destinations] è un&#39;integrazione Audience Manager premium. Contatta il tuo rappresentante di Adobe per approfittare di questa funzionalità premium.

## Perché utilizzare [!UICONTROL People-Based Destinations] {#why-use}

**Fornisci ai tuoi clienti esperienze cross-channel coerenti gestendo l&#39;intera segmentazione del pubblico dall&#39;interno di Audience Manager.**

La mancata attivazione dei segmenti di pubblico nei canali basati sulle persone tramite Audience Manager porta a esperienze scollegate tra ciò che i clienti vedono quando visitano il tuo sito web e ciò che vedono, ad , nei loro feed [!DNL Facebook]. Con un targeting coerente tra i canali, puoi aumentare i ricavi degli annunci e al contempo ottimizzare la spesa pubblicitaria.

**Raggiungi il pubblico nei canali basati sulle persone senza la necessità di una soluzione di onboarding dei dati dedicata o flussi di lavoro personalizzati per inviare il pubblico.**

Il modo più &quot;tradizionale&quot; di indirizzare il pubblico tra i canali basati sulle persone implica la necessità di esportare i dati del cliente in un formato accettato dalla piattaforma su cui desideri pubblicizzare, e quindi di utilizzare il metodo di onboarding dei dati dedicato della piattaforma per portare i dati del cliente all’account dell’inserzionista. Questo è tutto il lavoro manuale che devi fare per ogni piattaforma che desideri pubblicizzare. Inoltre, piattaforme diverse possono avere requisiti di formato dei dati diversi, rendendo il processo ancora più noioso.

![pbd-overview](assets/pbd-diagram.png)

Tramite [!DNL People-Based Destinations], Audience Manager ti consente di centralizzare i dati dei clienti, creare segmenti di pubblico e attivarli su più canali basati sulle persone. Puoi eseguire questa operazione dall’interfaccia utente di Audience Manager, evitando il lavoro aggiuntivo di caricamento manuale dei dati su ogni piattaforma, risparmiando tempo prezioso.

**Crea e attiva segmenti di pubblico da profili esclusivamente offline.**

[!DNL People-Based Destinations] risolve il problema che in precedenza, era possibile attivare i segmenti di pubblico solo in base all&#39;attività del dispositivo. Con [!DNL People-Based Destinations], puoi creare segmenti da dati puramente offline del tuo [!DNL CRM] e attivarli nelle piattaforme basate sulle persone. Inoltre, puoi correlare i dati offline con i dati del dispositivo già presenti in Audience Manager.

**Utilizza la governance dei dati e i controlli sulla privacy di Audience Manager per gestire in modo sicuro i dati dei clienti.**

[!DNL People-Based Destinations] richiede l&#39;utilizzo solo di identificatori con hash irreversibili. Questo riduce il rischio associato al caricamento manuale dei dati dei clienti in ogni piattaforma di destinazione.

Guarda il video seguente per una panoramica del flusso di dati quando utilizzi [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/34905?captions=ita)

## Casi d&#39;uso {#use-cases}

Per aiutarti a capire meglio come e quando utilizzare [!DNL People-Based Destinations], ecco due casi d&#39;uso di Audience Manager che i clienti possono risolvere utilizzando questa funzione.

### #1 del caso d’uso {#use-case-1}

Un rivenditore online desidera raggiungere i clienti esistenti tramite piattaforme social e mostrare loro offerte personalizzate basate sui loro ordini precedenti. Con [!DNL People-Based Destinations], il rivenditore online può acquisire gli indirizzi e-mail con hash dal proprio [!DNL CRM] per Audience Manager, creare segmenti dai propri dati offline e inviare questi segmenti alle piattaforme social sulle quali desidera fare pubblicità, ottimizzando le proprie spese pubblicitarie.

### #2 del caso d’uso {#use-case-2}

Una compagnia aerea ha diversi livelli di clienti (Bronzo, Argento e Oro) e vuole fornire a ciascuno di questi livelli offerte personalizzate tramite piattaforme social. L’azienda utilizza Audience Manager per analizzare l’attività dei clienti sul sito web. Tuttavia, non tutti i clienti utilizzano l&#39;app mobile della compagnia aerea e alcuni di loro non hanno effettuato l&#39;accesso al sito web della compagnia. Gli unici identificatori di questi clienti di cui dispone l’azienda sono gli ID iscrizione e gli indirizzi e-mail.

Per eseguire il targeting tra social media e canali simili basati su persone, è possibile integrare i dati del cliente dal proprio [!DNL CRM] in Audience Manager, utilizzando come identificatori gli indirizzi e-mail con hash.

Successivamente, possono combinare i propri dati offline con le caratteristiche delle attività online esistenti, per creare nuovi segmenti di pubblico a cui rivolgersi tramite [!DNL People-Based Destinations].
