---
description: 'Risposte alle domande comuni sulle destinazioni basate sulle persone.  '
seo-description: 'Risposte alle domande comuni sulle destinazioni basate sulle persone.  '
seo-title: Domande frequenti sulle destinazioni basate sulle persone
solution: Audience Manager
title: Domande frequenti sulle destinazioni basate sulle persone
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 0%

---


# Domande frequenti sulle destinazioni basate sulle persone {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Disponibilità {#availability}

**Non posso vedere[!DNL People-Based Destinations]nel mio account Audience Manager . Cosa devo sapere sulla disponibilità?**

[!DNL People-Based Destinations] è una funzione premium  Audience Manager disponibile al momento dell&#39;acquisto. Per informazioni su prezzi e disponibilità, contattate il vostro rappresentante commerciale Adobe.

## Onboarding dei dati {#data-onboarding}

**Come è possibile inserire gli indirizzi e-mail dei clienti  Audience Manager in modo da poterli utilizzare in[!DNL People-Based Destinations]?**

Esistono due modi per portare i dati offline  Audience Manager per [!DNL People-Based Destinations].

* **Utilizzare la sincronizzazione** ID basata su file. Per informazioni dettagliate sull’aspetto dei file [di sincronizzazione degli ID, consultate Requisiti di](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) nome e contenuto. Utilizzando questo metodo, potete eseguire il targeting di tutti gli indirizzi e-mail con hash dal [!DNL CRM] database.
* **Usate gli ID** dichiarati per dichiarare gli indirizzi e-mail con hash quando trasmettete gli ID cliente autenticati. Quando si utilizza questo metodo,  Audience Manager attiva solo gli indirizzi e-mail con hash degli utenti che hanno eseguito l&#39;autenticazione online. Gli indirizzi e-mail attivati tramite Facebook sono solo quelli nelle chiamate all’evento ID dichiarate. Gli altri indirizzi e-mail associati all&#39;ID cliente non vengono attivati in tempo reale.

**È possibile raccogliere indirizzi e-mail con hash tramite un modulo Web o un&#39;app mobile oppure è necessario che vengano inseriti in un file batch?**

Potete raccogliere indirizzi e-mail con hash tramite l&#39;autenticazione Web utilizzando [!DNL ECID] gli ID [dichiarati](../features/declared-ids.md). Il file batch consente inoltre di raccogliere indirizzi e-mail con hash che non possono essere inviati tramite autenticazione (ad esempio, utenti inattivi nel ([!DNL CRM]) e attivarli in destinazioni basate su persone).

**In che modo l&#39;acquisizione di indirizzi e-mail con hash tramite moduli Web è diversa dal caricamento di indirizzi e-mail con hash tramite file batch?**

L&#39;assimilazione dei dati offline è progettata per supportare i casi di utilizzo senza autenticazione, e una nuova regola di unione dei profili ([!UICONTROL All Cross-Device Profiles]) che viene eseguita su tutti i [!DNL CRM] profili offline a prescindere dall&#39;autenticazione è disponibile come parte di [!DNL People-Based Destinations]. Questo metodo è inteso a completare l’assimilazione di audience autenticate da fonti online.

**Qual è la frequenza massima con cui è possibile inviare/aggiornare indirizzi e-mail con hash?**

* Quando si utilizzano gli ID dichiarati,  Audience Manager invia in tempo reale gli indirizzi e-mail con hash alla destinazione.
* Durante l’assimilazione dei dati tramite i file di sincronizzazione ID,  Audience Manager li elabora quotidianamente.

**Come posso sapere se l&#39;hashing dell&#39;indirizzo e-mail è stato eseguito correttamente?**

 Audience Manager non sta inviando l&#39;indirizzo e-mail non elaborato e non è possibile verificare che l&#39;hash sia stato eseguito correttamente. Consulta [Prerequisiti e considerazioni](../features/destinations/people-based-destinations-prerequisites.md) per informazioni dettagliate sulla modalità di hash dei dati caricati.

## Regole di unione profilo {#profile-merge-rules}

**È possibile utilizzare una nuova regola di unione dei profili con[!DNL People-Based Destinations]?**

Sì. Ai clienti che acquistano [!DNL People-Based Destinations] viene inoltre concesso l&#39;accesso a una nuova regola di unione dei profili per la segmentazione offline. La regola viene chiamata [!DNL All Cross-Device Profiles] e utilizzata per la segmentazione solo offline. Quando vi registrate, [!DNL People-Based Destinations]questa è la quarta regola di unione di profilo che potete creare, a parte le tre regole basate sull&#39;autenticazione esistenti.

**Devo duplicare i segmenti di pubblico esistenti per attivarli in[!DNL People-Based Destinations]?**

Dipende dal caso d&#39;uso. Se prevedete di attivare segmenti di prime parti esistenti nei canali basati sulle persone, non è necessario creare nuovi segmenti. Puoi semplicemente mappare i segmenti su una destinazione basata sulle persone.

Se prevedete di attivare nuovi tipi di pubblico offline nei canali basati sulle persone, dovete creare nuovi segmenti di prime parti utilizzando la regola di [!DNL All Cross-Device Profiles] unione.
>[!NOTE]
>
> Puoi mappare solo segmenti con dati di prime parti a [!DNL People-Based Destinations]. Le nostre piattaforme di destinazione non accettano segmenti con dati di seconda e terza parte.

## Percentuali di corrispondenza {#match-rates}

**Sono[!DNL People-Based Destinations]visibili percentuali di corrispondenza o audience indirizzabili?**

No. Quando si inviano segmenti di pubblico a [!DNL People-Based Destinations], la corrispondenza dell&#39;audience avviene sul lato del partner. Adobe non ha accesso a tali metriche.  Audience Manager mostra il pubblico massimo condivisibile per ogni destinazione e il numero in tempo reale di persone appartenenti a un segmento. Queste informazioni possono essere utili per la pianificazione e la previsione delle campagne.

**In che modo i tassi sarebbero confrontati[!DNL People-Based Destinations]teoricamente con altri metodi di invio di audience alle piattaforme di destinazione?**

Fintanto che l&#39;indirizzo e-mail viene crittografato e inserito correttamente, non dovrebbe esserci alcuna differenza nella percentuale di corrispondenza tra [!DNL People-Based Destinations] e altri metodi. L&#39;unico motivo per cui una percentuale di corrispondenza sarebbe inferiore al 100% è che gli indirizzi e-mail inviati  Audience Manager non possono essere associati a un indirizzo e-mail nella base utenti della piattaforma di destinazione.

**Raccolgo gli indirizzi e-mail di lavoro dai miei clienti, che sono diversi dagli indirizzi e-mail personali utilizzati nei social network. In che modo le identità vengono confrontate tra più indirizzi e-mail?**

 Audience Manager è in grado di raccogliere e inviare fino a 10 e-mail per utente alle piattaforme di destinazione, ma gli indirizzi e-mail devono essere acquisiti tramite file di sincronizzazione. Dopo che  Audience Manager invia gli indirizzi e-mail alle piattaforme di destinazione, spetta alle piattaforme far corrispondere gli indirizzi e-mail rispetto alla propria base di utenti. Alcune piattaforme possono disporre di grafici degli indirizzi e-mail aggiuntivi per far corrispondere gli indirizzi inviati da  Audience Manager ai profili degli utenti.

## Controlli sull&#39;esportazione dei dati {#data-export-controls}

**Come si[!DNL Data Export Controls]lavora con[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloccherà qualsiasi segmento contenente dati di seconda e terza parte a cui gli utenti tentano di inviare [!DNL People-Based Destinations]. [!DNL People-Based Destinations] consenti solo l&#39;utilizzo di dati di prime parti per il targeting. [!DNL Data Export Controls] bloccare anche i segmenti utilizzando [!DNL Profile Merge Rules] con grafici dispositivo. [!DNL People-Based Destinations] vengono creati con le etichette di esportazione dei dati appropriate selezionate e non è possibile sovrascrivere le impostazioni di esportazione.

## Domande specifiche per i partner {#partner-specific-questions}

### [!DNL Facebook]

**Cosa devo fare prima di poter inviare segmenti di pubblico a[!DNL Facebook]?**

Prima di poter utilizzare [!DNL People-Based Destinations] per inviare segmenti di pubblico a [!DNL Facebook], è necessario eseguire le seguenti attività di configurazione:

1. Aggiungi l’account Adobe Experience Cloud come partner pubblicitario all’interno dell’ [!DNL Facebook Ad Account]. Utilizza gli `business ID=206617933627973`. Per informazioni, consulta Aggiunta di partner al tuo Business Manager.

   >[!IMPORTANT]
   >
   > Quando configuri le autorizzazioni per Adobe Experience Cloud, devi abilitare l&#39;autorizzazione Gestisci campagne. Questo è richiesto per l&#39; [!DNL People-Based Destinations] integrazione.

1. Leggete e firmate il [!DNL Facebook Custom Audiences Terms of Service]. Per fare questo, andate a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dov&#39; `accountID` è il vostro [!DNL Facebook Ad Account ID].

**Supporta[!DNL People-Based Destinations]il targeting dell&#39;audience in altre[!DNL Facebook]app, ad esempio[!DNL Instagram]?**

Potete utilizzare [!DNL People-Based Destinations] tutta [!DNL Facebook]la famiglia di app supportate da [!DNL Custom Audiences], inclusi [!DNL Facebook], [!DNL Instagram][!DNL Audience Network] e [!DNL Messenger]. La selezione dell&#39;app con cui si desidera eseguire la campagna è indicata al livello di posizionamento in [!DNL Facebook Ads Manager].

**Qual è la differenza tra[!DNL People-Based Destinations]e[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] sfrutta l&#39; [!DNL Custom Audiences (CA)] integrazione con [!DNL Facebook]. La differenza tra [!DNL WCA] e [!DNL CA] le integrazioni è la chiave che i clienti usano per inviare audience a [!DNL Facebook]. [!DNL WCA] utilizza il [!DNL Facebook] pixel (che sarebbe un ID utente del sito Web) mentre [!DNL People-Based Destinations] usa indirizzi e-mail con hash da integrare [!DNL CA].

Potete utilizzare &#39; [!DNL Facebook] integrazione di Audience Manager tramite la [!DNL WCA] [!DNL URL Destinations] funzione senza costi aggiuntivi.

Queste due integrazioni sono complementari; potete utilizzare entrambi per garantire una migliore copertura del pubblico. Ad esempio, [!DNL WCA] può essere utilizzato per la ricerca nel caso in cui un&#39;azienda desideri indirizzare i visitatori di siti Web che non hanno registrato un account, mentre [!DNL People-Based Destinations] può essere utile per individuare i clienti esistenti che hanno fornito il loro indirizzo e-mail ma che forse non hanno visitato il sito Web.
