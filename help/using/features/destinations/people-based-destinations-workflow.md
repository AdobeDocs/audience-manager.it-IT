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
source-wordcount: '1350'
ht-degree: 2%

---

# Guida all’implementazione {#implementation-guidance}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

[!DNL People-Based Destinations] offre più strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per [!DNL People-Based Destinations], a seconda dello scenario.

## Panoramica {#overview}

La configurazione di [!DNL People-Based Destinations] consente di esplorare più sezioni di Audience Manager e richiede impostazioni e metodi di onboarding diversi, a seconda del tipo di dati cliente già disponibili in Audience Manager e del tipo di targeting di pubblico che si desidera eseguire.

>[!IMPORTANT]
> Prima di configurare [!DNL People-Based Destinations], assicurati di leggere questo articolo attentamente e completamente. Dopo aver letto questa guida, dovresti avere una chiara comprensione dello scenario che verrà abilitato tramite [!DNL People-Based Destinations].

È necessario chiarire sei aspetti dell&#39;implementazione prima di utilizzare [!DNL People-Based Destinations]. Questo articolo ti aiuterà a capire qual è la configurazione corrente, in modo da poter seguire correttamente i passaggi di implementazione per il tuo scenario.

![pbd-implementation](assets/pbd-implementation.png)

## &#x200B;1. Definizione del caso d’uso {#defining-your-use-case}

Prima di iniziare a implementare [!DNL People-Based Destinations], è necessario definire chiaramente il caso d&#39;uso per il quale si utilizzerà questa funzione. È possibile utilizzare [!DNL People-Based Destinations] per eseguire il targeting dei tipi di pubblico in due modi, in base all&#39;attività del pubblico:

**A) targeting del pubblico in base all&#39;attività utente combinata online e offline**. In questo scenario, vuoi combinare i dati esistenti del pubblico da Audience Manager con i dati del tuo sistema interno [!DNL CRM] e inviare i segmenti di pubblico risultanti a [!DNL People-Based Destinations]. Ecco un esempio che illustra questo scenario:

La tua azienda, una compagnia aerea, ha diversi livelli di clienti (Bronzo, Argento e Oro) e desideri fornire a ciascuno di questi livelli offerte personalizzate tramite piattaforme social. Utilizza Audience Manager per analizzare l’attività dei clienti sul tuo sito web. Tuttavia, non tutti i clienti utilizzano l&#39;app mobile della compagnia aerea e alcuni di loro non hanno effettuato l&#39;accesso al sito web della compagnia. I dati dei clienti sono per lo più limitati agli ID iscrizione e agli indirizzi e-mail.

Per eseguire il targeting tra i social media e canali simili basati sulle persone, puoi portare i tuoi [indirizzi e-mail con hash](people-based-destinations-prerequisites.md) in Audience Manager e combinarli con le caratteristiche dell&#39;attività online esistente, per creare nuovi segmenti di pubblico. Successivamente, puoi utilizzare questi segmenti per eseguire il targeting del pubblico tramite [!DNL People-Based Destinations].

**B) targeting del pubblico basato esclusivamente sulla tua attività utente offline**. In questo scenario, il sistema [!DNL CRM] contiene gli indirizzi e-mail dei clienti e altri attributi del cliente, ma i clienti non hanno interagito con il sito Web, quindi non hai alcuna attività cliente in Audience Manager. Ecco un esempio che illustra questo scenario:

La tua azienda, un provider di servizi di telecomunicazione, conserva i dati dei clienti come indirizzi e-mail e piani di telecomunicazione acquistati in un [!DNL CRM] interno. Desideri indirizzare i clienti esistenti nelle piattaforme social per offrire loro pacchetti di aggiornamento in base ai loro abbonamenti esistenti. A tal fine, puoi acquisire in Audience Manager gli indirizzi e-mail dei clienti con hash e creare segmenti in base agli abbonamenti dei clienti esistenti. Quindi puoi inviare questi segmenti a [!DNL People-Based Destinations] per eseguire il targeting dei tuoi clienti con offerte personalizzate.

## &#x200B;2. Definire il tipo di indirizzi e-mail di destinazione {#define-target-email}

Il secondo passaggio nella definizione della strategia di implementazione consiste nel decidere il tipo di indirizzi e-mail dei clienti target.

**A) targeting del pubblico in base agli indirizzi e-mail autenticati**. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desideri eseguire il targeting con offerte personalizzate, in base solo all’indirizzo e-mail autenticato sul sito web, in tempo reale.

**B) targeting del pubblico in base a tutti gli indirizzi e-mail associati**. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desideri eseguirne il targeting in tutti gli indirizzi e-mail associati, indipendentemente dall’attività autenticata.

## &#x200B;3. Identifica il tipo di ID cliente (ID CRM) di cui disponi {#identify-customer-id}

Il targeting dei tipi di pubblico in [!DNL People-Based Destinations] richiede l&#39;invio di [versioni con hash SHA256](people-based-destinations-prerequisites.md) degli indirizzi e-mail dei clienti. A seconda della configurazione di Audience Manager esistente, è possibile che ci si trovi in uno dei due scenari seguenti:

**A) Gli ID cliente Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) sono già indirizzi e-mail con hash minuscoli**. In questo scenario, puoi utilizzare questi ID esistenti per eseguire il targeting dei tipi di pubblico in [!DNL People-Based Destinations].

**B) Gli ID cliente Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono indirizzi e-mail con hash in minuscolo**. In questo scenario, gli ID cliente esistenti non possono essere inviati a [!DNL People-Based Destinations]. Per utilizzare [!DNL People-Based Destinations], devi eseguire una sincronizzazione ID tra gli ID cliente esistenti e le versioni minuscole con hash degli indirizzi e-mail dei clienti. Puoi eseguire questa operazione tramite [sincronizzazione ID basata su file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) o utilizzando [ID dichiarati](../declared-ids.md).

## &#x200B;4. Qualificazione delle caratteristiche {#trait-qualification}

Per eseguire il targeting accurato del pubblico in [!DNL People-Based Destinations], gli utenti devono qualificarsi per caratteristiche basate su regole o onboarded, a seconda del tipo di targeting del pubblico che desideri eseguire.

**A) Qualifica i tuoi ID cliente e ID dispositivo in tempo reale per le caratteristiche basate su regole**. Questa opzione si applica al caso d&#39;uso A di [1. Definizione Del Caso D&#39;Uso](people-based-destinations-workflow.md#defining-your-use-case). Se il tuo piano prevede di indirizzare il pubblico a tipi di pubblico basati su attività online e offline, molto probabilmente stai già qualificando il pubblico per [caratteristiche basate su regole](../traits/trait-and-segment-qualification-reference.md).

**B) Effettua l&#39;onboarding delle caratteristiche in base agli ID cliente tramite file di dati in entrata**. Questa opzione si applica al caso d&#39;uso B di [1. Definizione Del Caso D&#39;Uso](people-based-destinations-workflow.md#defining-your-use-case). Quando esegui il targeting del pubblico in base a attività puramente offline, devi qualificare gli ID cliente per le caratteristiche onboarded tramite [file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## &#x200B;5. Creare o etichettare origini dati e indirizzi e-mail con hash incorporati {#create-label-data-sources}

A seconda del tipo di ID cliente disponibili in Audience Manager (vedi [3. Identifica il tipo di ID cliente (ID CRM) di cui disponi](people-based-destinations-workflow.md#identify-customer-id). Potrai trovarti in uno dei seguenti scenari:

**A) Etichettare un&#39;origine dati esistente**. Questa opzione si applica allo scenario in cui gli ID cliente Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già indirizzi e-mail con hash in minuscolo. In questa situazione, devi etichettare l&#39;origine dati in cui vengono memorizzati gli ID come origine dati [!DNL PII]. Per informazioni dettagliate sulle impostazioni dell&#39;origine dati, vedere [Impostazioni Source dati](../datasources-list-and-settings.md). Assicurati che l’opzione Impossibile essere vincolati a informazioni di identificazione personale non sia selezionata.

**B) Crea una nuova origine dati**. Questa opzione si applica allo scenario in cui gli ID cliente Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono indirizzi e-mail con hash. In questo caso, devi creare una nuova origine dati multi-dispositivo e integrare gli indirizzi e-mail con hash rispetto a essa. È possibile eseguire questa operazione in due modi:

* Utilizza la sincronizzazione ID basata su file. Per informazioni dettagliate sull’aspetto dei file di sincronizzazione ID, consulta [Name and Content Requirements for ID Synchronization Files](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). Quando si utilizza questo metodo, è possibile eseguire il targeting di tutti gli indirizzi e-mail con hash dal database [!DNL CRM].
* Utilizza [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmetti gli ID cliente autenticati. Quando si utilizza questo metodo, Audience Manager, per tuo conto, esegue il targeting solo degli indirizzi e-mail con hash degli utenti che si sono autenticati online. Gli indirizzi e-mail target nei canali basati sulle persone sono solo quelli nelle chiamate all’evento degli ID dichiarati. Gli altri indirizzi e-mail associati all’ID cliente non vengono attivati in tempo reale.

## &#x200B;6. Utilizzare una regola di unione profili per la segmentazione {#use-profile-merge-rules}

A seconda del tuo caso d&#39;uso (vedi [1. Definendo il tuo caso d&#39;uso &#x200B;](people-based-destinations-workflow.md#defining-your-use-case)), esistono due modi per utilizzare [!DNL Profile Merge Rules] per la segmentazione.

**A) Utilizza[!DNL Profile Merge Rules]** esistente. Questa opzione si applica al primo caso d’uso (targeting di pubblico basato sull’attività combinata degli utenti online e offline). In questo scenario, poiché esiste un’attività cliente in Audience Manager, hai già definito almeno una regola di unione profili utilizzata nella segmentazione. In questo caso, non è necessario creare alcun nuovo [!DNL Profile Merge Rules].

**B) Crea una nuova regola di unione [!DNL All Cross-Device Profiles]**. Questa opzione si applica al secondo caso d’uso (targeting del pubblico basato esclusivamente sull’attività dell’utente offline). In questo scenario, stai inserendo i dati dei clienti offline da [!DNL CRM] in Audience Manager e desideri creare segmenti da tali dati. A questo scopo, [!DNL People-Based Destinations] introduce una nuova quarta regola di unione profili, denominata **[!DNL All Cross-Device Profiles]**. Questa è la regola da utilizzare per la segmentazione di dati puramente offline.
