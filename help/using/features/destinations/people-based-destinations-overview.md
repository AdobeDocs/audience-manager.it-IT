---
description: 'Utilizza destinazioni basate su persone per inviare segmenti di pubblico di prime parti ad ambienti basati su persone. Questi ambienti sono ecosistemi chiusi appartenenti a un’entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come Facebook e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato. '
seo-description: 'Utilizza destinazioni basate su persone per inviare segmenti di pubblico di prime parti ad ambienti basati su persone. Questi ambienti sono ecosistemi chiusi appartenenti a un’entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come Facebook e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato.  '
seo-title: Panoramica e casi di utilizzo delle destinazioni basate su persone
solution: Audience Manager
title: Panoramica e casi di utilizzo
feature: Destinazioni basate su persone
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 1%

---

# Panoramica e casi di utilizzo {#overview-use-cases}

Utilizza [!DNL People-Based Destinations] per inviare segmenti di pubblico di prime parti ad ambienti basati sulle persone. Questi ambienti sono ecosistemi chiusi appartenenti a un’entità che controlla il contenuto visualizzato al suo interno. Includono piattaforme social come [!DNL Facebook] e altre piattaforme che si basano sugli account dei clienti per personalizzare il contenuto visualizzato.

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

## Panoramica {#overview}

[!DNL People-Based Destinations] ti consente di applicare la segmentazione sui dati online e offline per creare segmenti di pubblico in base a identificatori [ ](people-based-destinations-prerequisites.md#hashing-requirements)con hash come indirizzi e-mail o numeri di telefono. Poi, puoi inviare questi segmenti a &quot;giardini murati&quot; come [!DNL Facebook], dove puoi rivolgerti al tuo pubblico sulle piattaforme social. [!DNL People-Based Destinations] può aiutarti a:

* Eseguire il targeting dei tipi di pubblico offline e online su piattaforme quali [!DNL Facebook], in base a indirizzi e-mail con hash;
* integrare le funzionalità di targeting dei dispositivi e dei cookie esistenti di Audience Manager;
* Eliminare i costi associati a soluzioni di onboarding dei dati di terze parti;
* Eliminazione dei costi associati allo sviluppo di flussi di lavoro personalizzati di onboarding dei dati;
* Eseguire il targeting dei tipi di pubblico in ambienti senza cookie;
* Esegui il targeting dei tipi di pubblico deduplicando gli indirizzi e-mail con hash corrispondenti agli ID cliente.

Puoi utilizzare [!DNL People-Based Destinations] per segmentare ed eseguire il targeting di clienti di alto valore che non hanno visitato il tuo sito web o per interrompere il targeting di coloro che hanno già effettuato la conversione offline. Inoltre, puoi sfruttare [!DNL Profile Merge Rules] per combinare i dati di prime parti offline con i dati di prime parti online, inclusi i dati dei clienti provenienti da altre soluzioni Adobe Experience Cloud, per ottimizzare le attività pubblicitarie sui social media.

![pbd-overview](assets/pbd-overview.png)

## Disponibilità {#availability}

[!DNL People-Based Destinations] è un’integrazione premium Audience Manager. Contatta il tuo rappresentante Adobe per sfruttare questa funzionalità premium.

## Perché utilizzare [!UICONTROL People-Based Destinations] {#why-use}

**Fornisci ai tuoi clienti esperienze cross-channel coerenti gestendo l’intera segmentazione del pubblico dall’interno di un Audience Manager.**

Se non attivi i segmenti di pubblico nei canali basati sulle persone tramite l’Audience Manager, si ottengono esperienze sconosciute tra ciò che i clienti vedono quando visitano il tuo sito web e ciò che vedono, ad esempio, nei loro [!DNL Facebook] feed. Avere un targeting coerente tra i canali può aumentare le entrate degli annunci ottimizzando la spesa degli annunci.

**Raggiungi il pubblico nei canali basati sulle persone senza la necessità di una soluzione di onboarding dei dati dedicata o di flussi di lavoro personalizzati per inviare il pubblico.**

Il modo più &quot;tradizionale&quot; di indirizzare i tipi di pubblico tra canali basati sulle persone implica la necessità di esportare i dati dei clienti in un formato accettato dalla piattaforma su cui desideri fare pubblicità e quindi di utilizzare il metodo di onboarding dei dati dedicato della piattaforma per portare i dati dei clienti al tuo account inserzionista. Questo è tutto il lavoro manuale che devi fare per ogni piattaforma su cui vuoi pubblicizzare. Inoltre, piattaforme diverse possono avere requisiti di formato dati diversi, rendendo il processo ancora più noioso.

![pbd-overview](assets/pbd-diagram.png)

Attraverso [!DNL People-Based Destinations], un Audience Manager consente di centralizzare i dati dei clienti, creare segmenti di pubblico e attivarli su più canali basati sulle persone. È possibile farlo dall&#39;interfaccia utente di Audience Manager, evitando il lavoro aggiuntivo di caricare manualmente i dati su ogni piattaforma, risparmiando tempo prezioso nel processo.

**Crea e attiva segmenti di pubblico da profili puramente offline.**

[!DNL People-Based Destinations] risolvi il problema che in precedenza era possibile attivare solo segmenti di pubblico in base all’attività del dispositivo. Con [!DNL People-Based Destinations] puoi creare segmenti da dati puramente offline dal tuo [!DNL CRM] e attivarli nelle piattaforme basate su persone. Inoltre, puoi correlare i dati offline con quelli del dispositivo già in uso in Audience Manager.

**Sfrutta la governance dei dati e i controlli sulla privacy di Audience Manager per gestire in modo sicuro i dati dei clienti.**

[!DNL People-Based Destinations] richiede l’utilizzo di identificatori con hash irreversibili. Questo riduce il rischio associato al caricamento manuale dei dati del cliente in ciascuna piattaforma di destinazione.

Guarda il video seguente per ottenere una panoramica del flusso di dati quando utilizzi [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casi d&#39;uso {#use-cases}

Per comprendere meglio come e quando utilizzare [!DNL People-Based Destinations], ecco due esempi di casi d’uso che i clienti di Audience Manager possono risolvere utilizzando questa funzione.

### Caso d&#39;uso n. 1 {#use-case-1}

Un rivenditore online vuole raggiungere i clienti esistenti tramite piattaforme social e mostrare loro offerte personalizzate in base ai loro ordini precedenti. Con [!DNL People-Based Destinations], il rivenditore online può acquisire indirizzi e-mail con hash dal proprio [!DNL CRM] all’Audience Manager, creare segmenti dai propri dati offline e inviare tali segmenti alle piattaforme social sulle quali desidera pubblicizzare, ottimizzando le spese pubblicitarie.

### Caso d&#39;uso n. 2 {#use-case-2}

Una compagnia aerea ha diversi livelli di clienti (Bronze, Silver e Gold) e vuole fornire a ciascuno dei livelli offerte personalizzate tramite piattaforme social. L’azienda utilizza Audience Manager per analizzare l’attività dei clienti sul sito web. Tuttavia, non tutti i clienti utilizzano l’app mobile della compagnia aerea e alcuni di essi non hanno effettuato l’accesso al sito web della società. Gli unici identificatori che l&#39;azienda ha di questi clienti sono gli ID di iscrizione e gli indirizzi e-mail.

Per eseguire il targeting tra i social media e canali simili basati sulle persone, è possibile integrare i dati del cliente dai loro [!DNL CRM] all’Audience Manager, utilizzando come identificatori gli indirizzi e-mail con hash.

Successivamente, possono combinare i dati offline con le caratteristiche delle attività online esistenti, per creare nuovi segmenti di pubblico a cui possono rivolgersi tramite [!DNL People-Based Destinations].
