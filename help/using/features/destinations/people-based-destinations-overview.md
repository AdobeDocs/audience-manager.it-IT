---
description: 'Utilizza destinazioni basate sulle persone per inviare segmenti di pubblico di prime parti agli ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un''entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come Facebook e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato. '
seo-description: 'Utilizza destinazioni basate sulle persone per inviare segmenti di pubblico di prime parti agli ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un''entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come Facebook e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato.  '
seo-title: Casi di utilizzo e panoramica delle destinazioni basate sulle persone
solution: Audience Manager
title: Casi di utilizzo e panoramica
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 0%

---


# Casi di utilizzo e panoramica {#overview-use-cases}

Da utilizzare [!DNL People-Based Destinations] per inviare segmenti di audience di prime parti ad ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un&#39;entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come [!DNL Facebook]e altre piattaforme che si affidano agli account dei clienti per personalizzare il contenuto visualizzato.

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

## Panoramica {#overview}

[!DNL People-Based Destinations] consente di applicare la segmentazione ai dati online e offline per creare segmenti di pubblico basati su identificatori [](people-based-destinations-prerequisites.md#hashing-requirements)con hash, ad esempio indirizzi e-mail o numeri di telefono. Quindi, puoi inviare questi segmenti a &quot;giardini murati&quot; come [!DNL Facebook], ad esempio, dove puoi rivolgerti al pubblico sulle piattaforme social. [!DNL People-Based Destinations] può essere utile:

* tipi di pubblico Target offline e online in piattaforme come [!DNL Facebook], ad esempio, basati su indirizzi e-mail con hash;
* Completare le capacità di targeting dei dispositivi e dei cookie esistenti di  Audience Manager;
* eliminare i costi associati alle soluzioni di registrazione dei dati di terze parti;
* Eliminazione dei costi associati allo sviluppo di flussi di lavoro personalizzati di onboarding dei dati;
* audience Target in ambienti senza cookie;
* Tipi di pubblico Target deduplicando indirizzi e-mail con hash corrispondenti agli ID cliente.

Potete utilizzare [!DNL People-Based Destinations] per segmentare e mirare i clienti di alto valore che non hanno visitato il vostro sito Web o per interrompere il targeting per coloro che hanno già convertito offline. Inoltre, puoi sfruttare [!DNL Profile Merge Rules] per combinare i tuoi dati di prime parti offline con i dati di prime parti online, inclusi i dati dei clienti provenienti da altre soluzioni Adobe Experience Cloud, per ottimizzare le attività pubblicitarie sui social media.

![pbd-overview](assets/pbd-overview.png)

## Disponibilità {#availability}

[!DNL People-Based Destinations] è un&#39;integrazione premium  Audience Manager. Contattate il vostro rappresentante Adobe per sfruttare questa funzione premium.

## Perché dovresti usare [!UICONTROL People-Based Destinations] {#why-use}

**Offri ai tuoi clienti esperienze multicanale coerenti gestendo l&#39;intera segmentazione dell&#39;audience dall&#39;interno  Audience Manager.**

Non attivando i segmenti di pubblico nei canali basati sulle persone attraverso  Audience Manager, i clienti possono vedere esperienze diverse tra ciò che vedono durante la visita al sito Web e ciò che vedono, ad esempio, nei propri [!DNL Facebook] feed. Avere un targeting coerente tra i canali può aumentare le entrate degli annunci e ottimizzare al contempo le spese degli annunci.

**Raggiungete audience nei canali basati sulle persone senza la necessità di una soluzione di inserimento dati dedicata o di flussi di lavoro personalizzati per inviare audience.**

Il modo più &quot;tradizionale&quot; di targeting dei tipi di pubblico tra canali basati sulle persone implica la necessità di esportare i dati dei clienti in un formato accettato dalla piattaforma su cui desiderate pubblicizzare i dati, e quindi l&#39;utilizzo del metodo di configurazione dei dati dedicato della piattaforma per portare i dati dei clienti al vostro account advertiser. Questo è tutto il lavoro manuale che dovete fare per ogni piattaforma su cui desiderate pubblicizzare. Inoltre, piattaforme diverse possono avere requisiti di formato dati diversi, rendendo il processo ancora più noioso.

![pbd-overview](assets/pbd-diagram.png)

Grazie a [!DNL People-Based Destinations]Audience Manager è possibile centralizzare i dati dei clienti, creare segmenti di pubblico e attivarli su più canali basati su persone. È possibile farlo dall&#39;interfaccia utente  Audience Manager, evitando il lavoro aggiuntivo di caricamento manuale dei dati su ogni piattaforma, risparmiando tempo prezioso nel processo.

**Crea e attiva segmenti di pubblico da profili puramente offline.**

[!DNL People-Based Destinations] risolvi il problema che in precedenza era possibile attivare solo segmenti di pubblico in base all&#39;attività del dispositivo. Con [!DNL People-Based Destinations], puoi creare segmenti da dati puramente offline personali [!DNL CRM]e attivarli in piattaforme basate su persone. Inoltre, potete correlare i dati offline con quelli del dispositivo già in uso in  Audience Manager.

**Sfruttare la governance dei dati e i controlli sulla privacy  Audience Manager per gestire in modo sicuro i dati dei clienti.**

[!DNL People-Based Destinations] richiede che vengano utilizzati solo identificatori con hash irreversibile. Questo riduce i rischi associati al caricamento manuale dei dati dei clienti in ciascuna piattaforma di destinazione.

Guardate il video seguente per una panoramica del flusso di dati durante l’utilizzo [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casi d&#39;uso {#use-cases}

Per comprendere meglio come e quando utilizzare [!DNL People-Based Destinations], ecco due esempi di casi d’uso che  clienti Audience Manager possono risolvere utilizzando questa funzione.

### Use Case #1 {#use-case-1}

Un rivenditore online vuole raggiungere i clienti esistenti tramite piattaforme social e mostrare loro offerte personalizzate in base ai loro ordini precedenti. Con [!DNL People-Based Destinations], il rivenditore online può trasferire indirizzi e-mail con hash dai propri [!DNL CRM] a  Audience Manager, creare segmenti dai propri dati offline e inviare questi segmenti alle piattaforme social su cui vuole pubblicizzare, ottimizzando le spese pubblicitarie.

### Use Case #2 {#use-case-2}

Una compagnia aerea ha diversi livelli di clienti (Bronzo, Argento e Oro) e vuole fornire a ciascuno dei livelli offerte personalizzate tramite piattaforme social. L&#39;azienda utilizza  Audience Manager per analizzare l&#39;attività dei clienti sul sito Web. Tuttavia, non tutti i clienti utilizzano l&#39;app mobile della compagnia aerea e alcuni di essi non hanno effettuato l&#39;accesso al sito Web della società. Gli unici identificatori della società per questi clienti sono gli ID iscrizione e gli indirizzi e-mail.

Per utilizzarli tra i social media e canali simili basati su persone, possono tenere a bordo i dati dei clienti dal [!DNL CRM] proprio Audience Manager , utilizzando gli indirizzi e-mail con hash come identificatori.

In seguito, possono combinare i dati offline con le caratteristiche delle attività online esistenti, per creare nuovi segmenti di pubblico ai quali indirizzare [!DNL People-Based Destinations].
