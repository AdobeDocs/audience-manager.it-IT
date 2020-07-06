---
description: 'Risposte alle domande comuni sulle destinazioni basate su persone  '
seo-description: 'Risposte alle domande comuni sulle destinazioni basate su persone  '
seo-title: Domande frequenti sulle destinazioni basate su persone
solution: Audience Manager
title: Domande frequenti sulle destinazioni basate su persone
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 100%

---


# Domande frequenti sulle destinazioni basate su persone {#people-based-destinations-faq}

Risposte alle domande comuni su [!DNL People-Based Destinations].

## Disponibilità {#availability}

**Non visualizzo [!DNL People-Based Destinations] nel mio account Audience Manager. Cosa bisogna sapere sulla disponibilità?**

[!DNL People-Based Destinations] è una funzionalità premium di Audience Manager disponibile su acquisto. Per informazioni su prezzi e disponibilità, contatta il tuo rappresentante commerciale Adobe.

## Onboarding dei dati {#data-onboarding}

**Come posso integrare gli indirizzi e-mail dei clienti in Audience Manager in modo da poterli utilizzare in [!DNL People-Based Destinations]?**

Esistono due modi per trasferire i dati offline in Audience Manager per [!DNL People-Based Destinations].

* **Utilizzare la sincronizzazione ID basata su file**. Per informazioni dettagliate sull’aspetto dei file di sincronizzazione ID, consulta [Name and Content Requirements for ID Synchronization Files](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). Utilizzando questo metodo, puoi eseguire il targeting di tutti gli indirizzi e-mail con hash dal tuo database [!DNL CRM].
* **Utilizzare gli ID dichiarati** per dichiarare gli indirizzi e-mail con hash quando si trasmettono gli ID cliente autenticati. Quando si utilizza questo metodo, Audience Manager attiva solo gli indirizzi e-mail con hash degli utenti che hanno eseguito l’autenticazione online. Gli indirizzi e-mail attivati tramite Facebook sono solo quelli nelle chiamate all’evento degli ID dichiarati. Gli altri indirizzi e-mail associati all’ID cliente non vengono attivati in tempo reale.

**Posso raccogliere indirizzi e-mail con hash tramite un modulo web o un’app per dispositivi mobili oppure è necessario riceverli in un file batch?**

Puoi raccogliere indirizzi e-mail con hash tramite l’autenticazione web utilizzando [!DNL ECID] con [ID dichiarati](../features/declared-ids.md). Il file batch ti consente inoltre di raccogliere indirizzi e-mail con hash che non possono essere inviati tramite autenticazione (ad esempio, utenti inattivi nel tuo [!DNL CRM]) e attivarli nelle destinazioni basate su persone.

**In che modo l’acquisizione di indirizzi e-mail con hash tramite moduli web è diversa dal caricamento di indirizzi e-mail con hash tramite file batch?**

L’acquisizione di dati offline è progettata per supportare i casi di utilizzo senza autenticazione e, come parte di [!DNL People-Based Destinations], è disponibile una nuova regola di unione profili ([!UICONTROL All Cross-Device Profiles]) che viene eseguita su tutti i profili [!DNL CRM] offline a prescindere dall’autenticazione. Questo metodo punta a integrare l’assimilazione di pubblici autenticati da sorgenti online.

**Qual è la frequenza massima con cui posso inviare/aggiornare indirizzi e-mail con hash?**

* Quando si utilizzano gli ID dichiarati, Audience Manager invia gli indirizzi e-mail con hash alla destinazione in tempo reale.
* Quando si acquisiscono dati tramite i file di sincronizzazione ID, Audience Manager li elabora su base giornaliera.

**Come posso sapere se l’hash è stato aggiunto correttamente all’indirizzo e-mail?**

Audience Manager non acquisisce l’indirizzo e-mail non elaborato e non è possibile verificare che l’hash sia stato aggiunto correttamente. Consulta [Prerequisites and Considerations](../features/destinations/people-based-destinations-prerequisites.md) per informazioni dettagliate su come aggiungere hash ai dati caricati.

## Regole di unione profili {#profile-merge-rules}

**Esiste una nuova regola di unione profili che posso utilizzare con [!DNL People-Based Destinations]?**

Sì. Ai clienti che acquistano [!DNL People-Based Destinations] viene inoltre concesso l’accesso a una nuova regola di unione profili per la segmentazione offline. La regola è chiamata [!DNL All Cross-Device Profiles] e viene utilizzata per la segmentazione solo offline. Quando ti registri a [!DNL People-Based Destinations], è la quarta regola di unione profili che puoi creare, oltre alle tre regole basate sull’autenticazione esistenti.

**Devo duplicare i miei segmenti di pubblico esistenti per attivarli in [!DNL People-Based Destinations]?**

Dipende dal tuo caso d’uso. Se prevedi di attivare segmenti di prime parti esistenti nei canali basati sulle persone, non è necessario creare nuovi segmenti. Puoi semplicemente mappare i segmenti su una destinazione basata su persone.

Se prevedi di attivare nuovi tipi di pubblico offline nei canali basati sulle persone, devi creare nuovi segmenti di prime parti utilizzando la regola di unione [!DNL All Cross-Device Profiles].
>[!NOTE]
>
> Puoi mappare solo segmenti con dati di prime parti su [!DNL People-Based Destinations]. Le nostre piattaforme di destinazione non accettano segmenti con dati di seconde e terze parti.

## Percentuali di corrispondenza {#match-rates}

**In [!DNL People-Based Destinations] sono visibili percentuali di corrispondenza o pubblici indirizzabili?**

No. Quando si inviano segmenti di pubblico a [!DNL People-Based Destinations], la corrispondenza del pubblico avviene sul lato partner. Adobe non ha accesso a tali metriche. Audience Manager mostra il pubblico massimo condivisibile per ogni destinazione e il numero in tempo reale di persone appartenenti a un segmento. Queste informazioni possono esserti utili per la pianificazione e la previsione delle campagne.

**In che modo le percentuali di corrispondenza che utilizzano [!DNL People-Based Destinations] differiscono teoricamente da altri metodi di invio di pubblici alle piattaforme di destinazione?**

Se l’indirizzo e-mail viene dotato di hash e acquisito correttamente, non dovrebbe esserci alcuna differenza nella percentuale di corrispondenza tra [!DNL People-Based Destinations] e altri metodi. L’unico motivo per cui una percentuale di corrispondenza potrebbe essere inferiore al 100% è che gli indirizzi e-mail inviati in Audience Manager non possono essere associati a un indirizzo e-mail nella base utenti della piattaforma di destinazione.

**Raccolgo gli indirizzi e-mail di lavoro dai miei clienti, che sono diversi dagli indirizzi e-mail personali utilizzati nei social network. In che modo le identità vengono associate a più indirizzi e-mail?**

Audience Manager può raccogliere e inviare fino a 10 e-mail per utente alle piattaforme di destinazione, ma gli indirizzi e-mail devono essere acquisiti tramite file di sincronizzazione. Dopo che Audience Manager invia gli indirizzi e-mail alle piattaforme di destinazione, tocca alle piattaforme associare gli indirizzi e-mail rispetto alla propria base di utenti. Alcune piattaforme possono disporre di grafici degli indirizzi e-mail aggiuntivi far associare gli indirizzi inviati da Audience Manager ai profili degli utenti.

## Controlli sull’esportazione dei dati {#data-export-controls}

**Come funzionano i [!DNL Data Export Controls] con [!DNL People-Based Destinations]?**

[!DNL Data Export Controls] blocca qualsiasi segmento contenente dati di seconde e terze parti che gli utenti tentano di inviare a [!DNL People-Based Destinations]. [!DNL People-Based Destinations] consente solo l’utilizzo di dati di prime parti per il targeting. I [!DNL Data Export Controls] bloccano inoltre i segmenti utilizzando [!DNL Profile Merge Rules] con grafici dei dispositivi. [!DNL People-Based Destinations] vengono create con le etichette di esportazione dei dati appropriate selezionate e non puoi sovrascrivere le impostazioni di esportazione.

## Domande specifiche sui partner {#partner-specific-questions}

### [!DNL Facebook]

**Cosa devo fare prima di poter inviare segmenti di pubblico a [!DNL Facebook]?**

Prima di poter utilizzare [!DNL People-Based Destinations] per inviare segmenti di pubblico a [!DNL Facebook], è necessario eseguire le seguenti attività di configurazione:

1. Aggiungi l’account aziendale Adobe Experience Cloud come partner pubblicitario nel tuo [!DNL Facebook Ad Account]. Utilizza `business ID=206617933627973`. Per informazioni, consulta Aggiunta di partner a Business Manager.

   >[!IMPORTANT]
   >
   > Quando configuri le autorizzazioni per Adobe Experience Cloud, devi abilitare l’autorizzazione Manage campaigns. Questa è richiesta per l’integrazione di [!DNL People-Based Destinations].

1. Leggi e firma i [!DNL Facebook Custom Audiences Terms of Service]. Per fare questo, vai su `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dove `accountID` è il tuo [!DNL Facebook Ad Account ID].

**[!DNL People-Based Destinations] supporta il targeting del pubblico in altre app [!DNL Facebook], ad esempio [!DNL Instagram]?**

Puoi utilizzare [!DNL People-Based Destinations] in tutta la famiglia di app [!DNL Facebook] supportate da [!DNL Custom Audiences], incluse [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] e [!DNL Messenger]. La selezione dell’app su cui desideri eseguire la campagna è indicata al livello di posizionamento in [!DNL Facebook Ads Manager].

**Qual è la differenza tra [!DNL People-Based Destinations] e [!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] sfrutta l’integrazione di [!DNL Custom Audiences (CA)] con [!DNL Facebook]. La differenza tra le integrazioni [!DNL WCA] e [!DNL CA] è la chiave che i clienti usano per inviare pubblici a [!DNL Facebook]. [!DNL WCA] utilizza il pixel di [!DNL Facebook] (che sarebbe un ID utente del sito web), mentre [!DNL People-Based Destinations] utilizza indirizzi e-mail con hash da integrare con [!DNL CA].

Puoi utilizzare l’integrazione tra [!DNL Facebook] e [!DNL WCA] di Audience Manager tramite la funzionalità [!DNL URL Destinations] senza costi aggiuntivi.

Queste due integrazioni sono complementari; puoi utilizzare entrambe per garantire una migliore copertura del pubblico. Ad esempio, [!DNL WCA] può essere utile per la ricerca di potenziali clienti nel caso in cui un’azienda desideri effettuare il targeting di visitatori di siti web che non hanno registrato un account, mentre [!DNL People-Based Destinations] può aiutarti a individuare i clienti esistenti che hanno fornito il loro indirizzo e-mail ma che forse non hanno visitato il sito web.
