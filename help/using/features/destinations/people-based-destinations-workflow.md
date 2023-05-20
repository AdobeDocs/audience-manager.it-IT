---
description: Destinazioni basate su persone offre più strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le Destinazioni basate su persone, a seconda dello scenario.
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: Guida all’implementazione
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---

# Guida all’implementazione {#implementation-guidance}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

[!DNL People-Based Destinations] offre più strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per [!DNL People-Based Destinations], a seconda dello scenario.

## Panoramica {#overview}

La configurazione di [!DNL People-Based Destinations] illustra più sezioni di Audience Manager e richiede impostazioni e metodi di onboarding diversi, a seconda del tipo di dati cliente che hai già in Audience Manager e del tipo di targeting di pubblico che desideri eseguire.

>[!IMPORTANT]
> Prima della configurazione [!DNL People-Based Destinations], assicurati di leggere questo articolo attentamente e completamente. Dopo aver letto questa guida, dovresti avere una chiara comprensione dello scenario che verrà abilitato tramite [!DNL People-Based Destinations].

È necessario chiarire sei aspetti di implementazione prima di utilizzare [!DNL People-Based Destinations]. Questo articolo ti aiuterà a capire qual è la configurazione corrente, in modo da poter seguire correttamente i passaggi di implementazione per il tuo scenario.

![pbd-implementazione](assets/pbd-implementation.png)

## 1. Definizione del caso d’uso {#defining-your-use-case}

Prima di iniziare l’implementazione [!DNL People-Based Destinations], è necessario definire chiaramente il caso d’uso per il quale utilizzerai questa funzione. È possibile utilizzare [!DNL People-Based Destinations] per indirizzare il pubblico in due modi, in base all’attività del pubblico:

**A) Targeting del pubblico in base all’attività utente combinata online e offline**. In questo scenario, vuoi combinare i dati del pubblico esistenti di Audience Manager con i dati del tuo [!DNL CRM] e inviare i segmenti di pubblico risultanti a [!DNL People-Based Destinations]. Ecco un esempio che illustra questo scenario:

La tua azienda, una compagnia aerea, ha diversi livelli di clienti (Bronzo, Argento e Oro) e desideri fornire a ciascuno di questi livelli offerte personalizzate tramite piattaforme social. Utilizzi Audience Manager per analizzare l’attività dei clienti sul tuo sito web. Tuttavia, non tutti i clienti utilizzano l&#39;app mobile della compagnia aerea e alcuni di loro non hanno effettuato l&#39;accesso al sito web della compagnia. I dati dei clienti sono per lo più limitati agli ID iscrizione e agli indirizzi e-mail.

Per eseguire il targeting tra i social media e canali simili basati sulle persone, puoi portare il tuo [indirizzi e-mail con hash](people-based-destinations-prerequisites.md) in Audience Manager e combinarli con le caratteristiche dell’attività online esistente, per creare nuovi segmenti di pubblico. Successivamente, puoi utilizzare questi segmenti per eseguire il targeting del pubblico tramite [!DNL People-Based Destinations].

**B) Targeting del pubblico basato esclusivamente sull’attività degli utenti offline**. In questo scenario, il tuo [!DNL CRM] Il sistema contiene gli indirizzi e-mail dei clienti e altri attributi dei clienti, ma i clienti non hanno interagito con il tuo sito Web, quindi non hai alcuna attività con i clienti in Audience Manager. Ecco un esempio che illustra questo scenario:

La tua azienda, un fornitore di servizi di telecomunicazione, conserva i dati dei clienti come indirizzi e-mail e piani di telecomunicazione acquistati in un interno [!DNL CRM]. Desideri indirizzare i clienti esistenti nelle piattaforme social per offrire loro pacchetti di aggiornamento in base ai loro abbonamenti esistenti. A questo scopo, puoi acquisire in Audience Manager gli indirizzi e-mail dei clienti con hash e creare segmenti in base agli abbonamenti dei clienti esistenti. Quindi puoi inviare questi segmenti a [!DNL People-Based Destinations] per eseguire il targeting dei clienti con offerte personalizzate.

## 2. Definire il tipo di indirizzi e-mail di destinazione {#define-target-email}

Il secondo passaggio nella definizione della strategia di implementazione consiste nel decidere il tipo di indirizzi e-mail dei clienti target.

**A) Targeting del pubblico in base agli indirizzi e-mail autenticati**. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desideri eseguire il targeting con offerte personalizzate, in base solo all’indirizzo e-mail autenticato sul sito web, in tempo reale.

**B) Targeting del pubblico in base a tutti gli indirizzi e-mail associati**. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desideri eseguirne il targeting in tutti gli indirizzi e-mail associati, indipendentemente dall’attività autenticata.

## 3. Identifica il tipo di ID cliente (ID CRM) di cui disponi {#identify-customer-id}

Targeting dei pubblici in [!DNL People-Based Destinations] richiede di inviare [SHA256 con hash](people-based-destinations-prerequisites.md) versioni degli indirizzi e-mail dei clienti. A seconda della configurazione di Audience Manager esistente, è possibile che ci si trovi in uno dei due scenari seguenti:

**A) Gli ID cliente Audienci Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già indirizzi e-mail con hash in minuscolo**. In questo scenario, puoi utilizzare questi ID esistenti per eseguire il targeting dei tipi di pubblico in [!DNL People-Based Destinations].

**B) Gli ID cliente Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono indirizzi e-mail con hash in minuscolo**. In questo scenario, gli ID cliente esistenti non possono essere inviati a [!DNL People-Based Destinations]. Da utilizzare [!DNL People-Based Destinations], devi eseguire una sincronizzazione ID tra gli ID cliente esistenti e le versioni minuscole con hash degli indirizzi e-mail dei clienti. Puoi eseguire questa operazione tramite [sincronizzazione ID basata su file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) o utilizzando [ID dichiarati](../declared-ids.md).

## 4. Qualificazione delle caratteristiche {#trait-qualification}

Per indirizzare il pubblico in modo preciso in [!DNL People-Based Destinations], gli utenti devono essere idonei per le caratteristiche basate su regole o onboarded, a seconda del tipo di targeting del pubblico che desideri eseguire.

**A) Qualifica gli ID cliente e gli ID dispositivo in tempo reale per le caratteristiche basate su regole**. Questa opzione si applica al caso d’uso A da [1. Definizione del caso d’uso](people-based-destinations-workflow.md#defining-your-use-case). Se il tuo piano prevede di indirizzare il pubblico in base all’attività online e offline, molto probabilmente hai già qualificato il pubblico per [caratteristiche basate su regole](../traits/trait-and-segment-qualification-reference.md).

**B) Integrare le caratteristiche rispetto agli ID cliente tramite file di dati in entrata**. Questa opzione si applica al caso d’uso B da [1. Definizione del caso d’uso](people-based-destinations-workflow.md#defining-your-use-case). Quando esegui il targeting del pubblico in base a un’attività puramente offline, devi qualificare gli ID cliente per le caratteristiche onboarded tramite [file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Creare o etichettare origini dati e indirizzi e-mail con hash incorporati {#create-label-data-sources}

A seconda del tipo di ID cliente di cui disponi in Audience Manager (vedi [3. Identifica il tipo di ID cliente (ID CRM) di cui disponi](people-based-destinations-workflow.md#identify-customer-id), si troverà in uno dei seguenti scenari:

**A) Etichettare un&#39;origine dati esistente**. Questa opzione si applica allo scenario in cui gli ID cliente Audienci Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già indirizzi e-mail con hash in minuscolo. In questa situazione, devi etichettare l’origine dati in cui memorizzi gli ID come [!DNL PII] origine dati. Consulta [Impostazioni origine dati](../datasources-list-and-settings.md) per informazioni dettagliate sulle impostazioni dell’origine dati. Assicurati che l’opzione Impossibile essere vincolati a informazioni di identificazione personale non sia selezionata.

**B) Creare una nuova fonte di dati**. Questa opzione si applica allo scenario in cui gli ID cliente Audienci Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono indirizzi e-mail con hash. In questo caso, devi creare una nuova origine dati multi-dispositivo e integrare gli indirizzi e-mail con hash rispetto a essa. È possibile eseguire questa operazione in due modi:

* Utilizzare la sincronizzazione ID basata su file. Per informazioni dettagliate sull’aspetto dei file di sincronizzazione ID, consulta [Name and Content Requirements for ID Synchronization Files](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). Utilizzando questo metodo, puoi eseguire il targeting di tutti gli indirizzi e-mail con hash dal tuo [!DNL CRM] database.
* Utilizzare [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmetti gli ID cliente autenticati. Quando si utilizza questo metodo, ad Audience Manager, per tuo conto, esegue il targeting solo degli indirizzi e-mail con hash degli utenti che si sono autenticati online. Gli indirizzi e-mail target nei canali basati sulle persone sono solo quelli nelle chiamate all’evento degli ID dichiarati. Gli altri indirizzi e-mail associati all’ID cliente non vengono attivati in tempo reale.

## 6. Utilizzare una regola di unione profili per la segmentazione {#use-profile-merge-rules}

A seconda del caso d’uso (consulta [1. Definizione del caso d’uso](people-based-destinations-workflow.md#defining-your-use-case)), sono disponibili due modi per utilizzare [!DNL Profile Merge Rules] per la segmentazione.

**A) Usa esistente[!DNL Profile Merge Rules]**. Questa opzione si applica al primo caso d’uso (targeting di pubblico basato sull’attività combinata degli utenti online e offline). In questo scenario, disponi di un’attività cliente esistente in Audience Manager e hai già definito almeno una regola di unione profili utilizzata nella segmentazione. In questo caso, non è necessario creare nuovi [!DNL Profile Merge Rules].

**B) Crea un nuovo, [!DNL All Cross-Device Profiles] Regola di unione**. Questa opzione si applica al secondo caso d’uso (targeting del pubblico basato esclusivamente sull’attività dell’utente offline). In questo scenario stai portando i dati dei clienti offline dal tuo [!DNL CRM] in Audience Manager e desideri creare segmenti da tali dati. Per eseguire questa operazione, [!DNL People-Based Destinations] introduce una nuova quarta regola di unione profili, denominata **[!DNL All Cross-Device Profiles]**. Questa è la regola da utilizzare per la segmentazione di dati puramente offline.
