---
description: Destinazioni basate sulle persone offre diverse strategie di implementazione, a seconda della struttura dei dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le destinazioni basate sulle persone, a seconda dello scenario.
seo-description: 'Destinazioni basate sulle persone offre diverse strategie di implementazione, a seconda della struttura dei dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire per le destinazioni basate sulle persone, a seconda dello scenario.  '
seo-title: Istruzioni per l'implementazione delle destinazioni basate sulle persone
solution: Audience Manager
title: Guida all'implementazione
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Guida all'implementazione {#implementation-guidance}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell'utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per assistenza legale.

[!DNL People-Based Destinations] offre diverse strategie di implementazione, a seconda di come sono strutturati i dati dei clienti. Questo articolo fornisce una panoramica dei passaggi di implementazione da seguire [!DNL People-Based Destinations], a seconda dello scenario in uso.

## Panoramica {#overview}

La configurazione di [!DNL People-Based Destinations] porta attraverso più sezioni di Audience Manager e richiede diverse impostazioni e metodi di registrazione dei dati, a seconda del tipo di dati cliente già in uso in Audience Manager e del tipo di targeting dell'audience che si desidera eseguire.

>[!IMPORTANT]
> Prima di configurare [!DNL People-Based Destinations], leggete questo articolo con attenzione e completezza. Dopo aver letto questa guida, è necessario avere una chiara comprensione dello scenario che sarà attivato [!DNL People-Based Destinations].

Prima di utilizzare è necessario chiarire sei aspetti di implementazione [!DNL People-Based Destinations]. Questo articolo ti aiuterà a capire qual è la configurazione corrente, in modo da poter seguire correttamente i passaggi di implementazione per il tuo scenario.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definizione del caso d’uso {#defining-your-use-case}

Prima di iniziare l'implementazione [!DNL People-Based Destinations], è necessario definire chiaramente il caso d'uso per il quale utilizzerete questa funzione. Potete utilizzare [!DNL People-Based Destinations] per eseguire il targeting delle audience in due modi, in base all'attività dell'audience:

**A) Targeting dell'audience in base all'attività** combinata degli utenti online e offline. In questo scenario, vuoi combinare i dati di audience esistenti di Audience Manager con quelli del tuo [!DNL CRM] sistema interno e inviare i segmenti di pubblico risultanti a [!DNL People-Based Destinations]. Di seguito è riportato un esempio che illustra questo scenario:

La vostra azienda, una compagnia aerea, ha diversi livelli di clienti (Bronzo, Argento e Oro) e volete fornire a ciascuno dei livelli offerte personalizzate tramite piattaforme social. Potete utilizzare Audience Manager per analizzare l'attività dei clienti sul vostro sito Web. Tuttavia, non tutti i clienti utilizzano l'app mobile della compagnia aerea e alcuni di essi non hanno effettuato l'accesso al sito Web della società. I dati del cliente sono per lo più limitati agli ID iscrizione e agli indirizzi e-mail.

Per utilizzarli tra social media e canali simili basati su persone, puoi trasferire i tuoi indirizzi [e-mail con](people-based-destinations-prerequisites.md) hash in Audience Manager e combinarli con le caratteristiche dell'attività online esistenti, per creare nuovi segmenti di pubblico. Quindi, puoi usare questi segmenti per indirizzare il pubblico attraverso [!DNL People-Based Destinations].

**B) Targeting dell'audience basato esclusivamente sull'attività** dell'utente offline. In questo scenario, il [!DNL CRM] sistema contiene gli indirizzi e-mail del cliente e altri attributi del cliente, ma i clienti non hanno interagito con il tuo sito Web, per cui non hai alcuna attività con i clienti in Audience Manager. Di seguito è riportato un esempio che illustra questo scenario:

La vostra azienda, un fornitore di servizi di telecomunicazione, conserva i dati dei clienti come indirizzi e-mail e piani di telecomunicazione acquistati in un [!DNL CRM]sito interno. Desiderate essere indirizzati ai clienti esistenti nelle piattaforme social per offrire loro pacchetti di aggiornamento basati sulle loro iscrizioni esistenti. A tal fine, puoi inserire gli indirizzi e-mail dei clienti con hash in Audience Manager e creare segmenti in base alle iscrizioni dei clienti esistenti. Puoi quindi inviare questi segmenti [!DNL People-Based Destinations] ai clienti con offerte personalizzate.

## 2. Definire il tipo di indirizzi e-mail di destinazione {#define-target-email}

Il secondo passo nella definizione della strategia di implementazione consiste nel determinare il tipo di indirizzi e-mail del cliente a cui destinarsi.

**A) Targeting dell'audience in base agli indirizzi** e-mail autenticati. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desiderate inviarli a offerte personalizzate, basate solo sull’indirizzo e-mail che autenticano sul sito Web, in tempo reale.

**B) Targeting dell'audience basato su tutti gli indirizzi** e-mail associati. In questo scenario, gli utenti dispongono di più account associati a più indirizzi e-mail e desiderate inviarli a tutti i loro indirizzi e-mail associati, indipendentemente dall'attività autenticata.

## 3. Identificare il tipo di ID cliente (ID CRM) che hai {#identify-customer-id}

Il targeting del pubblico in [!DNL People-Based Destinations] richiede l'invio di versioni con hash [](people-based-destinations-prerequisites.md) SHA256 degli indirizzi e-mail del cliente. A seconda della configurazione di Audience Manager esistente, potresti trovarti in uno dei due scenari seguenti:

**A) Gli ID cliente di Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già minuscoli, indirizzi** e-mail con hash. In questo scenario, potete utilizzare questi ID esistenti per eseguire il targeting delle audience in [!DNL People-Based Destinations].

**B) Gli ID cliente Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono minuscoli, indirizzi** e-mail con hash. In questo scenario, non è possibile inviare gli ID cliente esistenti a [!DNL People-Based Destinations]. Per utilizzare [!DNL People-Based Destinations], devi eseguire una sincronizzazione ID tra gli ID cliente esistenti e le versioni in lettere minuscole e con hash degli indirizzi e-mail del cliente. A tale scopo, è possibile eseguire la sincronizzazione [degli ID basata su](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) file oppure utilizzare ID [](../declared-ids.md)dichiarati.

## 4. Qualificazione caratteristica {#trait-qualification}

Per eseguire il targeting accurato del pubblico in [!DNL People-Based Destinations], gli utenti devono essere qualificati per caratteristiche basate su regole o registrate, a seconda del tipo di targeting del pubblico che si desidera eseguire.

**A) Qualifica gli ID cliente e dispositivo in tempo reale per caratteristiche** basate su regole. Questa opzione si applica al caso di utilizzo A da [1. Definizione del caso](people-based-destinations-workflow.md#defining-your-use-case)di utilizzo. Se il piano prevede di eseguire il targeting delle audience in base alle attività online e offline, è probabile che il pubblico sia già idoneo per caratteristiche [basate su](../traits/trait-qualification-reference.md)regole.

**B) Caratteristiche di bordo rispetto agli ID cliente tramite file** di dati in entrata. Questa opzione si applica al caso di utilizzo B da [1. Definizione del caso](people-based-destinations-workflow.md#defining-your-use-case)di utilizzo. Quando eseguite il targeting del pubblico in base a un'attività puramente offline, è necessario qualificare gli ID cliente per le caratteristiche registrate attraverso i file [di dati](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)in entrata.

## 5. Creare o etichettare origini dati e indirizzi e-mail con hash integrati {#create-label-data-sources}

A seconda del tipo di ID cliente in Audience Manager (vedere [3). Identifica il tipo di ID cliente (ID CRM) che hai](people-based-destinations-workflow.md#identify-customer-id), ti ritroverai in uno dei seguenti scenari:

**A) Etichettare un'origine** dati esistente. Questa opzione si applica allo scenario in cui gli ID cliente di Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) sono già minuscoli, indirizzi e-mail con hash. In questa situazione, è necessario etichettare l’origine dati in cui vengono memorizzati gli ID come origine [!DNL PII] dati. Per informazioni dettagliate sulle impostazioni dell'origine dati, vedere Impostazioni [](../datasources-list-and-settings.md) origine dati. È necessario assicurarsi che l'opzione Impossibile essere legato a informazioni personali sia deselezionata.

**B) Creare una nuova origine** dati. Questa opzione si applica allo scenario in cui gli ID cliente di Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) non sono indirizzi e-mail con hash. In questo caso, è necessario creare una nuova origine dati cross-device e tenere a bordo gli indirizzi e-mail con hash. Potete eseguire questa operazione in due modi:

* Utilizzare la sincronizzazione ID basata su file. Per informazioni dettagliate sull’aspetto dei file [di sincronizzazione ID, consultate Requisiti di](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) nome e contenuto. Utilizzando questo metodo, potete eseguire il targeting di tutti gli indirizzi e-mail con hash dal [!DNL CRM] database.
* Usate gli ID [](../declared-ids.md) dichiarati per dichiarare i vostri indirizzi e-mail con hash quando trasmettete gli ID cliente autenticati. Quando usi questo metodo, Audience Manager, per tuo conto, ha come destinazione solo gli indirizzi e-mail con hash degli utenti che hanno eseguito l’autenticazione online. Gli indirizzi e-mail assegnati ai canali basati sulle persone sono solo quelli inclusi nelle chiamate dell'evento ID dichiarate. Gli altri indirizzi e-mail associati all'ID cliente non vengono attivati in tempo reale.

## 6. Usa una regola di unione dei profili per la segmentazione {#use-profile-merge-rules}

A seconda del caso d’uso (vedere [1. Definizione del caso](people-based-destinations-workflow.md#defining-your-use-case)d’uso), esistono due modi per utilizzare [!DNL Profile Merge Rules] la segmentazione.

**A) Utilizzare esistente[!DNL Profile Merge Rules]**. Questa opzione si applica al primo caso di utilizzo (targeting dell'audience basato su un'attività utente online e offline combinata). In questo scenario, esiste un'attività cliente in Audience Manager e hai già definito almeno una regola di unione profilo utilizzata nella segmentazione. In questo caso, non è necessario crearne di nuovi [!DNL Profile Merge Rules].

**B) Create una nuova regola[!DNL All Cross-Device Profiles]Unisci**. Questa opzione si applica al secondo caso di utilizzo (targeting dell'audience basato esclusivamente sull'attività dell'utente offline). In questo scenario i dati dei clienti offline vengono portati [!DNL CRM] in Audience Manager e si desidera creare segmenti da tali dati. A questo scopo, [!DNL People-Based Destinations] imposta una nuova, quarta regola di unione profilo, denominata **[!DNL All Cross-Device Profiles]**. Questa è la regola da utilizzare per segmentare dati puramente offline.
