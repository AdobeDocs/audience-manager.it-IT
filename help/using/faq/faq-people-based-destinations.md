---
description: 'Risposte alle domande più frequenti sulle destinazioni basate su persone.  '
seo-description: 'Risposte alle domande più frequenti sulle destinazioni basate su persone.  '
seo-title: Domande frequenti sulle destinazioni basate sulle persone
solution: Audience Manager
title: Domande frequenti sulle destinazioni basate sulle persone
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Domande frequenti sulle destinazioni basate sulle persone {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Disponibilità {#availability}

**Non riesco a visualizzare[!DNL People-Based Destinations]nell'account Audience Manager. Cosa devo sapere sulla disponibilità?**

[!DNL People-Based Destinations] è una funzionalità Premium Manager disponibile all'acquisto. Contattate il rappresentante vendite Adobe per informazioni su prezzi e disponibilità.

## Onboarding dei dati {#data-onboarding}

**Come posso fare per inserire gli indirizzi e-mail dei clienti in Audience Manager, in modo da poterli utilizzare[!DNL People-Based Destinations]?**

Esistono due modi per trasferire i dati offline ad Audience Manager.[!DNL People-Based Destinations]

* **Utilizzate la sincronizzazione ID basata su file**. Per [informazioni sui file di sincronizzazione ID, consultate Requisiti del nome e del contenuto per i file](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) di sincronizzazione ID. Quando utilizzate questo metodo, potete eseguire il targeting di tutti gli indirizzi e-mail con hash dal [!DNL CRM] database.
* **Utilizzare ID dichiarati** per dichiarare indirizzi e-mail con hash durante il passaggio in ID cliente autenticati. Quando utilizzate questo metodo, Audience Manager attiva solo gli indirizzi e-mail con hash da utenti che hanno eseguito l'autenticazione online. Gli indirizzi e-mail attivati tramite Facebook sono solo quelli nelle chiamate degli eventi ID dichiarati. Altri indirizzi e-mail associati all'ID cliente non vengono attivati in tempo reale.

**È possibile raccogliere indirizzi e-mail con hash tramite un modulo Web o un'app mobile oppure possono essere inclusi in un file batch?**

Potete raccogliere indirizzi e-mail con hash tramite autenticazione Web con [!DNL ECID] ID [dichiarati](../features/declared-ids.md). Il file batch consente inoltre di raccogliere indirizzi e-mail con hash che non possono essere inviati tramite autenticazione (ad es. utenti dormanti in ([!DNL CRM]) e attivati in destinazioni basate su persone.

**In che modo l'assimilazione degli indirizzi e-mail con hash tramite moduli Web differenti non comporta il caricamento di indirizzi e-mail con hash tramite file batch?**

L'assimilazione dei dati offline è progettata per supportare casi d'uso senza autenticazione, e una nuova regola di unione profili ([!UICONTROL All Cross-Device Profiles]) che viene eseguita su tutti [!DNL CRM] i profili offline a prescindere dall'autenticazione è disponibile come parte di [!DNL People-Based Destinations]. Questo metodo è pensato per completare l'assimilazione di audience autenticate da fonti online.

**Qual è la frequenza massima in cui è possibile inviare/aggiornare gli indirizzi e-mail con hash?**

* Quando si utilizzano gli ID dichiarati, Audience Manager invia alla destinazione gli indirizzi e-mail con hash in tempo reale.
* Quando si assimilano dati tramite file di sincronizzazione ID, Audience Manager li elabora su base giornaliera.

**Come posso sapere se l'hash dell'indirizzo e-mail viene eseguito correttamente?**

Audience Manager non sta assimilando l'indirizzo e-mail non elaborato e non possiamo convalidare che l'hash sia stato eseguito correttamente. Per informazioni su come hash dei dati caricati, consulta [Prerequisiti e considerazioni](../features/destinations/people-based-destinations-prerequisites.md) .

## Regole di unione profilo {#profile-merge-rules}

**Esiste una nuova regola di unione profilo con[!DNL People-Based Destinations]cui posso usarlo?**

Sì. I clienti che acquistano [!DNL People-Based Destinations] dispongono anche dell'accesso a una nuova regola di unione profilo per la segmentazione offline. La regola viene chiamata [!DNL All Cross-Device Profiles] e utilizzata per la segmentazione non in linea. Quando vi registrate, [!DNL People-Based Destinations]questa è la quarta regola di unione dei profili che potete creare, a parte le tre regole esistenti basate sull'autenticazione.

**Devo duplicare i segmenti di pubblico esistenti per attivarli[!DNL People-Based Destinations]?**

Dipende dal caso d'uso. Se pianificate di attivare segmenti di prime parti esistenti nei canali basati sulle persone, non dovete creare nuovi segmenti. Puoi semplicemente mappare i segmenti su una destinazione basata sulle persone.

Se pianificate di attivare nuovi tipi di pubblico offline nei canali basati su persone, dovete creare nuovi segmenti di prime parti utilizzando la regola [!DNL All Cross-Device Profiles] di unione.
>[!NOTE]
>
> È [!DNL People-Based Destinations]possibile mappare i segmenti solo con dati di prime parti. Le nostre piattaforme di destinazione non accettano i segmenti con dati di seconda e terza parte.

## Percentuali di corrispondenza {#match-rates}

**Hai visibilità[!DNL People-Based Destinations]su percentuali di corrispondenza o sui tipi di pubblico indirizzabili?**

No. Quando si inviano segmenti di pubblico a [!DNL People-Based Destinations], la corrispondenza dell'audience avviene sul lato partner. Adobe non ha accesso a tali metriche. Audience Manager mostra il pubblico condivisibile massimo per ogni destinazione e il numero in tempo reale di persone appartenenti a un segmento. Queste informazioni sono utili per pianificare e formulare previsioni.

**In che modo le percentuali corrispondono[!DNL People-Based Destinations]in teoria rispetto ad altri metodi per inviare audience alle piattaforme di destinazione?**

Finché l'indirizzo e-mail viene hashing e assimilato correttamente, non dovrebbe esserci alcuna differenza nella frequenza di corrispondenza tra [!DNL People-Based Destinations] e altri metodi. L'unico motivo per cui una percentuale di corrispondenza sarà inferiore al 100% è che gli indirizzi e-mail inseriti in Audience Manager non possono essere associati a un indirizzo e-mail nella base utente della piattaforma di destinazione.

**Raccolgo gli indirizzi e-mail di lavoro dai miei clienti, che sono diversi dagli indirizzi e-mail personali utilizzati nelle reti social. Come si corrispondenza con le identità tra più indirizzi e-mail?**

Audience Manager è in grado di raccogliere e inviare fino a 10 messaggi e-mail per utente alle piattaforme di destinazione, ma gli indirizzi e-mail devono essere acquisiti tramite file di sincronizzazione. Quando Audience Manager invia gli indirizzi e-mail alle piattaforme di destinazione, è necessario che le piattaforme corrispondano agli indirizzi e-mail rispetto alla loro base utente. Alcune piattaforme possono avere ulteriori grafici indirizzo e-mail per far corrispondere gli indirizzi inviati da Audience Manager ai profili utente.

## Controlli sull'esportazione dei dati {#data-export-controls}

**Come[!DNL Data Export Controls]funziona[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloccherà tutti i segmenti contenenti dati di seconda e terza parte che gli utenti tentano di inviare [!DNL People-Based Destinations]. [!DNL People-Based Destinations] consentire solo i dati di prime parti per il targeting. [!DNL Data Export Controls] bloccare anche i segmenti utilizzando [!DNL Profile Merge Rules] i grafici dei dispositivi. [!DNL People-Based Destinations] vengono create con etichette di esportazione dati appropriate e non è possibile sovrascrivere le impostazioni di esportazione.

## Domande specifiche sui partner {#partner-specific-questions}

### [!DNL Facebook]

**Cosa devo fare prima di poter inviare segmenti di pubblico[!DNL Facebook]?**

Prima di poter utilizzare [!DNL People-Based Destinations] per inviare segmenti di pubblico, [!DNL Facebook]devi eseguire le seguenti attività di configurazione:

1. Aggiungi l'account aziendale Adobe Experience Cloud come partner pubblicitario. [!DNL Facebook Ad Account] Utilizza gli `business ID=206617933627973`. Per ulteriori informazioni, consultate Aggiungere partner al vostro Business Manager.

   >[!IMPORTANT]
   >
   > Quando configuri le autorizzazioni per Adobe Experience Cloud, devi abilitare l'autorizzazione Gestisci campagna. Questa funzione è necessaria per l' [!DNL People-Based Destinations] integrazione.

1. Leggere e firmare l ' [!DNL Facebook Custom Audiences Terms of Service]. A questo scopo, vai a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dove `accountID`[!DNL Facebook Ad Account ID]è.

**[!DNL People-Based Destinations]Supporta il targeting dell'audience in altre[!DNL Facebook]app, ad esempio[!DNL Instagram]?**

Puoi utilizzare [!DNL People-Based Destinations] la [!DNL Facebook]famiglia di app supportate da [!DNL Custom Audiences], incluso [!DNL Facebook], [!DNL Instagram][!DNL Audience Network] e [!DNL Messenger]. La selezione dell'app a cui si desidera eseguire la campagna è indicata a livello di posizionamento.[!DNL Facebook Ads Manager]

**Qual è la differenza[!DNL People-Based Destinations]tra e[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] sfrutta l [!DNL Custom Audiences (CA)] 'integrazione [!DNL Facebook]con. La differenza tra [!DNL WCA] e [!DNL CA] integrazioni è la chiave utilizzata dai clienti per l'invio di audience [!DNL Facebook]. [!DNL WCA] utilizza [!DNL Facebook] il pixel (che rappresenta l'ID utente di un sito Web) mentre [!DNL People-Based Destinations] utilizza gli indirizzi e-mail con hash per l'integrazione [!DNL CA].

Puoi utilizzare [!DNL Facebook][!DNL WCA] l'integrazione di Audience Manager tramite [!DNL URL Destinations] la funzione senza costi aggiuntivi.

Queste due integrazioni sono complementari; potete utilizzare entrambi per garantire una migliore copertura del pubblico. Ad esempio, [!DNL WCA] può essere utilizzato per la pianificazione quando un'azienda cerca i visitatori di siti Web che non hanno registrato un account, mentre [!DNL People-Based Destinations] può aiutarti a rivolgerti a clienti esistenti che hanno fornito il proprio indirizzo e-mail ma che forse non hanno visitato il sito Web.
