---
description: Le destinazioni basate su persone offrono più strategie di implementazione, a seconda della struttura dei dati del cliente. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le Destinazioni basate su persone, a seconda dello scenario.
seo-description: 'Le destinazioni basate su persone offrono più strategie di implementazione, a seconda della struttura dei dati del cliente. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le Destinazioni basate su persone, a seconda dello scenario.  '
seo-title: Linee guida sull'implementazione delle destinazioni basate su persone
solution: Audience Manager
title: Linee guida sull'implementazione
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Linee guida sull'implementazione {#implementation-guidance}

[!DNL People-Based Destinations] offre più strategie di implementazione, a seconda della struttura dei dati del cliente. Questo articolo fornisce una panoramica dei passaggi di implementazione necessari [!DNL People-Based Destinations]a seconda dello scenario.

## Panoramica {#overview}

La configurazione di [!DNL People-Based Destinations] ti accompagna attraverso più sezioni di Audience Manager e richiede impostazioni e metodi di onboarding diversi, a seconda del tipo di dati cliente già posseduti in Audience Manager e del tipo di targeting dell'audience che vuoi eseguire.

>[!IMPORTANT]
> Prima di configurare [!DNL People-Based Destinations], leggete attentamente questo articolo. Dopo aver letto questa guida, è importante comprendere chiaramente lo scenario da [!DNL People-Based Destinations]abilitare.

Prima di utilizzare [!DNL People-Based Destinations]è necessario chiarire sei aspetti di implementazione. Questo articolo ti aiuterà a capire qual è la configurazione corrente, per seguire correttamente i passaggi di implementazione per il tuo scenario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definizione del caso d'uso {#defining-your-use-case}

Prima di iniziare l'implementazione [!DNL People-Based Destinations], devi definire chiaramente il caso d'uso per cui utilizzerai questa funzione. Potete utilizzare [!DNL People-Based Destinations] i tipi di pubblico in due modi, in base all'attività dell'audience:

**A) Targeting pubblico basato sull'attività combinato online e offline**. In questo scenario, vuoi combinare dati di audience esistenti da Audience Manager con dati provenienti dal [!DNL CRM] sistema interno e inviare i segmenti di pubblico risultanti a [!DNL People-Based Destinations]. Ecco un esempio che illustra questo scenario:

La tua società, una compagnia aerea, ha diversi livelli di clienti (Bronze, Silver e Gold) e vuoi fornire a ciascuno dei livelli offerte personalizzate tramite piattaforme social. Usi Audience Manager per analizzare l'attività del cliente sul tuo sito web. Tuttavia, non tutti i clienti usano l'app mobile della compagnia aerea e alcuni di essi non hanno mai eseguito l'accesso al sito Web della società. I dati dei clienti sono prevalentemente limitati agli ID iscrizione e agli indirizzi e-mail.

Per eseguire il targeting per social media e canali basati su persone simili, puoi importare gli [indirizzi e-mail con hash](people-based-destinations-prerequisites.md) in Audience Manager e combinarli con caratteristiche di attività online esistenti, per creare nuovi segmenti di pubblico. Successivamente, puoi usare questi segmenti per indirizzare il pubblico tramite [!DNL People-Based Destinations].

**B) Targeting pubblico basato unicamente sull'attività dell'utente offline**. In questo scenario, [!DNL CRM] il sistema contiene indirizzi e-mail del cliente e altri attributi del cliente, ma i clienti non hanno interagito con il tuo sito Web, per cui non hai attività cliente in Audience Manager. Ecco un esempio che illustra questo scenario:

La tua azienda, un fornitore di servizi di telefonia, mantiene i dati del cliente come indirizzi e-mail e li acquista in un interno. [!DNL CRM] Desiderate indirizzare i clienti esistenti nelle piattaforme social per offrire loro pacchetti di aggiornamento in base alle sottoscrizioni esistenti. A tal fine, puoi assimilare gli indirizzi e-mail dei clienti con hash in Audience Manager e creare segmenti basati sulle sottoscrizioni dei clienti esistenti. Quindi, puoi inviare questi segmenti a [!DNL People-Based Destinations] target con offerte personalizzate.

## 2. Definire il tipo di indirizzi e-mail mirati {#define-target-email}

Il secondo passaggio nella definizione della strategia di implementazione sta nel determinare il tipo di indirizzi e-mail del cliente che desideri destinare.

**A) Targeting pubblico basato su indirizzi e-mail autenticati**. In questo scenario, gli utenti hanno più account associati a più indirizzi e-mail e si desidera indirizzarli con offerte personalizzate, in base solo all'indirizzo e-mail che accedono sul sito Web in tempo reale.

**B) Targeting pubblico basato su tutti gli indirizzi e-mail associati**. In questo scenario, gli utenti hanno più account associati a più indirizzi e-mail e desiderate eseguire il targeting per tutti gli indirizzi e-mail associati, indipendentemente dall'attività autenticata.

## 3. Identificare il tipo di ID cliente (ID CRM) che hai {#identify-customer-id}

Il targeting di audience in richiede [!DNL People-Based Destinations] l'invio [di versioni hash](people-based-destinations-prerequisites.md) SHA 256 degli indirizzi e-mail del cliente. A seconda della configurazione di Audience Manager esistente, potresti trovare uno dei due scenari seguenti:

**A) Gli ID cliente di Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) sono già lettere minuscole, indirizzi e-mail con hash**. In questo scenario, puoi utilizzare questi ID esistenti per eseguire il targeting del pubblico in [!DNL People-Based Destinations].

**B) Gli ID cliente di Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) non sono lettere minuscole, indirizzi e-mail con hash**. In questo scenario, gli ID cliente esistenti non possono [!DNL People-Based Destinations]essere inviati. Per utilizzare [!DNL People-Based Destinations], devi eseguire una sincronizzazione ID tra gli ID cliente esistenti e le versioni in caratteri minuscoli degli indirizzi e-mail dei clienti. Effettuando questa operazione tramite [la sincronizzazione ID basata su file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) o utilizzando [ID dichiarati](../declared-ids.md).

## 4. Qualifica caratteristica {#trait-qualification}

Per indirizzare con precisione l'audience in [!DNL People-Based Destinations], i vostri utenti devono essere idonei per le caratteristiche basate su regole o caricate, a seconda del tipo di targeting dell'audience che intendete eseguire.

**A) Qualificare gli ID cliente e gli ID dispositivo in tempo reale per le caratteristiche basate su regole**. Questa opzione si applica al caso A da [1. Definizione del caso d'uso](people-based-destinations-workflow.md#defining-your-use-case). Se il tuo piano prevede di eseguire il targeting delle audience in base all'attività online e offline, probabilmente hai già la qualifica di audience per le caratteristiche [basate su regole](../traits/trait-qualification-reference.md).

**B) Caratteristiche della bacheca rispetto agli ID cliente tramite file di dati in entrata**. Questa opzione si applica al caso D di utilizzo B da [1. Definizione del caso d'uso](people-based-destinations-workflow.md#defining-your-use-case). Quando si esegue il targeting del pubblico in base a attività esclusivamente offline, è necessario qualificare gli ID cliente per tratti caricati attraverso [file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Creazione o etichette di Origini dati e indirizzi e-mail con hash {#create-label-data-sources}

In base al tipo di ID cliente che hai in Audience Manager (vedi [3. Identifica il tipo di ID cliente (ID CRM) che hai](people-based-destinations-workflow.md#identify-customer-id), che troverai in uno dei seguenti scenari:

**A) Etichettare un'origine dati esistente**. Questa opzione si applica allo scenario in cui gli ID cliente di Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) sono già minuscoli, indirizzi e-mail con hash. In questa situazione, è necessario etichettare l'origine dati in cui archiviare gli ID come origine [!DNL PII] dati. Consultate [Impostazioni origine dati](../datasources-list-and-settings.md) per informazioni dettagliate sulle impostazioni delle sorgenti dati. È necessario accertarsi che l'opzione Non sia associata all'opzione di identificazione personale non sia selezionata.

**B) Crea una nuova origine dati**. Questa opzione si applica allo scenario in cui gli indirizzi e-mail di Audience Manager ([dpuuids](../../reference/ids-in-aam.md)) non vengono inseriti in indirizzi e-mail con hash. In questo caso, è necessario creare una nuova origine dati cross-device e inserire in esso gli indirizzi e-mail con hash. Puoi eseguire questa operazione in due modi:

* Utilizzate la sincronizzazione ID basata su file. Per [informazioni sui file di sincronizzazione ID, consultate Requisiti del nome e del contenuto per i file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) di sincronizzazione ID. Quando utilizzate questo metodo, potete eseguire il targeting di tutti gli indirizzi e-mail con hash dal [!DNL CRM] database.
* Utilizza [ID dichiarati](../declared-ids.md) per dichiarare indirizzi e-mail con hash durante il passaggio in ID cliente autenticati. Quando si utilizza questo metodo, Audience Manager esegue il targeting degli indirizzi e-mail con hash da utenti che hanno eseguito l'autenticazione online. Gli indirizzi e-mail destinati tramite Facebook sono solo quelli nelle chiamate degli eventi ID dichiarati. Altri indirizzi e-mail associati all'ID cliente non vengono attivati in tempo reale.

## 6. Usare una regola unione profilo per segmentazione {#use-profile-merge-rules}

A seconda del caso d'uso (vedere [1. Definizione del caso d'uso](people-based-destinations-workflow.md#defining-your-use-case)), esistono due modi per utilizzare [!DNL Profile Merge Rules] la segmentazione.

**A) Utilizzate già[!DNL Profile Merge Rules]**. Questa opzione si applica al primo caso d'uso (targeting dell'audience in base all'attività utente online combinata e offline). In questo scenario, disponete dell'attività del cliente in Audience Manager e avete già definito almeno una Regola di unione profilo utilizzata nella segmentazione. In questo caso, non è necessario creare nuovi [!DNL Profile Merge Rules].

**B) Create una nuova regola[!DNL All Cross-Device Profiles]di unione**. Questa opzione si applica al secondo caso d'uso (targeting dell'audience basato esclusivamente sull'attività dell'utente offline). In questo scenario, trasferisci dati del cliente offline da Audience [!DNL CRM] Manager e desiderano creare segmenti da quei dati. A tal fine [!DNL People-Based Destinations] , viene introdotta una nuova regola Unisci profilo, chiamata **[!DNL All Cross-Device Profiles]**. Questa regola è necessaria per segmentare i dati esclusivamente offline.
