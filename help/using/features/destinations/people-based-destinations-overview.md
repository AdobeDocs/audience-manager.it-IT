---
description: 'Utilizza destinazioni basate sulle persone per inviare segmenti di pubblico di prime parti agli ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un''entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come Facebook e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato. '
seo-description: 'Utilizza destinazioni basate sulle persone per inviare segmenti di pubblico di prime parti agli ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un''entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come Facebook e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato.  '
seo-title: Casi di utilizzo e panoramica delle destinazioni basate sulle persone
solution: Audience Manager
title: Casi di utilizzo e panoramica
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Casi di utilizzo e panoramica {#overview-use-cases}

Da utilizzare [!DNL People-Based Destinations] per inviare segmenti di audience di prime parti ad ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un'entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come [!DNL Facebook]e altre piattaforme che si affidano agli account dei clienti per personalizzare il contenuto visualizzato.

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nothing contained herein is legal advice. Please consult your own legal counsel for legal guidance.

## Panoramica {#overview}

[!DNL People-Based Destinations] enable you to apply segmentation on online and offline data to create audience segments based on hashed identifiers, such as email addresses or phone numbers. [](people-based-destinations-prerequisites.md#hashing-requirements) Then, you can send these segments to "walled gardens" such as , where you can target your audience on the social platforms. [!DNL Facebook] [!DNL People-Based Destinations] can help you:

* Target offline and online audiences in platforms such as [!DNL Facebook], based on hashed email addresses;
* Complement existing device and cookie targeting capabilities of Audience Manager;
* Eliminate costs associated with third-party data onboarding solutions;
* Eliminate costs associated with developing custom data onboarding workflows;
* Target audiences in cookie-less environments;
* Target audiences by deduplicating email addresses matched to customer IDs.

You can use  to segment and target high value customers who may not visited your website, or stop targeting those who have already converted offline. [!DNL People-Based Destinations] Additionally, you can leverage  to combine your offline first-party data with your online first-party data, including customer data from other Adobe Experience Cloud solutions, to optimize your social media advertising efforts.[!DNL Profile Merge Rules]

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] è un’integrazione premium di Audience Manager. Contattate il vostro rappresentante Adobe per sfruttare questa funzione premium.

## Perché Utilizzare Le Destinazioni Basate Sulle Persone {#why-use}

**Fornisci ai tuoi clienti esperienze multicanale coerenti gestendo l'intera segmentazione dell'audience da Audience Manager.**

Se non attivi i segmenti di pubblico nei canali basati sulle persone tramite Audience Manager, puoi creare esperienze diverse tra ciò che i clienti vedono quando visitano il tuo sito Web e ciò che vedono, ad esempio, nei loro [!DNL Facebook] feed. Avere un targeting coerente tra i canali può aumentare le entrate degli annunci e ottimizzare al contempo le spese degli annunci.

**Raggiungete audience nei canali basati sulle persone senza la necessità di una soluzione di inserimento dati dedicata o di flussi di lavoro personalizzati per inviare audience.**

Il modo più "tradizionale" di targeting dei tipi di pubblico tra canali basati sulle persone implica la necessità di esportare i dati dei clienti in un formato accettato dalla piattaforma su cui desiderate pubblicizzare i dati, e quindi l'utilizzo del metodo di configurazione dei dati dedicato della piattaforma per portare i dati dei clienti al vostro account advertiser. Questo è tutto il lavoro manuale che dovete fare per ogni piattaforma su cui desiderate pubblicizzare. Inoltre, piattaforme diverse possono avere requisiti di formato dati diversi, rendendo il processo ancora più noioso.

![pbd-overview](assets/pbd-diagram.png)

Mediante [!DNL People-Based Destinations]Audience Manager puoi centralizzare i dati dei clienti, creare segmenti di pubblico e attivarli tra più canali basati su persone. Puoi farlo direttamente dall’interfaccia utente di Audience Manager, evitando il lavoro aggiuntivo di caricamento manuale dei dati su ciascuna piattaforma, risparmiando tempo prezioso nel processo.

**Crea e attiva segmenti di pubblico da profili puramente offline.**

[!DNL People-Based Destinations] risolvi il problema che in precedenza era possibile attivare solo segmenti di pubblico in base all'attività del dispositivo. Con [!DNL People-Based Destinations], puoi creare segmenti da dati puramente offline personali [!DNL CRM]e attivarli in piattaforme basate su persone. Inoltre, potete correlare i dati offline con quelli del dispositivo già in uso in Audience Manager.

**Sfruttate la governance dei dati e i controlli sulla privacy di Audience Manager per gestire in modo sicuro i dati dei clienti.**

[!DNL People-Based Destinations] richiede che vengano utilizzati solo identificatori con hash irreversibile. Questo riduce i rischi associati al caricamento manuale dei dati dei clienti in ciascuna piattaforma di destinazione.

Guardate il video seguente per una panoramica del flusso di dati durante l’utilizzo [!UICONTROL People-Based Destinations].

[!VIDEO](https://video.tv.adobe.com/v/28968/?captions=ita)

## Casi d'uso {#use-cases}

Per aiutarti a capire meglio come e quando dovresti usare [!DNL People-Based Destinations], ecco due esempi di casi di utilizzo che i clienti di Audience Manager possono risolvere utilizzando questa funzione.

### Use Case #1 {#use-case-1}

Un rivenditore online vuole raggiungere i clienti esistenti tramite piattaforme social e mostrare loro offerte personalizzate in base ai loro ordini precedenti. Con [!DNL People-Based Destinations]questo, il rivenditore online può trasferire indirizzi e-mail con hash da [!DNL CRM] propri ad Audience Manager, creare segmenti dai propri dati offline e inviare questi segmenti alle piattaforme social su cui desiderano pubblicizzare, ottimizzando le spese pubblicitarie.

### Use Case #2 {#use-case-2}

Una compagnia aerea ha diversi livelli di clienti (Bronzo, Argento e Oro) e vuole fornire a ciascuno dei livelli offerte personalizzate tramite piattaforme social. L'azienda utilizza Audience Manager per analizzare l'attività dei clienti sul sito Web. Tuttavia, non tutti i clienti utilizzano l'app mobile della compagnia aerea e alcuni di essi non hanno effettuato l'accesso al sito Web della società. Gli unici identificatori della società per questi clienti sono gli ID iscrizione e gli indirizzi e-mail.

Per utilizzarli tra social media e canali simili basati su persone, possono tenere a bordo i dati del cliente dal [!DNL CRM] proprio ad Audience Manager, utilizzando come identificatori gli indirizzi e-mail con hash.

Next, they can combine their offline data with their existing online activity traits, to build new audience segments that they can target through .[!DNL People-Based Destinations]
