---
description: Destinazioni basate sulle persone offre diverse strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le destinazioni basate sulle persone, a seconda dello scenario.
seo-description: 'Destinazioni basate sulle persone offre diverse strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le destinazioni basate sulle persone, a seconda dello scenario.  '
seo-title: Istruzioni per l'implementazione delle destinazioni basate sulle persone
solution: Audience Manager
title: Guida all'implementazione
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 2%

---


# Guida all&#39;implementazione {#implementation-guidance}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

[!DNL People-Based Destinations] offre diverse strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per [!DNL People-Based Destinations], a seconda dello scenario.

## Panoramica {#overview}

La configurazione di [!DNL People-Based Destinations] ti porta attraverso più sezioni di  Audience Manager e richiede diverse impostazioni e metodi di onboarding dei dati, a seconda del tipo di dati cliente già in  Audience Manager e del tipo di targeting del pubblico che desideri eseguire.

>[!IMPORTANT]
> Prima di configurare [!DNL People-Based Destinations], assicuratevi di leggere questo articolo con attenzione e completezza. Dopo aver letto questa guida, è necessario avere una chiara comprensione dello scenario che sarà attivato attraverso [!DNL People-Based Destinations].

È necessario chiarire sei aspetti di implementazione prima di utilizzare [!DNL People-Based Destinations]. Questo articolo ti aiuterà a capire qual è la configurazione corrente, in modo da poter seguire correttamente i passaggi di implementazione per il tuo scenario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definizione del caso d&#39;uso {#defining-your-use-case}

Prima di iniziare l&#39;implementazione di [!DNL People-Based Destinations], è necessario definire chiaramente il caso di utilizzo per il quale si intende utilizzare questa funzione. Potete utilizzare [!DNL People-Based Destinations] per eseguire il targeting dei tipi di pubblico in due modi, in base all&#39;attività dell&#39;audience:

**A) Targeting dell&#39;audience in base all&#39;attività** combinata degli utenti online e offline. In questo scenario, si desidera combinare i dati di audience esistenti da  Audience Manager con i dati del sistema interno [!DNL CRM] e inviare i segmenti di pubblico risultanti a [!DNL People-Based Destinations]. Di seguito è riportato un esempio che illustra questo scenario:

La vostra azienda, una compagnia aerea, ha diversi livelli di clienti (Bronzo, Argento e Oro) e volete fornire a ciascuno dei livelli offerte personalizzate tramite piattaforme social. Utilizzate  Audience Manager per analizzare l&#39;attività del cliente sul sito Web. Tuttavia, non tutti i clienti utilizzano l&#39;app mobile della compagnia aerea e alcuni di essi non hanno effettuato l&#39;accesso al sito Web della società. I dati del cliente sono per lo più limitati agli ID iscrizione e agli indirizzi e-mail.

Per eseguire il targeting su social media e canali simili basati su persone, puoi portare i tuoi [indirizzi e-mail con hash](people-based-destinations-prerequisites.md) in  Audience Manager e combinarli con le caratteristiche dell&#39;attività online esistente, per creare nuovi segmenti di pubblico. Successivamente, puoi utilizzare questi segmenti per indirizzare il pubblico attraverso [!DNL People-Based Destinations].

**B) Targeting dell&#39;audience basato esclusivamente sull&#39;attività** dell&#39;utente offline. In questo scenario, il sistema [!DNL CRM] contiene gli indirizzi e-mail del cliente e altri attributi del cliente, ma i clienti non hanno interagito con il sito Web, per cui non disponete di alcuna attività cliente nel  Audience Manager. Di seguito è riportato un esempio che illustra questo scenario:

La vostra azienda, un fornitore di servizi di telecomunicazione, mantiene i dati dei clienti come indirizzi e-mail e piani di telecomunicazione acquistati in un [!DNL CRM] interno. Desiderate essere indirizzati ai clienti esistenti nelle piattaforme social per offrire loro pacchetti di aggiornamento basati sulle loro iscrizioni esistenti. A tal fine, puoi inserire gli indirizzi e-mail del cliente con hash in  Audience Manager e creare segmenti in base alle iscrizioni del cliente esistenti. Potete quindi inviare questi segmenti a [!DNL People-Based Destinations] per indirizzare i vostri clienti con offerte personalizzate.

## 2. Definire il tipo di indirizzi e-mail di destinazione {#define-target-email}

Il secondo passo nella definizione della strategia di implementazione consiste nel determinare il tipo di indirizzi e-mail del cliente a cui destinarsi.

**A) Targeting dell&#39;audience in base agli indirizzi** e-mail autenticati. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desiderate inviarli a offerte personalizzate, basate solo sull’indirizzo e-mail che autenticano sul sito Web, in tempo reale.

**B) Targeting dell&#39;audience basato su tutti gli indirizzi** e-mail associati. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desiderate inviarli a tutti i loro indirizzi e-mail associati, indipendentemente dall&#39;attività autenticata.

## 3. Identificare il tipo di ID cliente (ID CRM) di cui si dispone {#identify-customer-id}

Il targeting del pubblico in [!DNL People-Based Destinations] richiede l&#39;invio di [SHA256 con hash](people-based-destinations-prerequisites.md) versioni degli indirizzi e-mail del cliente. A seconda della configurazione del Audience Manager  esistente, potete trovarvi in uno dei due scenari seguenti:

**A) Gli ID cliente  Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già minuscoli, indirizzi** e-mail con hash. In questo scenario, potete utilizzare questi ID esistenti per eseguire il targeting delle audience in [!DNL People-Based Destinations].

**B) Gli ID cliente  Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono minuscoli, indirizzi** e-mail con hash. In questo caso, gli ID cliente esistenti non possono essere inviati a [!DNL People-Based Destinations]. Per utilizzare [!DNL People-Based Destinations], devi eseguire una sincronizzazione ID tra gli ID cliente esistenti e versioni in lettere minuscole e con hash degli indirizzi e-mail del cliente. A tale scopo, è possibile eseguire una sincronizzazione degli ID basata su file [oppure utilizzare gli ID dichiarati [](../declared-ids.md).](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)

## 4. Qualificazione caratteristica {#trait-qualification}

Per eseguire il targeting accurato del pubblico in [!DNL People-Based Destinations], gli utenti devono essere qualificati per caratteristiche basate su regole o registrate, a seconda del tipo di targeting del pubblico che si desidera eseguire.

**A) Qualifica gli ID cliente e dispositivo in tempo reale per caratteristiche** basate su regole. Questa opzione si applica al caso di utilizzo A di [1. Definizione del caso di utilizzo](people-based-destinations-workflow.md#defining-your-use-case). Se il piano prevede di eseguire il targeting delle audience in base alle attività online e offline, è probabile che il pubblico sia già qualificato per le [caratteristiche basate su regola](../traits/trait-and-segment-qualification-reference.md).

**B) Caratteristiche di bordo rispetto agli ID cliente tramite file** di dati in entrata. Questa opzione si applica al caso di utilizzo B da [1. Definizione del caso di utilizzo](people-based-destinations-workflow.md#defining-your-use-case). Quando eseguite il targeting del pubblico in base a un&#39;attività puramente offline, è necessario qualificare gli ID cliente per le caratteristiche registrate tramite [file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Creare o etichettare origini dati e indirizzi e-mail con hash integrati {#create-label-data-sources}

A seconda del tipo di ID cliente in  Audience Manager (vedere [3. Identifica il tipo di ID cliente (ID CRM) che hai](people-based-destinations-workflow.md#identify-customer-id), ti ritroverai in uno dei seguenti scenari:

**A) Etichettare un&#39;origine** dati esistente. Questa opzione si applica allo scenario in cui gli ID cliente  Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già minuscoli, indirizzi e-mail con hash. In questa situazione, è necessario etichettare l&#39;origine dati in cui vengono memorizzati gli ID come origine dati [!DNL PII]. Per informazioni sulle impostazioni dell&#39;origine dati, vedere [Impostazioni origine dati](../datasources-list-and-settings.md). È necessario assicurarsi che l&#39;opzione Impossibile essere legato a informazioni personali sia deselezionata.

**B) Creare una nuova origine** dati. Questa opzione si applica allo scenario in cui gli ID cliente  Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) non vengono crittografati. In questo caso, è necessario creare una nuova origine dati cross-device e tenere a bordo gli indirizzi e-mail con hash. Potete eseguire questa operazione in due modi:

* Utilizzare la sincronizzazione ID basata su file. Per informazioni dettagliate sull’aspetto dei file di sincronizzazione ID, consulta [Name and Content Requirements for ID Synchronization Files](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). Quando si utilizza questo metodo, è possibile eseguire il targeting di tutti gli indirizzi e-mail con hash dal database [!DNL CRM].
* Utilizzate gli [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmettete gli ID cliente autenticati. Quando si utilizza questo metodo,  Audience Manager, per vostro conto, ha come destinazione solo gli indirizzi e-mail con hash degli utenti che hanno eseguito l&#39;autenticazione online. Gli indirizzi e-mail assegnati ai canali basati sulle persone sono solo quelli inclusi nelle chiamate dell&#39;evento ID dichiarate. Gli altri indirizzi e-mail associati all’ID cliente non vengono attivati in tempo reale.

## 6. Usa una regola di unione dei profili per la segmentazione {#use-profile-merge-rules}

A seconda del caso d&#39;uso (vedere [1. Definendo il caso di utilizzo](people-based-destinations-workflow.md#defining-your-use-case)), sono disponibili due modi per utilizzare [!DNL Profile Merge Rules] per la segmentazione.

**A) Utilizzare esistente[!DNL Profile Merge Rules]**. Questa opzione si applica al primo caso di utilizzo (targeting dell&#39;audience basato su un&#39;attività utente online e offline combinata). In questo scenario, esiste un&#39;attività cliente  Audience Manager e hai già definito almeno una regola di unione profilo utilizzata nella segmentazione. In questo caso, non è necessario creare nuovi [!DNL Profile Merge Rules].

**B) Create una nuova regola  [!DNL All Cross-Device Profiles] Unisci**. Questa opzione si applica al secondo caso di utilizzo (targeting dell&#39;audience basato esclusivamente sull&#39;attività dell&#39;utente offline). In questo scenario, i dati dei clienti offline vengono portati da [!DNL CRM] al Audience Manager  e si desidera creare segmenti da tali dati. A questo scopo, [!DNL People-Based Destinations] introduce una nuova, quarta regola di unione dei profili, denominata **[!DNL All Cross-Device Profiles]**. Questa è la regola da utilizzare per segmentare dati puramente offline.
