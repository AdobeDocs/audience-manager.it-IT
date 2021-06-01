---
description: Le destinazioni basate su persone offrono diverse strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le destinazioni basate su persone, a seconda dello scenario.
seo-description: 'Le destinazioni basate su persone offrono diverse strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le destinazioni basate su persone, a seconda dello scenario.  '
seo-title: Guida all’implementazione delle destinazioni basate su persone
solution: Audience Manager
title: Guida all'implementazione
feature: Destinazioni basate su persone
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# Guida all&#39;implementazione {#implementation-guidance}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

[!DNL People-Based Destinations] offre diverse strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per [!DNL People-Based Destinations], a seconda dello scenario.

## Panoramica {#overview}

La configurazione di [!DNL People-Based Destinations] ti porta attraverso più sezioni di Audience Manager e richiede diverse impostazioni e metodi di onboarding dei dati, a seconda del tipo di dati cliente già in uso in Audience Manager e del tipo di targeting di pubblico che desideri eseguire.

>[!IMPORTANT]
> Prima di configurare [!DNL People-Based Destinations], assicurati di leggere attentamente e completamente questo articolo. Dopo aver letto questa guida, dovresti avere una chiara comprensione dello scenario che verrà attivato tramite [!DNL People-Based Destinations].

È necessario chiarire sei aspetti di implementazione prima di utilizzare [!DNL People-Based Destinations]. Questo articolo ti aiuterà a capire qual è la configurazione corrente, in modo da poter seguire correttamente i passaggi di implementazione per il tuo scenario.

![implementazione pbd](assets/pbd-implementation.png)

## 1. Definizione del caso d’uso {#defining-your-use-case}

Prima di iniziare a implementare [!DNL People-Based Destinations], devi definire chiaramente il caso d’uso per il quale utilizzerai questa funzione. Puoi utilizzare [!DNL People-Based Destinations] per eseguire il targeting dei tipi di pubblico in due modi, in base all’attività del pubblico:

**A) Targeting del pubblico in base all&#39;attività** utente combinata online e offline. In questo scenario, desideri combinare i dati esistenti del pubblico di Audience Manager con i dati del tuo sistema interno [!DNL CRM] e inviare i segmenti di pubblico risultanti a [!DNL People-Based Destinations]. Ecco un esempio che illustra questo scenario:

La tua azienda, una compagnia aerea, ha diversi livelli di clienti (Bronze, Silver e Gold) e vuoi fornire a ciascuno dei livelli offerte personalizzate tramite piattaforme social. Utilizza Audience Manager per analizzare l’attività del cliente sul tuo sito web. Tuttavia, non tutti i clienti utilizzano l’app mobile della compagnia aerea e alcuni di essi non hanno effettuato l’accesso al sito web della società. I dati dei clienti sono per lo più limitati agli ID di iscrizione e agli indirizzi e-mail.

Per eseguire il targeting tra i social media e canali simili basati sulle persone, puoi portare i tuoi [indirizzi e-mail con hash](people-based-destinations-prerequisites.md) nell’Audience Manager e combinarli con le caratteristiche dell’attività online esistenti, per creare nuovi segmenti di pubblico. Successivamente, puoi utilizzare questi segmenti per eseguire il targeting del pubblico tramite [!DNL People-Based Destinations].

**B) Targeting del pubblico basato esclusivamente sull&#39;attività** dell&#39;utente offline. In questo scenario, il sistema [!DNL CRM] contiene gli indirizzi e-mail del cliente e altri attributi del cliente, ma i clienti non hanno interagito con il tuo sito web, per cui non hai alcuna attività con il cliente in Audience Manager. Ecco un esempio che illustra questo scenario:

La tua azienda, fornitore di servizi di telecomunicazione, conserva i dati dei clienti come indirizzi e-mail e piani di telefonia acquistati in un [!DNL CRM] interno. Vuoi rivolgerti ai clienti esistenti nelle piattaforme social per offrire loro pacchetti di aggiornamento in base alle loro iscrizioni esistenti. A questo scopo, puoi inserire gli indirizzi e-mail dei clienti con hash in un Audience Manager e creare segmenti in base alle iscrizioni dei clienti esistenti. Quindi puoi inviare questi segmenti a [!DNL People-Based Destinations] per indirizzare i tuoi clienti con offerte personalizzate.

## 2. Definisci il tipo di indirizzi e-mail di destinazione {#define-target-email}

Il secondo passaggio nella definizione della strategia di implementazione consiste nel decidere quale tipo di indirizzi e-mail del cliente desideri eseguire il targeting.

**A) Targeting del pubblico basato sui tuoi indirizzi** e-mail autenticati. In questo scenario, gli utenti hanno più account associati a più indirizzi e-mail e desideri indirizzarli con offerte personalizzate, basate solo sull’indirizzo e-mail che autenticano sul sito web in tempo reale.

**B) Targeting del pubblico basato su tutti gli indirizzi** e-mail associati. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desideri eseguirne il targeting in tutti gli indirizzi e-mail associati, indipendentemente dall’attività autenticata.

## 3. Identifica il tipo di ID cliente (ID CRM) di cui disponi {#identify-customer-id}

Per eseguire il targeting dei tipi di pubblico in [!DNL People-Based Destinations] è necessario inviare [SHA256 con hash](people-based-destinations-prerequisites.md) versioni degli indirizzi e-mail dei clienti. A seconda della configurazione di Audience Manager esistente, potresti trovarti in uno dei due scenari seguenti:

**A) Gli ID cliente Audienci Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già minuscoli indirizzi** e-mail con hash. In questo scenario, puoi utilizzare questi ID esistenti per eseguire il targeting del pubblico in [!DNL People-Based Destinations].

**B) Gli ID cliente Audienci Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono minuscoli indirizzi** e-mail con hash. In questo caso, gli ID cliente esistenti non possono essere inviati a [!DNL People-Based Destinations]. Per utilizzare [!DNL People-Based Destinations], devi eseguire una sincronizzazione ID tra gli ID cliente esistenti e le versioni con hash precedenti degli indirizzi e-mail del cliente. Puoi farlo tramite [sincronizzazione ID basata su file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) o utilizzando [ID dichiarati](../declared-ids.md).

## 4. Qualificazione delle caratteristiche {#trait-qualification}

Per eseguire con precisione il targeting del pubblico in [!DNL People-Based Destinations], gli utenti devono qualificarsi per le caratteristiche basate su regole o onboarded, a seconda del tipo di targeting del pubblico che desideri eseguire.

**A) Qualifica gli ID cliente e gli ID dispositivo in tempo reale per le caratteristiche** basate su regole. Questa opzione si applica al caso d’uso A di [1. Definizione del caso d&#39;uso](people-based-destinations-workflow.md#defining-your-use-case). Se il tuo piano è di indirizzare i tipi di pubblico in base a attività online e offline, molto probabilmente stai già qualificando il tuo pubblico per [caratteristiche basate su regole](../traits/trait-and-segment-qualification-reference.md).

**B) Caratteristiche di bordo rispetto agli ID cliente tramite file** di dati in entrata. Questa opzione si applica al caso d’uso B da [1. Definizione del caso d&#39;uso](people-based-destinations-workflow.md#defining-your-use-case). Quando esegui il targeting del pubblico in base a un’attività puramente offline, devi qualificare gli ID cliente per le caratteristiche onboarded tramite [file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Creare o etichettare origini dati e indirizzi e-mail con hash integrati {#create-label-data-sources}

A seconda del tipo di ID cliente di cui disponi nell’Audience Manager (consulta [3. Identifica il tipo di ID cliente (ID CRM) che hai](people-based-destinations-workflow.md#identify-customer-id), ti troverai in uno dei seguenti scenari:

**A) Etichettare un&#39;origine** dati esistente. Questa opzione si applica allo scenario in cui gli ID cliente Audienci Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già minuscoli indirizzi e-mail con hash. In questa situazione, devi assegnare un’etichetta all’origine dati in cui sono archiviati gli ID come origine dati [!DNL PII]. Per informazioni sulle impostazioni dell&#39;origine dati, vedere [Impostazioni origine dati](../datasources-list-and-settings.md) . Ciò che devi fare è assicurarsi che l&#39;opzione Impossibile essere legato a informazioni personali sia deselezionata.

**B) Creare una nuova origine** dati. Questa opzione si applica allo scenario in cui gli ID cliente Audienci Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono indirizzi e-mail con hash. In questo caso, devi creare una nuova origine dati multi-dispositivo e inserire gli indirizzi e-mail con hash rispetto a essa. Puoi eseguire questa operazione in due modi:

* Utilizzare la sincronizzazione ID basata su file. Per informazioni dettagliate sull’aspetto dei file di sincronizzazione ID, consulta [Name and Content Requirements for ID Synchronization Files](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). Utilizzando questo metodo, puoi eseguire il targeting di tutti gli indirizzi e-mail con hash dal database [!DNL CRM].
* Utilizza [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmetti gli ID cliente autenticati. Quando utilizzi questo metodo, ad Audience Manager, esegue il targeting per tuo conto solo degli indirizzi e-mail con hash degli utenti che hanno eseguito l’autenticazione online. Gli indirizzi e-mail di destinazione nei canali basati sulle persone sono solo quelli nelle chiamate dell’evento ID dichiarate. Gli altri indirizzi e-mail associati all’ID cliente non vengono attivati in tempo reale.

## 6. Utilizza una regola di unione profili per la segmentazione {#use-profile-merge-rules}

A seconda del caso d’uso (consulta [1. Definendo il caso d’uso](people-based-destinations-workflow.md#defining-your-use-case)), esistono due modi per utilizzare [!DNL Profile Merge Rules] per la segmentazione.

**A) Utilizzare[!DNL Profile Merge Rules]** esistente. Questa opzione si applica al primo caso d’uso (targeting del pubblico basato su attività utente online e offline combinate). In questo scenario, disponi di un’attività cliente esistente in Audience Manager e hai già definito almeno una regola di unione profili utilizzata nella segmentazione. In questo caso, non è necessario creare nuovi [!DNL Profile Merge Rules].

**B) Crea una nuova regola di  [!DNL All Cross-Device Profiles] unione**. Questa opzione si applica al secondo caso d’uso (targeting del pubblico basato esclusivamente sull’attività dell’utente offline). In questo scenario, inserisci in Audience Manager i dati dei clienti offline dal tuo [!DNL CRM] e vuoi creare segmenti da tali dati. A questo scopo, [!DNL People-Based Destinations] introduce una nuova, quarta regola di unione profili, denominata **[!DNL All Cross-Device Profiles]**. Questa è la regola da utilizzare per segmentare dati puramente offline.
